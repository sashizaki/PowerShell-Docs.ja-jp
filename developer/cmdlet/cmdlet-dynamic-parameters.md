---
title: コマンドレットの動的パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 2fc73b6ef5a862fafb7a3c8fe3da19ac71bafc05
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853808"
---
# <a name="cmdlet-dynamic-parameters"></a><span data-ttu-id="2ef23-102">コマンドレットの動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ef23-102">Cmdlet Dynamic Parameters</span></span>

<span data-ttu-id="2ef23-103">コマンドレットは、特定の値を別のパラメーターの引数の場合などの特殊な条件下でユーザーに使用できるパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2ef23-103">Cmdlets can define parameters that are available to the user under special conditions, such as when the argument of another parameter is a specific value.</span></span> <span data-ttu-id="2ef23-104">これらのパラメーターは、実行時に追加されと呼ばれます*動的パラメーター*のために必要な場合にのみ追加されます。</span><span class="sxs-lookup"><span data-stu-id="2ef23-104">These parameters are added at runtime and are referred to as *dynamic parameters* because they are added only when they are needed.</span></span> <span data-ttu-id="2ef23-105">たとえば、特定のスイッチ パラメーターを指定する場合にのみ、いくつかのパラメーターを追加するコマンドレットをデザインできます。</span><span class="sxs-lookup"><span data-stu-id="2ef23-105">For example, you can design a cmdlet that adds several parameters only when a specific switch parameter is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef23-106">プロバイダーと Windows PowerShell 関数では、動的パラメーターも定義できます。</span><span class="sxs-lookup"><span data-stu-id="2ef23-106">Providers and Windows PowerShell functions can also define dynamic parameters.</span></span>

## <a name="dynamic-parameters-in-windows-powershell-cmdlets"></a><span data-ttu-id="2ef23-107">Windows PowerShell コマンドレットで動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ef23-107">Dynamic Parameters in Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2ef23-108">Windows PowerShell は、そのプロバイダーのコマンドレットのいくつかの動的パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-108">Windows PowerShell uses dynamic parameters in several of its provider cmdlets.</span></span> <span data-ttu-id="2ef23-109">たとえば、`Get-Item`と`Get-ChildItem`コマンドレットを追加、`CodeSigningCert`時にパラメーターと、`Path`コマンドレットのパラメーターは、証明書プロバイダー パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-109">For example, the `Get-Item` and `Get-ChildItem` cmdlets add a `CodeSigningCert` parameter at runtime when the `Path` parameter of the cmdlet specifies the Certificate provider path.</span></span> <span data-ttu-id="2ef23-110">場合、`Path`コマンドレットのパラメーターは、別のプロバイダーのパスを指定します、`CodeSigningCert`パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2ef23-110">If the `Path` parameter of the cmdlet specifies a path for a different provider, the `CodeSigningCert` parameter is not available.</span></span>

<span data-ttu-id="2ef23-111">次の例に示す方法、`CodeSigningCert`時にパラメーターが追加されるときに、`Get-Item`コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-111">The following examples show how the `CodeSigningCert` parameter is added at runtime when the `Get-Item` cmdlet is run.</span></span>

<span data-ttu-id="2ef23-112">最初の例では、Windows PowerShell ランタイムには、パラメーターが追加と、コマンドレットは成功します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-112">In the first example, the Windows PowerShell runtime has added the parameter, and the cmdlet is successful.</span></span>

```powershell
Get-Item -Path cert:\CurrentUser -codesigningcert
```

```output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

<span data-ttu-id="2ef23-113">2 番目の例では、ファイル システム ドライブを指定し、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="2ef23-113">In the second example, a FileSystem drive is specified, and an error is returned.</span></span> <span data-ttu-id="2ef23-114">エラー メッセージが示す、`CodeSigningCert`パラメーターが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="2ef23-114">The error message indicates that the `CodeSigningCert` parameter cannot be found.</span></span>

```powershell
Get-Item -Path C:\ -codesigningcert
```

```output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a><span data-ttu-id="2ef23-115">動的パラメーターのサポート</span><span class="sxs-lookup"><span data-stu-id="2ef23-115">Support for Dynamic Parameters</span></span>

<span data-ttu-id="2ef23-116">動的パラメーターをサポートするには、コマンドレットのコードは、次の要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ef23-116">To support dynamic parameters, the cmdlet code must include the following elements.</span></span>

<span data-ttu-id="2ef23-117">[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)このインターフェイスは、動的パラメーターを取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-117">[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) This interface provides the method that retrieves the dynamic parameters.</span></span>

<span data-ttu-id="2ef23-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-118">Example:</span></span>

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

<span data-ttu-id="2ef23-119">[System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)このメソッドは、動的パラメーターの定義を含むオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-119">[System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) This method retrieves the object that contains the dynamic parameter definitions.</span></span>

<span data-ttu-id="2ef23-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-120">Example:</span></span>

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

<span data-ttu-id="2ef23-121">動的パラメーター クラスこのクラスは、追加するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-121">Dynamic Parameter class This class defines the parameters to be added.</span></span> <span data-ttu-id="2ef23-122">このクラスは、各パラメーターと、コマンドレットで必要なオプションのエイリアスと検証属性のパラメーターの属性を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ef23-122">This class must include a Parameter attribute for each parameter and any optional Alias and Validation attributes that are needed by the cmdlet.</span></span>

<span data-ttu-id="2ef23-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-123">Example:</span></span>

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

<span data-ttu-id="2ef23-124">動的パラメーターをサポートするコマンドレットの完全な例を参照してください。[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ef23-124">For a complete example of a cmdlet that supports dynamic parameters, see [How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef23-125">参照</span><span class="sxs-lookup"><span data-stu-id="2ef23-125">See Also</span></span>

[<span data-ttu-id="2ef23-126">System.Management.Automation.Idynamicparameters</span><span class="sxs-lookup"><span data-stu-id="2ef23-126">System.Management.Automation.Idynamicparameters</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters)

[<span data-ttu-id="2ef23-127">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span><span class="sxs-lookup"><span data-stu-id="2ef23-127">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="2ef23-128">動的パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="2ef23-128">How to Declare Dynamic Parameters</span></span>](./how-to-declare-dynamic-parameters.md)

[<span data-ttu-id="2ef23-129">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="2ef23-129">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
