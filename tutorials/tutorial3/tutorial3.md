---
title: UnicTutorial5_09072018
description: example
tags: [products>sap-hana, topic>api, tutorial>beginner]
primary_tag: tutorial:product/mobile
---
### Time to Complete
13 min


[ACCORDION-BEGIN [STEP 1](Accordion component which contains Images in Body)]
    
First Header | Second Header | Third Header | Fourth Header | Fifth Header | Sixth Header
------------ | ------------- | ------------ | ------------- | -------------| -------------
Content from cell 1 | Content from cell 2 | Content from cell 3 | Content from cell 4 | Content from cell 5 | Content from cell 6
Content.js in the first column | Content in the second column | Content in the third column | Content in the fourth column | Content in the fifth column.js | Content in the sixth column

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [STEP 2](Accordion component which contains Images in Body)]

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
    
[ACCORDION-BEGIN [Step 3: ](Add custom code)]

1. Open the new `OrdersService.java` file and replace the template with the following code:

    ```java
    package my.bookshop;

    import java.util.ArrayList;
    import java.util.List;

    import com.sap.cloud.sdk.service.prov.api.*;
    import com.sap.cloud.sdk.service.prov.api.annotations.*;
    import com.sap.cloud.sdk.service.prov.api.exits.*;
    import com.sap.cloud.sdk.service.prov.api.request.*;
    import com.sap.cloud.sdk.service.prov.api.response.*;
    import org.slf4j.*;

    public class OrdersService {

      private static final Logger LOG = LoggerFactory.getLogger (OrdersService.class.getName());

      @BeforeRead (entity="Orders", serviceName="CatalogService")
      public BeforeReadResponse beforeReadOrders (ReadRequest req, ExtensionHelper h){
        LOG.error ("##### Orders - beforeReadOrders ########");
        return BeforeReadResponse.setSuccess().response();
      }

      @AfterRead (entity = "Orders", serviceName="CatalogService")
      public ReadResponse afterReadOrders (ReadRequest req, ReadResponseAccessor res, ExtensionHelper h) {
        EntityData ed = res.getEntityData();
        EntityData ex = EntityData.getBuilder(ed).addElement("amount", 1000).buildEntityData("Orders");
        return ReadResponse.setSuccess().setData(ex).response();
      }

      @AfterQuery (entity = "Orders", serviceName="CatalogService")
      public QueryResponse afterQueryOrders (QueryRequest req, QueryResponseAccessor res, ExtensionHelper h) {
        List<EntityData> dataList = res.getEntityDataList(); //original list
        List<EntityData> modifiedList = new ArrayList<EntityData>(dataList.size()); //modified list
        for(EntityData ed : dataList){
    		  EntityData ex = EntityData.getBuilder(ed).addElement("amount", 1000).buildEntityData("Orders");
    		  modifiedList.add(ex);
    	  }
        return QueryResponse.setSuccess().setData(modifiedList).response();
      }
    }  
    ```

1. Save your changes.

    >In this sample code, we set a value of 1000 for the property amount of each returned entity in reading operations.

[DONE]

[ACCORDION-END]
