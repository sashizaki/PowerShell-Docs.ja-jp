---
ms.date: 09/13/2016
ms.topic: reference
title: 資格情報属性の宣言
description: 資格情報属性の宣言
ms.openlocfilehash: fb826d9a46cadc021fe0c667091bbc7a9251aaa8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648594"
---
# <a name="credential-attribute-declaration"></a><span data-ttu-id="d1a6c-103">資格情報属性の宣言</span><span class="sxs-lookup"><span data-stu-id="d1a6c-103">Credential Attribute Declaration</span></span>

<span data-ttu-id="d1a6c-104">Credential 属性は省略可能な属性であり、文字列を引数としてパラメーターに渡すこともできるように、型 system.servicemodel の credential パラメーターと共に使用[できます。](/dotnet/api/System.Management.Automation.PSCredential)</span><span class="sxs-lookup"><span data-stu-id="d1a6c-104">The Credential attribute is an optional attribute that can be used with credential parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="d1a6c-105">この属性がパラメーター宣言に追加されると、Windows PowerShell は文字列入力を system.string [オブジェクトに](/dotnet/api/System.Management.Automation.PSCredential) 変換します。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-105">When this attribute is added to a parameter declaration, Windows PowerShell converts the string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span> <span data-ttu-id="d1a6c-106">たとえば、 [Get Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) コマンドレットでは、この属性を使用して、Windows PowerShell に対して、コマンドレットによって返される [system.servicemodel オブジェクトが](/dotnet/api/System.Management.Automation.PSCredential) 生成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-106">For example, the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet uses this attribute to have Windows PowerShell generate the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object that is returned by the cmdlet.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1a6c-107">構文</span><span class="sxs-lookup"><span data-stu-id="d1a6c-107">Syntax</span></span>

```csharp
[Credential]
```

## <a name="remarks"></a><span data-ttu-id="d1a6c-108">解説</span><span class="sxs-lookup"><span data-stu-id="d1a6c-108">Remarks</span></span>

- <span data-ttu-id="d1a6c-109">通常、この属性は、文字列を引数としてパラメーターに渡すことが [できるように、型](/dotnet/api/System.Management.Automation.PSCredential) system.servicemodel のパラメーターによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-109">Typically this attribute is used by parameters of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) so that a string can also be passed as an argument to the parameter.</span></span> <span data-ttu-id="d1a6c-110">System.string オブジェクト [が](/dotnet/api/System.Management.Automation.PSCredential) パラメーターに渡されると、Windows PowerShell は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-110">When a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object is passed to the parameter, Windows PowerShell does nothing.</span></span>

- <span data-ttu-id="d1a6c-111">Windows PowerShell で [は、system.servicemodel オブジェクトを](/dotnet/api/System.Management.Automation.PSCredential) 作成するときに、現在のホストを使用してユーザーに適切なプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-111">When creating the [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object, Windows PowerShell uses the current Host to display the appropriate prompts to the user.</span></span> <span data-ttu-id="d1a6c-112">たとえば、既定のホストでは、この属性を使用するときに、ユーザー名とパスワードの入力を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-112">For example, the default Host displays a prompt for a user name and password when this attribute is used.</span></span> <span data-ttu-id="d1a6c-113">ただし、別のプロンプトを定義するカスタムホストが使用されている場合は、そのプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-113">However, if a custom host is being used that defines a different prompt then that prompt would be displayed.</span></span>

- <span data-ttu-id="d1a6c-114">この属性は、Parameter 属性と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-114">This attribute is used with the Parameter attribute.</span></span> <span data-ttu-id="d1a6c-115">この属性の詳細については、「 [パラメーター属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-115">For more information about that attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

- <span data-ttu-id="d1a6c-116">Credential 属性は、system.servicemodel [属性](/dotnet/api/System.Management.Automation.CredentialAttribute) クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="d1a6c-116">The credential attribute is defined by the [System.Management.Automation.Credentialattribute](/dotnet/api/System.Management.Automation.CredentialAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1a6c-117">参照</span><span class="sxs-lookup"><span data-stu-id="d1a6c-117">See Also</span></span>

[<span data-ttu-id="d1a6c-118">パラメーターのエイリアス</span><span class="sxs-lookup"><span data-stu-id="d1a6c-118">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="d1a6c-119">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="d1a6c-119">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="d1a6c-120">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d1a6c-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
