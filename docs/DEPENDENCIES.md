# Dependencies

## Public Demo

The public demo package is distributed as a compiled Windows GUI binary:

```text
bin/CoeusAI.exe
```

Any required runtime DLLs should remain beside the executable.

---

## Private Build Dependencies

The private build uses a native C++ stack with dependencies such as:

- C++20
- MSVC / Visual Studio 2022 Build Tools
- CMake
- Skia
- SDL2
- OpenGL
- vcpkg
- libcurl
- OpenSSL
- SQLite
- FAISS
- fmt
- xxHash
- tree-sitter
- nlohmann/json
- ICU / HarfBuzz

---

## Dependency Notes

This project demonstrates practical integration of several native libraries in a Windows C++ desktop application.

The public release does not include instructions for rebuilding every dependency from source because the full source tree is private.

The private development environment also contains a headless/testing build path, but that is not part of the public dependency package.
