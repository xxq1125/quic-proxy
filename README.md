quic-proxy
==========

quic-proxy is a quic-http reverseproxy based on proto-quic which is standalone library for [QUIC](https://www.chromium.org/quic).

Currently, the only supported platform is Linux (and the only tested version is
Google's Ubuntu clone).

Building on Linux
-----------------

0. Clone this repository:
   ```
   git clone https://github.com/google/proto-quic.git
   cd proto-quic
   export PROTO_QUIC_ROOT=`pwd`/src
   export PATH=$PATH:`pwd`/depot_tools
   ./proto_quic_tools/sync.sh
   ```

1. If you're building for the first time, install dependencies:
   ```
   ./src/build/install-build-deps.sh
   ```

2. Build the QUIC client, server, and tests:
   ```
   cd src
   gn gen out/Default && ninja -C out/Default quic_client quic_server net_unittests
   ```

From then on you can follow the usual Chromium instructions for playing with the
toy client and server:

https://www.chromium.org/quic/playing-with-quic
