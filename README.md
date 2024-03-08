# libndk_fixer
This fixes the roblox app crashing inside Waydroid when using libndk_translation.

## How to install
Note: I've only tested these instructions Ubuntu 23.04, the waydroid directory may differ on your machine.
- Build yourself or download a precompiled binary from ci.
- Ensure you have libndk installed, if not you can install it using [waydroid_script](https://github.com/casualsnek/waydroid_script)
- Edit `/var/lib/waydroid/waydroid_base.prop`
-- Find the line that says `ro.dalvik.vm.native.bridge=libndk_translation.so` and replace the `translation` with `fixer`
- Copy the `libndk_fixer.so` file to this directory `/var/lib/waydroid/overlay/system/lib64/`
- Finished! The app should start normally now.
## Building yourself
- Ensure you have cmake and the [android ndk](https://developer.android.com/ndk/downloads) on your system and the path is stored in the `ANDROID_NDK_HOME` environment variable.
- Clone the repository with `--recursive` to pull the dobby submodule.
- Run build.sh
- The resulting built file `libndk_fixer.so` will be in the build directory.