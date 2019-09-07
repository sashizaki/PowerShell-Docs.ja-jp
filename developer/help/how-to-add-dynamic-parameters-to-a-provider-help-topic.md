---
title: プロバイダーに動的パラメーターを追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: cc4877242a16a9caa99564aeaae985f85e38791e
ms.sourcegitcommit: ffcc1c55f5b3adc063353cb75f2a2183acc2234a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70737596"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="65f25-102">プロバイダーのヘルプ トピックに動的パラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="65f25-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="65f25-103">このセクションでは、プロバイダーヘルプトピックの**動的パラメーター**セクションにデータを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65f25-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="65f25-104">*動的パラメーター*とは、指定された条件下でのみ使用可能なコマンドレットまたは関数のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="65f25-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="65f25-105">プロバイダーのヘルプトピックに記載されている動的パラメーターは、プロバイダーのドライブでコマンドレットまたは関数が使用されている場合に、プロバイダーがコマンドレットまたは関数に追加する動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="65f25-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="65f25-106">動的パラメーターは、プロバイダーのカスタムコマンドレットのヘルプにも記載されています。</span><span class="sxs-lookup"><span data-stu-id="65f25-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="65f25-107">プロバイダーのヘルプとカスタムコマンドレットのヘルプの両方を作成するときは、両方のドキュメントに動的パラメーターのドキュメントを含めてください。</span><span class="sxs-lookup"><span data-stu-id="65f25-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span> <span data-ttu-id="65f25-108">カスタムコマンドレットのヘルプの詳細については、「[プロバイダーの Windows PowerShell カスタムコマンドレットヘルプの記述](./writing-custom-cmdlet-help-for-windows-powershell-providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65f25-108">For more information about custom cmdlet help, see [Writing Windows PowerShell Custom Cmdlet Help for Providers](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).</span></span>

<span data-ttu-id="65f25-109">プロバイダーが動的パラメーターを実装していない場合、プロバイダーヘルプトピックには`DynamicParameters`空の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="65f25-109">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="65f25-110">動的パラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="65f25-110">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="65f25-111">Dll-help `providerHelp`ファイル*の要素*内に、要素を`DynamicParameters`追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-111">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="65f25-112">要素は、要素の`Tasks`後、 `RelatedLinks`要素の前に記述する必要があります。 `DynamicParameters`</span><span class="sxs-lookup"><span data-stu-id="65f25-112">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="65f25-113">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="65f25-113">For example:</span></span>

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

   <span data-ttu-id="65f25-114">プロバイダーが動的パラメーターを`DynamicParameters`実装していない場合は、要素を空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="65f25-114">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

2. <span data-ttu-id="65f25-115">要素内で、各動的パラメーターに要素を`DynamicParameter`追加します。 `DynamicParameters`</span><span class="sxs-lookup"><span data-stu-id="65f25-115">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="65f25-116">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="65f25-116">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. <span data-ttu-id="65f25-117">各`DynamicParameter`要素に、要素`Name`と`CmdletSupported`要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-117">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   |<span data-ttu-id="65f25-118">要素名</span><span class="sxs-lookup"><span data-stu-id="65f25-118">Element Name</span></span>|<span data-ttu-id="65f25-119">説明</span><span class="sxs-lookup"><span data-stu-id="65f25-119">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="65f25-120">名前</span><span class="sxs-lookup"><span data-stu-id="65f25-120">Name</span></span>|<span data-ttu-id="65f25-121">パラメーター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="65f25-121">Specifies the parameter name.</span></span>|
   |<span data-ttu-id="65f25-122">サポートされているもの</span><span class="sxs-lookup"><span data-stu-id="65f25-122">CmdletSupported</span></span>|<span data-ttu-id="65f25-123">パラメーターが有効なコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="65f25-123">Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="65f25-124">コマンドレット名のコンマ区切りリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="65f25-124">Type a comma-separated list of cmdlet names.</span></span>|

   <span data-ttu-id="65f25-125">たとえば、次の XML `Encoding`ドキュメントでは、Windows PowerShell FileSystem プロバイダー `Add-Content`によって、 `Get-Content` `Set-Content` 、コマンドレットに追加される動的パラメーターについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="65f25-125">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. <span data-ttu-id="65f25-126">各`DynamicParameter`要素に要素を`Type`追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-126">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="65f25-127">要素は、動的パラメーターの値`Name`の .net 型を含む要素のコンテナーです。 `Type`</span><span class="sxs-lookup"><span data-stu-id="65f25-127">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="65f25-128">たとえば、次の XML は、 `Encoding`動的パラメーターの .net 型が、 [Microsoft. PowerShell. filesystemコマンドレット](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding)の列挙体であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="65f25-128">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

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

5. <span data-ttu-id="65f25-129">`Description`要素を追加します。これには、動的パラメーターの簡単な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65f25-129">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="65f25-130">説明を作成する場合は、「[パラメーター情報を追加する方法](./how-to-add-parameter-information.md)」のすべてのコマンドレットパラメーターに指定されているガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="65f25-130">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="65f25-131">たとえば、次の XML には、 `Encoding`動的パラメーターの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65f25-131">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

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

6. <span data-ttu-id="65f25-132">`PossibleValues`要素とその子要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-132">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="65f25-133">これらの要素には、動的パラメーターの値が記述されています。</span><span class="sxs-lookup"><span data-stu-id="65f25-133">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="65f25-134">この要素は、列挙値用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="65f25-134">This element is designed for enumerated values.</span></span> <span data-ttu-id="65f25-135">スイッチパラメーターを使用した場合など、動的パラメーターに値がない場合、または値を列挙できない場合は、空`PossibleValues`の要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-135">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="65f25-136">次の表に、要素と`PossibleValues`その子要素の一覧とその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="65f25-136">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   |<span data-ttu-id="65f25-137">要素名</span><span class="sxs-lookup"><span data-stu-id="65f25-137">Element Name</span></span>|<span data-ttu-id="65f25-138">説明</span><span class="sxs-lookup"><span data-stu-id="65f25-138">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="65f25-139">指定した値</span><span class="sxs-lookup"><span data-stu-id="65f25-139">PossibleValues</span></span>|<span data-ttu-id="65f25-140">この要素はコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="65f25-140">This element is a container.</span></span> <span data-ttu-id="65f25-141">その子要素について以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="65f25-141">Its child elements are described below.</span></span> <span data-ttu-id="65f25-142">各プロバイダー `PossibleValues`ヘルプトピックに1つの要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-142">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="65f25-143">要素は空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="65f25-143">The element can be empty.</span></span>|
   |<span data-ttu-id="65f25-144">指定した値</span><span class="sxs-lookup"><span data-stu-id="65f25-144">PossibleValue</span></span>|<span data-ttu-id="65f25-145">この要素はコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="65f25-145">This element is a container.</span></span> <span data-ttu-id="65f25-146">その子要素について以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="65f25-146">Its child elements are described below.</span></span> <span data-ttu-id="65f25-147">動的パラメーター `PossibleValue`の値ごとに1つの要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="65f25-147">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>|
   |<span data-ttu-id="65f25-148">値</span><span class="sxs-lookup"><span data-stu-id="65f25-148">Value</span></span>|<span data-ttu-id="65f25-149">値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="65f25-149">Specifies the value name.</span></span>|
   |<span data-ttu-id="65f25-150">説明</span><span class="sxs-lookup"><span data-stu-id="65f25-150">Description</span></span>|<span data-ttu-id="65f25-151">この要素には`Para`要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65f25-151">This element contains a `Para` element.</span></span> <span data-ttu-id="65f25-152">`Para`要素内のテキストは、 `Value`要素で指定されている値を表します。</span><span class="sxs-lookup"><span data-stu-id="65f25-152">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>|

   <span data-ttu-id="65f25-153">たとえば、次の XML は、 `PossibleValue` `Encoding`動的パラメーターの1つの要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="65f25-153">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

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

## <a name="example"></a><span data-ttu-id="65f25-154">例</span><span class="sxs-lookup"><span data-stu-id="65f25-154">Example</span></span>

<span data-ttu-id="65f25-155">次の例は、 `DynamicParameters` `Encoding`動的パラメーターの要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="65f25-155">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

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