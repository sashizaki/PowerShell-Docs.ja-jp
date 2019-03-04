---
title: 資格情報の属性の宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96a5dcad-faed-44d8-8c80-321f10499710
caps.latest.revision: 6
ms.openlocfilehash: abdd6e915b768b8ac688b6fc8c3194723961765e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863398"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="ae1f9-102">資格情報属性の宣言</span><span class="sxs-lookup"><span data-stu-id="ae1f9-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="ae1f9-103">資格情報の属性は、型の資格情報パラメーターで使用できる省略可能な属性[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="ae1f9-104">Windows PowerShell がへの文字列入力を変換パラメーター宣言には、この属性を追加するときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="ae1f9-105">たとえば、 [Get-credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential)コマンドレットでは、この属性を使用して、Windows PowerShell の生成、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)コマンドレットによって返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>
<span data-ttu-id="ae1f9-106">資格情報の属性は、型の資格情報パラメーターで使用できる省略可能な属性[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-106">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="ae1f9-107">Windows PowerShell がへの文字列入力を変換パラメーター宣言には、この属性を追加するときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-107">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="ae1f9-108">たとえば、 [Get-credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential)コマンドレットでは、この属性を使用して、Windows PowerShell の生成、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)コマンドレットによって返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-108">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae1f9-109">構文</span><span class="sxs-lookup"><span data-stu-id="ae1f9-109">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="ae1f9-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ae1f9-110">Remarks</span></span>

- <span data-ttu-id="ae1f9-111">型のパラメーターでこの属性を使用する通常[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-111">Typically this attribute is used by parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="ae1f9-112">ときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクトがパラメーターに渡されると、Windows PowerShell は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-112">When a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="ae1f9-113">作成するときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト、Windows PowerShell は、現在のホストを使用して、ユーザーに適切な指示を表示します。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-113">When creating the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="ae1f9-114">たとえば、既定のホストが表示されますユーザー名とパスワードを入力するプロンプトこの属性を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-114">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="ae1f9-115">ただし、カスタム ホストを使用している場合は、さまざまなプロンプトを定義するし、プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-115">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="ae1f9-116">この属性は、パラメーターの属性で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-116">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="ae1f9-117">その属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-117">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="ae1f9-118">資格情報の属性を定義した、 [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="ae1f9-118">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae1f9-119">参照</span><span class="sxs-lookup"><span data-stu-id="ae1f9-119">See Also</span></span>

[<span data-ttu-id="ae1f9-120">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="ae1f9-120">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="ae1f9-121">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="ae1f9-121">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="ae1f9-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ae1f9-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
