---
ms.date: 09/13/2016
ms.topic: reference
title: カスタム コントロールを作成する
description: カスタム コントロールを作成する
ms.openlocfilehash: 78d8cc2970b2b3e493bef25d78404ba1be195bb1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668050"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="d3c7b-103">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="d3c7b-103">Creating Custom Controls</span></span>

<span data-ttu-id="d3c7b-104">カスタムコントロールは、書式設定ファイルの最も柔軟なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d3c7b-104">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="d3c7b-105">データテーブルなどのデータの正式な構造を定義するテーブル、リスト、およびワイドビューとは異なり、カスタムコントロールでは、個々のデータの表示方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d3c7b-105">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="d3c7b-106">書式設定ファイルのすべてのビューで使用できるカスタムコントロールの共通セットを定義したり、特定のビューで使用できるカスタムコントロールを定義したり、オブジェクトのグループで使用できるコントロールのセットを定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="d3c7b-106">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="d3c7b-107">カスタムコントロールの例</span><span class="sxs-lookup"><span data-stu-id="d3c7b-107">Custom Control Example</span></span>

<span data-ttu-id="d3c7b-108">次の例は、Certificates.Format.ps1xml ファイルで定義されているカスタムコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="d3c7b-108">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="d3c7b-109">このカスタムコントロールは、テーブルビューに表示さ [れるオブジェクトを](/dotnet/api/System.Management.Automation.Signature) 区切るために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d3c7b-109">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d3c7b-110">参照</span><span class="sxs-lookup"><span data-stu-id="d3c7b-110">See Also</span></span>

[<span data-ttu-id="d3c7b-111">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d3c7b-111">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
