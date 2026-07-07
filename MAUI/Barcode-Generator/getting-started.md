---
layout: post
title: Getting Started with .NET MAUI Barcode Generator control | Syncfusion
description: Learn here all about getting started with Syncfusion<sup>&reg;</sup> .NET MAUI Barcode Generator(SfBarcodeGenerator) control and more.
platform: maui
control: SfBarcodeGenerator
documentation: ug
---

# Getting Started with .NET MAUI Barcode Generator

This section explains the steps required to add the [`.NET MAUI Barcode Generator`](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Barcode.html) control, set its symbology, and covers only the basic features needed to get started with the Syncfusion<sup>&reg;</sup> Barcode Generator control. Follow the steps below to add a .NET MAUI Barcode Generator to your project.

To get started quickly with our .NET MAUI Barcode Generator, you can check the video below.

{% youtube
"youtube:https://www.youtube.com/watch?v=WwdtIotODpE"%}

{% tabcontents %}
{% tabcontent Visual Studio %}

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install [.NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0) or later.
2. Set up a .NET MAUI environment with Visual Studio 2022 v17.12 or later.
3. Ensure that the .NET MAUI workloads are installed and configured as described [here](https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-9.0&tabs=visual-studio).

## Step 1: Create a new .NET MAUI project

1. Go to **File > New > Project** and choose the **.NET MAUI App** template.
2. Name the project and choose a location. Then click **Next**.
3. Select the .NET framework version and click **Create**.

## Step 2: Install the Syncfusion<sup>&reg;</sup> MAUI Barcode NuGet package

1. In **Solution Explorer,** right-click the project and choose **Manage NuGet Packages.**
2. Search for [Syncfusion.Maui.Barcode](https://www.nuget.org/packages/Syncfusion.Maui.Barcode/) and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored.

{% endtabcontent %}
{% tabcontent Visual Studio Code %}

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install [.NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0) or later.
2. Set up a .NET MAUI environment with Visual Studio Code.
3. Ensure that the .NET MAUI workloads are installed and configured as described [here](https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-9.0&tabs=visual-studio-code).

## Step 1: Create a new .NET MAUI project

1. Open the command palette by pressing `Ctrl+Shift+P`, type **.NET: New Project**, and press **Enter**.
2. Choose the **.NET MAUI App** template.
3. Select the project location, type the project name and press **Enter**.
4. Then choose **Create project**.

## Step 2: Install the Syncfusion<sup>&reg;</sup> MAUI Barcode NuGet package

1. Press <kbd>Ctrl</kbd> + <kbd>`</kbd> (backtick) to open the integrated terminal in Visual Studio Code.
2. Ensure you're in the project root directory where your .csproj file is located.
3. Run the command `dotnet add package Syncfusion.Maui.Barcode` to install the Syncfusion<sup>&reg;</sup> .NET MAUI Barcode NuGet package.
4. To ensure all dependencies are installed, run `dotnet restore`.

{% endtabcontent %}
{% tabcontent JetBrains Rider %}

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install [.NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0) or later.
2. Set up a .NET MAUI environment with JetBrains Rider 2024.3 or later.
3. Make sure the MAUI workloads are installed and configured as described [here.](https://www.jetbrains.com/help/rider/MAUI.html#before-you-start)

## Step 1: Create a new .NET MAUI project

1. Go to **File > New Solution,** select **.NET (C#)** and choose the .NET MAUI App template.
2. Enter the Project Name, Solution Name, and Location.
3. Select the .NET framework version and click Create.

## Step 2: Install the Syncfusion<sup>&reg;</sup> MAUI Barcode NuGet package

1. In **Solution Explorer,** right-click the project and choose **Manage NuGet Packages.**
2. Search for [Syncfusion.Maui.Barcode](https://www.nuget.org/packages/Syncfusion.Maui.Barcode/) and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored. If not, open the Terminal in Rider and manually run: `dotnet restore`

{% endtabcontent %}
{% endtabcontents %}

## Step 3: Register the Syncfusion handler
 
To use Syncfusion controls, register the Syncfusion core handler in the `CreateMauiApp` method of `MauiProgram.cs`. Add the following namespace at the top of `MauiProgram.cs`:
 
{% tabs %}
{% highlight c# %}
using Syncfusion.Maui.Core.Hosting;
{% endhighlight %}
{% endtabs %}
 
Then, call `ConfigureSyncfusionCore()` on the `builder` to register the handlers required for Syncfusion controls to render:
 
{% tabs %}
{% highlight c# %}
public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        builder
            .UseMauiApp<App>()
            .ConfigureSyncfusionCore();

        return builder.Build();
    }
}
{% endhighlight %}
{% endtabs %}

## Step 4: Import the Barcode Generator namespace

Add the following namespace in your XAML or C#.

{% tabs %}
{% highlight xaml %}
xmlns:barcode="clr-namespace:Syncfusion.Maui.Barcode;assembly=Syncfusion.Maui.Barcode"
{% endhighlight %}
{% highlight c# %}
using Syncfusion.Maui.Barcode;
{% endhighlight %}
{% endtabs %}

## Step 5: Add the Barcode Generator component 

Create an instance of the Barcode Generator control, set a `Value`, and add it as content. The following C# snippet is intended for a `ContentPage` code-behind file.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:barcode="clr-namespace:Syncfusion.Maui.Barcode;assembly=Syncfusion.Maui.Barcode"
             x:Class="BarcodeApp.MainPage">
    <barcode:SfBarcodeGenerator Value="12634388927"
                                HeightRequest="150" />
</ContentPage>

{% endhighlight %}

{% highlight c# %}

SfBarcodeGenerator barcode = new SfBarcodeGenerator();
barcode.Value = "12634388927";
barcode.HeightRequest = 150;
this.Content = barcode;

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates the result of the above code.

![.NET MAUI Barcode Generator Initialize Barcode](images/getting-started/maui-intialize-barcode.png)

N> The default symbology of `SfBarcodeGenerator` is [`Code128`](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Barcode.Code128.html). To render other symbologies such as `QRCode`, `DataMatrix`, or `Codabar`, set the `Symbology` property. See the [Customization](customization.md) topic for details.

You can download the Barcode Generator Getting Started sample from [GitHub](https://github.com/SyncfusionExamples/getting-started-with-the-dotnet-maui-barcode-generator).

## See also

- [Customization in .NET MAUI Barcode Generator](customization.md)
- [.NET MAUI Barcode Generator feature tour](https://www.syncfusion.com/maui-controls/maui-barcodes)
- [.NET MAUI Barcode Generator example](https://github.com/syncfusion/maui-demos/tree/master/MAUI/Barcode)
