## How to detect lines in pdf with pdf extractor sdk in VB.NET with ByteScout Premium Suite

### Learning is essential in computer world and the tutorial below will demonstrate how to detect lines in pdf with pdf extractor sdk in VB.NET

The sample source code below will teach you how to detect lines in pdf with pdf extractor sdk in VB.NET. ByteScout Premium Suite is the bundle that includes twelve SDK products from ByteScout including tools and components for PDF, barcodes, spreadsheets, screen video recording. It can be applied to detect lines in pdf with pdf extractor sdk using VB.NET.

This prolific sample source code in VB.NET for ByteScout Premium Suite contains various functions and other necessary options you should do calling the API to detect lines in pdf with pdf extractor sdk. IF you want to implement the functionality, just copy and paste this code for VB.NET below into your code editor with your app, compile and run your application. This basic programming language sample code for VB.NET will do the whole work for you to detect lines in pdf with pdf extractor sdk.

ByteScout Premium Suite free trial version is available on our website. VB.NET and other programming languages are supported.

## REQUEST FREE TECH SUPPORT

[Click here to get in touch](https://bytescout.zendesk.com/hc/en-us/requests/new?subject=ByteScout%20Premium%20Suite%20Question)

or just send email to [support@bytescout.com](mailto:support@bytescout.com?subject=ByteScout%20Premium%20Suite%20Question) 

## ON-PREMISE OFFLINE SDK 

[Get Your 60 Day Free Trial](https://bytescout.com/download/web-installer?utm_source=github-readme)
[Explore SDK Docs](https://bytescout.com/documentation/index.html?utm_source=github-readme)
[Sign Up For Online Training](https://academy.bytescout.com/)


## ON-DEMAND REST WEB API

[Get your API key](https://pdf.co/documentation/api?utm_source=github-readme)
[Explore Web API Documentation](https://pdf.co/documentation/api?utm_source=github-readme)
[Explore Web API Samples](https://github.com/bytescout/ByteScout-SDK-SourceCode/tree/master/PDF.co%20Web%20API)

## VIDEO REVIEW

[https://www.youtube.com/watch?v=NEwNs2b9YN8](https://www.youtube.com/watch?v=NEwNs2b9YN8)




<!-- code block begin -->

##### ****DetectLines.vbproj:**
    
```
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProjectGuid>{846F275E-BE99-4254-85ED-B8CBBB4546A9}</ProjectGuid>
    <OutputType>Exe</OutputType>
    <StartupObject>LineDetectorDemo.Program</StartupObject>
    <RootNamespace>LineDetectorDemo</RootNamespace>
    <AssemblyName>LineDetectorDemo</AssemblyName>
    <FileAlignment>512</FileAlignment>
    <MyType>Console</MyType>
    <TargetFrameworkVersion>v2.0</TargetFrameworkVersion>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <PlatformTarget>AnyCPU</PlatformTarget>
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <DefineDebug>true</DefineDebug>
    <DefineTrace>true</DefineTrace>
    <OutputPath>bin\Debug\</OutputPath>
    <DocumentationFile>LineDetectorDemo.xml</DocumentationFile>
    <NoWarn>42016,41999,42017,42018,42019,42032,42036,42020,42021,42022</NoWarn>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <PlatformTarget>AnyCPU</PlatformTarget>
    <DebugType>pdbonly</DebugType>
    <DefineDebug>false</DefineDebug>
    <DefineTrace>true</DefineTrace>
    <Optimize>true</Optimize>
    <OutputPath>bin\Release\</OutputPath>
    <DocumentationFile>LineDetectorDemo.xml</DocumentationFile>
    <NoWarn>42016,41999,42017,42018,42019,42032,42036,42020,42021,42022</NoWarn>
  </PropertyGroup>
  <PropertyGroup>
    <OptionExplicit>On</OptionExplicit>
  </PropertyGroup>
  <PropertyGroup>
    <OptionCompare>Binary</OptionCompare>
  </PropertyGroup>
  <PropertyGroup>
    <OptionStrict>Off</OptionStrict>
  </PropertyGroup>
  <PropertyGroup>
    <OptionInfer>On</OptionInfer>
  </PropertyGroup>
  <ItemGroup>
    <Reference Include="Bytescout.PDFExtractor, Version=9.1.0.3170, Culture=neutral, PublicKeyToken=f7dd1bd9d40a50eb, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>..\..\..\..\..\..\..\..\..\..\Program Files\Bytescout PDF Extractor SDK\net2.00\Bytescout.PDFExtractor.dll</HintPath>
    </Reference>
    <Reference Include="System" />
    <Reference Include="System.Data" />
    <Reference Include="System.Deployment" />
    <Reference Include="System.Drawing" />
    <Reference Include="System.Xml" />
  </ItemGroup>
  <ItemGroup>
    <Import Include="Microsoft.VisualBasic" />
    <Import Include="System" />
    <Import Include="System.Collections" />
    <Import Include="System.Collections.Generic" />
    <Import Include="System.Data" />
    <Import Include="System.Diagnostics" />
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Program.vb" />
  </ItemGroup>
  <ItemGroup>
    <None Include="LineDetectSample.pdf">
      <CopyToOutputDirectory>Always</CopyToOutputDirectory>
    </None>
  </ItemGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />
</Project>
```

<!-- code block end -->    

<!-- code block begin -->

##### ****Program.vb:**
    
```
Imports Bytescout.PDFExtractor

' Detect all lines in PDF documents

Module Program

    Sub Main()

        Try

            Using lineDetector As New LineDetector("demo", "demo")

                ' Load PDF Document
                lineDetector.LoadDocumentFromFile("LineDetectSample.pdf")

                ' Get all lines
                Dim foundLinesCollection As FoundLinesCollection = lineDetector.FindLines(0, LineOrientationsToFind.HorizontalAndVertical)

                ' Print output
                Console.WriteLine("Total {0} lines Detected", foundLinesCollection.Count)

                For Each foundLine As FoundLine In foundLinesCollection
                    Console.WriteLine("From: {0}, To: {1}, Width: {2}, Line Orientation: {3}",
                            foundLine.From.ToString(), foundLine.To.ToString(), foundLine.Width, foundLine.LineOrientation.ToString())
                Next

            End Using

        Catch ex As Exception
            Console.WriteLine("ERROR:" + ex.Message)
        End Try

        Console.WriteLine("Press any key to exit...")
        Console.ReadLine()
    End Sub

End Module

```

<!-- code block end -->