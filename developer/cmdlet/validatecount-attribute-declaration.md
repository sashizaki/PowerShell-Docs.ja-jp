---
title: ValidateCount 属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067180"
---
# <a name="validatecount-attribute-declaration"></a><span data-ttu-id="7e426-102">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="7e426-102">ValidateCount Attribute Declaration</span></span>

<span data-ttu-id="7e426-103">ValidateCount 属性には、コマンドレット パラメーターの許可されている引数の最小値と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e426-103">The ValidateCount attribute specifies the minimum and maximum number of arguments allowed for a cmdlet parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e426-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e426-104">Syntax</span></span>

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a><span data-ttu-id="7e426-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e426-105">Parameters</span></span>

<span data-ttu-id="7e426-106">`MinLength` ([System.Int32][]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="7e426-106">`MinLength` ([System.Int32][]) Required.</span></span> <span data-ttu-id="7e426-107">引数の最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e426-107">Specifies the minimum number of arguments.</span></span>

<span data-ttu-id="7e426-108">`MaxLength`([System.Int32][]) が必要です。</span><span class="sxs-lookup"><span data-stu-id="7e426-108">`MaxLength`([System.Int32][]) Required.</span></span> <span data-ttu-id="7e426-109">引数の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e426-109">Specifies the maximum number of arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e426-110">コメント</span><span class="sxs-lookup"><span data-stu-id="7e426-110">Remarks</span></span>

- <span data-ttu-id="7e426-111">この属性を宣言する方法の詳細については、次を参照してください。[引数の数を検証する方法][]します。</span><span class="sxs-lookup"><span data-stu-id="7e426-111">For more information about how to declare this attribute, see [How to Validate an Argument Count][].</span></span>

- <span data-ttu-id="7e426-112">この属性がない呼び出されると、コマンドレットの対応するパラメーターに任意の数の引数のことができます。</span><span class="sxs-lookup"><span data-stu-id="7e426-112">When this attribute is not invoked, the corresponding cmdlet parameter can have any number of arguments.</span></span>

- <span data-ttu-id="7e426-113">Windows PowerShell ランタイムには、次の条件下でエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="7e426-113">The Windows PowerShell runtime throws an error under the following conditions:</span></span>

    - <span data-ttu-id="7e426-114">`MinLength`と`MaxLength`型の属性のパラメーターがない[System.Int32][]します。</span><span class="sxs-lookup"><span data-stu-id="7e426-114">The `MinLength` and `MaxLength` attribute parameters are not of type [System.Int32][].</span></span>

    - <span data-ttu-id="7e426-115">値、`MaxLength`属性パラメーターは、の値より小さい、`MinLength`属性パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7e426-115">The value of the `MaxLength` attribute parameter is less than the value of the `MinLength` attribute parameter.</span></span>

- <span data-ttu-id="7e426-116">ValidateCount 属性を定義した、 [System.Management.Automation.ValidateCountAttribute][]クラス。</span><span class="sxs-lookup"><span data-stu-id="7e426-116">The ValidateCount attribute is defined by the [System.Management.Automation.ValidateCountAttribute][] class.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e426-117">参照</span><span class="sxs-lookup"><span data-stu-id="7e426-117">See Also</span></span>

<span data-ttu-id="7e426-118">[System.Management.Automation.ValidateCountAttribute][]</span><span class="sxs-lookup"><span data-stu-id="7e426-118">[System.Management.Automation.ValidateCountAttribute][]</span></span>

<span data-ttu-id="7e426-119">[引数の数を検証する方法][]</span><span class="sxs-lookup"><span data-stu-id="7e426-119">[How to Validate an Argument Count][]</span></span>

<span data-ttu-id="7e426-120">[Windows PowerShell コマンドレットの記述][]</span><span class="sxs-lookup"><span data-stu-id="7e426-120">[Writing a Windows PowerShell Cmdlet][]</span></span>

[引数の数を検証する方法]: how-to-validate-an-argument-count.md
[How to Validate an Argument Count]: how-to-validate-an-argument-count.md
[Windows PowerShell コマンドレットの記述]: writing-a-windows-powershell-cmdlet.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.Management.Automation.ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
