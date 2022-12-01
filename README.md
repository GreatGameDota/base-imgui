# Base ImGui Repo

Clean boiler plate code, directories, and submodules for ImGui development using the SDL and Vulkan backends.

## Requirements

- [Visual Studio 2022 Community](https://visualstudio.microsoft.com/) or lower versions
- [Any SDL2 (VC) release](https://github.com/libsdl-org/SDL/releases) downloaded and path to it saved in `SDL2_DIR` environment variable
- [Any Vulkan SDK release](https://vulkan.lunarg.com/sdk/home#windows) downloaded and path to it saved in `VK_SDK_PATH` and `VULKAN_SDK` environment variables

## Getting Started

### Build

1. Clone Repository

```cli
git clone https://github.com/GreatGameDota/base-imgui.git
cd base-imgui
```

2. Open `base-imgui.sln` in Visual Studio 2022 (or earlier). Build and compile Debug version or Release version to x64 platform.

### Run

Run debug through Visual Studio or run built `exe` in generated bin subdirectories.

## Licenses

This project uses [Dear ImGui](https://github.com/ocornut/imgui) which is licensed under the MIT License

This project uses the [Roboto](https://fonts.google.com/specimen/Roboto) font which is licensed under [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)
