---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレットの動的パラメーター
description: コマンドレットの動的パラメーター
ms.openlocfilehash: b44dda2354e8b689e419c7bf4deefadfc4edcb07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653432"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="43803-103">コマンドレット動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="43803-103">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="43803-104">コマンドレットでは、他のパラメーターの引数が特定の値の場合など、特殊な条件下でユーザーが使用できるパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="43803-104">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="43803-105">これらのパラメーターは、必要なときにのみ追加されるため、実行時に追加され、動的パラメーターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="43803-105">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="43803-106">たとえば、特定のスイッチパラメーターが指定されている場合にのみ、いくつかのパラメーターを追加するコマンドレットを設計できます。</span><span class="sxs-lookup"><span data-stu-id="43803-106">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="43803-107">プロバイダーと PowerShell 関数では、動的パラメーターを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="43803-107">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="43803-108">PowerShell コマンドレットの動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="43803-108">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="43803-109">PowerShell では、プロバイダーコマンドレットのいくつかで動的パラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="43803-109">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="43803-110">たとえば、 `Get-Item` `Get-ChildItem` コマンドレットとコマンドレットは、 **Path** パラメーターで **証明書** プロバイダーのパスを指定した場合に、実行時に **codesigningcert** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="43803-110">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="43803-111">**Path** パラメーターに別のプロバイダーのパスが指定されている場合、 **Codesigningcert** パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="43803-111">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="43803-112">次の例は、を実行したときに、実行時に **Codesigningcert** パラメーターがどのように追加されるかを示してい `Get-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="43803-112">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="43803-113">この例では、PowerShell ランタイムによってパラメーターが追加され、コマンドレットが正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="43803-113">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="43803-114">この例では、 **ファイルシステム** ドライブが指定され、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="43803-114">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="43803-115">エラーメッセージは、 **Codesigningcert** パラメーターが見つからないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="43803-115">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="43803-116">動的パラメーターのサポート</span><span class="sxs-lookup"><span data-stu-id="43803-116">Support for dynamic parameters</span></span>

<span data-ttu-id="43803-117">動的パラメーターをサポートするには、次の要素をコマンドレットコードに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="43803-117">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="43803-118">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43803-118">Interface</span></span>

<span data-ttu-id="43803-119">[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters)のようになります。</span><span class="sxs-lookup"><span data-stu-id="43803-119">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="43803-120">このインターフェイスは、動的パラメーターを取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="43803-120">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="43803-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43803-121">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="43803-122">Method</span><span class="sxs-lookup"><span data-stu-id="43803-122">Method</span></span>

<span data-ttu-id="43803-123">[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)のようにしてください。</span><span class="sxs-lookup"><span data-stu-id="43803-123">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="43803-124">このメソッドは、動的パラメーター定義を含むオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="43803-124">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="43803-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43803-125">For example:</span></span>

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a><span data-ttu-id="43803-126">クラス</span><span class="sxs-lookup"><span data-stu-id="43803-126">Class</span></span>

<span data-ttu-id="43803-127">追加する動的パラメーターを定義するクラス。</span><span class="sxs-lookup"><span data-stu-id="43803-127">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="43803-128">このクラスには、各パラメーターの **パラメーター** 属性と、コマンドレットで必要とされるオプションの **エイリアス** および **検証** 属性が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43803-128">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="43803-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43803-129">For example:</span></span>

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

<span data-ttu-id="43803-130">動的パラメーターをサポートするコマンドレットの完全な例については、「 [動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43803-130">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43803-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="43803-131">See also</span></span>

[<span data-ttu-id="43803-132">IDynamicParameters (システム管理)</span><span class="sxs-lookup"><span data-stu-id="43803-132">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="43803-133">IDynamicParameters (システムの管理) パラメーター</span><span class="sxs-lookup"><span data-stu-id="43803-133">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="43803-134">動的パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="43803-134">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="43803-135">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="43803-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
