---
title: ワイドビュー (基本) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9abb63b8-6d02-4e24-9c0e-2d15a04e9051
caps.latest.revision: 8
ms.openlocfilehash: 7a36f548a3eccdf2c9cad04a8bfe28bf4e8d6dfd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367941"
---
# <a name="wide-view-basic"></a>ワイド ビュー (基本)

この例では、Servicecontroller を表示する基本的なワイドビューを実装する方法を示します。 [Displayproperty =](/dotnet/api/System.ServiceProcess.ServiceController) `Get-Service` コマンドレットによって返される Fullname オブジェクト。 ワイドビューのコンポーネントの詳細については、「[ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。

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

- ビューによって表示されるプロパティを定義する[WideItem](./wideitem-element-for-widecontrol-format.md)要素。

## <a name="example"></a>例

次の XML は、 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController.ServiceName)プロパティの値を表示するワイドビューを定義しています。

```xml
<?xml version="1.0" encoding="utf-8" ?>

<Configuration>
  <ViewDefinitions>
    <View>
      <Name>ServiceWideView</Name>
      <ViewSelectedBy>
        <TypeName>System.ServiceProcess.ServiceController</TypeName>
      </ViewSelectedBy>
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
Fax                      FCSAM
fdPHost                  FDResPub
FontCache                FontCache3.0.0.0
FSysAgent                FwcAgent
```

## <a name="see-also"></a>参照

[フォーマットファイルの例](./examples-of-formatting-files.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
