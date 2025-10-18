# 🧰 ZakariaAitAli.Logging

A lightweight **C# / .NET logging library**, published as a **NuGet package** on **GitHub Packages**.  
Provides simple, formatted console logging for any .NET application.

---

## 🚀 Build & Run Locally

Clone the repository and run the demo:

```bash
git clone https://github.com/ZakariaAitAli/logging.git
cd logging
dotnet build
dotnet run --project logging-demo/logging-demo.csproj
````

You should see output like:

```
[INFO] 2025-10-18 20:00:00 - Hello, Zakaria!
[ERROR] 2025-10-18 20:00:00 - Something went wrong!
```

---

## 🧪 Project Structure

```
logging/
├── src/               # Library source code
│   ├── logging.csproj
│   └── Logging.cs
├── logging-demo/      # Console demo project
│   ├── logging-demo.csproj
│   └── Program.cs
└── .github/workflows/ # CI/CD pipeline for build + publish
```

---

## 📦 Publish to GitHub Packages

Authenticate using your **GitHub Personal Access Token (Classic)** with the `write:packages` scope:

```bash
export GITHUB_TOKEN=your_token

dotnet nuget add source \
  --username zakariaaitali \
  --password $GITHUB_TOKEN \
  --store-password-in-clear-text \
  --name github \
  "https://nuget.pkg.github.com/ZakariaAitAli/index.json"
```

Then build and publish your package:

```bash
cd src
dotnet pack -c Release
dotnet nuget push bin/Release/ZakariaAitAli.Logging.1.0.0.nupkg --source "github"
```

After publishing, the package will be visible here:
👉 [https://github.com/ZakariaAitAli?tab=packages](https://github.com/ZakariaAitAli?tab=packages)

---

## 📥 Usage in Your Project

Add this to your project’s `.csproj` file:

```xml
<PackageReference Include="ZakariaAitAli.Logging" Version="1.0.0" />
```

Then use it in your code:

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

---

## ⚙️ Continuous Integration (CI)

This repository includes a **GitHub Actions** workflow:

* Builds both `src` and `logging-demo`
* Runs the demo for verification
* Packages and uploads artifacts
* Publishes automatically to **GitHub Packages** when a tag like `v1.0.0` is pushed

File: `.github/workflows/dotnet.yml`

---

## 🧾 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
