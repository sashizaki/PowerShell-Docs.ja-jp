---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース メソッドの直接呼び出し
ms.openlocfilehash: cf237f638593706e5959e2bcc0d851b0e55baf0e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62079627"
---
# <a name="calling-dsc-resource-methods-directly"></a><span data-ttu-id="bfc45-103">DSC リソース メソッドの直接呼び出し</span><span class="sxs-lookup"><span data-stu-id="bfc45-103">Calling DSC resource methods directly</span></span>

><span data-ttu-id="bfc45-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="bfc45-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="bfc45-105">[Invoke DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) コマンドレットを使用すると、DSC リソースの関数やメソッド (MOF ベースのリソースの **Get-TargetResource**、**Set-TargetResource**、**Test-TargetResource** 関数、またはクラスベースのリソースの **Get**、**Set**、**Test** メソッド) を直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfc45-105">You can use the [Invoke-DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) cmdlet to directly call the functions or methods of a DSC resource (The **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** functions of a MOF-based resource, or the **Get**, **Set**, and **Test** methods of a class-based resource).</span></span>
<span data-ttu-id="bfc45-106">これは、DSC リソースを使用するサード パーティが使用したり、リソースの開発中に役立つツールとして利用したりできます。</span><span class="sxs-lookup"><span data-stu-id="bfc45-106">This can be used by third-parties that want to use DSC resources, or as a helpful tool while developing resources.</span></span>

<span data-ttu-id="bfc45-107">通常このコマンドレットは、メタ構成プロパティ `refreshMode = 'Disabled'` と組み合わせて使用されますが、どの **refreshMode** が設定されているかに関係なく使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfc45-107">This cmdlet is typically used in combination with a metaconfiguration property `refreshMode = 'Disabled'`, but it can be used no matter what **refreshMode** is set to.</span></span>

<span data-ttu-id="bfc45-108">**Invoke-DscResource** コマンドレットを呼び出すときに、**Method** パラメーターを使用して、呼び出すメソッドまたは関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfc45-108">When calling the **Invoke-DscResource** cmdlet, you specify which method or function to call by using the **Method** parameter.</span></span> <span data-ttu-id="bfc45-109">リソースのプロパティを指定するには、ハッシュ テーブルを、**Property** パラメーターの値として渡します。</span><span class="sxs-lookup"><span data-stu-id="bfc45-109">You specify the properties of the resource by passing a hashtable as the value of the **Property** parameter.</span></span>

<span data-ttu-id="bfc45-110">リソースのメソッドを直接呼び出す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bfc45-110">The following are examples of directly calling resource methods:</span></span>

## <a name="ensure-a-file-is-present"></a><span data-ttu-id="bfc45-111">ファイルが存在することを確認します</span><span class="sxs-lookup"><span data-stu-id="bfc45-111">Ensure a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
                            DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
                            Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a><span data-ttu-id="bfc45-112">ファイルが存在することをテストします</span><span class="sxs-lookup"><span data-stu-id="bfc45-112">Test that a file is present</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a><span data-ttu-id="bfc45-113">ファイルの内容を取得します</span><span class="sxs-lookup"><span data-stu-id="bfc45-113">Get the contents of file</span></span>

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

><span data-ttu-id="bfc45-114">**注:** 複合リソースのメソッドを直接呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bfc45-114">**Note:** Directly calling composite resource methods is not supported.</span></span> <span data-ttu-id="bfc45-115">代わりに、複合リソースの基になるリソースのメソッドを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="bfc45-115">Instead, call the methods of the underlying resources that make up the composite resource.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfc45-116">参照</span><span class="sxs-lookup"><span data-stu-id="bfc45-116">See Also</span></span>
- [<span data-ttu-id="bfc45-117">MOF を使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="bfc45-117">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="bfc45-118">PowerShell クラスを使用したカスタム DSC リソースの記述</span><span class="sxs-lookup"><span data-stu-id="bfc45-118">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
- [<span data-ttu-id="bfc45-119">DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="bfc45-119">Debugging DSC resources</span></span>](../troubleshooting/debugResource.md)