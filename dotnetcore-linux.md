---
title: PDFTron for .NET Core for Linux
---

## Running sample projects

1. Install the .NET Core SDK: https://www.microsoft.com/net/learn/get-started/linux/
2. Download PDFTron SDK
3. Navigate into a sample project, for example `/Samples/AddImageTest/CS`
4. Run `dotnet run`

## Creating your app

1. Install the .NET Core SDK: https://www.microsoft.com/net/learn/get-started/linux/
2. Download PDFTron SDK
3. Create a new project

```shell
> dotnet new console -o myApp
> cd myApp
```

4. Unzip PDFTron SDK package, copy `/Lib/libPDFNetC.so`, `/Lib/libPDFNetC.so.//variable linux-cpp-ver//` and `/Lib/PDFNetDotNetCore.dll` into `myApp` folder.
5. Open `myApp.csproj` in your favorite text editor, add:

```
<ItemGroup>
  <Content Include="libPDFNetC.so">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
</ItemGroup>

<ItemGroup>
  <Reference Include="PDFNetDotNetCore">
    <HintPath>PDFNetDotNetCore.dll</HintPath>
  </Reference>
</ItemGroup>
```

6. Open `Program.cs` in your favorite text editor, add:

```csharp
static void Main(string[] args)
{
    Console.WriteLine("Hello World!");
    pdftron.PDFNet.Initialize();
}
```

7. Run the project:

```shell
> dotnet run
```

Now you have made a .NET Core project with PDFTron SDK!

```
Hello World!

PDFNet is running in demo mode.
```
