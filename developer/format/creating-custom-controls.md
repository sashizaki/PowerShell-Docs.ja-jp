---
title: カスタム コントロールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3baa406-cd33-4420-be5a-07ef09d93480
caps.latest.revision: 8
ms.openlocfilehash: 3504ab1d974c55e9279172d0e851961474ccb926
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066687"
---
# <a name="creating-custom-controls"></a><span data-ttu-id="7f970-102">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="7f970-102">Creating Custom Controls</span></span>

<span data-ttu-id="7f970-103">カスタム コントロールは、書式設定ファイルの最も柔軟なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7f970-103">Custom controls are the most flexible components of a formatting file.</span></span> <span data-ttu-id="7f970-104">カスタム コントロールでは、テーブル、リスト、およびデータのテーブルなどのデータの正式な構造を定義するワイド ビューとは異なり、個々 のデータを表示する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="7f970-104">Unlike table, list, and wide views that define a formal structure of data, such as a table of data, custom controls allow you to define how an individual piece of data is displayed.</span></span> <span data-ttu-id="7f970-105">書式設定ファイルのすべてのビューを使用できるカスタム コントロールの共通セットを定義することができます、特定のビューに使用できるカスタム コントロールを定義することができます、またはオブジェクトのグループに使用できるコントロールのセットを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="7f970-105">You can define a common set of custom controls that are available to all the views of the formatting file, you can define custom controls that are available to a specific view, or you can define a set of controls that are available to a group of objects.</span></span>

## <a name="custom-control-example"></a><span data-ttu-id="7f970-106">カスタム コントロールの例</span><span class="sxs-lookup"><span data-stu-id="7f970-106">Custom Control Example</span></span>

<span data-ttu-id="7f970-107">次の例では、Certificates.Format.ps1xml ファイルで定義されているカスタム コントロールを示します。</span><span class="sxs-lookup"><span data-stu-id="7f970-107">The following example shows a custom control that is defined in the Certificates.Format.ps1xml file.</span></span> <span data-ttu-id="7f970-108">このカスタム コントロールを使用して区別、 [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature)テーブル ビューに表示されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7f970-108">This custom control is used to separate the [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature) objects displayed in a table view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7f970-109">参照</span><span class="sxs-lookup"><span data-stu-id="7f970-109">See Also</span></span>

[<span data-ttu-id="7f970-110">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7f970-110">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
