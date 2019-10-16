---
title: パラメーターの別名 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c9096a1-46fa-48ea-9b8a-a583484b9d68
caps.latest.revision: 13
ms.openlocfilehash: 6545e71ea18d10621ee9c203e70f64dece460ef5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369591"
---
# <a name="parameter-aliases"></a>パラメーターのエイリアス

コマンドレットのパラメーターには別名を設定することもできます。 コマンドでパラメーターを入力または指定するときに、パラメーター名の代わりにエイリアスを使用できます。

## <a name="benefits-of-using-aliases"></a>エイリアスを使用する利点

パラメーターに別名を追加すると、次のような利点があります。

- コマンドレットが呼び出されたときに、ユーザーが完全なパラメーター名を使用する必要がないように、ショートカットを指定することができます。 たとえば、パラメーター名 "ComputerName" の代わりに "CN" エイリアスを使用できます。

- 同じパラメーターに別の名前を指定する場合は、複数のエイリアスを定義できます。 同じデータをさまざまな方法で参照する複数のユーザーグループを操作する必要がある場合は、複数のエイリアスを定義することもできます。

- パラメーターの名前が変更された場合は、既存のスクリプトに下位互換性を持たせることができます。

- Alias 属性を ValueFromPipelineByName 属性と共に使用することで、コマンドレットがさまざまなオブジェクトの種類にバインドできるようにするパラメーターを定義できます。 たとえば、異なる型の2つのオブジェクトがあり、最初のオブジェクトが writer プロパティを持ち、2番目のオブジェクトにエディタープロパティがあるとします。 コマンドレットにライターとエディターのエイリアスを持つパラメーターがあり、コマンドレットがプロパティ名に基づくパイプライン入力を受け入れた場合、2つのパラメーターエイリアスを使用して、コマンドレットで両方のオブジェクトにバインドすることができます。

特定のパラメーターと共に使用できるエイリアスの詳細については、「[共通パラメーター名](./common-parameter-names.md)」を参照してください。

## <a name="defining-parameter-aliases"></a>パラメーターの別名の定義

パラメーターのエイリアスを定義するには、次のパラメーター宣言に示すように、Alias 属性を宣言します。 この例では、同じパラメーターに対して複数のエイリアスが定義されています。 (詳細については、「[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)」を参照してください)。

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

[共通パラメーター名](./common-parameter-names.md)

[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
