# EasiNote.Sdk.Documentation
## 运行 EasiNote.Sdk.Demo 项目
1. 下载 EasiNote.Sdk.Demo_X.X.X.zip 文件（其中 X.X.X 为版本号），解压后得到 EasiNote.Sdk 和 EasiNote.Sdk.Demo 两个文件夹。
2. 使用 Visual Studio 2019 或其更高版本打开  EasiNote.Sdk.Demo 文件夹下的 EasiNote.Sdk.Demo.sln 文件。
3. 在 Visual Studio 中新增 Nuget 包源，指定到 EasiNote.Sdk 文件夹（或者将 EasiNote.Sdk 中的 EasiNote.Sdk.*.nupnkg 文件拷贝到现有的包源路径下）。
4. 运行项目。

## 如何使用 EasiNote.Sdk
1. 下载 EasiNote.Sdk.Demo_X.X.X.zip 文件（其中 X.X.X 为版本号），解压后得到 EasiNote.Sdk 和 EasiNote.Sdk.Demo 两个文件夹。
2. 在 Visual Studio 中创建 WPF APP (.NET) 类型的工程，如果现有工程是 WPF APP (.NET Framework) 类型，请参照 [将基于 .NET Framework 的 WPF 项目迁移到基于 .NET Core 3](https://blog.walterlv.com/post/migrate-wpf-project-from-dotnet-framework-to-dotnet-core.html) 把即将引用 SDK 的项目修改为 .NET 类型。 
3. 通过 NuGet 安装 EasiNote.Sdk 下的 EasiNote.Sdk.*.nupnkg 包。
4. 在 XAML 中添加对 EasiNote.Sdk 的引用，并实例化白板组件。
```xaml
<Window x:Class="EasiNote.Sdk.Demo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        .....
        xmlns:sdk="clr-namespace:EasiNote.Sdk;assembly=EasiNote.Sdk"
        ......>
    <Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                ......
                <ResourceDictionary Source="/EasiNote.Sdk;component/Resources.xaml" />
                ......
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Window.Resources>
    <Grid>
        ......
        <sdk:Board x:Name="EasiNoteBoard"/>
        ......
    </Grid>
</Window>
```
5. 可通过 4 中的 EasiNoteBoard 实例来调用相关的 API，详见 EasiNote.Sdk.Demo 项目。
6. 运行项目。
