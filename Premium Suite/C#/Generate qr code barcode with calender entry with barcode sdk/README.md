## How to generate qr code barcode with calender entry with barcode sdk in C# with ByteScout Premium Suite

### This code in C# shows how to generate qr code barcode with calender entry with barcode sdk with this how to tutorial

These source code samples are assembled by their programming language and functions they apply. ByteScout Premium Suite can generate qr code barcode with calender entry with barcode sdk. It can be applied from C#. ByteScout Premium Suite is the set that includes 12 SDK products from ByteScout including tools and components for PDF, barcodes, spreadsheets, screen video recording.

This prolific sample source code in C# for ByteScout Premium Suite contains various functions and other necessary options you should do calling the API to generate qr code barcode with calender entry with barcode sdk. This C# sample code is all you need for your app. Just copy and paste the code, add references (if needs to) and you are all set! This basic programming language sample code for C# will do the whole work for you to generate qr code barcode with calender entry with barcode sdk.

Our website gives trial version of ByteScout Premium Suite for free. It also includes documentation and source code samples.

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

##### ****Program.cs:**
    
```
using System;
using System.Diagnostics;
using Bytescout.BarCode;

namespace QRCodeWithCalenderEntry
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                // Create new barcode
                using (Barcode barcode = new Barcode())
                {
                    // Set symbology
                    barcode.Symbology = SymbologyType.QRCode;

                    // Get QRCode value in CalenderEntry format
                    barcode.Value = GetCalenderEntryFormatText();

                    // Save barcode to image
                    barcode.SaveImage("result.png");
                }

                // Show image in default image viewer
                Process.Start("result.png");
            }
            catch (Exception ex)
            {
                Console.WriteLine("Error: " + ex.Message);

                Console.WriteLine("Press enter key to exit...");
                Console.ReadLine();
            }

        }

        /// <summary>
        /// Return Calender Entry Format
        /// </summary>
        /// <returns></returns>
        private static string GetCalenderEntryFormatText()
        {
            return @"BEGIN:VCALENDAR
BEGIN:VEVENT
DTSTART:20181113T100000Z
DTEND:20181113T150000Z
SUMMARY:New Calendar Entry
DESCRIPTION:Description Text
LOCATION:Chicago
RRULE:FREQ=YEARLY;BYDAY=-1SU;BYMONTH=3
END:VEVENT
END:VCALENDAR";
        }

    }
}
```

<!-- code block end -->    

<!-- code block begin -->

##### ****QRCodeWithCalenderEntry.csproj:**
    
```
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProjectGuid>{99735776-2956-463D-9795-EBCE16928C30}</ProjectGuid>
    <OutputType>Exe</OutputType>
    <RootNamespace>QRCodeWithCalenderEntry</RootNamespace>
    <AssemblyName>QRCodeWithCalenderEntry</AssemblyName>
    <TargetFrameworkVersion>v2.0</TargetFrameworkVersion>
    <FileAlignment>512</FileAlignment>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <PlatformTarget>AnyCPU</PlatformTarget>
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <Optimize>false</Optimize>
    <OutputPath>bin\Debug\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <PlatformTarget>AnyCPU</PlatformTarget>
    <DebugType>pdbonly</DebugType>
    <Optimize>true</Optimize>
    <OutputPath>bin\Release\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <ItemGroup>
    <Reference Include="Bytescout.BarCode, Version=4.80.0.993, Culture=neutral, PublicKeyToken=f7dd1bd9d40a50eb, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
      <HintPath>c:\Program Files\Bytescout BarCode Reader SDK\net2.00\Bytescout.BarCodeReader.dll</HintPath>
    </Reference>
    <Reference Include="System" />
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Program.cs" />
  </ItemGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

<!-- code block end -->