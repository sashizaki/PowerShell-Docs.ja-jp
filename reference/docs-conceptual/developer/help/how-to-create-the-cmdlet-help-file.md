---
title: コマンドレットのヘルプファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: 186a8ceecea47564503dc181a76cc314033b6d3f
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76996045"
---
# <a name="how-to-create-the-cmdlet-help-file"></a>コマンドレットのヘルプ ファイルを作成する方法

このセクションでは、Windows PowerShell コマンドレットのヘルプトピックを含む有効な XML ファイルを作成する方法について説明します。 このセクションでは、ヘルプファイルに名前を付ける方法、適切な XML ヘッダーを追加する方法、コマンドレットのヘルプコンテンツのさまざまなセクションを含むノードを追加する方法について説明します。

> [!NOTE]
> ヘルプファイルの完全なビューを表示するには、Windows PowerShell のインストールディレクトリにあるいずれかの dll-Help ファイルを開きます。 たとえば、dll-Help ファイルには、いくつかの Windows PowerShell コマンドレットのコンテンツが含まれています。

### <a name="how-to-create-a-cmdlet-help-file"></a>コマンドレットのヘルプファイルを作成する方法

1. テキストファイルを作成し、UTF8 エンコーディングを使用して保存します。 Windows PowerShell でコマンドレットヘルプファイルとして検出できるように、ファイル名は次の形式である必要があります。

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. 次の XML ヘッダーをテキストファイルに追加します。 ファイルは、マルチエージェントモデリング言語 (MAML) スキーマに対して検証されることに注意してください。 現在、Windows PowerShell には、ファイルを検証するためのツールは用意されていません。

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. コマンドノードを、アセンブリ内の各コマンドレットのコマンドレットヘルプファイルに追加します。 コマンドノード内の各ノードは、コマンドレットのヘルプトピックのさまざまなセクションに関連しています。

   次の表に、各ノードの XML 要素と各ノードの説明を示します。

   |Node|Description|
   |----------|-----------------|
   |`<details>`|コマンドレットのヘルプトピックの [名前] セクションと [概要] セクションの内容を追加します。 詳細については、「[コマンドレット名と概要の追加方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)」を参照してください。|
   |`<maml:description>`|コマンドレットのヘルプトピックの [説明] セクションの内容を追加します。 詳細については、[コマンドレットのヘルプトピックの「詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)」を参照してください。|
   |`<command:syntax>`|コマンドレットのヘルプトピックの「構文」セクションの内容を追加します。 詳細については、[コマンドレットヘルプトピックの「構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)」を参照してください。|
   |`<command:parameters>`|コマンドレットのヘルプトピックの PARAMETERS セクションにコンテンツを追加します。 詳細については、「[コマンドレットにパラメーターを追加する方法](./how-to-add-parameter-information.md)」を参照してください。|
   |`<command:inputTypes>`|コマンドレットのヘルプトピックの入力セクションの内容を追加します。 詳細については、[コマンドレットヘルプトピックの「入力の種類を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)」を参照してください。|
   |`<command:returnValues>`|コマンドレットヘルプトピックの出力セクションの内容を追加します。 詳細については、[コマンドレットヘルプトピックの「戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)」を参照してください。|
   |`<maml:alertset>`|コマンドレットのヘルプトピックのメモセクションにコンテンツを追加します。 詳細については、「[コマンドレットにメモを追加する方法](./how-to-add-notes-to-a-cmdlet-help-topic.md)」を参照してください。|
   |`<command:examples>`|コマンドレットのヘルプトピックの「例」セクションの内容を追加します。 詳細については、「 [How To Add 例をコマンドレットヘルプトピックに追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)」を参照してください。|
   |`<maml:relatedLinks>`|コマンドレットヘルプトピックの「関連リンク」セクションの内容を追加します。 詳細については、[コマンドレットヘルプトピックの「関連リンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)」を参照してください。|

## <a name="example"></a>例

 コマンドレットのヘルプトピックのさまざまなセクションのノードを含むコマンドノードの例を次に示します。

```xml
<command:command
  xmlns:maml="https://schemas.microsoft.com/maml/2004/10"
  xmlns:command="https://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="https://schemas.microsoft.com/maml/dev/2004/10">
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

## <a name="see-also"></a>関連項目

 [コマンドレット名と概要を追加する方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [詳細な説明をコマンドレットヘルプトピックに追加する方法](./how-to-add-a-cmdlet-description.md)

 [コマンドレットヘルプトピックに構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [コマンドレットにパラメーターを追加する方法に関するヘルプトピック](./how-to-add-parameter-information.md)

 [コマンドレットのヘルプトピックに入力の種類を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [コマンドレットヘルプトピックに戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [コマンドレットヘルプトピックにメモを追加する方法](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [コマンドレットのヘルプトピックに例を追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [コマンドレットヘルプトピックに関連リンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Windows PowerShell SDK](../windows-powershell-reference.md)