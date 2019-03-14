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
ms.openlocfilehash: 1513d340cdadc5cb7622e791cc3c163ff39dfe1d
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795404"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="022bc-102">資格情報属性の宣言</span><span class="sxs-lookup"><span data-stu-id="022bc-102">Credential Attribute Declaration</span></span>

<span data-ttu-id="022bc-103">資格情報の属性は、型の資格情報パラメーターで使用できる省略可能な属性[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="022bc-103">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="022bc-104">Windows PowerShell がへの文字列入力を変換パラメーター宣言には、この属性を追加するときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="022bc-104">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="022bc-105">たとえば、 [Get-credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential)コマンドレットでは、この属性を使用して、Windows PowerShell の生成、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)コマンドレットによって返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="022bc-105">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="022bc-106">構文</span><span class="sxs-lookup"><span data-stu-id="022bc-106">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="022bc-107">コメント</span><span class="sxs-lookup"><span data-stu-id="022bc-107">Remarks</span></span>

- <span data-ttu-id="022bc-108">型のパラメーターでこの属性を使用する通常[System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)をパラメーターに文字列が引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="022bc-108">Typically this attribute is used by parameters of type [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="022bc-109">ときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクトがパラメーターに渡されると、Windows PowerShell は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="022bc-109">When a [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="022bc-110">作成するときに、 [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential)オブジェクト、Windows PowerShell は、現在のホストを使用して、ユーザーに適切な指示を表示します。</span><span class="sxs-lookup"><span data-stu-id="022bc-110">When creating the [System.Management.Automation.Pscredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="022bc-111">たとえば、既定のホストが表示されますユーザー名とパスワードを入力するプロンプトこの属性を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="022bc-111">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="022bc-112">ただし、カスタム ホストを使用している場合は、さまざまなプロンプトを定義するし、プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="022bc-112">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="022bc-113">この属性は、パラメーターの属性で使用されます。</span><span class="sxs-lookup"><span data-stu-id="022bc-113">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="022bc-114">その属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="022bc-114">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="022bc-115">資格情報の属性を定義した、 [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute)クラス。</span><span class="sxs-lookup"><span data-stu-id="022bc-115">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="022bc-116">参照</span><span class="sxs-lookup"><span data-stu-id="022bc-116">See Also</span></span>

[<span data-ttu-id="022bc-117">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="022bc-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="022bc-118">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="022bc-118">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="022bc-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="022bc-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
