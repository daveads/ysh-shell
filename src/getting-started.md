## Getting Started

Installing Oils on macOS and Linux.


Oils provides two shells in one binary:
- **OSH** - A bash-compatible shell
- **YSH** - The modern shell language (what we're learning!)

Both are built into a single `oils-for-unix` binary with symlinks for convenience.

## System Requirements

Before installing, you need:
- c++ compiler (gcc or clang)
- Standard C and C++ libraries (libc, libstdc++)
- GNU readline library (optional, but recommended for interactive features)

## Quick Installation (macOS and Linux)

### Download the Release

Visit the releases page and download the latest version:
- **Releases:** https://oils.pub/releases.html
- **Latest:** https://oils.pub/release/latest/

Or download directly:

```bash
# Download latest version (0.36.0 as of this writing)
wget https://oils.pub/download/oils-for-unix-0.36.0.tar.gz

# Or use curl if you don't have wget
curl -O https://oils.pub/download/oils-for-unix-0.36.0.tar.gz
```

### Extract the Tarball

```bash
tar -xzf oils-for-unix-0.36.0.tar.gz
cd oils-for-unix-0.36.0
```

### Step 3: Build and Install

```bash
# Configure (completes very quickly)
./configure

# Build (takes 30-60 seconds)
_build/oils.sh

# Install system-wide (requires sudo)
sudo ./install
```

## Verify Installation

After installation, verify everything works:

```bash
# Check installation location
which ysh
# Should show: /usr/local/bin/ysh (or your custom prefix)

# Check version
ysh --version
# Should show: Oils 0.36.0

# Test OSH (bash-compatible)
osh -c 'echo "OSH works!"'

# Test YSH (modern syntax)
ysh -c 'echo "YSH works!"'

# Test YSH with JSON
ysh -c 'json write ({x: 42, y: "hello"})'
```

## What Gets Installed

After installation, you'll have:

```
/usr/local/bin/
  oils-for-unix      # The main binary
  osh                # Symlink to oils-for-unix
  ysh                # Symlink to oils-for-unix
```

And man pages:
```
/usr/local/share/man/man1/
  osh.1
  ysh.1
```

## Running Without Installing

You can run the binary directly from the build directory:

```bash
# After running _build/oils.sh
_bin/cxx-opt-sh/osh -c 'echo hi'
_bin/cxx-opt-sh/ysh -c 'echo hi'
```

This is useful for testing before installation.


## Next Steps

Now that YSH is installed, let's write your first script!

**Next:** [Your First YSH Script](Basics/hello.md)


## Additional Resources

- [**Release home page:**](https://oils.pub/release/0.36.0/)
- [**All releases:**](https://oils.pub/releases.html)
- [**Installation docs:**](https://oils.pub/release/latest/doc/INSTALL.html)
- [**GitHub issues:**](https://github.com/oilshell/oil/issues)
- [**Portability notes:**](https://oils.pub/release/0.36.0/doc/portability.html)