# Build FFmpeg and Libav

[details](https://trac.ffmpeg.org/wiki/CompilationGuide)

pull repo
```bash
git clone https://github.com/FFmpeg/FFmpeg.git
cd FFmpeg
git checkout release/5.0
```

configure (windows)
```powershell
./configure \
  --toolchain=msvc \
  --prefix="./ffmpeg_build" \
  --pkg-config-flags="--static" \
  --extra-cflags="-I./ffmpeg_build/include" \
  --extra-ldflags="-L./ffmpeg_build/lib" \
  --extra-libs=-lpthread \
  --extra-libs=-lm \
  --bindir="./bin" \
  --enable-static
```

compile
```bash
make -j10
make install
```