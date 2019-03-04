---
title: コマンドレット属性 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.assetid: d3f4f652-d929-4c27-9358-9baa390a094c
caps.latest.revision: 14
ms.openlocfilehash: b06faf7204213b383b25685837941ad63dcb225b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853918"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="e07a3-102">コマンドレットの属性</span><span class="sxs-lookup"><span data-stu-id="e07a3-102">Cmdlet Attributes</span></span>

<span data-ttu-id="e07a3-103">Windows PowerShell では、独自のコード内でその機能を実装することがなく、コマンドレットに共通の機能を追加するのに使用できるいくつかの属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-103">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="e07a3-104">これには、コマンドレット クラスでコマンドレットとしてパブリック プロパティを識別するパラメーターの属性がコマンドレットによって返される .NET Framework 型を指定する OutputType 属性として Microsoft .NET Framework クラスを識別するコマンドレットの属性が含まれますパラメーター、および詳細。</span><span class="sxs-lookup"><span data-stu-id="e07a3-104">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e07a3-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e07a3-105">In This Section</span></span>

<span data-ttu-id="e07a3-106">[コマンドレット コード内の属性](./attributes-in-cmdlet-code.md)コマンドレットのコードで属性を使用する利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-106">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="e07a3-107">[属性型](./attribute-types.md)装飾できるは、コマンドレット クラスを別の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-107">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="e07a3-108">[属性の宣言にエイリアス](./alias-attribute-declaration.md)コマンドレットのパラメーター名のエイリアスを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-108">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="e07a3-109">[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)コマンドレットとして .NET Framework クラスを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-109">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="e07a3-110">[資格情報の属性宣言](./credential-attribute-declaration.md)への入力を文字列に変換するためのサポートを追加する方法について説明します、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e07a3-110">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="e07a3-111">[OutputType 属性宣言](./outputtype-attribute-declaration.md)コマンドレットによって返される .NET Framework 型を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-111">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="e07a3-112">[パラメーター属性宣言](./parameter-attribute-declaration.md)コマンドレットのパラメーターを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-112">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="e07a3-113">[属性の宣言は ValidateCount](./validatecount-attribute-declaration.md)パラメーターの引数の数が許可されているかを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-113">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="e07a3-114">[属性の宣言は ValidateLength](./validatelength-attribute-declaration.md) (文字) でパラメーターの引数の長さを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-114">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="e07a3-115">[ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)パラメーターの引数の有効なパターンを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-115">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="e07a3-116">[属性の宣言は ValidateRange](./validaterange-attribute-declaration.md)パラメーターの引数の有効な範囲を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-116">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="e07a3-117">[属性の宣言は ValidateSet](./validateset-attribute-declaration.md)パラメーターの引数の値を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e07a3-117">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="e07a3-118">参照先</span><span class="sxs-lookup"><span data-stu-id="e07a3-118">Reference</span></span>

[<span data-ttu-id="e07a3-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="e07a3-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
