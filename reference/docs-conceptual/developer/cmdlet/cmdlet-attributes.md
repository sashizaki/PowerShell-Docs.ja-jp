---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレットの属性
description: コマンドレットの属性
ms.openlocfilehash: 6a106f33cb34c6c33b88a981815543bc9af4e4ba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653522"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="9c48b-103">コマンドレットの属性</span><span class="sxs-lookup"><span data-stu-id="9c48b-103">Cmdlet Attributes</span></span>

<span data-ttu-id="9c48b-104">Windows PowerShell では、コマンドレットに共通機能を追加するために使用できるいくつかの属性が定義されています。独自のコード内でその機能を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c48b-104">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="9c48b-105">これには、コマンドレットクラスとして Microsoft .NET Framework クラスを識別するコマンドレット属性、コマンドレットによって返される .NET Framework 型を指定する OutputType 属性、コマンドレットパラメーターとしてパブリックプロパティを識別するパラメーター属性などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c48b-105">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9c48b-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9c48b-106">In This Section</span></span>

<span data-ttu-id="9c48b-107">[コマンドレットコードの属性](./attributes-in-cmdlet-code.md) コマンドレットコードで属性を使用する利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-107">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="9c48b-108">[属性の型](./attribute-types.md) コマンドレットクラスを修飾できるさまざまな属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-108">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="9c48b-109">[エイリアス属性の宣言](./alias-attribute-declaration.md) コマンドレットパラメーター名のエイリアスを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-109">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="9c48b-110">[コマンドレットの属性宣言](./cmdlet-attribute-declaration.md) .NET Framework クラスをコマンドレットとして定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-110">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="9c48b-111">[Credential 属性の宣言](./credential-attribute-declaration.md)文字列入力を system.string オブジェクトに変換するためのサポートを追加する方法について説明[します。](/dotnet/api/System.Management.Automation.PSCredential)</span><span class="sxs-lookup"><span data-stu-id="9c48b-111">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="9c48b-112">[OutputType 属性の宣言](./outputtype-attribute-declaration.md) コマンドレットによって返される .NET Framework 型を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-112">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="9c48b-113">[パラメーター属性の宣言](./parameter-attribute-declaration.md) コマンドレットのパラメーターを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-113">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="9c48b-114">[Validatecount 属性の宣言](./validatecount-attribute-declaration.md) パラメーターで許容される引数の数を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-114">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="9c48b-115">[ValidateLength 属性の宣言](./validatelength-attribute-declaration.md) パラメーター引数の長さ (文字数) を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-115">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="9c48b-116">[Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md) パラメーター引数の有効なパターンを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-116">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="9c48b-117">[ValidateRange 属性の宣言](./validaterange-attribute-declaration.md) パラメーター引数の有効な範囲を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-117">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="9c48b-118">[Validateset 属性の宣言](./validateset-attribute-declaration.md) パラメーター引数に使用できる値を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c48b-118">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="9c48b-119">リファレンス</span><span class="sxs-lookup"><span data-stu-id="9c48b-119">Reference</span></span>

[<span data-ttu-id="9c48b-120">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="9c48b-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
