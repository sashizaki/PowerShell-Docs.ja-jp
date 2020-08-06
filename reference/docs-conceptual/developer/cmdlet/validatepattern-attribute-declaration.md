---
title: ValidatePattern 属性宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787803"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="996ed-102">ValidatePattern 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="996ed-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="996ed-103">ValidatePattern 属性は、コマンドレットパラメーターの引数を検証する正規表現パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="996ed-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="996ed-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="996ed-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="996ed-105">ValidatePattern がコマンドレット内で呼び出されると、Windows PowerShell ランタイムはコマンドレットパラメーターの引数を文字列に変換し、その文字列を ValidatePattern 属性によって指定されたパターンと比較します。</span><span class="sxs-lookup"><span data-stu-id="996ed-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="996ed-106">コマンドレットは、変換された引数の文字列形式と、指定されたパターンが一致する場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="996ed-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="996ed-107">一致しない場合は、Windows PowerShell ランタイムによってエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="996ed-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="996ed-108">構文</span><span class="sxs-lookup"><span data-stu-id="996ed-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="996ed-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="996ed-109">Parameters</span></span>

<span data-ttu-id="996ed-110">`RegexString`([System.string](/dotnet/api/System.String)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="996ed-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="996ed-111">パラメーター引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="996ed-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="996ed-112">オプション ([system.text.regularexpressions.regexoptions. Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) 省略可能な名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="996ed-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="996ed-113">正規表現オプションを指定する[system.text.regularexpressions.regexoptions の Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)フラグのビットごとの組み合わせを指定します。</span><span class="sxs-lookup"><span data-stu-id="996ed-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="996ed-114">解説</span><span class="sxs-lookup"><span data-stu-id="996ed-114">Remarks</span></span>

- <span data-ttu-id="996ed-115">この属性は、パラメーターごとに1回だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="996ed-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="996ed-116">属性のパラメーターを使用して、 `Option` パターンをさらに定義できます。</span><span class="sxs-lookup"><span data-stu-id="996ed-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="996ed-117">たとえば、パターンの大文字と小文字を区別することができます。</span><span class="sxs-lookup"><span data-stu-id="996ed-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="996ed-118">この属性をコレクションに適用する場合は、コレクション内の各要素がパターンと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="996ed-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="996ed-119">ValidatePattern 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="996ed-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="996ed-120">参照</span><span class="sxs-lookup"><span data-stu-id="996ed-120">See Also</span></span>

[<span data-ttu-id="996ed-121">システムの管理. Validatepattern 属性</span><span class="sxs-lookup"><span data-stu-id="996ed-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="996ed-122">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="996ed-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
