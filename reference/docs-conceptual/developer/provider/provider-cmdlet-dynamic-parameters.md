---
title: プロバイダーコマンドレット動的パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f1069f7-8fa8-4622-9e2c-af29b0b961c2
caps.latest.revision: 6
ms.openlocfilehash: a50de014988336c473c565b506a73de1c864d7e0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359951"
---
# <a name="provider-cmdlet-dynamic-parameters"></a><span data-ttu-id="29b98-102">コマンドレット コマンドレットの動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="29b98-102">Provider cmdlet dynamic parameters</span></span>

<span data-ttu-id="29b98-103">プロバイダーは、ユーザーがコマンドレットのいずれかの静的パラメーターに特定の値を指定した場合に、プロバイダーコマンドレットに追加される動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="29b98-103">Providers can define dynamic parameters that are added to a provider cmdlet when the user specifies a certain value for one of the static parameters of the cmdlet.</span></span> <span data-ttu-id="29b98-104">たとえば、プロバイダーは、`Get-Item` または `Set-Item` プロバイダーコマンドレットを呼び出すときに、ユーザーが指定するパスに基づいて、さまざまな動的パラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="29b98-104">For example, a provider can add different dynamic parameters based on what path the user specifies when they call the `Get-Item` or `Set-Item` provider cmdlets.</span></span>

## <a name="dynamic-parameter-methods"></a><span data-ttu-id="29b98-105">動的パラメーターメソッド</span><span class="sxs-lookup"><span data-stu-id="29b98-105">Dynamic Parameter Methods</span></span>

<span data-ttu-id="29b98-106">動的パラメーターは、 [Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) [などの動的パラメーターメソッドの1つを実装することによって定義されます。Setitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s メソッドを、このメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="29b98-106">Dynamic parameters are defined by implementing one of the dynamic parameter methods, such as the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s methods.</span></span> <span data-ttu-id="29b98-107">これらのメソッドは、スタンドアロンのコマンドレットと同様の属性で装飾されたパブリックプロパティを持つオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="29b98-107">These methods return an object that has public properties that are decorated with attributes similar to those of stand-alone cmdlets.</span></span> <span data-ttu-id="29b98-108">次に示すのは、証明書プロバイダーから取得した[Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドの実装例です。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="29b98-108">Here is an example of an implementation of the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) method taken from the Certificate provider:</span></span>

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

<span data-ttu-id="29b98-109">プロバイダーコマンドレットの静的パラメーターとは異なり、スタンドアロンのコマンドレットでパラメーターを定義するのと同じ方法で、これらのパラメーターの特性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="29b98-109">Unlike the static parameters of provider cmdlets, you can specify the characteristics of these parameters in the same way that parameters are defined in stand-alone cmdlets.</span></span> <span data-ttu-id="29b98-110">証明書プロバイダーから取得した動的パラメータークラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="29b98-110">Here is an example of a dynamic parameter class taken from the Certificate provider:</span></span>

```csharp
internal sealed class CertificateProviderDynamicParameters
{
  /// <summary>
  /// Dynamic parameter the controls whether we only return
  /// code signing certs.
  /// </summary>
  [Parameter()]
  public SwitchParameter CodeSigningCert
  {
    get
    {
      {
        return codeSigningCert;
      }
    }

    set
    {
      {
        codeSigningCert = value;
      }
    }
  }

    private SwitchParameter codeSigningCert = new SwitchParameter();
}
```

## <a name="dynamic-parameters"></a><span data-ttu-id="29b98-111">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="29b98-111">Dynamic Parameters</span></span>

<span data-ttu-id="29b98-112">動的パラメーターの追加に使用できる静的パラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="29b98-112">Here is a list of the static parameters that can be used to add dynamic parameters.</span></span>

<span data-ttu-id="29b98-113">`Clear-Content` コマンドレットを使用すると、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)を実装することにより、clear clear コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。b.</span><span class="sxs-lookup"><span data-stu-id="29b98-113">`Clear-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the Clear-Clear cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-114">`Clear-Item` コマンドレットを使用すると、`Clear-Item` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、[このメソッドを](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)実装します。</span><span class="sxs-lookup"><span data-stu-id="29b98-114">`Clear-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Clear-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-115">`Clear-ItemProperty` コマンドレットを使用すると、 [Ipropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッドを実装することによって、`Clear-ItemProperty` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます.</span><span class="sxs-lookup"><span data-stu-id="29b98-115">`Clear-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Clear-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-116">`Copy-Item` コマンドレットでは、`Copy-Item` コマンドレットの `Path`、`Destination`、および `Recurse` のパラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッドをコピーします。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="29b98-116">`Copy-Item` cmdlet You can define dynamic parameters that are triggered by the `Path`, `Destination`, and `Recurse` parameters of the `Copy-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-117">ChildItems コマンドレットは、`Get-ChildItem` コマンドレットの `Path` と `Recurse` パラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) \* メソッドと Getchilditemsdynamicparameters \* メソッドと[Containercmdletprovider... Getchildnamesdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="29b98-117">Get-ChildItems cmdlet You can define dynamic parameters that are triggered by the `Path` and `Recurse` parameters of the `Get-ChildItem` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) and [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) methods.</span></span>

<span data-ttu-id="29b98-118">`Get-Content` コマンドレットを使用すると、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)を実装することによって、`Get-Content` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。b.</span><span class="sxs-lookup"><span data-stu-id="29b98-118">`Get-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Get-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-119">`Get-Item` コマンドレットを使用すると、 [Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドを実装することによって、`Get-Item` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="29b98-119">`Get-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Get-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-120">`Get-ItemProperty` コマンドレットでは、Ipropertycmdletprovider を実装することによって、`Get-ItemProperty` コマンドレットの `Path` と `Name` パラメーターによってトリガーされる動的パラメーターを定義できます。 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="29b98-120">`Get-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Name` parameters of the `Get-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-121">`Invoke-Item` コマンドレットを使用すると、`Invoke-Item` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。これを行うには、....................。 [Invokedefaultactiondynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)b.</span><span class="sxs-lookup"><span data-stu-id="29b98-121">`Invoke-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Invoke-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-122">`Move-Item` コマンドレットを使用すると、`Move-Item` コマンドレットの `Path` と `Destination` パラメーターによってトリガーされる動的パラメーターを定義できます。これを行うには、コマンドレットを実装します。 [Moveitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="29b98-122">`Move-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Destination` parameters of the `Move-Item` cmdlet by implementing the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-123">`New-Item` コマンドレットでは、`New-Item` コマンドレットの `Path`、`ItemType`、および `Value` のパラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)メソッドを管理していることをご相談ください。</span><span class="sxs-lookup"><span data-stu-id="29b98-123">`New-Item` cmdlet You can define dynamic parameters that are triggered by the `Path`, `ItemType`, and `Value` parameters of the `New-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-124">`New-ItemProperty` コマンドレットを使用すると、`Value` コマンドレットの `Path`、`Name`、`PropertyType`、および `New-ItemProperty` パラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、 [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)メソッドを管理していることをご相談ください。</span><span class="sxs-lookup"><span data-stu-id="29b98-124">`New-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path`, `Name`, `PropertyType`, and `Value` parameters of the `New-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-125">`New-PSDrive` コマンドレットを使用して、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) `New-PSDrive` コマンドレットによって返される system.management.automation.psdriveinfo オブジェクトによってトリガーされる動的パラメーターを定義できます。[System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="29b98-125">`New-PSDrive` cmdlet You can define dynamic parameters that are triggered by the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object returned by the `New-PSDrive` cmdlet by implementing the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-126">`Remove-Item`、 [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)を実装することによって、`Remove-Item` コマンドレットの `Path` と `Recurse` パラメーターによってトリガーされる動的パラメーターを定義できます。b.</span><span class="sxs-lookup"><span data-stu-id="29b98-126">`Remove-Item` You can define dynamic parameters that are triggered by the `Path` and `Recurse` parameters of the `Remove-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-127">`Remove-ItemProperty`、`Remove-ItemProperty` コマンドレットの `Path` と `Name` パラメーターによってトリガーされる動的パラメーターを定義するには、 [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッドを管理していることをテストします。</span><span class="sxs-lookup"><span data-stu-id="29b98-127">`Remove-ItemProperty` You can define dynamic parameters that are triggered by the `Path` and `Name` parameters of the `Remove-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-128">`Rename-Item` コマンドレットでは、Containercmdletprovider を実装することによって、`Rename-Item` コマンドレットの `Path` と `NewName` パラメーターによってトリガーされる動的パラメーターを定義できます。 [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="29b98-128">`Rename-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `NewName` parameters of the `Rename-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-129">`Rename-ItemProperty`、`Rename-ItemProperty` コマンドレットの `Path`、`Name`、および `NewName` パラメーターによってトリガーされる動的パラメーターを定義するには、 [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッドを管理します。このメソッドは、</span><span class="sxs-lookup"><span data-stu-id="29b98-129">`Rename-ItemProperty` You can define dynamic parameters that are triggered by the `Path`, `Name`, and `NewName` parameters of the `Rename-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-130">`Set-Content` コマンドレットでは、 [Icontentcmdletprovider. Getcontentwriterdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)を実装することによって `Set-Content` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。b.</span><span class="sxs-lookup"><span data-stu-id="29b98-130">`Set-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Set-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-131">`Set-Item` コマンドレットでは、 [Setitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)を実装することによって、`Set-Item` コマンドレットの `Path` と `Value` パラメーターによってトリガーされる動的パラメーターを定義できます。b.</span><span class="sxs-lookup"><span data-stu-id="29b98-131">`Set-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-132">`Set-ItemProperty` コマンドレットでは、Ipropertycmdletprovider を実装することによって、`Set-Item` コマンドレットの `Path` と `Value` パラメーターによってトリガーされる動的パラメーターを定義できます。 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッド。</span><span class="sxs-lookup"><span data-stu-id="29b98-132">`Set-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="29b98-133">`Test-Path` コマンドレットを使用すると、`Test-Path` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。これを行うには、....................。 [Invokedefaultactiondynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)b.</span><span class="sxs-lookup"><span data-stu-id="29b98-133">`Test-Path` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Test-Path` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) method.</span></span>

## <a name="see-also"></a><span data-ttu-id="29b98-134">参照</span><span class="sxs-lookup"><span data-stu-id="29b98-134">See Also</span></span>

[<span data-ttu-id="29b98-135">Windows PowerShell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="29b98-135">Writing a Windows PowerShell Provider</span></span>](./writing-a-windows-powershell-provider.md)