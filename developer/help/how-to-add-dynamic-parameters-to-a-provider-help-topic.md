---
title: プロバイダーのヘルプ トピックに動的パラメーターを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: cc4877242a16a9caa99564aeaae985f85e38791e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859878"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="c1e73-102">プロバイダーのヘルプ トピックに動的パラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="c1e73-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="c1e73-103">このセクションを設定する方法を説明します、**動的パラメーター**プロバイダーのヘルプ トピックの「します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="c1e73-104">*動的パラメーター*コマンドレットのパラメーターまたは指定された条件の下にのみ利用できる関数です。</span><span class="sxs-lookup"><span data-stu-id="c1e73-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="c1e73-105">プロバイダーのヘルプ トピックで説明されている動的パラメーターは、コマンドレットまたは関数を使用して、プロバイダー ドライブでコマンドレットまたは関数にプロバイダーを追加する動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c1e73-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="c1e73-106">動的パラメーターは、プロバイダーのカスタム コマンドレット ヘルプにも記載されていることができます。</span><span class="sxs-lookup"><span data-stu-id="c1e73-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="c1e73-107">プロバイダーのヘルプとカスタム コマンドレット ヘルプの両方のプロバイダーを記述する場合は、ドキュメントの両方で動的パラメーターのドキュメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1e73-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span> <span data-ttu-id="c1e73-108">カスタム コマンドレット ヘルプの詳細については、[書き込み Windows PowerShell のカスタム コマンドレット ヘルプのプロバイダー](./writing-custom-cmdlet-help-for-windows-powershell-providers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1e73-108">For more information about custom cmdlet help, see [Writing Windows PowerShell Custom Cmdlet Help for Providers](./writing-custom-cmdlet-help-for-windows-powershell-providers.md).</span></span>

<span data-ttu-id="c1e73-109">プロバイダーのヘルプ トピックにはプロバイダーが動的パラメーターを実装していない場合、空が含まれています`DynamicParameters`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-109">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="c1e73-110">動的パラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="c1e73-110">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="c1e73-111">*AssemblyName*.dll help.xml ファイル内で、`providerHelp`要素を追加、`DynamicParameters`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-111">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="c1e73-112">`DynamicParameters`後に要素が表示されます、`Tasks`要素とする前に、`RelatedLinks`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-112">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="c1e73-113">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-113">For example:</span></span>

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

   <span data-ttu-id="c1e73-114">プロバイダーは、動的パラメーターを実装していない場合、`DynamicParameters`要素を空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c1e73-114">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

2. <span data-ttu-id="c1e73-115">内で、`DynamicParameters`要素、各動的パラメーターの追加、`DynamicParameter`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-115">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="c1e73-116">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-116">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. <span data-ttu-id="c1e73-117">各`DynamicParameter`要素を追加、`Name`と`CmdletSupported`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-117">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   |<span data-ttu-id="c1e73-118">要素名</span><span class="sxs-lookup"><span data-stu-id="c1e73-118">Element Name</span></span>|<span data-ttu-id="c1e73-119">説明</span><span class="sxs-lookup"><span data-stu-id="c1e73-119">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="c1e73-120">名前</span><span class="sxs-lookup"><span data-stu-id="c1e73-120">Name</span></span>|<span data-ttu-id="c1e73-121">パラメーター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-121">Specifies the parameter name.</span></span>|
   |<span data-ttu-id="c1e73-122">CmdletSupported</span><span class="sxs-lookup"><span data-stu-id="c1e73-122">CmdletSupported</span></span>|<span data-ttu-id="c1e73-123">パラメーターの有効なコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-123">Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="c1e73-124">コマンドレット名のコンマ区切りの一覧を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-124">Type a comma-separated list of cmdlet names.</span></span>|

   <span data-ttu-id="c1e73-125">次の XML ドキュメントなど、`Encoding`に、Windows PowerShell FileSystem プロバイダーを追加する動的パラメーター、 `Add-Content`、 `Get-Content`、`Set-Content`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="c1e73-125">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. <span data-ttu-id="c1e73-126">各`DynamicParameter`要素を追加、`Type`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-126">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="c1e73-127">`Type`要素は、コンテナー、`Name`動的パラメーターの値の .NET 型を含む要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-127">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="c1e73-128">たとえば、次の XML を .NET の種類を表示、`Encoding`動的パラメーターとは、 [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding)列挙体。</span><span class="sxs-lookup"><span data-stu-id="c1e73-128">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

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

5. <span data-ttu-id="c1e73-129">追加、`Description`要素で、動的パラメーターの簡単な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1e73-129">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="c1e73-130">説明を作成するときは、すべてのコマンドレット パラメーターで規定されているガイドラインを使用して[パラメーター情報を追加する方法](./how-to-add-parameter-information.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-130">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="c1e73-131">たとえば、次の XML には、説明が含まれます。、`Encoding`動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c1e73-131">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

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

6. <span data-ttu-id="c1e73-132">追加、`PossibleValues`要素とその子要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-132">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="c1e73-133">同時に、これらの要素には、動的パラメーターの値について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-133">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="c1e73-134">この要素は、列挙値に適しています。</span><span class="sxs-lookup"><span data-stu-id="c1e73-134">This element is designed for enumerated values.</span></span> <span data-ttu-id="c1e73-135">など、スイッチ パラメーターの場合は、または値を列挙することはできません、空を追加する動的パラメーターが値を受け取らない場合`PossibleValues`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-135">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="c1e73-136">次の表を示し、`PossibleValues`要素とその子要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-136">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   |<span data-ttu-id="c1e73-137">要素名</span><span class="sxs-lookup"><span data-stu-id="c1e73-137">Element Name</span></span>|<span data-ttu-id="c1e73-138">説明</span><span class="sxs-lookup"><span data-stu-id="c1e73-138">Description</span></span>|
   |------------------|-----------------|
   |<span data-ttu-id="c1e73-139">PossibleValues</span><span class="sxs-lookup"><span data-stu-id="c1e73-139">PossibleValues</span></span>|<span data-ttu-id="c1e73-140">この要素は、コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c1e73-140">This element is a container.</span></span> <span data-ttu-id="c1e73-141">その子要素を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-141">Its child elements are described below.</span></span> <span data-ttu-id="c1e73-142">1 つ追加`PossibleValues`各プロバイダーのヘルプ トピックへの要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-142">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="c1e73-143">要素を空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c1e73-143">The element can be empty.</span></span>|
   |<span data-ttu-id="c1e73-144">PossibleValue</span><span class="sxs-lookup"><span data-stu-id="c1e73-144">PossibleValue</span></span>|<span data-ttu-id="c1e73-145">この要素は、コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c1e73-145">This element is a container.</span></span> <span data-ttu-id="c1e73-146">その子要素を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-146">Its child elements are described below.</span></span> <span data-ttu-id="c1e73-147">1 つ追加`PossibleValue`動的パラメーターの値ごとの要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-147">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>|
   |<span data-ttu-id="c1e73-148">値</span><span class="sxs-lookup"><span data-stu-id="c1e73-148">Value</span></span>|<span data-ttu-id="c1e73-149">値の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1e73-149">Specifies the value name.</span></span>|
   |<span data-ttu-id="c1e73-150">説明</span><span class="sxs-lookup"><span data-stu-id="c1e73-150">Description</span></span>|<span data-ttu-id="c1e73-151">この要素が含まれています、`Para`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-151">This element contains a `Para` element.</span></span> <span data-ttu-id="c1e73-152">内のテキスト、`Para`要素で指定されている値を記述する、`Value`要素。</span><span class="sxs-lookup"><span data-stu-id="c1e73-152">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>|

   <span data-ttu-id="c1e73-153">たとえば、次の XML では 1 つ`PossibleValue`の要素、`Encoding`動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c1e73-153">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

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

## <a name="example"></a><span data-ttu-id="c1e73-154">例</span><span class="sxs-lookup"><span data-stu-id="c1e73-154">Example</span></span>

<span data-ttu-id="c1e73-155">次の例は、`DynamicParameters`の要素、`Encoding`動的パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c1e73-155">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

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