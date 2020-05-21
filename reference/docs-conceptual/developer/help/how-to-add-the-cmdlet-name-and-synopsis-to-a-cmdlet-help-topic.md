---
title: コマンドレット名と概要をコマンドレットに追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: 5b4c04a14c3d86c7a3b94b768e8fb59116d8c6f5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560629"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックにコマンドレットの名前と概要を追加する方法

このセクションでは、コマンドレットのヘルプの [名前] セクションと [概要] セクションに表示されるコンテンツを追加する方法について説明します。 ヘルプファイルでは、各コマンドレットのコマンドノードにこのコンテンツが追加されます。

> [!NOTE]
> ヘルプファイルの完全なビューを表示するには、Windows PowerShell のインストールディレクトリにあるいずれかの dll-Help ファイルを開きます。 たとえば、dll-Help ファイルには、いくつかの Windows PowerShell コマンドレットのコンテンツが含まれています。

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a>コマンドレット名と概要を追加するには

- コマンドレットのヘルプには、コマンドレットの2つの説明が表示されます。 最初の説明は、簡単な説明です。 2番目の説明では、詳細な説明を[コマンドレットヘルプトピックに追加](./how-to-add-a-cmdlet-description.md)する方法について詳しく説明します。 これらの説明は、両方とも1つの段落として記述する必要があります。

- ここでは、コマンドレット名を繰り返しません。 Get Server コマンドレットがサーバーを取得することをユーザーに通知しますが、情報は表示されません。 代わりに、シノニムを使用し、詳細を説明に追加します。

  例: "ローカルコンピューターまたはリモートコンピューターを表すオブジェクトを取得します。"

- "Get"、"create"、"change" のような単純な動詞を使用します。 "Set" はあいまいであるため、"modify" などの凝った単語は使用しないでください。

  例: "ファイル内の Authenticode 署名に関する情報を取得します。"

- アクティブな音声で書き込みます。 たとえば、"TimeSpan オブジェクトの使用...""TimeSpan オブジェクトを使用して..." を

- オブジェクトを取得するコマンドレットを記述するときは、動詞 "display" を避けてください。 Windows PowerShell にはコマンドレットのデータが表示されますが、このコマンドレットによって返されるデータが表示されない .NET Framework オブジェクトが返されるという概念をユーザーに紹介することが重要です。 表示を強調すると、コマンドレットで表示されない他の便利なプロパティやメソッドが多数返された可能性があることをユーザーが認識できない可能性があります。

## <a name="see-also"></a>参照

 [Windows PowerShell SDK](../windows-powershell-reference.md)
