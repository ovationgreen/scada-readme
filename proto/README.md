# Proto

This directory contains Protocol Buffer (`.proto`) definitions used by the Ovation Green SCADA system.

## Prerequisites

Before working with the proto files, ensure you have the following tools installed.

### Node.js (v24)

Node.js v24 is required to run the code generation scripts and related tooling.

1. Download Node.js v24 from the official website: https://nodejs.org/en/download
2. Select **v24** (LTS or Current) for your operating system.
3. Follow the installer instructions.
4. Verify the installation:
   ```bash
   node --version
   # Expected output: v24.x.x
   ```

### protoc (Protocol Buffer Compiler)

`protoc` is the Protocol Buffer compiler used to generate code from `.proto` files.

1. Download the latest release of `protoc` from the official GitHub releases page:
   https://github.com/protocolbuffers/protobuf/releases
2. Choose the appropriate binary for your operating system (e.g., `protoc-*-win64.zip`, `protoc-*-linux-x86_64.zip`, or `protoc-*-osx-aarch_64.zip`).
3. Extract the archive and add the `bin/` directory to your system `PATH`.
4. Verify the installation:
   ```bash
   protoc --version
   # Expected output: libprotoc 3.x.x (or later)
   ```
