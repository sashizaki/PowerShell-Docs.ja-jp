---
title: コマンドレットのヘルプ ファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: 08e05939f8aee42f2cd502a3da7a528d8460dec1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858978"
---
# <a name="how-to-create-the-cmdlet-help-file"></a>コマンドレットのヘルプ ファイルを作成する方法

このセクションでは、Windows PowerShell コマンドレットのヘルプ トピックのコンテンツを含む有効な XML ファイルを作成する方法について説明します。 このセクションでは、ヘルプ ファイルの名前を付ける方法や、適切な XML ヘッダーを追加する方法、コマンドレットのヘルプ コンテンツのさまざまなセクションを含むノードを追加する方法について説明します。

> [!NOTE]
> ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。 たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。

### <a name="how-to-create-a-cmdlet-help-file"></a>コマンドレットのヘルプ ファイルを作成する方法

1. テキスト ファイルを作成し、UTF8 エンコーディングを使用して保存します。 ファイル名は、Windows PowerShell を使用すると、コマンドレットのヘルプ ファイルとして検出できるように、次の形式にすることが必要です。

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. テキスト ファイルに次の XML ヘッダーを追加します。 ファイルが複数のエージェントのモデリング言語 (MAML) スキーマに対して検証されることに注意します。 現時点では、Windows PowerShell では、ファイルを検証する任意のツールは提供されません。

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. コマンド ノードをアセンブリ内の各コマンドレットのヘルプ ファイルをコマンドレットに追加します。 コマンド ノード内の各ノードは、コマンドレットのヘルプ トピックのさまざまなセクションに関連しています。

   次の表では、各ノードの説明については、後に、各ノードの XML 要素を示します。

   |ノード|説明|
   |----------|-----------------|
   |`<details>`|コマンドレットのヘルプ トピックの名前と概要セクションのコンテンツを追加します。 詳細については、次を参照してください。[概要とコマンドレットの名前を追加する方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)します。|
   |`<maml:description>`|コマンドレットのヘルプ トピックの説明 セクションのコンテンツを追加します。 詳細については、次を参照してください。[コマンドレットのヘルプ トピックを詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)します。|
   |`<command:syntax>`|コマンドレットのヘルプ トピックの「構文」セクションのコンテンツを追加します。 詳細については、次を参照してください。[構文コマンドレットのヘルプ トピックをに追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)します。|
   |`<command:parameters>`|コマンドレットのヘルプ トピックの PARAMETERS セクションのコンテンツを追加します。 詳細については、次を参照してください。[コマンドレットのヘルプ トピックにパラメーターを追加する方法](./how-to-add-parameter-information.md)します。|
   |`<command:inputTypes>`|コマンドレットのヘルプ トピックの入力のセクションのコンテンツを追加します。 詳細については、次を参照してください。[コマンドレットのヘルプ トピックへの入力タイプの追加方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)します。|
   |`<command:returnValues>`|コマンドレットのヘルプ トピックの出力セクションのコンテンツを追加します。 詳細については、次を参照してください。[戻り値の追加コマンドレットのヘルプ トピックにする方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)します。|
   |`<maml:alertset>`|コマンドレットのヘルプ トピックのノートのセクションには、コンテンツを追加します。 詳細については、次を参照してください。[を追加する方法は、コマンドレットのヘルプ トピックをノート](./how-to-add-notes-to-a-cmdlet-help-topic.md)します。|
   |`<command:examples>`|コマンドレットのヘルプ トピックの例」のセクションのコンテンツを追加します。 詳細については、次を参照してください。[コマンドレットのヘルプ トピックに例を追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)します。|
   |`<maml:relatedLinks>`|コマンドレットのヘルプ トピックの「関連リンク」のコンテンツを追加します。 詳細については、次を参照してください。[コマンドレットのヘルプ トピックへの関連リンクの追加方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)します。|

## <a name="example"></a>例

 次のコマンドレットのヘルプ トピックのさまざまなセクションでは、ノードを含むコマンド ノードの例に示します。

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a>参照

 [概要とコマンドレットの名前を追加する方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックの詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)

 [コマンドレットのヘルプ トピックに構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックにパラメーターを追加する方法](./how-to-add-parameter-information.md)

 [コマンドレットのヘルプ トピックへの入力の種類を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックに戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [追加する方法は、コマンドレットのヘルプ トピックをノートします。](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックの例を追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプ トピックに関連するリンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Windows PowerShell SDK](../windows-powershell-reference.md)