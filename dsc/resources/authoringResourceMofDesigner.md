---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: リソース デザイナー ツールの使用
ms.openlocfilehash: 3fd2f06cf46602ee30dd34f8e7bd77d3c92b808f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076669"
---
# <a name="using-the-resource-designer-tool"></a><span data-ttu-id="6c2b3-103">リソース デザイナー ツールの使用</span><span class="sxs-lookup"><span data-stu-id="6c2b3-103">Using the Resource Designer tool</span></span>

> <span data-ttu-id="6c2b3-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c2b3-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6c2b3-105">リソース デザイナー ツールは、Windows PowerShell Desired State Configuration (DSC) リソースの作成を簡単にする、**xDscResourceDesigner** モジュールによって公開されている一連のコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-105">The Resource Designer tool is a set of cmdlets exposed by the **xDscResourceDesigner** module that make creating Windows PowerShell Desired State Configuration (DSC) resources easier.</span></span> <span data-ttu-id="6c2b3-106">このリソースのコマンドレットは、MOF スキーマ、スクリプト モジュール、および新しいリソースのディレクトリ構造の作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-106">The cmdlets in this resource help create the MOF schema, the script module, and the directory structure for your new resource.</span></span> <span data-ttu-id="6c2b3-107">DSC リソースの詳細については、「[カスタム Windows PowerShell Desired State Configuration のビルド](authoringResource.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-107">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md).</span></span>
<span data-ttu-id="6c2b3-108">このトピックでは、Active Directory ユーザーを管理する DSC リソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-108">In this topic, we will create a DSC resource that manages Active Directory users.</span></span>
<span data-ttu-id="6c2b3-109">[Install-Module](/powershell/module/PowershellGet/Install-Module) コマンドレットを使用して **xDscResourceDesigner** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-109">Use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xDscResourceDesigner** module.</span></span>

><span data-ttu-id="6c2b3-110">**注**:**Install-Module** は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-110">**Note**: **Install-Module** is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span> <span data-ttu-id="6c2b3-111">「[PackageManagement PowerShell Modules Preview (PackageManagement PowerShell モジュールのプレビュー)](https://www.microsoft.com/en-us/download/details.aspx?id=49186)」で PowerShell 3.0 と 4.0 の **PowerShellGet** モジュールをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-111">You can download the **PowerShellGet** module for PowerShell 3.0 and 4.0 at [PackageManagement PowerShell Modules Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span></span>

## <a name="creating-resource-properties"></a><span data-ttu-id="6c2b3-112">リソース プロパティの作成</span><span class="sxs-lookup"><span data-stu-id="6c2b3-112">Creating resource properties</span></span>
<span data-ttu-id="6c2b3-113">まず、リソースで公開するプロパティを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-113">The first thing we need to do is decide on properties that the resource will expose.</span></span> <span data-ttu-id="6c2b3-114">この例では、次のプロパティを持つ Active Directory ユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-114">For this example, we will define an Active Directory user with the following properties.</span></span>

<span data-ttu-id="6c2b3-115">パラメーター名  説明</span><span class="sxs-lookup"><span data-stu-id="6c2b3-115">Parameter name  Description</span></span>
* <span data-ttu-id="6c2b3-116">**UserName**:ユーザーを一意に識別するキー プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-116">**UserName**: Key property that uniquely identifies a user.</span></span>
* <span data-ttu-id="6c2b3-117">**Ensure**:ユーザー アカウントが存在するかしないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-117">**Ensure**: Specifies whether the user account should be Present or Absent.</span></span> <span data-ttu-id="6c2b3-118">このパラメーターに使用できる値は 2 つのみです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-118">This parameter will have only two possible values.</span></span>
* <span data-ttu-id="6c2b3-119">**DomainCredential**:ユーザーのドメイン パスワードです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-119">**DomainCredential**: The domain password for the user.</span></span>
* <span data-ttu-id="6c2b3-120">**Password**:必要に応じて構成でユーザー パスワードを変更できるようにするために必要なユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-120">**Password**: The desired password for the user to allow a configuration to change the user password if necessary.</span></span>

<span data-ttu-id="6c2b3-121">プロパティを作成するには、**New-xDscResourceProperty** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-121">To create the properties, we use the **New-xDscResourceProperty** cmdlet.</span></span> <span data-ttu-id="6c2b3-122">次の PowerShell コマンドでは、上記で説明したプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-122">The following PowerShell commands create the properties described above.</span></span>

```powershell
$UserName = New-xDscResourceProperty –Name UserName -Type String -Attribute Key
$Ensure = New-xDscResourceProperty –Name Ensure -Type String -Attribute Write –ValidateSet “Present”, “Absent”
$DomainCredential = New-xDscResourceProperty –Name DomainCredential -Type PSCredential -Attribute Write
$Password = New-xDscResourceProperty –Name Password -Type PSCredential -Attribute Write
```

## <a name="create-the-resource"></a><span data-ttu-id="6c2b3-123">リソースの作成</span><span class="sxs-lookup"><span data-stu-id="6c2b3-123">Create the resource</span></span>

<span data-ttu-id="6c2b3-124">リソース プロパティが作成されたので、**New-xDscResource** コマンドレットを呼び出してリソースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-124">Now that the resource properties have been created, we can call the **New-xDscResource** cmdlet to create the resource.</span></span> <span data-ttu-id="6c2b3-125">**New-xDscResource** コマンドレットは、パラメーターとしてプロパティのリストを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-125">The **New-xDscResource** cmdlet takes the list of properties as parameters.</span></span> <span data-ttu-id="6c2b3-126">モジュールを作成するパス、新しいリソースの名前、そのリソースが含まれているモジュールの名前も受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-126">It also takes the path where the module should be created, the name of the new resource, and the name of the module in which it is contained.</span></span> <span data-ttu-id="6c2b3-127">次の PowerShell コマンドでは、リソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-127">The following PowerShell command creates the resource.</span></span>

```powershell
New-xDscResource –Name Demo_ADUser –Property $UserName, $Ensure, $DomainCredential, $Password –Path ‘C:\Program Files\WindowsPowerShell\Modules’ –ModuleName Demo_DSCModule
```

<span data-ttu-id="6c2b3-128">**New-xDscResource** コマンドレットは、MOF スキーマ、スケルトン リソース スクリプト、新しいリソースに必要なディレクトリ構造、および新しいリソースを公開するモジュールのマニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-128">The **New-xDscResource** cmdlet creates the MOF schema, a skeleton resource script, the required directory structure for your new resource, and a manifest for the module that exposes the new resource.</span></span>

<span data-ttu-id="6c2b3-129">MOF スキーマ ファイルは、**C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof** にあり、その内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-129">The MOF schema file is at **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof**, and its contents are as follows.</span></span>

```
[ClassVersion("1.0.0.0"), FriendlyName("Demo_ADUser")]
class Demo_ADUser : OMI_BaseResource
{
  [Key] string UserName;
  [Write, ValueMap{"Present","Absent"}, Values{"Present","Absent"}] string Ensure;
  [Write, EmbeddedInstance("MSFT_Credential")] String DomainCredential;
  [Write, EmbeddedInstance("MSFT_Credential")] String Password;
};
```

<span data-ttu-id="6c2b3-130">リソース スクリプトは **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1** にあります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-130">The resource script is at **C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1**.</span></span> <span data-ttu-id="6c2b3-131">これには、自分自身を追加する必要があるリソースを実装する実際のロジックは含まれません。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-131">It does not include the actual logic to implement the resource, which you must add yourself.</span></span> <span data-ttu-id="6c2b3-132">スケルトン スクリプトの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-132">The contents of the skeleton script are as follows.</span></span>

```powershell
function Get-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Collections.Hashtable])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."


  <#
  $returnValue = @{
  UserName = [System.String]
  Ensure = [System.String]
  DomainAdminCredential = [System.Management.Automation.PSCredential]
  Password = [System.Management.Automation.PSCredential]
  }

  $returnValue
  #>
}


function Set-TargetResource
{
  [CmdletBinding()]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  #Include this line if the resource requires a system reboot.
  #$global:DSCMachineStatus = 1


}


function Test-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Boolean])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."


  <#
  $result = [System.Boolean]

  $result
  #>
}


Export-ModuleMember -Function *-TargetResource
```

## <a name="updating-the-resource"></a><span data-ttu-id="6c2b3-133">リソースの更新</span><span class="sxs-lookup"><span data-stu-id="6c2b3-133">Updating the resource</span></span>

<span data-ttu-id="6c2b3-134">リソースのパラメーター リストを追加または変更する必要がある場合は、**Update-xDscResource** コマンドレットを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-134">If you need to add or modify the parameter list of the resource, you can call the **Update-xDscResource** cmdlet.</span></span> <span data-ttu-id="6c2b3-135">コマンドレットは、新しいパラメーター リストでリソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-135">The cmdlet updates the resource with a new parameter list.</span></span> <span data-ttu-id="6c2b3-136">リソース スクリプトに既にロジックを追加している場合は、そのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-136">If you have already added logic in your resource script, it is left intact.</span></span>

<span data-ttu-id="6c2b3-137">たとえば、リソースにユーザーの最後のログイン時間を追加するとします。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-137">For example, suppose you want to include the last log in time for the user in our resource.</span></span> <span data-ttu-id="6c2b3-138">リソースを完全に再作成するのではなく、**New-xDscResourceProperty** を呼び出して新しいプロパティを作成してから **Update-xDscResource** を呼び出し、プロパティ リストに新しいプロパティを追加できます。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-138">Rather than writing the resource again completely, you can call the **New-xDscResourceProperty** to create the new property, and then call **Update-xDscResource** and add your new property to the properties list.</span></span>

```powershell
$lastLogon = New-xDscResourceProperty –Name LastLogon –Type Hashtable –Attribute Write –Description “For mapping users to their last log on time”
Update-xDscResource –Name ‘Demo_ADUser’ –Property $UserName, $Ensure, $DomainCredential, $Password, $lastLogon -Force
```

## <a name="testing-a-resource-schema"></a><span data-ttu-id="6c2b3-139">リソース スキーマのテスト</span><span class="sxs-lookup"><span data-stu-id="6c2b3-139">Testing a resource schema</span></span>

<span data-ttu-id="6c2b3-140">リソース デザイナー ツールは、手動で記述した MOF スキーマの有効性をテストするために使用できる 1 つ以上のコマンドレットを公開します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-140">The Resource Designer tool exposes one more cmdlet that can be used to test the validity of a MOF schema that you have written manually.</span></span> <span data-ttu-id="6c2b3-141">パラメーターとして MOF リソース スキーマのパスを渡して、**Test-xDscSchema** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-141">Call the **Test-xDscSchema** cmdlet, passing the path of a MOF resource schema as a parameter.</span></span> <span data-ttu-id="6c2b3-142">コマンドレットは、スキーマにエラーを出力します。</span><span class="sxs-lookup"><span data-stu-id="6c2b3-142">The cmdlet will output any errors in the schema.</span></span>

### <a name="see-also"></a><span data-ttu-id="6c2b3-143">参照</span><span class="sxs-lookup"><span data-stu-id="6c2b3-143">See Also</span></span>

#### <a name="concepts"></a><span data-ttu-id="6c2b3-144">概念</span><span class="sxs-lookup"><span data-stu-id="6c2b3-144">Concepts</span></span>
[<span data-ttu-id="6c2b3-145">Build Custom Windows PowerShell Desired State Configuration Resources (カスタム Windows PowerShell Desired State Configuration のビルド)</span><span class="sxs-lookup"><span data-stu-id="6c2b3-145">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)

#### <a name="other-resources"></a><span data-ttu-id="6c2b3-146">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="6c2b3-146">Other Resources</span></span>
[<span data-ttu-id="6c2b3-147">xDscResourceDesigner モジュール</span><span class="sxs-lookup"><span data-stu-id="6c2b3-147">xDscResourceDesigner Module</span></span>](https://www.powershellgallery.com/packages/xDscResourceDesigner/1.12.0.0)
