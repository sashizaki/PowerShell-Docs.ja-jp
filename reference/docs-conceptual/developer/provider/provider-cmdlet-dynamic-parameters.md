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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359951"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>コマンドレット コマンドレットの動的パラメーター

プロバイダーは、ユーザーがコマンドレットのいずれかの静的パラメーターに特定の値を指定した場合に、プロバイダーコマンドレットに追加される動的パラメーターを定義できます。 たとえば、プロバイダーは、`Get-Item` または `Set-Item` プロバイダーコマンドレットを呼び出すときに、ユーザーが指定するパスに基づいて、さまざまな動的パラメーターを追加できます。

## <a name="dynamic-parameter-methods"></a>動的パラメーターメソッド

動的パラメーターは、 [Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)および[Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s メソッドなどの動的パラメーターメソッドの1つを実装することによって定義されています。このメソッドについては、「」をご指定ください。 これらのメソッドは、スタンドアロンのコマンドレットと同様の属性で装飾されたパブリックプロパティを持つオブジェクトを返します。 次に示すのは、証明書プロバイダーから取得した[Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドの実装例です。次に例を示します。

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

プロバイダーコマンドレットの静的パラメーターとは異なり、スタンドアロンのコマンドレットでパラメーターを定義するのと同じ方法で、これらのパラメーターの特性を指定できます。 証明書プロバイダーから取得した動的パラメータークラスの例を次に示します。

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

## <a name="dynamic-parameters"></a>動的パラメーター

動的パラメーターの追加に使用できる静的パラメーターの一覧を次に示します。

`Clear-Content` コマンドレットを使用すると、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッドを実装することにより、clear clear コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Clear-Item` コマンドレットを使用すると、`Clear-Item` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、[このメソッドを](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)実装します。

`Clear-ItemProperty` コマンドレットを使用すると、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッドを実装することによって、`Clear-ItemProperty` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Copy-Item` コマンドレットを使用すると、 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッドを実装することによって、`Copy-Item` コマンドレットの `Path`、`Destination`、および `Recurse` パラメーターによってトリガーされる動的パラメーターを定義できます。

ChildItems コマンドレットは、 [Getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)メソッドと Containercmdletprovider パラメーター * メソッドを実装することによって、`Get-ChildItem` コマンドレットの `Path` および `Recurse` パラメーターによってトリガーされる動的パラメーターを定義できます。この引数には、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)を使用します。

`Get-Content` コマンドレットを使用すると、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッドを実装することによって、`Get-Content` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Get-Item` コマンドレットを使用すると、 [Getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドを実装することによって、`Get-Item` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Get-ItemProperty` コマンドレットでは、Ipropertycmdletprovider を実装することによって、`Get-ItemProperty` コマンドレットの `Path` と `Name` パラメーターによってトリガーされる動的パラメーターを定義できます。 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッド。

`Invoke-Item` コマンドレットを使用すると、`Invoke-Item` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、 [Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)メソッドを実装します。

`Move-Item` コマンドレットを使用すると、`Move-Item` コマンドレットの `Path` と `Destination` パラメーターによってトリガーされる動的パラメーターを定義できます。これを行うに[は、](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)コマンドレットを使用します。

`New-Item` コマンドレットを使用すると、 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)メソッドを実装することによって、`New-Item` コマンドレットの `Path`、`ItemType`、および `Value` パラメーターによってトリガーされる動的パラメーターを定義できます。

`New-ItemProperty` コマンドレットを使用すると、 [Idynamicpropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)メソッドを実装することによって、`Value` コマンドレットの `Path`、`Name`、`PropertyType`、および `New-ItemProperty` パラメーターによってトリガーされる動的パラメーターを定義できます。

`New-PSDrive` コマンドレットを使用して、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) `New-PSDrive` コマンドレットによって返される system.management.automation.psdriveinfo オブジェクトによってトリガーされる動的パラメーターを定義できます。[System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドを提供します。

`Remove-Item`、 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッドを実装することによって、`Remove-Item` コマンドレットの `Path` と `Recurse` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Remove-ItemProperty`、 [Idynamicpropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッドを実装することによって、`Remove-ItemProperty` コマンドレットの `Path` と `Name` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Rename-Item` コマンドレットでは、Containercmdletprovider を実装することによって、`Rename-Item` コマンドレットの `Path` と `NewName` パラメーターによってトリガーされる動的パラメーターを定義できます。 [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッド。

`Rename-ItemProperty`、 [Idynamicpropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッドを実装することによって、`Rename-ItemProperty` コマンドレットの `Path`、`Name`、および `NewName` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Set-Content` コマンドレットでは、 [Getcontentwriterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)メソッドを実装することによって、`Set-Content` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Set-Item` コマンドレットでは、 [Setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッドを実装することによって、`Set-Item` コマンドレットの `Path` と `Value` パラメーターによってトリガーされる動的パラメーターを定義できます。

`Set-ItemProperty` コマンドレットでは、Ipropertycmdletprovider を実装することによって、`Set-Item` コマンドレットの `Path` と `Value` パラメーターによってトリガーされる動的パラメーターを定義できます。 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッド。

`Test-Path` コマンドレットを使用すると、`Test-Path` コマンドレットの `Path` パラメーターによってトリガーされる動的パラメーターを定義できます。そのためには、 [Invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)メソッドを実装します。

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの作成](./writing-a-windows-powershell-provider.md)