---
title: プロバイダーのヘルプ トピックに動的パラメーターを追加する方法
ms.date: 09/13/2016
ms.openlocfilehash: ddf964292ee7bf477767a2ca17c717aef84bad51
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893460"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="67aba-102">プロバイダーのヘルプ トピックに動的パラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="67aba-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="67aba-103">このセクションでは、プロバイダーヘルプトピックの**動的パラメーター**セクションにデータを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67aba-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="67aba-104">*動的パラメーター*とは、指定された条件下でのみ使用可能なコマンドレットまたは関数のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="67aba-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="67aba-105">プロバイダーのヘルプトピックに記載されている動的パラメーターは、プロバイダーのドライブでコマンドレットまたは関数が使用されている場合に、プロバイダーがコマンドレットまたは関数に追加する動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="67aba-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="67aba-106">動的パラメーターは、プロバイダーのカスタムコマンドレットのヘルプにも記載されています。</span><span class="sxs-lookup"><span data-stu-id="67aba-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="67aba-107">プロバイダーのヘルプとカスタムコマンドレットのヘルプの両方を作成するときは、両方のドキュメントに動的パラメーターのドキュメントを含めてください。</span><span class="sxs-lookup"><span data-stu-id="67aba-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span>

<span data-ttu-id="67aba-108">プロバイダーが動的パラメーターを実装していない場合、プロバイダーヘルプトピックには空の要素が含まれ `DynamicParameters` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-108">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="67aba-109">動的パラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="67aba-109">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="67aba-110">ファイルの `<AssemblyName>.dll-help.xml` 要素内に `providerHelp` 要素を追加 `DynamicParameters` します。</span><span class="sxs-lookup"><span data-stu-id="67aba-110">In the `<AssemblyName>.dll-help.xml` file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="67aba-111">要素は、要素の `DynamicParameters` 後、要素の前に記述する必要があり `Tasks` `RelatedLinks` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-111">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="67aba-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="67aba-112">For example:</span></span>

    ```xml
    <providerHelp>
        <Tasks>
        </Tasks>
        <DynamicParameters>
        </DynamicParameters>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

   <span data-ttu-id="67aba-113">プロバイダーが動的パラメーターを実装していない場合は、 `DynamicParameters` 要素を空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="67aba-113">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

1. <span data-ttu-id="67aba-114">要素内で `DynamicParameters` 、各動的パラメーターに要素を追加し `DynamicParameter` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-114">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="67aba-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="67aba-115">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

1. <span data-ttu-id="67aba-116">各要素に、 `DynamicParameter` `Name` 要素と要素を追加し `CmdletSupported` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-116">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   - <span data-ttu-id="67aba-117">名前-パラメーター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="67aba-117">Name - Specifies the parameter name</span></span>
   - <span data-ttu-id="67aba-118">コマンドレットサポート-パラメーターが有効なコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="67aba-118">CmdletSupported - Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="67aba-119">コマンドレット名のコンマ区切りリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="67aba-119">Type a comma-separated list of cmdlet names.</span></span>

   <span data-ttu-id="67aba-120">たとえば、次の XML ドキュメントでは、 `Encoding` Windows PowerShell FileSystem プロバイダーによって、、コマンドレットに追加される動的パラメーターについて説明して `Add-Content` `Get-Content` `Set-Content` います。</span><span class="sxs-lookup"><span data-stu-id="67aba-120">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

1. <span data-ttu-id="67aba-121">各 `DynamicParameter` 要素に要素を追加 `Type` します。</span><span class="sxs-lookup"><span data-stu-id="67aba-121">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="67aba-122">要素は、 `Type` `Name` 動的パラメーターの値の .net 型を含む要素のコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="67aba-122">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="67aba-123">たとえば、次の XML は、動的パラメーターの .NET 型 `Encoding` が[Filesystemcmdletproviderencoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding)列挙体であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="67aba-123">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
    ...
    </DynamicParameters>
    ```

1. <span data-ttu-id="67aba-124">`Description`要素を追加します。これには、動的パラメーターの簡単な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67aba-124">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="67aba-125">説明を作成する場合は、「[パラメーター情報を追加する方法](./how-to-add-parameter-information.md)」のすべてのコマンドレットパラメーターに指定されているガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="67aba-125">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="67aba-126">たとえば、次の XML には、動的パラメーターの説明が含まれてい `Encoding` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-126">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
            <Description> Specifies the encoding of the output file that contains the content. </Description>
    ...
    </DynamicParameters>
    ```

1. <span data-ttu-id="67aba-127">`PossibleValues`要素とその子要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="67aba-127">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="67aba-128">これらの要素には、動的パラメーターの値が記述されています。</span><span class="sxs-lookup"><span data-stu-id="67aba-128">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="67aba-129">この要素は、列挙値用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="67aba-129">This element is designed for enumerated values.</span></span> <span data-ttu-id="67aba-130">スイッチパラメーターを使用した場合など、動的パラメーターに値がない場合、または値を列挙できない場合は、空の要素を追加し `PossibleValues` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-130">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="67aba-131">次の表に、 `PossibleValues` 要素とその子要素の一覧とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="67aba-131">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   - <span data-ttu-id="67aba-132">指定された値-この要素はコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="67aba-132">PossibleValues - This element is a container.</span></span> <span data-ttu-id="67aba-133">その子要素について以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="67aba-133">Its child elements are described below.</span></span> <span data-ttu-id="67aba-134">`PossibleValues`各プロバイダーヘルプトピックに1つの要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="67aba-134">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="67aba-135">要素は空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="67aba-135">The element can be empty.</span></span>
   - <span data-ttu-id="67aba-136">指定された値-この要素はコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="67aba-136">PossibleValue - This element is a container.</span></span> <span data-ttu-id="67aba-137">その子要素について以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="67aba-137">Its child elements are described below.</span></span> <span data-ttu-id="67aba-138">`PossibleValue`動的パラメーターの値ごとに1つの要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="67aba-138">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>
   - <span data-ttu-id="67aba-139">値-値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="67aba-139">Value - Specifies the value name.</span></span>
   - <span data-ttu-id="67aba-140">説明-この要素には要素が含まれてい `Para` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-140">Description - This element contains a `Para` element.</span></span> <span data-ttu-id="67aba-141">要素内のテキストは、 `Para` 要素で指定されている値を表し `Value` ます。</span><span class="sxs-lookup"><span data-stu-id="67aba-141">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>

   <span data-ttu-id="67aba-142">たとえば、次の XML は、 `PossibleValue` 動的パラメーターの1つの要素を示して `Encoding` います。</span><span class="sxs-lookup"><span data-stu-id="67aba-142">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
    ...
            <Description> Specifies the encoding of the output file that contains the content. </Description>
            <PossibleValues>
                <PossibleValue>
                    <Value> ASCII </Value>
                    <Description>
                        <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                    </Description>
                </PossibleValue>
    ...
            </PossibleValues>
    </DynamicParameters>
    ```

## <a name="example"></a><span data-ttu-id="67aba-143">例</span><span class="sxs-lookup"><span data-stu-id="67aba-143">Example</span></span>

<span data-ttu-id="67aba-144">次の例は、 `DynamicParameters` 動的パラメーターの要素を示して `Encoding` います。</span><span class="sxs-lookup"><span data-stu-id="67aba-144">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

```xml
<DynamicParameters/>
    <DynamicParameter>
        <Name> Encoding </Name>
        <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
        <Type>
            <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
        <Type>
        <Description> Specifies the encoding of the output file that contains the content. </Description>
        <PossibleValues>
            <PossibleValue>
                <Value> ASCII </Value>
                <Description>
                    <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                </Description>
            </PossibleValue>
            <PossibleValue>
                <Value> Unicode </Value>
                <Description>
                    <para> Encodes in UTF-16 format using the little-endian byte order. </para>
                </Description>
            </PossibleValue>
        </PossibleValues>
</DynamicParameters>
```
