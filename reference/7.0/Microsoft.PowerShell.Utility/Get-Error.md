---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: 1a8e278e03d8aea4129c172d786d285d6b55b083
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211843"
---
# <span data-ttu-id="48a1e-103">Get-Error</span><span class="sxs-lookup"><span data-stu-id="48a1e-103">Get-Error</span></span>

## <span data-ttu-id="48a1e-104">概要</span><span class="sxs-lookup"><span data-stu-id="48a1e-104">SYNOPSIS</span></span>

<span data-ttu-id="48a1e-105">現在のセッションからの最新のエラーメッセージを取得して表示します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-105">Gets and displays the most recent error messages from the current session.</span></span>

## <span data-ttu-id="48a1e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48a1e-106">SYNTAX</span></span>

### <span data-ttu-id="48a1e-107">最新 (既定値)</span><span class="sxs-lookup"><span data-stu-id="48a1e-107">Newest (Default)</span></span>

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="48a1e-108">エラー</span><span class="sxs-lookup"><span data-stu-id="48a1e-108">Error</span></span>

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="48a1e-109">Description</span><span class="sxs-lookup"><span data-stu-id="48a1e-109">DESCRIPTION</span></span>

<span data-ttu-id="48a1e-110">`Get-Error`コマンドレットは、セッションで発生した最後のエラーからの現在のエラーの詳細を表す **Psexthe dederror** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-110">The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.</span></span>

<span data-ttu-id="48a1e-111">を使用すると、 `Get-Error` **最新** のパラメーターを使用して、現在のセッションで発生した指定された数のエラーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="48a1e-111">You can use `Get-Error` to display a specified number of errors that have occurred in the current session using the **Newest** parameter.</span></span>

<span data-ttu-id="48a1e-112">また、このコマンドレットは、などの `Get-Error` コレクションからエラーオブジェクトを受け取り `$Error` 、現在のセッションから複数のエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-112">The `Get-Error` cmdlet also receives error objects from a collection, such as `$Error`, to display multiple errors from the current session.</span></span>

## <span data-ttu-id="48a1e-113">例</span><span class="sxs-lookup"><span data-stu-id="48a1e-113">EXAMPLES</span></span>

### <span data-ttu-id="48a1e-114">例 1: 最新のエラーの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="48a1e-114">Example 1: Get the most recent error details</span></span>

<span data-ttu-id="48a1e-115">この例では、は、 `Get-Error` 現在のセッションで発生した最新のエラーの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-115">In this example, `Get-Error` displays the details of the most recent error that occurred in the current session.</span></span>

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### <span data-ttu-id="48a1e-116">例 2: 現在のセッションで発生した、指定された数のエラーメッセージを取得する</span><span class="sxs-lookup"><span data-stu-id="48a1e-116">Example 2: Get the specified number of error messages that occurred in the current session</span></span>

<span data-ttu-id="48a1e-117">この例では、を `Get-Error` **最新** のパラメーターと共に使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-117">This example shows how to use `Get-Error` with the **Newest** parameter.</span></span> <span data-ttu-id="48a1e-118">この例では、[ **最新** ] は、このセッションで発生した3つの最新のエラーの詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-118">In this example, **Newest** returns the details of the 3 newest errors that occurred in this session.</span></span>

```powershell
Get-Error -Newest 3
```

### <span data-ttu-id="48a1e-119">例 3: 詳細なメッセージを受信するためにエラーのコレクションを送信する</span><span class="sxs-lookup"><span data-stu-id="48a1e-119">Example 3: Send a collection of errors to receive detailed messages</span></span>

<span data-ttu-id="48a1e-120">自動変数には、 `$Error` 現在のセッションのエラーオブジェクトの配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48a1e-120">The `$Error` automatic variable contains an array of error objects in the current session.</span></span> <span data-ttu-id="48a1e-121">オブジェクトの配列をにパイプ処理して、 `Get-Error` 詳細なエラーメッセージを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="48a1e-121">The array of objects can be piped to `Get-Error` to receive detailed error messages.</span></span>

<span data-ttu-id="48a1e-122">この例で `$Error` は、はパイプを使用してコマンドレットに渡され `Get-Error` ます。</span><span class="sxs-lookup"><span data-stu-id="48a1e-122">In this example, `$Error` is piped to the `Get-Error` cmdlet.</span></span> <span data-ttu-id="48a1e-123">結果は、例1の結果に似た詳細なエラーメッセージの一覧になります。</span><span class="sxs-lookup"><span data-stu-id="48a1e-123">the result is list of detailed error messages, similar to the result of Example 1.</span></span>

```powershell
$Error | Get-Error
```

## <span data-ttu-id="48a1e-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48a1e-124">PARAMETERS</span></span>

### <span data-ttu-id="48a1e-125">-最新</span><span class="sxs-lookup"><span data-stu-id="48a1e-125">-Newest</span></span>

<span data-ttu-id="48a1e-126">現在のセッションで発生したエラーの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-126">Specifies the number of errors to display that have occurred in the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48a1e-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="48a1e-127">-InputObject</span></span>

<span data-ttu-id="48a1e-128">このパラメーターは、パイプライン入力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="48a1e-128">This parameter is used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="48a1e-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="48a1e-129">CommonParameters</span></span>

<span data-ttu-id="48a1e-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="48a1e-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48a1e-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48a1e-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48a1e-132">入力</span><span class="sxs-lookup"><span data-stu-id="48a1e-132">INPUTS</span></span>

### <span data-ttu-id="48a1e-133">PSObject</span><span class="sxs-lookup"><span data-stu-id="48a1e-133">PSObject</span></span>

<span data-ttu-id="48a1e-134">任意の **PSObject** からの入力をサポートしますが、結果は **Errorrecord** または **Exception** オブジェクトが指定されていない限り異なります。</span><span class="sxs-lookup"><span data-stu-id="48a1e-134">Supports input from any **PSObject** , but results vary unless either an **ErrorRecord** or **Exception** object are supplied.</span></span>

## <span data-ttu-id="48a1e-135">出力</span><span class="sxs-lookup"><span data-stu-id="48a1e-135">OUTPUTS</span></span>

### <span data-ttu-id="48a1e-136">システムの管理. ErrorRecord # Psexの Dederror</span><span class="sxs-lookup"><span data-stu-id="48a1e-136">System.Management.Automation.ErrorRecord#PSExtendedError</span></span>

<span data-ttu-id="48a1e-137">**Psexの Dederror** オブジェクトに出力します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-137">Output in a **PSExtendedError** object.</span></span>

## <span data-ttu-id="48a1e-138">注</span><span class="sxs-lookup"><span data-stu-id="48a1e-138">NOTES</span></span>

<span data-ttu-id="48a1e-139">`Get-Error` パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="48a1e-139">`Get-Error` accepts pipeline input.</span></span> <span data-ttu-id="48a1e-140">たとえば、「 `$Error | Get-Error` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="48a1e-140">For example, `$Error | Get-Error`.</span></span>

## <span data-ttu-id="48a1e-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="48a1e-141">RELATED LINKS</span></span>

[<span data-ttu-id="48a1e-142">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="48a1e-142">about_Try_Catch_Finally</span></span>](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
