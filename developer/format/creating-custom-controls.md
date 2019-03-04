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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853198"
---
# <a name="creating-custom-controls"></a>カスタム コントロールを作成する

カスタム コントロールは、書式設定ファイルの最も柔軟なコンポーネントです。 カスタム コントロールでは、テーブル、リスト、およびデータのテーブルなどのデータの正式な構造を定義するワイド ビューとは異なり、個々 のデータを表示する方法を定義できます。 書式設定ファイルのすべてのビューを使用できるカスタム コントロールの共通セットを定義することができます、特定のビューに使用できるカスタム コントロールを定義することができます、またはオブジェクトのグループに使用できるコントロールのセットを定義することができます。

## <a name="custom-control-example"></a>カスタム コントロールの例

次の例では、Certificates.Format.ps1xml ファイルで定義されているカスタム コントロールを示します。 このカスタム コントロールを使用して区別、 [System.Management.Automation.Signature](/dotnet/api/System.Management.Automation.Signature)テーブル ビューに表示されるオブジェクト。

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

[PowerShell のファイルを書式設定の書き込み](./writing-a-powershell-formatting-file.md)
