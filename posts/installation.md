
# Installation

## Prerequisites

Before installing native.cr, you need Crystal installed on your system.

### Install Crystal

**macOS:**
```bash
brew install crystal
```

Linux (Ubuntu/Debian):

```bash
curl -fsSL https://crystal-lang.org/install.sh | sudo bash
```

Linux (Arch):

```bash
sudo pacman -S crystal
```

Windows (WSL2):

```bash
# Use Ubuntu on WSL2, then follow Linux instructions
```

Verify installation:

```bash
crystal --version
```

Install native.cr

For Crystal Developers (Recommended)

Add to your shard.yml:

```yaml
dependencies:
  native:
    github: slick-lab/native.cr
    version: ~> 0.1.0
```

Then run:

```bash
shards install
```

The post-install script will:

- Download prebuilt Android libraries
- Build the native.cr CLI
- Install it to ~/.local/bin

For Non-Crystal Users

```bash
git clone https://github.com/slick-lab/native.cr
cd native.cr
shards install
shards build
sudo cp bin/native.cr /usr/local/bin/
```

Verify Installation

```bash
native.cr doctor
```

Expected output:

```
Native.cr Doctor

[OK] Crystal: 1.20.0
[OK] Android SDK: /home/user/android-sdk
[OK] Android NDK: 27.2.12479018
[OK] Native.cr: 0.0.98
```

Platform Dependencies

For Android Development

You need the Android NDK.

macOS:

```bash
brew install android-ndk
export ANDROID_NDK=/usr/local/share/android-ndk
```

Linux:

```bash
wget https://dl.google.com/android/repository/android-ndk-r27c-linux.zip
unzip android-ndk-r27c-linux.zip -d ~/
export ANDROID_NDK=~/android-ndk-r27c
```

Add to ~/.bashrc:

```bash
echo 'export ANDROID_NDK=$HOME/android-ndk-r27c' >> ~/.bashrc
source ~/.bashrc
```

For iOS Development (macOS only)

iOS support is coming soon. For now, you need:

- macOS with Xcode installed
- An Apple Developer account (for device testing)


Next: [Creating Your First App](create.md)
