---
title: コマンドレットのパラメーターの設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f902fd4d-8f6e-4ef1-b07f-59983039a0d1
caps.latest.revision: 10
ms.openlocfilehash: a5822ef1ed3c9efb5957c20255783d515de8957a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068524"
---
# <a name="cmdlet-parameter-sets"></a>コマンドレット パラメーター セット

Windows PowerShell では、パラメーター セットを使用して、さまざまなシナリオのさまざまなアクションを実行できる 1 つのコマンドレットを記述できるようにします。 パラメーター セットを使用すると、ユーザーに異なるパラメーターを公開して、ユーザーによって指定されたパラメーターに基づいて異なる情報を返すことができます。

## <a name="examples-of-parameter-sets"></a>パラメーター セットの例

たとえば、`Get-EventLog`コマンドレット (Windows PowerShell によって提供される) は、ユーザーを指定するかどうかに応じて、異なる情報を返します、`List`または`LogName`パラメーター。 場合、`List`パラメーターを指定すると、自体が含まれているイベント情報ではなく、コマンドレットは、ログ ファイルに関する情報を返します。 場合、`LogName`パラメーターを指定すると、cmdlet は、特定のイベント ログでイベントについての情報を返します。 `List`と`LogName`パラメーターが 2 つの個別のパラメーター セットを識別します。

## <a name="unique-parameter"></a>一意のパラメーター

各パラメーターのセットには、適切なパラメーター セットを公開する、Windows PowerShell ランタイムが使用できる一意のパラメーターが必要です。 可能であれば、一意のパラメーターには、必須のパラメーターがあります。 パラメーターが必須の場合は、パラメーターを指定するユーザーが強制実行され、Windows PowerShell ランタイムは、パラメーターを使用する設定を識別するためにそのパラメーターを使用することができます。 一意のパラメーターは、パラメーターを指定せずに実行するコマンドレットが設計されている場合に必須にすることはできません。

## <a name="multiple-parameter-sets"></a>複数のパラメーター セット

次の図では、左側の列は、次の 3 つの有効なパラメーター セットを表示します。 パラメーター A が最初のパラメーターのセットに一意、B のパラメーターが 2 番目のパラメーターのセットに一意およびパラメーター C は 3 番目のパラメーターのセットに一意です。 ただし、右側の列にパラメーター セットはありません、一意のパラメーター。

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a>パラメーター セットの要件

次の要件は、すべてのパラメーター セットに適用されます。

- 各パラメーターのセットには、少なくとも 1 つの一意のパラメーターが必要です。 可能であれば、このパラメーターは必須のパラメーターを確認します。

- 複数の位置指定パラメーターを含むパラメーター セットでは、パラメーターごとに一意の位置を定義する必要があります。 2 つの位置指定パラメーターなしでは、同じ位置を指定できます。

- セット内の 1 つだけのパラメーターを宣言できます、`ValueFromPipeline`キーワードの値を持つ`true`します。 複数のパラメーターを定義できます、`ValueFromPipelineByPropertyName`キーワードの値を持つ`true`します。

- パラメーターのパラメーター セットが指定されていない場合、パラメーターは、すべてのパラメーター セットに属しています。

## <a name="default-parameter-sets"></a>既定のパラメーター セット

複数のパラメーター セットが定義されているときに使用できます、`DefaultParameterSetName`コマンドレットの既定のパラメーター セットを指定する属性のキーワード。 Windows PowerShell では、コマンドによって提供される情報に基づいて、パラメーターを使用する設定を判断できない場合は、設定、既定のパラメーターを使用します。 コマンドレットの属性の詳細については、次を参照してください。[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。

## <a name="declaring-parameter-sets"></a>パラメーター セットを宣言します。

パラメーター セットを作成することを指定する必要があります、`ParameterSetName`パラメーター セットのすべてのパラメーターのパラメーターの属性を宣言するときに、キーワード。 パラメーターの複数のパラメーター セットに属している場合に、各パラメーター セットのパラメーターの属性を追加します。 これにより、パラメーターのセットごとに異なるパラメーターを定義することができます。 たとえば、1 つのセットで必須で、別のオプションとして、パラメーターを定義できます。 ただし、各パラメーター セットは、1 つの一意のパラメーターを含める必要があります。

次の例では、`UserName`パラメーター Test01 パラメーター セットの一意のパラメーターでは、`ComputerName`は Test02 パラメーター セットの一意のパラメーター。 `SharedParam`パラメーターは、両方のセットに属しているし、ただし Test02 パラメーター セットの省略可能な設定 Test01 パラメーターは必須です。

```csharp
[Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test02")]
public string ComputerName
{
  get { return computerName; }
  set { computerName = value; }
}
private string computerName;

[Parameter(Mandatory= true, ParameterSetName = "Test01")]
[Parameter(ParameterSetName = "Test02")]
public string SharedParam
{
    get { return sharedParam; }
    set { sharedParam = value; }
}
private string sharedParam;    [Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```