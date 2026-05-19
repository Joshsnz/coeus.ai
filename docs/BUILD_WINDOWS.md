# Build Notes — Windows

## Public Demo Context

The public Coeus AI repository is a binary/demo portfolio package. It is not intended to provide a complete public source build.

The included executable is the GUI desktop build:

```powershell
.\bin\CoeusAI.exe
```

No public headless executable is included.

---

## Private Build Environment

The private source version is built on Windows using:

- Windows 10/11
- Visual Studio 2022 Build Tools
- MSVC x64
- CMake
- C++20
- vcpkg-managed dependencies
- Skia
- SDL2
- OpenGL

---

## Major Native Dependencies

The application uses native libraries including:

- Skia
- SDL2
- OpenGL
- libcurl
- OpenSSL
- SQLite
- FAISS
- fmt
- xxHash
- tree-sitter
- nlohmann/json
- ICU / HarfBuzz through the rendering/text stack

---

## Build Outputs

The public release package uses:

```text
bin/
└── CoeusAI.exe
```

Depending on how the package is prepared, `bin/` may also include runtime DLLs required by the executable.

---

## CMake Build Path

A private CMake build path was established for the GUI application so the project can be built in a more professional and portable way than a single local batch script.

Typical private build shape:

```powershell
cmake -S . -B build_cmake -G "Visual Studio 17 2022" -A x64
cmake --build build_cmake --config Release
```

The final portfolio binary is exported as:

```text
CoeusAI.exe
```

---

## Headless Build Note

A separate private/internal headless build path exists for testing and evaluation. It is not part of this public repository and is not required to run the public GUI demo.

---

## Why the Full Build Is Not Included

The public repository intentionally excludes the full source build because it contains private implementation details, proprietary runtime work, internal prompt systems, and project-specific development artifacts.

For portfolio review, the binary and documentation are provided instead.
