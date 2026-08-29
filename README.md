[![](https://img.shields.io/nuget/v/soenneker.libraries.ffprobe.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ffprobe/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ffprobe/build-and-test.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ffprobe/actions/workflows/build-and-test.yml)
[![](https://img.shields.io/nuget/dt/soenneker.libraries.ffprobe.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ffprobe/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ffprobe/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ffprobe/actions/workflows/codeql.yml)

# Soenneker.Libraries.ffprobe

Simply adds the ffprobe (FFmpeg) Windows executable, updated daily (if available).

## Install

```bash
dotnet add package Soenneker.Libraries.ffprobe
```

## What it provides

- Simply adds the ffprobe (FFmpeg) Windows executable, updated daily (if available).
- The file is copied to the output directory, and located at the relative path: `Resources\ffprobe.exe`.

## How to use it

After installation, resolve the packaged file from the output-relative path above. The package deploys the asset but does not invoke it for you.
