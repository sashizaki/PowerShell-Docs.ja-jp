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
ms.openlocfilehash: 49a62ccb09f06f77862d4737199e58293e7fbe0a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059254"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="8ae7e-102">資格情報属性の宣言</span><span class="sxs-lookup"><span data-stu-id="8ae7e-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="8ae7e-103">資格情報の属性は、型の資格情報パラメーターで使用できる省略可能な属性[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="8ae7e-104">Windows PowerShell がへの文字列入力を変換パラメーター宣言には、この属性を追加するときに、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="8ae7e-105">たとえば、 [Get-credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential)コマンドレットでは、この属性を使用して、Windows PowerShell の生成、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)コマンドレットによって返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ae7e-106">構文</span><span class="sxs-lookup"><span data-stu-id="8ae7e-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="8ae7e-107">コメント</span><span class="sxs-lookup"><span data-stu-id="8ae7e-107">Remarks</span></span>

- <span data-ttu-id="8ae7e-108">型のパラメーターでこの属性を使用する通常[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-108">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="8ae7e-109">ときに、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクトがパラメーターに渡されると、Windows PowerShell は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-109">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="8ae7e-110">作成するときに、 [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト、Windows PowerShell は、現在のホストを使用して、ユーザーに適切な指示を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-110">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="8ae7e-111">たとえば、既定のホストが表示されますユーザー名とパスワードを入力するプロンプトこの属性を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="8ae7e-112">ただし、カスタム ホストを使用している場合は、さまざまなプロンプトを定義するし、プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="8ae7e-113">この属性は、パラメーターの属性で使用されます。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="8ae7e-114">その属性の詳細については、[パラメーター属性宣言](./parameter-attribute-declaration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="8ae7e-115">資格情報の属性を定義した、 [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="8ae7e-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ae7e-116">参照</span><span class="sxs-lookup"><span data-stu-id="8ae7e-116">See Also</span></span>

[<span data-ttu-id="8ae7e-117">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="8ae7e-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="8ae7e-118">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="8ae7e-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="8ae7e-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="8ae7e-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
