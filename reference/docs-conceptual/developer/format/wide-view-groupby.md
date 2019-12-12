---
title: Wide ビュー (GroupBy) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39388197-4ff9-4889-aa32-526011afa1f6
caps.latest.revision: 6
ms.openlocfilehash: e95ec550a7815a76a8bd7f9526dfa405a9644360
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367951"
---
# <a name="wide-view-groupby"></a>ワイド ビュー (グループ別)

この例では、Servicecontroller のグループを表示するワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) `Get-Service` コマンドレットによって返される Fullname オブジェクト。 ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

### <a name="to-load-this-formatting-file"></a>この書式設定ファイルを読み込むには

1. このトピックの「例」のセクションにある XML をテキストファイルにコピーします。

2. テキスト ファイルを保存します。 `format.ps1xml` 拡張機能をファイルに追加して、フォーマットファイルとして識別するようにしてください。

3. Windows PowerShell を開き、次のコマンドを実行して、書式設定ファイルを現在のセッションに読み込みます: `Update-formatdata -prependpath PathToFormattingFile`。

   > [!WARNING]
   > この書式設定ファイルは、Windows PowerShell の書式設定ファイルによって既に定義されているオブジェクトの表示を定義します。 コマンドレットの実行時には `prependPath` パラメーターを使用する必要があり、このフォーマットファイルをモジュールとして読み込むことはできません。

## <a name="demonstrates"></a>使用例

この書式設定ファイルは、次の XML 要素を示しています。

- ビューの[Name](./name-element-for-view-format.md)要素。

- ビューによって表示されるオブジェクトを定義する[Viewselectedby](./viewselectedby-element-format.md)要素。

- 新しいグループが表示されるタイミングを定義する[GroupBy](./groupby-element-for-view-format.md)要素。

- ビューによって表示されるプロパティを定義する[WideItem](./wideitem-element-for-widecontrol-format.md)要素。

## <a name="example"></a>例

次の XML は、オブジェクトのグループを表示するワイドビューを定義します。 新しい各グループは、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType)プロパティの値が変更されると開始されます。

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <Label>Service Type</Label>
        <PropertyName>ServiceType</PropertyName>
      </GroupBy>
      <WideControl>
        <WideEntries>
          <WideEntry>
            <WideItem>
              <PropertyName>ServiceName</PropertyName>
            </WideItem>
          </WideEntry>
        </WideEntries>
      </WideControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

次の例は、Windows PowerShell で Servicecontroller を表示する方法を示しています。 [Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクトこのフォーマットファイルが読み込まれた後。

```powershell
Get-Service f*
```

```output
   Service Type: Win32OwnProcess

Fax                             FCSAM

   Service Type: Win32ShareProcess

fdPHost                         FDResPub
FontCache

   Service Type: Win32OwnProcess

FontCache3.0.0.0                FSysAgent
FwcAgent
```

## <a name="see-also"></a>参照

[フォーマットファイルの例](./examples-of-formatting-files.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
