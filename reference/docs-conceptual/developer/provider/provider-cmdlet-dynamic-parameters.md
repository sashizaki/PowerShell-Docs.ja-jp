---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット コマンドレットの動的パラメーター
description: コマンドレット コマンドレットの動的パラメーター
ms.openlocfilehash: ac05a847afb0729c34d733fa4ba8da11f46746fe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662978"
---
# <a name="provider-cmdlet-dynamic-parameters"></a><span data-ttu-id="42bec-103">コマンドレット コマンドレットの動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="42bec-103">Provider cmdlet dynamic parameters</span></span>

<span data-ttu-id="42bec-104">プロバイダーは、ユーザーがコマンドレットのいずれかの静的パラメーターに特定の値を指定した場合に、プロバイダーコマンドレットに追加される動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-104">Providers can define dynamic parameters that are added to a provider cmdlet when the user specifies a certain value for one of the static parameters of the cmdlet.</span></span> <span data-ttu-id="42bec-105">たとえば、プロバイダーは、プロバイダーのコマンドレットを呼び出すときに、ユーザーが指定するパスに基づいて、さまざまな動的パラメーターを追加でき `Get-Item` `Set-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="42bec-105">For example, a provider can add different dynamic parameters based on what path the user specifies when they call the `Get-Item` or `Set-Item` provider cmdlets.</span></span>

## <a name="dynamic-parameter-methods"></a><span data-ttu-id="42bec-106">動的パラメーターメソッド</span><span class="sxs-lookup"><span data-stu-id="42bec-106">Dynamic Parameter Methods</span></span>

<span data-ttu-id="42bec-107">動的パラメーターは、 [Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) および [Setitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s メソッドなどの動的パラメーターメソッドの1つを実装することによって定義されています。このメソッドについては、「」をご指定ください。</span><span class="sxs-lookup"><span data-stu-id="42bec-107">Dynamic parameters are defined by implementing one of the dynamic parameter methods, such as the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) and [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s methods.</span></span> <span data-ttu-id="42bec-108">これらのメソッドは、スタンドアロンのコマンドレットと同様の属性で装飾されたパブリックプロパティを持つオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="42bec-108">These methods return an object that has public properties that are decorated with attributes similar to those of stand-alone cmdlets.</span></span> <span data-ttu-id="42bec-109">次に示すのは、証明書プロバイダーから取得した [Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) メソッドの実装例です。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="42bec-109">Here is an example of an implementation of the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) method taken from the Certificate provider:</span></span>

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

<span data-ttu-id="42bec-110">プロバイダーコマンドレットの静的パラメーターとは異なり、スタンドアロンのコマンドレットでパラメーターを定義するのと同じ方法で、これらのパラメーターの特性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-110">Unlike the static parameters of provider cmdlets, you can specify the characteristics of these parameters in the same way that parameters are defined in stand-alone cmdlets.</span></span> <span data-ttu-id="42bec-111">証明書プロバイダーから取得した動的パラメータークラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="42bec-111">Here is an example of a dynamic parameter class taken from the Certificate provider:</span></span>

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

## <a name="dynamic-parameters"></a><span data-ttu-id="42bec-112">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="42bec-112">Dynamic Parameters</span></span>

<span data-ttu-id="42bec-113">動的パラメーターの追加に使用できる静的パラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="42bec-113">Here is a list of the static parameters that can be used to add dynamic parameters.</span></span>

<span data-ttu-id="42bec-114">`Clear-Content` コマンドレットを使用すると `Path` 、 [Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) メソッドを実装することによって、Clear-Clear コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-114">`Clear-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the Clear-Clear cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-115">`Clear-Item`コマンドレットを使用すると `Path` 、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。これを行う `Clear-Item` には、このメソッドを実装[](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)します。</span><span class="sxs-lookup"><span data-stu-id="42bec-115">`Clear-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Clear-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-116">`Clear-ItemProperty` コマンドレットを使用して、 `Path` `Clear-ItemProperty` [Ipropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-116">`Clear-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Clear-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-117">`Copy-Item` コマンドレットを使用して、 `Path` `Destination` `Recurse` `Copy-Item` [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) メソッドを実装することで、コマンドレットの、、およびパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-117">`Copy-Item` cmdlet You can define dynamic parameters that are triggered by the `Path`, `Destination`, and `Recurse` parameters of the `Copy-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-118">Get-ChildItems コマンドレットを使用すると、 `Path` `Recurse` `Get-ChildItem` [Containercmdletprovider. Getchilditemsdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) メソッドと [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) メソッドを実装することによって、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="42bec-118">Get-ChildItems cmdlet You can define dynamic parameters that are triggered by the `Path` and `Recurse` parameters of the `Get-ChildItem` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) and [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) methods.</span></span>

<span data-ttu-id="42bec-119">`Get-Content` コマンドレットを使用すると、 `Path` `Get-Content` [Icontentcmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) メソッドを実装することによって、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-119">`Get-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Get-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-120">`Get-Item` コマンドレットを使用して、 `Path` `Get-Item` [Getitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-120">`Get-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Get-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-121">`Get-ItemProperty` コマンドレットを使用して、 `Path` `Name` `Get-ItemProperty` [Ipropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-121">`Get-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Name` parameters of the `Get-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-122">`Invoke-Item`コマンドレットを使用すると `Path` 、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。これを行う `Invoke-Item` には、このメソッドを実装[](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)します。</span><span class="sxs-lookup"><span data-stu-id="42bec-122">`Invoke-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Invoke-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-123">`Move-Item` コマンドレットを使用する `Path` と、 `Destination` コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます `Move-Item` [。これ](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) を行うには、このメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="42bec-123">`Move-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Destination` parameters of the `Move-Item` cmdlet by implementing the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-124">`New-Item` コマンドレットを使用すると、 `Path` `ItemType` `Value` `New-Item` [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) メソッドを実装することによって、コマンドレットの、、およびパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-124">`New-Item` cmdlet You can define dynamic parameters that are triggered by the `Path`, `ItemType`, and `Value` parameters of the `New-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-125">`New-ItemProperty` コマンドレットを使用する `Path` `Name` と、 `PropertyType` `Value` `New-ItemProperty` [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) メソッドを実装することによって、コマンドレットの、、、およびパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-125">`New-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path`, `Name`, `PropertyType`, and `Value` parameters of the `New-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-126">`New-PSDrive`コマンドレットを使用して、 [](/dotnet/api/System.Management.Automation.PSDriveInfo) `New-PSDrive` [Drivecmdletprovider. Newdrivedynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドを実装することで、コマンドレットによって返されるSystem.Management.Automation.PSDriveinfo オブジェクトによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-126">`New-PSDrive` cmdlet You can define dynamic parameters that are triggered by the [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) object returned by the `New-PSDrive` cmdlet by implementing the [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-127">`Remove-Item``Path` `Recurse` `Remove-Item` [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッドを実装することによって、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-127">`Remove-Item` You can define dynamic parameters that are triggered by the `Path` and `Recurse` parameters of the `Remove-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-128">`Remove-ItemProperty``Path` `Name` `Remove-ItemProperty` [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッドを実装することによって、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-128">`Remove-ItemProperty` You can define dynamic parameters that are triggered by the `Path` and `Name` parameters of the `Remove-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-129">`Rename-Item` コマンドレットを使用して、 `Path` `NewName` `Rename-Item` [Containercmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-129">`Rename-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `NewName` parameters of the `Rename-Item` cmdlet by implementing the [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-130">`Rename-ItemProperty``Path` `Name` `NewName` `Rename-ItemProperty` [Idynamicpropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッドを実装することによって、コマンドレットの、、およびパラメーターによってトリガーされる動的パラメーターを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="42bec-130">`Rename-ItemProperty` You can define dynamic parameters that are triggered by the `Path`, `Name`, and `NewName` parameters of the `Rename-ItemProperty` cmdlet by implementing the [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-131">`Set-Content` コマンドレットを使用して、 `Path` `Set-Content` [Icontentcmdletprovider. Getcontentwriterdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-131">`Set-Content` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Set-Content` cmdlet by implementing the [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-132">`Set-Item` コマンドレットを使用して、 `Path` `Value` `Set-Item` [Setitemdynamicparameters \*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-132">`Set-Item` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-133">`Set-ItemProperty` コマンドレットを使用して、 `Path` `Value` `Set-Item` [Ipropertycmdletprovider \*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) メソッドを実装することで、コマンドレットのパラメーターとパラメーターによってトリガーされる動的パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="42bec-133">`Set-ItemProperty` cmdlet You can define dynamic parameters that are triggered by the `Path` and `Value` parameters of the `Set-Item` cmdlet by implementing the [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) method.</span></span>

<span data-ttu-id="42bec-134">`Test-Path`コマンドレットを使用すると `Path` 、コマンドレットのパラメーターによってトリガーされる動的パラメーターを定義できます。これを行う `Test-Path` には、このメソッドを実装[](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)します。</span><span class="sxs-lookup"><span data-stu-id="42bec-134">`Test-Path` cmdlet You can define dynamic parameters that are triggered by the `Path` parameter of the `Test-Path` cmdlet by implementing the [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters\*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) method.</span></span>

## <a name="see-also"></a><span data-ttu-id="42bec-135">参照</span><span class="sxs-lookup"><span data-stu-id="42bec-135">See Also</span></span>

[<span data-ttu-id="42bec-136">Windows PowerShell プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="42bec-136">Writing a Windows PowerShell Provider</span></span>](./writing-a-windows-powershell-provider.md)
