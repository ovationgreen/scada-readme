# Proto

This directory contains Protocol Buffer (`.proto`) definitions used by the Ovation Green SCADA system.

## Prerequisites

Before working with the proto files, ensure you have the following tools installed.

### Java (26)

Java 17 or higher is required. It is recommended to install **Java 26** for the best compatibility going forward.

> **Note:** Java 17 is the minimum supported version. Ensure that `java` resolves to version 17 or later by default in your shell environment.

1. Download Java 26 from the official website: https://jdk.java.net/26/
2. Run the installer for your operating system.
3. Set the `JAVA_HOME` environment variable to the installation directory.
4. Add `$JAVA_HOME/bin` to your system `PATH`.
5. Verify the installation:
   ```bash
   java -version
   # Expected output: java 26 (or higher, minimum 17)
   ```

### Maven (latest)

Maven is used to build and manage Java-based project dependencies. Ensure you are running the **latest version**.

1. Download the latest Maven release from the official website: https://maven.apache.org/download.cgi
2. Extract the archive and add the `bin/` directory to your system `PATH`.
3. Verify the installation:
   ```bash
   mvn --version
   # Expected output: Apache Maven 3.x.x (or later)
   ```

> **Tip:** If Maven is already installed, update it by downloading the latest release and replacing your existing installation.

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

### Python (3.x)

Python 3.x is required by some tooling and scripts used in the proto workflow.

1. Download Python 3.x from the official website: https://www.python.org/downloads/
2. Run the installer for your operating system.
3. On Windows, enable **Add Python to PATH** during installation.
4. On Windows, if needed, add `%APPDATA%\Python\Python314\Scripts` (or your Python user Scripts directory) to your `PATH`.
5. Verify the installation:
   ```bash
   python --version
   # Expected output: Python 3.x.x
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

### TSC (TypeScript Compiler)

The TypeScript compiler (`tsc`) is used to build TypeScript-based tooling and scripts.

1. Install TypeScript globally using npm:
   ```bash
   npm install -g typescript
   ```
2. Verify the installation:
   ```bash
   tsc --version
   # Expected output: Version 5.x.x
   ```
### grpc_tools (Python gRPC tools)

`grpcio-tools` provides the Python plugin for `protoc` to generate gRPC stubs from `.proto` files.

Please follow the official setup steps from the gRPC Python quickstart guide:
https://grpc.io/docs/languages/python/quickstart/

1. Install the package using pip:
   ```bash
   python -m pip install --upgrade pip
   ```
   ```bash
   python -m pip install virtualenv
   ```
   ```bash
   python -m pip install grpcio
   ```
   ```bash
   python -m pip install grpcio-tools
   ```
   ```bash
   python -m pip install protobuf
   ```
   ```bash
   python -m pip install types-protobuf
   ```
   ```bash
   python -m pip install types-grpcio
   ```
   ```bash
   python -m pip install pydantic
   ```
2. Verify the installation:
   ```bash
   python -m grpc_tools.protoc --version
   # Expected output: libprotoc 31.x (or later)
   ```

### ts-proto

`ts-proto` is a `protoc` plugin that generates idiomatic TypeScript code from `.proto` files.

1. Install `ts-proto` using npm:
   ```bash
   npm install -g ts-proto
   ```
2. Verify the installation:
   ```bash
   npm list -g ts-proto --depth=0
   # Expected output includes: ts-proto@x.y.z
   ```
3. (Optional) Verify that the plugin binary is discoverable on your `PATH`:
   ```powershell
   where protoc-gen-ts_proto
   ```

### mypy (latest)

`mypy` is used for static type checking of Python code in the proto workflow.

1. Install `mypy` using pip:
   ```bash
   python -m pip install --upgrade mypy
   ```
2. Verify the installation:
   ```bash
   mypy --version
   # Expected output: mypy x.y.z
   ```

### Ruff (latest)

`ruff` is used for fast Python linting and formatting checks in the proto workflow.

1. Install `ruff` using pip:
   ```bash
   python -m pip install --upgrade ruff
   ```
2. Verify the installation:
   ```bash
   ruff --version
   # Expected output: ruff x.y.z
   ```

### Poetry (latest)

`poetry` is used for Python dependency and virtual environment management.

1. Install Poetry using the official installer:
   ```bash
   (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
   ```
2. Alternative (manual) installation using pip:
   ```bash
   python -m pip install --user --upgrade poetry
   ```
3. Verify the installation:
   ```bash
   poetry --version
   # Expected output: Poetry (version x.y.z)
   ```
