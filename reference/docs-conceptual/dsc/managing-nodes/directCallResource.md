---
ms.date: 08/11/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース メソッドの直接呼び出し
ms.openlocfilehash: 029a278c938e414820e172b85fac3cb3ad4b4afa
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "88162496"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="88b77-103">DSC リソース メソッドの直接呼び出し</span><span class="sxs-lookup"><span data-stu-id="88b77-103">Calling DSC resource methods directly</span></span>

><span data-ttu-id="88b77-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="88b77-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="88b77-105">[Invoke DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) コマンドレットを使用すると、DSC リソースの関数またはメソッド (MOF ベースのリソースの `Get-TargetResource` 関数、`Set-TargetResource` 関数、`Test-TargetResource` 関数、またはクラスベースのリソースの **Get** メソッド、**Set** メソッド、**Test** メソッド) を直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="88b77-105">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions of a MOF-based resource, or the **Get**, **Set**, and **Test** methods of a class-based resource).</span></span> <span data-ttu-id="88b77-106">これは、DSC リソースを使用するサード パーティが使用したり、リソースの開発中に役立つツールとして利用したりできます。</span><span class="sxs-lookup"><span data-stu-id="88b77-106">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

> [!NOTE]
> <span data-ttu-id="88b77-107">PowerShell 7.0 以降では、`Invoke-DscResource` は WMI DSC リソースの呼び出しをサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="88b77-107">In PowerShell 7.0+, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="88b77-108">これには、**PSDesiredStateConfiguration** の**ファイル** リソースと**ログ** リソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="88b77-108">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="88b77-109">通常このコマンドレットは、メタ構成プロパティ `refreshMode = 'Disabled'` と組み合わせて使用されますが、どの **refreshMode** が設定されているかに関係なく使用できます。</span><span class="sxs-lookup"><span data-stu-id="88b77-109">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="88b77-110">`Invoke-DscResource` コマンドレットを呼び出すときに、**Method** パラメーターを使用して、呼び出すメソッドまたは関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="88b77-110">When calling the `Invoke-DscResource` cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="88b77-111">リソースのプロパティを指定するには、ハッシュ テーブルを、**Property** パラメーターの値として渡します。</span><span class="sxs-lookup"><span data-stu-id="88b77-111">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="88b77-112">リソースのメソッドを直接呼び出す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88b77-112">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="88b77-113">ファイルが存在することを確認します</span><span class="sxs-lookup"><span data-stu-id="88b77-113">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
              DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
              Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="88b77-114">ファイルが存在することをテストします</span><span class="sxs-lookup"><span data-stu-id="88b77-114">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="88b77-115">ファイルの内容を取得します</span><span class="sxs-lookup"><span data-stu-id="88b77-115">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
              DestinationPath="$env:SystemDrive\\DirectAccess.txt";
              Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

>[!NOTE]
> <span data-ttu-id="88b77-116">複合リソースのメソッドを直接呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="88b77-116">Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="88b77-117">代わりに、複合リソースの基になるリソースのメソッドを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="88b77-117">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="88b77-118">参照</span><span class="sxs-lookup"><span data-stu-id="88b77-118">See Also</span></span>

- [<span data-ttu-id="88b77-119">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="88b77-119">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="88b77-120">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="88b77-120">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="88b77-121">DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="88b77-121">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)
