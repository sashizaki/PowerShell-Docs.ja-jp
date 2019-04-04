---
title: パラメーター属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, Parameter
- Parameter attribute, described
- Parameter attribute
ms.assetid: 08433d0b-169b-42c8-9335-2881d9034698
caps.latest.revision: 13
ms.openlocfilehash: a3488d5fb3f7eb3df28d0242d6c39d07145a3c8d
ms.sourcegitcommit: 10c347a8c3dcbf8962295601834f5ba85342a87b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "56863618"
---
# <a name="parameter-attribute-declaration"></a>パラメーター属性の宣言

パラメーター属性では、コマンドレット パラメーターとして、コマンドレット クラスのパブリック プロパティを識別します。

## <a name="syntax"></a>構文

```csharp
[Parameter()]
[Parameter(Named Parameters...)]
```

#### <a name="parameters"></a>パラメーター

`Mandatory` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 `True` コマンドレットのパラメーターが必要なことを示します。 コマンドレットが呼び出されたときに必要なパラメーターが指定されていない場合、Windows PowerShell には、パラメーター値をユーザーが求められます。 既定値は `false` です。

`ParameterSetName` ([System.String](/dotnet/api/System.String)) という名前のパラメーター (省略可能)。 パラメーターの設定をこのコマンドレットのパラメーターが属していることを指定します。 パラメーター セットが指定されていない場合、パラメーターは、すべてのパラメーター セットに属しています。

`Position` ([System.Integer](/dotnet/api/System.Integer)) という名前のパラメーター (省略可能)。 Windows PowerShell コマンド内でパラメーターの位置を指定します。

`ValueFromPipeline` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 `True` コマンドレットのパラメーターが、パイプライン オブジェクトから値を受け取ることを示します。 コマンドレットが、完全にアクセスする場合にこのキーワードを指定するだけでなく、オブジェクトのプロパティのオブジェクトします。 既定値は `false` です。

`ValueFromPipelineByPropertyName` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 `True` コマンドレットのパラメーターが同じ名前またはこのパラメーターと同じエイリアスのいずれかのあるパイプライン オブジェクトのプロパティから値を受け取ることを示します。 たとえば、次のコマンドレットがある、`Name`パラメーターと、パイプライン オブジェクトがあります、`Name`プロパティ、値の`Name`に割り当てられているプロパティ、`Name`コマンドレットのパラメーター。 既定値は `false` です。

`ValueFromRemainingArguments` ([System.Boolean](/dotnet/api/System.Boolean)) という名前のパラメーター (省略可能)。 `True` コマンドレット パラメーターをコマンドレットに渡されるすべての残りの引数を受け入れることを示します。 既定値は `false` です。

`HelpMessage` 名前付きパラメーターを省略可能です。 パラメーターの短い説明を指定します。 Windows PowerShell では、コマンドレットが実行され、必須のパラメーターが指定されていないときに、このメッセージが表示されます。

`HelpMessageBaseName` 名前付きパラメーターを省略可能です。リソース識別子が存在する場所を指定します。 たとえば、このパラメーターは、ローカライズするヘルプ メッセージを含むリソース アセンブリを指定できます。

`HelpMessageResourceId` 名前付きパラメーターを省略可能です。ヘルプ メッセージのリソース識別子を指定します。

## <a name="remarks"></a>コメント

- この属性を宣言する方法の詳細については、[コマンドレット パラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)を参照してください。

- コマンドレットは、任意の数のパラメーターを持つことができます。 ただし、ユーザー エクスペリエンスを向上させるには、パラメーターの数を制限します。

- パブリックの非静的フィールドまたはプロパティでは、パラメーターを宣言する必要があります。 プロパティでは、パラメーターを宣言する必要があります。 プロパティには、パブリック set アクセサーと場合、`ValueFromPipeline`または`ValueFromPipelineByPropertyName`キーワードを指定すると、プロパティは、public の get アクセサーをいる必要があります。

- 位置指定パラメーターを指定する場合は、5 未満に設定するパラメーターの位置指定パラメーターの数を制限します。 また、位置指定パラメーターは、連続している必要はありません。 5、100、および 250 の位置は、同じを位置 0、1、および 2 として機能します。

- ときに、`Position`キーワードが指定されていない、コマンドレット パラメーターは、名前で参照する必要があります。

- パラメーター セットを使用すると、次に注意してください。

    - 各パラメーターのセットには、少なくとも 1 つの一意のパラメーターが必要です。 適切なコマンドレットのデザインでは、この一意のパラメーターも必須にするか可能な場合を示します。 場合は、コマンドレットがパラメーターなしで動作するように設計、一意のパラメーターを必須にすることはできません。

    - パラメーター セットは同じ位置に 1 つ以上の位置指定パラメーターを含めることがない必要があります。

    - パラメーター セットで 1 つだけのパラメーターを宣言する必要があります`ValueFromPipeline = true`します。 複数のパラメーターを定義できます`ValueFromPipelineByPropertyName = true`します。

    - 複数のパラメーターを定義できます`ValueFromPipelineByPropertyName = true`します。

- パラメーター名に関するガイドラインの詳細については、[コマンドレットのパラメーター名](standard-cmdlet-parameter-names-and-types.md)を参照してください。

- パラメーター属性が定義した、 [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)クラス。

## <a name="see-also"></a>参照

[System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute)

[コマンドレットのパラメーター名](standard-cmdlet-parameter-names-and-types.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
