# Build FFmpeg and Libav

[details](https://trac.ffmpeg.org/wiki/CompilationGuide)  
use MinGW 64 with MSYS on Windows

pull repo
```bash
git clone https://github.com/FFmpeg/FFmpeg.git
cd FFmpeg
git checkout release/5.0
```

configure (windows)
```
./configure \
  --toolchain=msvc \
  --prefix="./ffmpeg_build" \
  --pkg-config-flags="--static" \
  --extra-cflags="-I./ffmpeg_build/include" \
  --extra-ldflags="-L./ffmpeg_build/lib" \
  --extra-libs=-lpthread \
  --extra-libs=-lm \
  --bindir="./bin" \
  --enable-small \
  --enable-static \
  --enable-version3 \
  --disable-runtime-cpudetect \
  --disable-programs \
  --disable-doc \
  --enable-vpx \
  --enable-encoder=apng
```

compile
```bash
make -j10
make install -j10
```

# libvpx

```
git clone https://github.com/webmproject/libvpx.git
```

```
./configure \
  --target=x86_64-win64-vs17 \
  --disable-install-bins \
  --disable-examples \
  --disable-tools \
  --disable-docs \
  --enable-vp8 \
  --enbale-vp9 \
  --enable-webm-io \
  --enable-small
```

# zlib

```
git clone https://github.com/madler/zlib.git
git checkout v1.2.12
```

```
mkdir build
cd build
cmake ..
cmake --build . --config Release
```
