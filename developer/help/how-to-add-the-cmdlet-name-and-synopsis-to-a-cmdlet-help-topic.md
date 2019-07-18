---
title: 概要とコマンドレットの名前をコマンドレットのヘルプ トピックを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: f142548be473da15e702f4fa01835609d75b9d51
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083339"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックにコマンドレットの名前と概要を追加する方法

このセクションでは、名前と概要セクションでは、コマンドレットのヘルプに表示されるコンテンツを追加する方法について説明します。 ヘルプ ファイルでこのコンテンツは、各コマンドレットのコマンドのノードに追加されます。

> [!NOTE]
> ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。 たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a>コマンドレット名と概要を追加するには

- コマンドレットのヘルプには、コマンドレットの 2 つの説明を表示できます。 最初の説明は、概要として参照される簡単な説明です。 2 番目の説明に記載されているより詳細な説明は、[コマンドレットのヘルプ トピックの詳細な説明を追加する](./how-to-add-a-cmdlet-description.md)します。 段落を 1 つとして、これら両方の説明を記述する必要があります。

- 概要でコマンドレット名を繰り返されません。 Get-server コマンドレットが、サーバーを取得することをユーザーに通知は、簡単な有益です。 代わりに、シノニムを使用し、詳細説明を追加します。

  次に例を示します。「ローカルまたはリモート コンピューターを表すオブジェクトを取得します。」

- "Get"、「作成」、および概要には、「変更」などの単純な動詞を使用します。 不明瞭な言葉を飾るなど「を変更します」ため、"set"を使用しないでください。

  次に例を示します。「ファイルの Authenticode 署名に関する情報を取得」します。

- 能動態で記述します。 たとえば、「オブジェクトを使用して、TimeSpan...」「TimeSpan オブジェクトできますを使用して...」方が明確には

- オブジェクトを取得するコマンドレットを記述するときは、「表示」動詞を回避します。 Windows PowerShell には、コマンドレットのデータが表示されますは、コマンドレットは、データが表示されないことが .NET Framework オブジェクトを返す概念にユーザーを導入する必要があります。 表示を強調する場合、ユーザー気付かない可能性があります、コマンドレットから返されたその他の多くの便利なプロパティやメソッドが表示されていないこと。

## <a name="see-also"></a>参照

 [Windows PowerShell SDK](../windows-powershell-reference.md)