---
title: コマンドレットのエイリアス |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d70864-33fb-49ce-8054-c41ba19fd554
caps.latest.revision: 11
ms.openlocfilehash: 32f45702cc0d28e6652ef61ebdbe085291013408
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068722"
---
# <a name="cmdlet-aliases"></a>コマンドレット エイリアス

コマンドレットのエイリアスを使用して、コマンドレットのユーザー エクスペリエンスを向上させることができます。 頻繁に使用されるコマンドレット」と入力を削減し、迅速でタスクの実行を容易にできるようにするには、エイリアスを追加できます。 コマンドレットでは、組み込みエイリアスを含めることも、ユーザーが独自のカスタム エイリアスを定義できます。

たとえば、 [Get-command](/powershell/module/microsoft.powershell.core/get-command)コマンドレットは、組み込み`gcm`エイリアス。 ユーザーは新しいコマンドの習得するのに必要があるないように、他の言語からコマンド名を追加するのにエイリアスを使用することもできます。

## <a name="alias-guidelines"></a>エイリアスのガイドライン

コマンドレットの組み込みエイリアスを作成するときに、次のガイドラインに従います。

- 別名を割り当てる前に、Windows PowerShell を起動し、実行、 [Get-alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias)コマンドレットを既に使用されているエイリアスを参照してください。

- コマンドレット名と、コマンドレット名の名詞を参照する別名サフィックスの動詞を参照する別名のプレフィックスが含まれます。 エイリアスなど、`Import-Module`コマンドレットは、"ipmo"です。 すべての動詞と、エイリアスの一覧は、次を参照してください。[コマンドレット動詞](./approved-verbs-for-windows-powershell-commands.md)します。

- 同じ動詞を含むコマンドレットでは、同じ別名のプレフィックスを含めます。 たとえば、名前に"Get"動詞を含むすべての Windows PowerShell コマンドレットのエイリアスは、"g"プレフィックスを使用します。

- 同じ名詞を含むコマンドレットでは、同じエイリアス サフィックスが含まれます。 たとえば、名前に「セッション」という名詞を含むすべての Windows PowerShell コマンドレットのエイリアスは"sn"サフィックスを使用します。

- 他の言語でのコマンドとほぼ同等であるコマンドレット、コマンドの名前を使用します。

- 一般に、できるだけ短くエイリアスを行います。 エイリアスが動詞の少なくとも 1 つの異なる文字と、名詞の 1 つの異なる文字確認します。 エイリアスに一意にするために必要な多くの文字を追加します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
