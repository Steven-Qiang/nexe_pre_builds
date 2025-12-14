# Nexe Pre-built Binaries Repository

A [nexe](https://github.com/nexe/nexe) pre-built binaries repository containing pre-compiled files for multiple platforms and Node.js versions to accelerate the nexe packaging process. All binaries have been compressed with [UPX](https://upx.github.io/) to reduce file size.

## Available Pre-built Versions

### Windows (x64)
- Node.js 16.19.0
- Node.js 18.14.0
- Node.js 20.17.0
- Node.js 22.14.0
- Node.js 24.12.0
- Node.js 25.2.1

### Linux (x64)
- Node.js 16.19.0
- Node.js 18.14.0
- Node.js 20.17.0
- Node.js 22.14.0
- Node.js 24.12.0
- Node.js 25.2.1

## Usage

Use this repository as a remote source for nexe to avoid recompiling Node.js every time, significantly speeding up the packaging process.

### Command Line

```bash
nexe -t windows-x64-20.17.0 --remote https://raw.githubusercontent.com/Steven-Qiang/nexe_pre_builds/refs/heads/main/
```

### Programmatic API

```javascript
const { compile } = require('nexe')

compile({
  input: './index.js',
  target: 'windows-x64-20.17.0',
  remote: 'https://raw.githubusercontent.com/Steven-Qiang/nexe_pre_builds/refs/heads/main/'
})
```

## Directory Structure

```
nexe_pre_builds/
├── windows-x64-[version]/    # Windows x64 pre-built files
├── linux-x64-[version]/       # Linux x64 pre-built files
└── index.js                   # Test file
```

## Notes

- All binaries are for x64 architecture
- All pre-built binaries have been compressed with UPX, reducing file size by 50-70%
- Pre-built files significantly reduce nexe first-time packaging time
- Choose the appropriate platform and Node.js version based on your target deployment environment
