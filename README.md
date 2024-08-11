# Setup

Install [cargo-mobile2](https://github.com/tauri-apps/cargo-mobile2)
```bash
cargo install --git https://github.com/tauri-apps/cargo-mobile2
```
To update the libray just run:
```bash
cargo mobile update
```
Now in order to build properly you need to have an ANDROID_HOME & NDK_HOME environment variable set. Either do it manually or download [Andorid Studio](https://developer.android.com/studio)
Download via paru:
```bash
paru -S android-studio
```
>Hint
>
>This can also be used to simulate an android phone on your device
Now setup Android Studio on default configuration. After click on `more Actions` under `Projects`. Here select `SDK Manager` and afterwards `SDK Tools` then install `NDK (Side by side)`.

After installation add the ANDROID_HOME and NDK_HOME environment variable to your shell.
For fish add:
```
## Android
set --export ANDROID_HOME $HOME/Android/Sdk
set -gx PATH $ANDROID_HOME/emulator $PATH;
set -gx PATH $ANDROID_HOME/tools $PATH;
set -gx PATH $ANDROID_HOME/tools/bin $PATH;
set -gx PATH $ANDROID_HOME/platform-tools $PATH;

set --export NDK_HOME $HOME/Android/Sdk/ndk/27.0.12077973
```
to your ``config.fish``.

For this project you need a java version between 18-21. Check your java version via:
```bash
java --version
```
if it is not between java 18-21 please install a new/older version. I would recommend openjdk-21. You can download it with:
```bash
paru -S openjdk21-src
```
Then for arch-users you can change it via:
```bash
archlinux-java set java-21-openjdk
```
Now you should be all set

# Build

It is possibile to build for different platforms.
For linux:
```bash
cargo build
```
For connected android devices: (Install App and Run)
```bash
cargo android run
```
Otherwise you can build the apk file with:
```bash
cargo android apk build
```


# egui

This is an example based on [agdk-egui example](https://github.com/rust-mobile/rust-android-examples), using `egui`, `winit` and `wgpu` to run [egui_demo_app](https://github.com/emilk/egui/tree/master/egui_demo_app).

To run this on desktop, just do `cargo run` like normal! For mobile, use `cargo android run` and `cargo apple run` respectively (or use `cargo android open` and `cargo apple open` to open in Android Studio and Xcode respectively).
