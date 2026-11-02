# Fortnite Hacks

> **Archived.** This project is from May 2018. The bundled SDK (`SDK.hpp`, `SDK/`) were dumped from a 2018 Fortnite build, so it won't work with current versions of the game. It's kept for reference only.

## Requirements

- Windows 10 or 11
- Visual Studio 2017 or newer with the **Desktop development with C++** workload
  - MSVC v141 toolset (or let VS retarget to a newer one, see below)
  - Windows 10 SDK

No other dependencies are needed. MinHook, FW1FontWrapper and the SDK are included in the repo. DirectX headers and libraries (`d3d11`, `d3dcompiler`, `dwrite`, `winmm`) come with the Windows SDK and are linked through `#pragma comment(lib, ...)`.

## Building

1. Clone or download the repository.
2. Open `d3d11hook.sln` in Visual Studio.
3. If you're using VS 2019 or newer, accept the **Retarget Projects** prompt (or right-click the project → *Retarget Projects*) to move it to your installed toolset and Windows SDK. The project file targets toolset `v141` and SDK `10.0.15063.0`.
4. Set the configuration to **Release** and the platform to **x64**. The SDK is 64-bit only, so x86 builds won't work.
5. Choose **Build → Build Solution** (Ctrl+Shift+B).

The output is `x64\Release\d3d11hook.dll`.

### Command line

From a *x64 Native Tools Command Prompt for VS*:

```
msbuild d3d11hook.sln /p:Configuration=Release /p
```

## Troubleshooting

- **MSB8020: build tools for v141 cannot be foundp 3), or install the "MSVC v141 – VS 2017 C++
build tools" component.
- **MSB8036: Windows SDK version 10.0.15063.0 wast *Project Properties → General → Windows SDKVersion* to an SDK you have installed.
- **Errors in `SDK/` files on newer compilers.** ++ → Language → Conformance mode: No*.
- **Linux or macOS:** not supported. The project  11.
