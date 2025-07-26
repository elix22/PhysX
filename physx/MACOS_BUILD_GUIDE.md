# PhysX macOS Build Presets

This document describes the cleaned and updated macOS build presets for PhysX SDK.

## Overview

All macOS presets have been updated to:
- ✅ **Support snippets** - OpenGL context initialization fixed
- ✅ **Proper architecture targeting** - Native ARM64 and x86_64 support  
- ✅ **Correct platform settings** - Fixed from incorrect `linux` to proper `mac64`/`macArm64`
- ✅ **Both build systems** - Unix Makefiles and Xcode generator support

## Available Presets

### ARM64 (Apple Silicon) Presets

#### `macos-clang-arm64-cpu-only`
- **Architecture**: ARM64 (Apple Silicon native)
- **Generator**: Unix Makefiles
- **Snippets**: ✅ Enabled
- **Use case**: Standard ARM64 development and testing
- **Command**: `./generate_projects.sh macos-clang-arm64-cpu-only`

#### `macos-clang-arm64-cpu-only-xcode`
- **Architecture**: ARM64 (Apple Silicon native)  
- **Generator**: Xcode
- **Snippets**: ✅ Enabled
- **GPU Support**: CPU-only
- **Use case**: ARM64 debugging and development in Xcode (CPU-only)
- **Command**: `./generate_projects.sh macos-clang-arm64-cpu-only-xcode`
- **Xcode Project**: `compiler/macos-clang-arm64-cpu-only-xcode-debug/PhysXSDK.xcodeproj`

#### `macos-clang-arm64-xcode` ⭐ **NEW**
- **Architecture**: ARM64 (Apple Silicon native)  
- **Generator**: Xcode
- **Snippets**: ✅ Enabled
- **GPU Support**: Full GPU support enabled
- **Use case**: ARM64 debugging and development in Xcode with GPU features
- **Command**: `./generate_projects.sh macos-clang-arm64-xcode`
- **Xcode Project**: `compiler/macos-clang-arm64-xcode-debug/PhysXSDK.xcodeproj`

#### `macos-clang-arm64`
- **Architecture**: ARM64 (Apple Silicon native)
- **Generator**: Unix Makefiles
- **Snippets**: ✅ Enabled
- **GPU Support**: Full GPU support enabled
- **Use case**: Standard ARM64 development with full GPU features
- **Command**: `./generate_projects.sh macos-clang-arm64`

### x86_64 (Intel Mac) Presets

#### `macos-clang-x86_64-cpu-only`
- **Architecture**: x86_64 (Intel Mac)
- **Generator**: Unix Makefiles  
- **Snippets**: ✅ Enabled (fixed from previously disabled)
- **Use case**: Intel Mac development and compatibility testing
- **Command**: `./generate_projects.sh macos-clang-x86_64-cpu-only`

#### `macos-clang-x86_64-cpu-only-xcode`
- **Architecture**: x86_64 (Intel Mac)
- **Generator**: Xcode
- **Snippets**: ✅ Enabled
- **GPU Support**: CPU-only
- **Use case**: Intel Mac debugging and development in Xcode (CPU-only)
- **Command**: `./generate_projects.sh macos-clang-x86_64-cpu-only-xcode`
- **Xcode Project**: `compiler/macos-clang-x86_64-cpu-only-xcode-debug/PhysXSDK.xcodeproj`

#### `macos-clang-x86_64-xcode` ⭐ **NEW**
- **Architecture**: x86_64 (Intel Mac)
- **Generator**: Xcode
- **Snippets**: ✅ Enabled
- **GPU Support**: Full GPU support enabled
- **Use case**: Intel Mac debugging and development in Xcode with GPU features
- **Command**: `./generate_projects.sh macos-clang-x86_64-xcode`
- **Xcode Project**: `compiler/macos-clang-x86_64-xcode-debug/PhysXSDK.xcodeproj`

#### `macos-clang-x86_64`
- **Architecture**: x86_64 (Intel Mac)
- **Generator**: Unix Makefiles  
- **Snippets**: ✅ Enabled (fixed from previously disabled)
- **GPU Support**: Full GPU support enabled
- **Use case**: Intel Mac development with full GPU features
- **Command**: `./generate_projects.sh macos-clang-x86_64`

### Universal Binary Presets

#### `macos-clang-universal-cpu-only`
- **Architecture**: Universal Binary (x86_64 + ARM64)
- **Generator**: Unix Makefiles
- **Snippets**: ✅ Enabled
- **GPU Support**: CPU-only
- **Use case**: Distribution builds supporting both Intel and Apple Silicon Macs (CPU-only)
- **Command**: `./generate_projects.sh macos-clang-universal-cpu-only`

#### `macos-clang-universal-cpu-only-xcode`  
- **Architecture**: Universal Binary (x86_64 + ARM64)
- **Generator**: Xcode
- **Snippets**: ✅ Enabled
- **GPU Support**: CPU-only
- **Use case**: Universal binary debugging and development in Xcode (CPU-only)
- **Command**: `./generate_projects.sh macos-clang-universal-cpu-only-xcode`
- **Xcode Project**: `compiler/macos-clang-universal-cpu-only-xcode-debug/PhysXSDK.xcodeproj`

## Complete Preset Matrix

| Preset Name | Architecture | Generator | GPU Support | Xcode | Command |
|-------------|-------------|-----------|-------------|-------|---------|
| `macos-clang-arm64-cpu-only` | ARM64 | Unix Makefiles | CPU-only | ❌ | `./generate_projects.sh macos-clang-arm64-cpu-only` |
| `macos-clang-arm64-cpu-only-xcode` | ARM64 | Xcode | CPU-only | ✅ | `./generate_projects.sh macos-clang-arm64-cpu-only-xcode` |
| `macos-clang-arm64` | ARM64 | Unix Makefiles | Full GPU | ❌ | `./generate_projects.sh macos-clang-arm64` |
| `macos-clang-arm64-xcode` ⭐ | ARM64 | Xcode | Full GPU | ✅ | `./generate_projects.sh macos-clang-arm64-xcode` |
| `macos-clang-x86_64-cpu-only` | x86_64 | Unix Makefiles | CPU-only | ❌ | `./generate_projects.sh macos-clang-x86_64-cpu-only` |
| `macos-clang-x86_64-cpu-only-xcode` | x86_64 | Xcode | CPU-only | ✅ | `./generate_projects.sh macos-clang-x86_64-cpu-only-xcode` |
| `macos-clang-x86_64` | x86_64 | Unix Makefiles | Full GPU | ❌ | `./generate_projects.sh macos-clang-x86_64` |
| `macos-clang-x86_64-xcode` ⭐ | x86_64 | Xcode | Full GPU | ✅ | `./generate_projects.sh macos-clang-x86_64-xcode` |
| `macos-clang-universal-cpu-only` | Universal | Unix Makefiles | CPU-only | ❌ | `./generate_projects.sh macos-clang-universal-cpu-only` |
| `macos-clang-universal-cpu-only-xcode` | Universal | Xcode | CPU-only | ✅ | `./generate_projects.sh macos-clang-universal-cpu-only-xcode` |

⭐ = New presets added

## Key Features

### OpenGL Context Fix
All presets include the fixed OpenGL context initialization order:
1. GLUT window creation
2. GLEW initialization  
3. Font renderer initialization (after valid OpenGL context)

This eliminates the previous `EXC_BAD_ACCESS` crashes when running snippets.

### Xcode Generator Support
Xcode presets use `compiler="xcode"` to properly trigger the Xcode generator in the PhysX build system, following the Windows preset pattern. Both CPU-only and GPU-enabled Xcode presets are available for debugging and development.

### Binary Output Structure  
The build system now correctly separates binaries by architecture:
- **ARM64 builds**: Output to `bin/mac.arm64_64/` directories
- **Intel builds**: Output to `bin/mac.x86_64/` directories  
- **Universal builds**: Output to appropriate directories based on build configuration

This ensures proper library separation and prevents architecture conflicts.

### Snippets Support
All presets now have `PX_BUILDSNIPPETS=True` with working OpenGL rendering:
- Font rendering works properly
- Window positioning fixed for macOS
- Cross-architecture compatibility

### Build Configurations
All Xcode presets include complete build configurations:
- Debug (with full symbols)
- Release (optimized)
- Profile (optimized with profiling)
- Checked (optimized with assertions)

## Usage Examples

```bash
# Build ARM64 with Unix Makefiles (CPU-only)
./generate_projects.sh macos-clang-arm64-cpu-only
make -C compiler/macos-clang-arm64-cpu-only-debug -j8

# Build ARM64 with full GPU support
./generate_projects.sh macos-clang-arm64
make -C compiler/macos-clang-arm64-debug -j8

# Build ARM64 with Xcode (full GPU support)
./generate_projects.sh macos-clang-arm64-xcode
open compiler/macos-clang-arm64-xcode-debug/PhysXSDK.xcodeproj

# Build x86_64 with Xcode (full GPU support)  
./generate_projects.sh macos-clang-x86_64-xcode
open compiler/macos-clang-x86_64-xcode-debug/PhysXSDK.xcodeproj

# Build Universal Binary
./generate_projects.sh macos-clang-universal-cpu-only
make -C compiler/macos-clang-universal-cpu-only-debug -j8

# Test snippets (architecture-specific directories)
./bin/mac.arm64_64/debug/SnippetHelloWorld_64    # ARM64 build
./bin/mac.x86_64/debug/SnippetHelloWorld_64      # Intel build
```

## Troubleshooting

### Window Minimization
If snippet windows appear minimized, the issue is separate from the OpenGL crash fix. Use the Xcode presets for debugging window management behavior.

### Architecture Mismatch
Ensure you're using the correct preset for your target architecture:
- Apple Silicon Macs: Use `arm64` presets for best performance
- Intel Macs: Use `x86_64` presets  
- Distribution: Use `universal` presets

### CPU-only vs GPU-enabled Presets
- **CPU-only presets**: Faster builds, suitable for basic physics without GPU acceleration
- **GPU-enabled presets**: Full PhysX features including GPU acceleration (if available)
- For debugging: Both types work equally well in Xcode

### Binary Output Directories
Check the correct output directory for your architecture:
- ARM64 builds: Look in `bin/mac.arm64_64/`
- Intel builds: Look in `bin/mac.x86_64/`
- If binaries appear in wrong directory, verify preset `targetPlatform` setting

### OpenGL Deprecation Warnings
OpenGL is deprecated on macOS but still functional. The warnings are expected and do not affect functionality.

## iOS Build Presets

PhysX now includes iOS build support with dedicated presets that exclude snippets (since GLUT is not available on iOS) and properly target iOS platforms.

### iOS Device (ARM64) Presets

#### `ios-clang-arm64`
- **Architecture**: ARM64 (iOS device)
- **Generator**: Unix Makefiles
- **Snippets**: ❌ Disabled (GLUT not available on iOS)
- **Target**: iOS 12.0+
- **Use case**: iOS device builds
- **Command**: `./generate_projects.sh ios-clang-arm64`
- **Output**: `bin/ios.arm64_device_64/` (static libraries)

#### `ios-clang-arm64-xcode`
- **Architecture**: ARM64 (iOS device)
- **Generator**: Xcode
- **Snippets**: ❌ Disabled (GLUT not available on iOS)
- **Target**: iOS 12.0+
- **Use case**: iOS development and debugging in Xcode
- **Command**: `./generate_projects.sh ios-clang-arm64-xcode`
- **Xcode Project**: `compiler/ios-clang-arm64-xcode-debug/PhysXSDK.xcodeproj`

### iOS Simulator Presets

#### `ios-clang-x86_64-simulator`
- **Architecture**: x86_64 (iOS Simulator on Intel Macs)
- **Generator**: Unix Makefiles
- **Snippets**: ❌ Disabled (GLUT not available on iOS)
- **Target**: iOS 12.0+
- **Use case**: iOS Simulator builds on Intel Macs
- **Command**: `./generate_projects.sh ios-clang-x86_64-simulator`
- **Output**: `bin/ios.x86_64_simulator_64/`

#### `ios-clang-arm64-simulator`
- **Architecture**: ARM64 (iOS Simulator on Apple Silicon)
- **Generator**: Unix Makefiles
- **Snippets**: ❌ Disabled (GLUT not available on iOS)
- **Target**: iOS 14.0+ (ARM64 simulator support)
- **Use case**: iOS Simulator builds on Apple Silicon Macs
- **Command**: `./generate_projects.sh ios-clang-arm64-simulator`
- **Output**: `bin/ios.arm64_simulator_64/`

#### `ios-clang-simulator-xcode`
- **Architecture**: Universal (x86_64 + ARM64 simulator)
- **Generator**: Xcode
- **Snippets**: ❌ Disabled (GLUT not available on iOS)
- **Target**: iOS 12.0+
- **Use case**: Universal iOS Simulator development in Xcode
- **Command**: `./generate_projects.sh ios-clang-simulator-xcode`
- **Xcode Project**: `compiler/ios-clang-simulator-xcode-debug/PhysXSDK.xcodeproj`

### iOS Build Notes

- **Static Libraries Only**: iOS presets generate static libraries (`.a` files) as required by iOS
- **No Snippets**: Snippets are disabled because GLUT/OpenGL context creation is not supported on iOS
- **Minimum iOS Version**: Device presets target iOS 12.0+, ARM64 simulator requires iOS 14.0+
- **Development Team**: For Xcode presets, set your development team ID in the preset file if needed
- **Code Signing**: Xcode presets include basic code signing settings that may need customization

### iOS Usage Examples

```bash
# Build for iOS device (ARM64)
./generate_projects.sh ios-clang-arm64
make -C compiler/ios-clang-arm64-release -j8

# Generate Xcode project for iOS development
./generate_projects.sh ios-clang-arm64-xcode
open compiler/ios-clang-arm64-xcode-debug/PhysXSDK.xcodeproj

# Build for iOS Simulator (Universal)
./generate_projects.sh ios-clang-simulator-xcode
open compiler/ios-clang-simulator-xcode-debug/PhysXSDK.xcodeproj

# Verify iOS libraries were generated with proper directory separation
ls bin/ios.arm64_device_64/release/libPhysX*.a          # iOS device libraries
ls bin/ios.x86_64_simulator_64/release/libPhysX*.a      # iOS simulator libraries  
ls bin/mac.arm64_64/release/libPhysX*.a                 # macOS libraries (separate!)
```

```
