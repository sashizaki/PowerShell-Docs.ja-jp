---
title: ValidateCount 属性の宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.openlocfilehash: c013a354ee339bd14508fe30549673bc79d5c616
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786324"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="18245-102">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="18245-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="18245-103">ValidateCount 属性では、コマンドレットパラメーターに許可される引数の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="18245-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="18245-104">構文</span><span class="sxs-lookup"><span data-stu-id="18245-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="18245-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18245-105">Parameters</span></span>

<span data-ttu-id="18245-106">`MinLength`([System.string][]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="18245-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="18245-107">引数の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="18245-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="18245-108">`MaxLength`([System.string][]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="18245-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="18245-109">引数の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="18245-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="18245-110">解説</span><span class="sxs-lookup"><span data-stu-id="18245-110">Remarks</span></span>

- <span data-ttu-id="18245-111">この属性を宣言する方法の詳細については、「[引数カウントを検証する方法][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18245-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="18245-112">この属性が呼び出されない場合、対応するコマンドレットパラメーターには任意の数の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="18245-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="18245-113">Windows PowerShell ランタイムは、次の状況でエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="18245-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

  - <span data-ttu-id="18245-114">`MinLength`属性と `MaxLength` 属性のパラメーターが、system.string [System.Int32][]型ではありません。</span><span class="sxs-lookup"><span data-stu-id="18245-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

  - <span data-ttu-id="18245-115">属性パラメーターの値 `MaxLength` が、属性パラメーターの値未満です `MinLength` 。</span><span class="sxs-lookup"><span data-stu-id="18245-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="18245-116">ValidateCount 属性は、 [system.string クラスに][]よって定義されています。</span><span class="sxs-lookup"><span data-stu-id="18245-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="18245-117">参照</span><span class="sxs-lookup"><span data-stu-id="18245-117">See Also</span></span>

<span data-ttu-id="18245-118">[System. Automation. ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="18245-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="18245-119">[引数カウントを検証する方法][]</span><span class="sxs-lookup"><span data-stu-id="18245-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="18245-120">[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)][]</span><span class="sxs-lookup"><span data-stu-id="18245-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[引数カウントを検証する方法]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
