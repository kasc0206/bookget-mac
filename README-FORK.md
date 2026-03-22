# ⚠️ Bookget Fork for macOS Apple Silicon

## Fork Information

This is a fork of [deweizhu/bookget](https://github.com/deweizhu/bookget) with enhancements for **macOS Apple Silicon (M-series) only**.

**Original Repository**: https://github.com/deweizhu/bookget  
**License**: GPLv3 (same as original)

## Key Changes

This fork introduces an **auto-naming framework** that replaces sequential numbered files with meaningful book titles and metadata. Major updates include:

1. **Generic Auto-Naming System** (`app/template.go`):
   - `BuildOutputFileName()`: Creates readable filenames with deduplicated parts
   - `ExtractHTMLTitle()`: Extracts titles from HTML meta tags
   - `NormalizeNamePart()`: Handles HTML entities and whitespace

2. **Enhanced Downloaders**:
   - **NLC** (National Library of China): Adds publication time to filename
   - **Wzlib**: Supports both new and old campuses with smart naming
   - **Tokyo University**: HTML-based title extraction
   - **Luoyang Library**: Metadata-enriched filenames
   - **Guangzhou Library**: Dynamic title naming
   - **Seoul National**: Improved header handling for compatibility

3. **Real-World Validation**:
   - ✓ Tested with actual library links
   - ✓ Verified output filenames quality
   - ✓ All 6 major sites working correctly

## Platform Support

### ✅ Supported
- **macOS 11+** with Apple Silicon (M1, M2, M3, M4, etc.)
- Binary: `dist/darwin-arm64/bookget-macos-arm64`

### ❌ NOT Supported in This Fork
- Intel Mac (use original repository)
- Linux, Windows (use original repository)
- Other architectures

## Building from Source

```bash
# Install Go (v1.18+)
brew install go

# Clone and build
git clone https://github.com/kasc0206/bookget.git
cd bookget

# Build for macOS M-series
go build -trimpath -ldflags "-s -w" -o dist/darwin-arm64/bookget-macos-arm64 ./cmd/
```

## Usage

```bash
# Download from National Library of China
./dist/darwin-arm64/bookget-macos-arm64 'https://www.nlc.cn/...'

# Download from Wenzhou Library
./dist/darwin-arm64/bookget-macos-arm64 'https://www.wzlib.cn/...'

# See full documentation
./dist/darwin-arm64/bookget-macos-arm64 --help
```

## Documentation

- **Original Wiki**: https://github.com/deweizhu/bookget/wiki
- **Our Changes**: See [CHANGELOG.md](CHANGELOG.md)
- **Original Repo**: https://github.com/deweizhu/bookget

## License

This fork maintains the **GPLv3 License** from the original project. All modifications are also under GPLv3.

See [LICENSE](LICENSE) for details.

---

### For Other Platforms

This fork is **macOS M-series specific**. For other systems, please use the original repository:
- **Original**: https://github.com/deweizhu/bookget
- **Windows/Intel Mac/Linux**: Follow instructions at the original repository

