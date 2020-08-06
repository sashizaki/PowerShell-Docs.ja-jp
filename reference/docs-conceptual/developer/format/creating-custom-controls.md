---
title: カスタムコントロールの作成 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c36fa9b778e01501a3c88f735cdefdfbb04411a0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786120"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="2fe6e-102">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="2fe6e-102">Creating Custom Controls</span></span>

<span data-ttu-id="2fe6e-103">カスタムコントロールは、書式設定ファイルの最も柔軟なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="2fe6e-103">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="2fe6e-104">データテーブルなどのデータの正式な構造を定義するテーブル、リスト、およびワイドビューとは異なり、カスタムコントロールでは、個々のデータの表示方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2fe6e-104">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="2fe6e-105">書式設定ファイルのすべてのビューで使用できるカスタムコントロールの共通セットを定義したり、特定のビューで使用できるカスタムコントロールを定義したり、オブジェクトのグループで使用できるコントロールのセットを定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="2fe6e-105">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="2fe6e-106">カスタムコントロールの例</span><span class="sxs-lookup"><span data-stu-id="2fe6e-106">Custom Control Example</span></span>

<span data-ttu-id="2fe6e-107">次の例は、Certificates.Format.ps1xml ファイルで定義されているカスタムコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="2fe6e-107">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="2fe6e-108">このカスタムコントロールは、テーブルビューに表示さ[れるオブジェクトを](/dotnet/api/System.Management.Automation.Signature)区切るために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2fe6e-108">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

```xml
<Controls>
  <Control>
    <Name>SignatureTypes-GroupingFormat</Name>
    <CustomControl>
      <CustomEntries>
        <CustomEntry>
          <CustomItem>
            <Frame>
              <LeftIndent>4</LeftIndent>
              <CustomItem>
                <Text AssemblyName="System.Management.Automation" BaseName="FileSystemProviderStrings"
                  ResourceId="DirectoryDisplayGrouping"/>
                <ExpressionBinding>
                  <ScriptBlock>split-path $_.Path</ScriptBlock>
                </ExpressionBinding>
                <NewLine/>
              </CustomItem>
            </Frame>
          </CustomItem>
        </CustomEntry>
      </CustomEntries>
    </CustomControl>
  </Control>
</Controls>

```

## <a name="see-also"></a><span data-ttu-id="2fe6e-109">参照</span><span class="sxs-lookup"><span data-stu-id="2fe6e-109">See Also</span></span>

[<span data-ttu-id="2fe6e-110">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2fe6e-110">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
