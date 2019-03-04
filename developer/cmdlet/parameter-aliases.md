---
title: パラメーターのエイリアス |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853318"
---
# <a name="parameter-aliases"></a>パラメーターのエイリアス

コマンドレットのパラメーターは、エイリアスをこともできます。 入力するかのコマンドで、パラメーターを指定する場合は、パラメーター名の代わりにエイリアスを使用できます。

## <a name="benefits-of-using-aliases"></a>エイリアスを使用する利点

パラメーターにエイリアスを追加するには、次の利点が提供します。

- ユーザーが、コマンドレットが呼び出されたときに、完全なパラメーター名を使用する必要があるないようにショートカットを行うことができます。 たとえば、"ComputerName"パラメーター名の代わりに、"CN"エイリアスを使用できます。

- 同じパラメーターに対して異なる名前を指定する場合は、複数のエイリアスを定義できます。 さまざまな方法で、同じデータを参照する複数のユーザー グループを使用する必要がある場合は、複数のエイリアスを定義する場合があります。

- 行うことができます下位互換性の既存のスクリプトのパラメーターの名前が変更された場合。

- ValueFromPipelineByName 属性とエイリアス属性を使用するにはのコマンドレットを別のオブジェクトの型にバインドできるようにするパラメーターを定義できます。 たとえば、最初のオブジェクトがライターのプロパティと 2 番目のオブジェクトには、エディター プロパティがありました。 さまざまな種類の 2 つのオブジェクトを作成する必要があります。 コマンドレットが含まれていたパラメーターがある場合、ライターおよびエディターのエイリアスとコマンドレットは、プロパティ名に基づくパイプライン入力を受け入れ、コマンドレットは、2 つのパラメーターのエイリアスを使用して両方のオブジェクトへバインドできます。

特定のパラメーターで使用できるエイリアスに関する詳細については、次を参照してください。[パラメーターの共通名](./common-parameter-names.md)します。

## <a name="defining-parameter-aliases"></a>パラメーターのエイリアスを定義します。

パラメーターのエイリアスを定義するには、次のパラメーターの宣言で示すように、エイリアス属性を宣言します。 この例では、複数のエイリアスは、同じパラメーターに対して定義されます。 (詳細については、次を参照してください[コマンドレット パラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)。)。

```csharp
[Alias("UN","Writer","Editor")]
[Parameter()]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="see-also"></a>参照

[一般的なパラメーター名](./common-parameter-names.md)

[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
