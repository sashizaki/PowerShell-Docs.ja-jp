---
title: コマンドレットの属性 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.openlocfilehash: f22c2882fbe5b2f51ca5ea218b921192b0a7d41f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784522"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="d683f-102">コマンドレットの属性</span><span class="sxs-lookup"><span data-stu-id="d683f-102">Cmdlet Attributes</span></span>

<span data-ttu-id="d683f-103">Windows PowerShell では、コマンドレットに共通機能を追加するために使用できるいくつかの属性が定義されています。独自のコード内でその機能を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d683f-103">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="d683f-104">これには、コマンドレットクラスとして Microsoft .NET Framework クラスを識別するコマンドレット属性、コマンドレットによって返される .NET Framework 型を指定する OutputType 属性、コマンドレットパラメーターとしてパブリックプロパティを識別するパラメーター属性などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d683f-104">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d683f-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d683f-105">In This Section</span></span>

<span data-ttu-id="d683f-106">[コマンドレットコードの属性](./attributes-in-cmdlet-code.md)コマンドレットコードで属性を使用する利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-106">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="d683f-107">[属性の型](./attribute-types.md)コマンドレットクラスを修飾できるさまざまな属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-107">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="d683f-108">[エイリアス属性の宣言](./alias-attribute-declaration.md)コマンドレットパラメーター名のエイリアスを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-108">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="d683f-109">[コマンドレットの属性宣言](./cmdlet-attribute-declaration.md).NET Framework クラスをコマンドレットとして定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-109">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="d683f-110">[Credential 属性の宣言](./credential-attribute-declaration.md)文字列入力を system.string オブジェクトに変換するためのサポートを追加する方法について説明[します。](/dotnet/api/System.Management.Automation.PSCredential)</span><span class="sxs-lookup"><span data-stu-id="d683f-110">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="d683f-111">[OutputType 属性の宣言](./outputtype-attribute-declaration.md)コマンドレットによって返される .NET Framework 型を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-111">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="d683f-112">[パラメーター属性の宣言](./parameter-attribute-declaration.md)コマンドレットのパラメーターを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-112">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="d683f-113">[Validatecount 属性の宣言](./validatecount-attribute-declaration.md)パラメーターで許容される引数の数を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-113">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="d683f-114">[ValidateLength 属性の宣言](./validatelength-attribute-declaration.md)パラメーター引数の長さ (文字数) を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-114">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="d683f-115">[Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)パラメーター引数の有効なパターンを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-115">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="d683f-116">[ValidateRange 属性の宣言](./validaterange-attribute-declaration.md)パラメーター引数の有効な範囲を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-116">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="d683f-117">[Validateset 属性の宣言](./validateset-attribute-declaration.md)パラメーター引数に使用できる値を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d683f-117">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="d683f-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="d683f-118">Reference</span></span>

[<span data-ttu-id="d683f-119">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="d683f-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
