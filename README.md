

![Flowgger](https://raw.github.com/awslabs/flowgger/master/flowgger.png)

[![Build Status](https://app.travis-ci.com/awslabs/flowgger.svg?branch=master)](https://app.travis-ci.com/awslabs/flowgger) [![License: BSD2](https://img.shields.io/badge/License-BSD2-brightgreen.svg)](https://github.com/awslabs/flowgger/blob/master/LICENSE)

Flowgger is a fast, simple and lightweight data collector written in Rust.

It reads log entries over a given protocol, extracts them, decodes them using a
given format, re-encodes them into a different format, and asynchronously pushes
the result into a remote data store.

Flowgger is designed to be:
- Paranoid: it carefully validates input data to prevent injection of
malformed/incomplete records down the chain.
- Safe: written in Rust, without any `unsafe` code.
- Fast: even though messages are systematically parsed and validated, Flowgger
is orders of magnitude faster than Logstash and Fluentd.
- Standalone: it comes as a single executable file, and doesn't require a JVM.

Flowgger supports common input types: stdin, UDP, TCP, TLS and Redis,
as well as multiple input formats: JSON (GELF), LTSV, Cap'n Proto and
RFC5424. Normalized messages can be sent to Kafka, Graylog, to downstream
Flowgger servers, or to other log collectors for further processing.

# Static linkage
1.  Check pkg-config installaton
    > which pkg-config
2.  Set enviroments as
   -  export OPENSSL\_INCLUDE\_DIR=/usr/local/include
   -  export OPENSSL\_LIB\_DIR=/usr/local/lib
   -  export OPENSSL\_STATIC=yes
   -  export PKG_CONFIG=/usr/bin/pkg-config
3. Compile with
   - RUSTFLAGS="-C target-feature=+crt-static" cargo build --release --frozen --offline


# [Jump to the Flowgger documentation](https://github.com/awslabs/flowgger/wiki)
