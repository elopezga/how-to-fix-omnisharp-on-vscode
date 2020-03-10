# how-to-fix-omnisharp-on-vscode
## Why?
Installing Unity + VSCode on a new machine yields this ugly error:
```
C:\Users\#######\.vscode\extensions\ms-vscode.csharp-1.15.2\.omnisharp\1.30.1\msbuild\15.0\Bin\Microsoft.Common.CurrentVersion.targets(1126,5): Error: The reference assemblies for framework ".NETFramework,Version=v4.7.1" were not found. To resolve this, install the SDK or Targeting Pack for this framework version or retarget your application to a version of the framework for which you have the SDK or Targeting Pack installed. Note that assemblies will be resolved from the Global Assembly Cache (GAC) and will be used in place of reference assemblies. Therefore your assembly may not be correctly targeted for the framework you intend.
```
You try installing the .Net Core and .Net Framework to the specific version they suggests. You try reinstalling the C# plugin, VSCode, and ultimately your computer. Nothing works!. This document is an attempt to help the future weary programmer (me) that encounters it (once more).

## The Fix
### Windows
1. Download & install Visual Studio Community
1. Install everything related to Unity, C#, and .NETFramework,Version=v4.7.1
1. Delete Assembly-CSharp-Editor.csproj, Assembly-CSharp.csproj, LabrynthChallenge.sln
1. Open the Unity project in Visual Studio Community (remember to set it in External Tools) by right-clicking Assets and select Open C# Project. This will rebuild Assembly-CSharp-Editor.csproj, Assembly-CSharp.csproj & LabrynthChallenge.sln
1. Open the project in Unity and wait for it to compile.
1. Open VSCode & check the Omnisharp log window. If you get an error again, reinstall the plugin.

This could help you out or not. This is what I found works for me, but this fix is not a guarentee. I really hope it works for you 🤞.
