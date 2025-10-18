# 🧰 ZakariaAitAli.Logging

A minimal **C# / .NET logging library**, published as a **NuGet package** on **GitHub Packages**.

---

## 🚀 Build & Test Locally

```bash
dotnet build
dotnet run
````

---

## 📦 Publish to GitHub Packages

Authenticate with your **GitHub personal access token (Classic)** that has the `write:packages` scope:

```bash
export GITHUB_TOKEN=your_token
dotnet nuget add source \
  --username zakariaaitali \
  --password $GITHUB_TOKEN \
  --store-password-in-clear-text \
  --name github \
  "https://nuget.pkg.github.com/ZakariaAitAli/index.json"
```

Then build and publish:

```bash
dotnet pack -c Release
dotnet nuget push bin/Release/ZakariaAitAli.Logging.1.0.0.nupkg \
  --source "github"
```

---

## 📥 Usage

Add this to your project’s `.csproj`:

```xml
<PackageReference Include="ZakariaAitAli.Logging" Version="1.0.0" />
```

Then use it:

```csharp
using ZakariaAitAli.Logging;

class Program
{
    static void Main()
    {
        Logger.Info("Hello, Zakaria!");
        Logger.Error("Something went wrong!");
    }
}
```
