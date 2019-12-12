---
title: コマンドレット Alias |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d70864-33fb-49ce-8054-c41ba19fd554
caps.latest.revision: 11
ms.openlocfilehash: 32f45702cc0d28e6652ef61ebdbe085291013408
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369981"
---
# <a name="cmdlet-aliases"></a>コマンドレット エイリアス

コマンドレットのエイリアスを使用して、コマンドレットのユーザーエクスペリエンスを向上させることができます。 頻繁に使用するコマンドレットにエイリアスを追加して、入力を減らし、タスクをすばやく完了できるようにすることができます。 組み込みのエイリアスをコマンドレットに含めることも、ユーザーが独自のカスタムエイリアスを定義することもできます。

たとえば、 [Get コマンド](/powershell/module/microsoft.powershell.core/get-command)レットには `gcm` エイリアスが組み込まれています。 エイリアスを使用して、他の言語のコマンド名を追加して、ユーザーが新しいコマンドを習得する必要がないようにすることもできます。

## <a name="alias-guidelines"></a>エイリアスのガイドライン

コマンドレットの組み込みエイリアスを作成するときは、次のガイドラインに従ってください。

- エイリアスを割り当てる前に、Windows PowerShell を起動してから、 [Get Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias)コマンドレットを実行して、既に使用されているエイリアスを確認します。

- コマンドレット名の動詞を参照するエイリアスプレフィックスと、コマンドレット名の名詞を参照するエイリアスサフィックスを含めます。 たとえば、`Import-Module` コマンドレットのエイリアスは "ipmo" です。 すべての動詞とそのエイリアスの一覧については、「[コマンドレットの動詞](./approved-verbs-for-windows-powershell-commands.md)」を参照してください。

- 同じ動詞を持つコマンドレットの場合は、同じエイリアスプレフィックスを含めます。 たとえば、名前に "Get" という動詞があるすべての Windows PowerShell コマンドレットのエイリアスは、"g" プレフィックスを使用します。

- 同じ名詞を持つコマンドレットの場合は、同じエイリアスサフィックスを含めます。 たとえば、名前に "Session" という名詞が付いているすべての Windows PowerShell コマンドレットのエイリアスは、"sn" サフィックスを使用します。

- 他の言語のコマンドと同等のコマンドレットについては、コマンドの名前を使用します。

- 一般に、エイリアスはできるだけ短くしてください。 動詞と名詞に1つの個別の文字がエイリアスに1つ以上含まれていることを確認します。 エイリアスを一意にするために、必要に応じてさらに文字を追加します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
