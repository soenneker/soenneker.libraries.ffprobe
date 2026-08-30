[![](https://img.shields.io/nuget/v/soenneker.libraries.ffprobe.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ffprobe/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ffprobe/build-and-test.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ffprobe/actions/workflows/build-and-test.yml)
[![](https://img.shields.io/nuget/dt/soenneker.libraries.ffprobe.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.libraries.ffprobe/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.libraries.ffprobe/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/soenneker/soenneker.libraries.ffprobe/actions/workflows/codeql.yml)

# Soenneker.Libraries.ffprobe

The ffprobe Windows executable packaged as a .NET content asset.

## Install

```bash
dotnet add package Soenneker.Libraries.ffprobe
```

The package copies the executable to `Resources/ffprobe.exe` beneath the application output directory.

```csharp
string ffprobe = Path.Combine(AppContext.BaseDirectory, "Resources", "ffprobe.exe");

var startInfo = new ProcessStartInfo(ffprobe)
{
    RedirectStandardOutput = true,
    UseShellExecute = false
};

startInfo.ArgumentList.Add("-v");
startInfo.ArgumentList.Add("error");
startInfo.ArgumentList.Add("-show_streams");
startInfo.ArgumentList.Add("-of");
startInfo.ArgumentList.Add("json");
startInfo.ArgumentList.Add(inputPath);

using Process process = Process.Start(startInfo)!;
string json = await process.StandardOutput.ReadToEndAsync(cancellationToken);
await process.WaitForExitAsync(cancellationToken);
```

Check `process.ExitCode` before trusting the output. The package supplies the Windows executable but does not manage processes or parse ffprobe results.
