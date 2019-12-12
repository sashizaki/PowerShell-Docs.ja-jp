---
title: コマンドレットのパラメーターセット |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f902fd4d-8f6e-4ef1-b07f-59983039a0d1
caps.latest.revision: 10
ms.openlocfilehash: dfe747893b4aef6376ea3b12dd79b7c144455ed0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74415691"
---
# <a name="cmdlet-parameter-sets"></a>コマンドレットのパラメーターセット

PowerShell では、パラメーターセットを使用して、さまざまなシナリオに対して異なるアクションを実行できる単一のコマンドレットを作成できます。 パラメーターセットを使用すると、さまざまなパラメーターをユーザーに公開できます。 また、ユーザーが指定したパラメーターに基づいて異なる情報を返すことができます。

## <a name="examples-of-parameter-sets"></a>パラメーターセットの例

たとえば、PowerShell `Get-EventLog` コマンドレットは、ユーザーが**List**パラメーターまたは**LogName**パラメーターを指定したかどうかに応じて異なる情報を返します。 **List**パラメーターが指定されている場合、コマンドレットはログファイル自体に関する情報を返しますが、含まれているイベント情報は返しません。 **LogName**パラメーターを指定すると、コマンドレットは、特定のイベントログ内のイベントに関する情報を返します。 **List**および**LogName**パラメーターは、2つの異なるパラメーターセットを識別します。

## <a name="unique-parameter"></a>一意のパラメーター

各パラメーターセットには、適切なパラメーターセットを公開するために PowerShell ランタイムが使用する一意のパラメーターが必要です。 可能であれば、unique パラメーターは必須パラメーターである必要があります。 パラメーターが必須の場合、ユーザーはパラメーターを指定する必要があり、PowerShell ランタイムはそのパラメーターを使用してパラメーターセットを識別します。 コマンドレットがパラメーターを指定せずに実行するように設計されている場合、unique パラメーターを必須にすることはできません。

## <a name="multiple-parameter-sets"></a>複数のパラメーターセット

次の図では、左側の列に3つの有効なパラメーターセットが示されています。 **パラメーター a**は最初のパラメーターセットに対して一意で、**パラメーター B**は2番目のパラメーターセットに対して一意であり、**パラメーター C**は3番目のパラメーターセットに対して一意です。 右側の列では、パラメーターセットに一意のパラメーターがありません。

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a>パラメーターセットの要件

すべてのパラメーターセットには、次の要件が適用されます。

- 各パラメーターセットには、少なくとも1つの一意のパラメーターが必要です。 可能であれば、このパラメーターを必須パラメーターにします。

- 複数の位置指定パラメーターを含むパラメーターセットでは、パラメーターごとに一意の位置を定義する必要があります。 2つの位置指定パラメーターで同じ位置を指定することはできません。

- 値が `true`の `ValueFromPipeline` キーワードを宣言できるのは、セット内の1つのパラメーターだけです。
  複数のパラメーターで、`true`の値を持つ `ValueFromPipelineByPropertyName` キーワードを定義できます。

- パラメーターにパラメーターセットが指定されていない場合、パラメーターはすべてのパラメーターセットに属します。

> [!NOTE]
> コマンドレットまたは関数の場合、32パラメーターセットの制限があります。

## <a name="default-parameter-sets"></a>既定のパラメーターセット

複数のパラメーターセットが定義されている場合は、**コマンドレット**属性の `DefaultParameterSetName` キーワードを使用して、既定のパラメーターセットを指定できます。 PowerShell では、コマンドによって提供される情報に基づいて、使用するパラメーターセットを特定できない場合、既定のパラメーターセットが使用されます。 **コマンドレット**属性の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。

## <a name="declaring-parameter-sets"></a>パラメーターセットの宣言

パラメーターセットを作成するには、パラメーターセット内のすべてのパラメーターの**パラメーター**属性を宣言するときに、`ParameterSetName` キーワードを指定する必要があります。 複数のパラメーターセットに属するパラメーターの場合は、パラメーターセットごとに**パラメーター**属性を追加します。 この属性を使用すると、パラメーターセットごとに異なる方法でパラメーターを定義できます。 たとえば、あるセットでは必須として、別のセットでは省略可能なパラメーターを定義できます。 ただし、各パラメーターセットには一意のパラメーターを1つ含める必要があります。 詳細については、「[パラメーター属性の宣言](parameter-attribute-declaration.md)」を参照してください。

次の例では、 **UserName**パラメーターは `Test01` パラメーターセットの一意のパラメーターであり、 **ComputerName**パラメーターは `Test02` パラメーターセットの一意のパラメーターです。 **Sharedparam**パラメーターは両方のセットに属しており、`Test01` パラメーターセットでは必須ですが、`Test02` パラメーターセットでは省略可能です。

```csharp
[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test02")]
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
private string sharedParam;
```
