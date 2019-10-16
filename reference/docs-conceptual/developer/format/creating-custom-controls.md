---
title: カスタムコントロールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3baa406-cd33-4420-be5a-07ef09d93480
caps.latest.revision: 8
ms.openlocfilehash: 3504ab1d974c55e9279172d0e851961474ccb926
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363381"
---
# <a name="creating-custom-controls"></a>カスタム コントロールを作成する

カスタムコントロールは、書式設定ファイルの最も柔軟なコンポーネントです。 データテーブルなどのデータの正式な構造を定義するテーブル、リスト、およびワイドビューとは異なり、カスタムコントロールでは、個々のデータの表示方法を定義できます。 書式設定ファイルのすべてのビューで使用できるカスタムコントロールの共通セットを定義したり、特定のビューで使用できるカスタムコントロールを定義したり、オブジェクトのグループで使用できるコントロールのセットを定義したりできます。

## <a name="custom-control-example"></a>カスタムコントロールの例

次の例は、types.ps1xml ファイルで定義されているカスタムコントロールを示しています。 このカスタムコントロールは、テーブルビューに表示さ[れるオブジェクトを](/dotnet/api/System.Management.Automation.Signature)区切るために使用されます。

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

## <a name="see-also"></a>参照

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
