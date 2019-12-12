---
title: コマンドレット動的パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 19d31f6b619dff23e7e35bb53d2397f4f41eb728
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369881"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="394b5-102">コマンドレット動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="394b5-102">Cmdlet dynamic parameters</span></span>

<span data-ttu-id="394b5-103">コマンドレットでは、他のパラメーターの引数が特定の値の場合など、特殊な条件下でユーザーが使用できるパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="394b5-103">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="394b5-104">これらのパラメーターは、必要なときにのみ追加されるため、実行時に追加され、動的パラメーターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="394b5-104">These parameters are added at runtime and are referred to as dynamic parameters because they're only added when needed.</span></span> <span data-ttu-id="394b5-105">たとえば、特定のスイッチパラメーターが指定されている場合にのみ、いくつかのパラメーターを追加するコマンドレットを設計できます。</span><span class="sxs-lookup"><span data-stu-id="394b5-105">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="394b5-106">プロバイダーと PowerShell 関数では、動的パラメーターを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="394b5-106">Providers and PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-powershell-cmdlets"></a><span data-ttu-id="394b5-107">PowerShell コマンドレットの動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="394b5-107">Dynamic parameters in PowerShell cmdlets</span></span>

<span data-ttu-id="394b5-108">PowerShell では、プロバイダーコマンドレットのいくつかで動的パラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="394b5-108">PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="394b5-109">たとえば、`Get-Item` および `Get-ChildItem` のコマンドレットは、 **Path**パラメーターに**証明書**プロバイダーのパスが指定されている場合に、実行時に**codesigningcert**パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="394b5-109">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a **CodeSigningCert** parameter at runtime when the **Path** parameter specifies the **Certificate** provider path.</span></span> <span data-ttu-id="394b5-110">**Path**パラメーターに別のプロバイダーのパスが指定されている場合、 **Codesigningcert**パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="394b5-110">If the **Path** parameter specifies a path for a different provider, the **CodeSigningCert** parameter isn't available.</span></span>

<span data-ttu-id="394b5-111">次の例は、`Get-Item` の実行時に**Codesigningcert**パラメーターを実行時に追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="394b5-111">The following examples show how the **CodeSigningCert** parameter is added at runtime when `Get-Item` is run.</span></span>

<span data-ttu-id="394b5-112">この例では、PowerShell ランタイムによってパラメーターが追加され、コマンドレットが正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="394b5-112">In this example, the PowerShell runtime has added the parameter and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="394b5-113">この例では、**ファイルシステム**ドライブが指定され、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="394b5-113">In this example, a **FileSystem** drive is specified and an error is returned.</span></span> <span data-ttu-id="394b5-114">エラーメッセージは、 **Codesigningcert**パラメーターが見つからないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="394b5-114">The error message indicates that the **CodeSigningCert** parameter can't be found.</span></span>

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

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="394b5-115">動的パラメーターのサポート</span><span class="sxs-lookup"><span data-stu-id="394b5-115">Support for dynamic parameters</span></span>

<span data-ttu-id="394b5-116">動的パラメーターをサポートするには、次の要素をコマンドレットコードに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="394b5-116">To support dynamic parameters, the following elements must be included in the cmdlet code.</span></span>

### <a name="interface"></a><span data-ttu-id="394b5-117">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="394b5-117">Interface</span></span>

<span data-ttu-id="394b5-118">[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters)のようになります。</span><span class="sxs-lookup"><span data-stu-id="394b5-118">[System.Management.Automation.IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters).</span></span>
<span data-ttu-id="394b5-119">このインターフェイスは、動的パラメーターを取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="394b5-119">This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="394b5-120">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="394b5-120">For example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a><span data-ttu-id="394b5-121">認証方法</span><span class="sxs-lookup"><span data-stu-id="394b5-121">Method</span></span>

<span data-ttu-id="394b5-122">[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)のようにしてください。</span><span class="sxs-lookup"><span data-stu-id="394b5-122">[System.Management.Automation.IDynamicParameters.GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters).</span></span>
<span data-ttu-id="394b5-123">このメソッドは、動的パラメーター定義を含むオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="394b5-123">This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="394b5-124">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="394b5-124">For example:</span></span>

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

### <a name="class"></a><span data-ttu-id="394b5-125">［クラス］</span><span class="sxs-lookup"><span data-stu-id="394b5-125">Class</span></span>

<span data-ttu-id="394b5-126">追加する動的パラメーターを定義するクラス。</span><span class="sxs-lookup"><span data-stu-id="394b5-126">A class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="394b5-127">このクラスには、各パラメーターの**パラメーター**属性と、コマンドレットで必要とされるオプションの**エイリアス**および**検証**属性が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="394b5-127">This class must include a **Parameter** attribute for each parameter and any optional **Alias** and **Validation** attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="394b5-128">たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="394b5-128">For example:</span></span>

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

<span data-ttu-id="394b5-129">動的パラメーターをサポートするコマンドレットの完全な例については、「[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="394b5-129">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="394b5-130">「</span><span class="sxs-lookup"><span data-stu-id="394b5-130">See also</span></span>

[<span data-ttu-id="394b5-131">IDynamicParameters (システム管理)</span><span class="sxs-lookup"><span data-stu-id="394b5-131">System.Management.Automation.IDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="394b5-132">IDynamicParameters (システムの管理) パラメーター</span><span class="sxs-lookup"><span data-stu-id="394b5-132">System.Management.Automation.IDynamicParameters.GetDynamicParameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="394b5-133">動的パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="394b5-133">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="394b5-134">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="394b5-134">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
