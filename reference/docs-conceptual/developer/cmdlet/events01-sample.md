---
ms.date: 09/13/2016
ms.topic: reference
title: Events01 サンプル
description: Events01 サンプル
ms.openlocfilehash: ed8b7903537504609602e27693351847d322f904
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390407"
---
# <a name="events01-sample"></a><span data-ttu-id="1d3ce-103">Events01 サンプル</span><span class="sxs-lookup"><span data-stu-id="1d3ce-103">Events01 Sample</span></span>

<span data-ttu-id="1d3ce-104">このサンプルでは、ユーザーが、system.object [によって発生した](/dotnet/api/System.IO.FileSystemWatcher)イベントに登録できるようにするコマンドレットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-104">This sample shows how to create a cmdlet that allows the user to register for events that are raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="1d3ce-105">このコマンドレットを使用すると、ユーザーは、特定のディレクトリにファイルが作成されたときに実行するアクションを登録できます。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-105">With this cmdlet, users can register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="1d3ce-106">このサンプルは、 [ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-106">This sample derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="1d3ce-107">Visual Studio を使用してサンプルをビルドする方法。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-107">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="1d3ce-108">Windows PowerShell 2.0 SDK がインストールされている状態で、Events01 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-108">With the Windows PowerShell 2.0 SDK installed, navigate to the Events01 folder.</span></span> <span data-ttu-id="1d3ce-109">既定の場所は `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01` です。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-109">The default location is `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`.</span></span>

2. <span data-ttu-id="1d3ce-110">ソリューション (.sln) ファイルのアイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="1d3ce-111">これにより、Microsoft Visual Studio でサンプルプロジェクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-111">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="1d3ce-112">**[ビルド]** メニューで、 **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-112">In the **Build** menu, select **Build Solution**.</span></span> <span data-ttu-id="1d3ce-113">サンプルのライブラリは、既定の `\bin` フォルダーまたはフォルダーに組み込まれ `\bin\debug` ます。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-113">The library for the sample will be built in the default `\bin` or `\bin\debug` folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="1d3ce-114">サンプルを実行する方法</span><span class="sxs-lookup"><span data-stu-id="1d3ce-114">How to run the sample</span></span>

1. <span data-ttu-id="1d3ce-115">次のモジュールフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/events01`

2. <span data-ttu-id="1d3ce-116">サンプルのライブラリファイルをモジュールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-116">Copy the library file for the sample to the module folder.</span></span>

3. <span data-ttu-id="1d3ce-117">Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="1d3ce-118">次のコマンドを実行して、Windows PowerShell にコマンドレットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-118">Run the following command to load the cmdlet into Windows PowerShell:</span></span>

    ```powershell
    import-module events01
    ```

5. <span data-ttu-id="1d3ce-119">Register-FileSystemEvent コマンドレットを使用して、一時ディレクトリにファイルが作成されたときにメッセージを書き込むアクションを登録します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-119">Use the Register-FileSystemEvent cmdlet to register an action that will write a message when a file is created under the TEMP directory.</span></span>

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. <span data-ttu-id="1d3ce-120">TEMP ディレクトリの下にファイルを作成し、アクションが実行されることを確認します (メッセージが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-120">Create a file under the TEMP directory and note that the action is executed (the message is displayed).</span></span>

<span data-ttu-id="1d3ce-121">これは、次の手順に従って生成される出力サンプルです。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-121">This is a sample output that results by following these steps.</span></span>

```output
Id              Name            State      HasMoreData     Location             Command
--              ----            -----      -----------     --------             -------
1               26932870-d3b... NotStarted False                                 Write-Host "A f...

```

```powershell
Set-Content $env:temp\test.txt "This is a test file"
```

```output
A file was created in the TEMP directory
```

## <a name="requirements"></a><span data-ttu-id="1d3ce-122">要件</span><span class="sxs-lookup"><span data-stu-id="1d3ce-122">Requirements</span></span>

<span data-ttu-id="1d3ce-123">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-123">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1d3ce-124">対象</span><span class="sxs-lookup"><span data-stu-id="1d3ce-124">Demonstrates</span></span>

<span data-ttu-id="1d3ce-125">このサンプルでは、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-125">This sample demonstrates the following.</span></span>

### <a name="how-to-write-a-cmdlet-for-event-registration"></a><span data-ttu-id="1d3ce-126">イベント登録用のコマンドレットを記述する方法</span><span class="sxs-lookup"><span data-stu-id="1d3ce-126">How to write a cmdlet for event registration</span></span>

<span data-ttu-id="1d3ce-127">コマンドレットは、コマンドレットに共通のパラメーターをサポートする[ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)クラスから派生します。 `Register-*Event`</span><span class="sxs-lookup"><span data-stu-id="1d3ce-127">The cmdlet derives from the [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) class, which provides support for parameters common to the `Register-*Event` cmdlets.</span></span> <span data-ttu-id="1d3ce-128">[ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)から派生したコマンドレットでは、特定のパラメーターを定義し、 `GetSourceObject` および抽象メソッドをオーバーライドするだけで済みます。 `GetSourceObjectEventName`</span><span class="sxs-lookup"><span data-stu-id="1d3ce-128">Cmdlets that are derived from [Microsoft.PowerShell.Commands.ObjectEventRegistrationBase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) need only to define their particular parameters and override the `GetSourceObject` and `GetSourceObjectEventName` abstract methods.</span></span>

## <a name="example"></a><span data-ttu-id="1d3ce-129">例</span><span class="sxs-lookup"><span data-stu-id="1d3ce-129">Example</span></span>

<span data-ttu-id="1d3ce-130">このサンプルでは、system.object [によって](/dotnet/api/System.IO.FileSystemWatcher)生成されるイベントに登録する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d3ce-130">This sample shows how to register for events raised by [System.IO.FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span>

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="1d3ce-131">参照</span><span class="sxs-lookup"><span data-stu-id="1d3ce-131">See Also</span></span>

[<span data-ttu-id="1d3ce-132">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="1d3ce-132">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
