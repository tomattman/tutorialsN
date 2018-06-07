---
title: MY_2205
description: example
tags: [products>sap-hana, topic>api, tutorial>beginner]
primary_tag: tutorial:product/mobile
---



[ACCORDION-BEGIN [STEP 1](Accordion component which contains Images in Body)]
    
First Header | Second Header | Third Header | Fourth Header | Fifth Header | Sixth Header
------------ | ------------- | ------------ | ------------- | -------------| -------------
Content from cell 1 | Content from cell 2 | Content from cell 3 | Content from cell 4 | Content from cell 5 | Content from cell 6
Content.js in the first column | Content in the second column | Content in the third column | Content in the fourth column | Content in the fifth column.js | Content in the sixth column

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [STEP 1](Accordion component which contains Images in Body)]

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProjectGuid>{99D9BF15-2911-4D10-8079-83ABAD688E8B}</ProjectGuid>
    <OutputType>Exe</OutputType>
    <AppDesignerFolder>Properties</AppDesignerFolder>
    <RootNamespace>csproj_sample</RootNamespace>
    <AssemblyName>csproj-sample</AssemblyName>
    <TargetFrameworkVersion>v4.5.1</TargetFrameworkVersion>
    <FileAlignment>512</FileAlignment>
    <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
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
    <Reference Include="System" />
    <Reference Include="System.Core" />
    <Reference Include="System.Xml.Linq" />
    <Reference Include="System.Data.DataSetExtensions" />
    <Reference Include="Microsoft.CSharp" />
    <Reference Include="System.Data" />
    <Reference Include="System.Xml" />
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Program.cs" />
    <Compile Include="Properties\AssemblyInfo.cs" />
  </ItemGroup>
  <ItemGroup>
    <None Include="App.config" />
  </ItemGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
  <!-- To modify your build process, add your task inside one of the targets below and uncomment it. 
       Other similar extension points exist, see Microsoft.Common.targets.
  <Target Name="BeforeBuild">
  </Target>
  <Target Name="AfterBuild">
  </Target>
  -->
</Project>
```

[DONE]
[ACCORDION-END]
    
[ACCORDION-BEGIN [STEP 12](Accordion component which contains code block and no code block in Body)]

```json
{
     "firstName": "John",
     "lastName" : "Smith",
     "age"      : 25,
     "address"  :
     {
         "streetAddress": "21 2nd Street",
         "city"         : "New York",
         "state"        : "NY",
         "postalCode"   : "10021"
     },
     "phoneNumber":
     [
         {
           "type"  : "home",
           "number": "212 555-1234"
         },
         {
           "type"  : "fax",
           "number": "646 555-4567"
         }
     ]
 }
 {
        "name":"Product",
        "properties":
        {
                "id":
                {
                        "type":"number",
                        "description":"Product identifier",
                        "required":true
                },
                "name":
                {
                        "type":"string",
                        "description":"Name of the product",
                        "required":true
                },
                "price":
                {
                        "type":"number",
                        "minimum":0,
                        "required":true
                },
                "tags":
                {
                        "type":"array",
                        "items":
                        {
                                "type":"string"
                        }
                },
                "stock":
                {
                        "type":"object",
                        "properties":
                        {
                                "warehouse":
                                {
                                        "type":"number"
                                },
                                "retail":
                                {
                                        "type":"number"
                                }
                        }
                }
        }
}
{
        "id": 1,
        "name": "Foo",
        "price": 123,
        "tags": ["Bar","Eek"],
        "stock": { "warehouse":300, "retail":20 }
}
```
[ACCORDION-END]

