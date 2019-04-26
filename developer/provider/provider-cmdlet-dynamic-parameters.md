---
title: プロバイダー コマンドレットの動的パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f1069f7-8fa8-4622-9e2c-af29b0b961c2
caps.latest.revision: 6
ms.openlocfilehash: a50de014988336c473c565b506a73de1c864d7e0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080970"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>コマンドレット コマンドレットの動的パラメーター

プロバイダーは、ユーザーがコマンドレットの静的パラメーターのいずれかの特定の値を指定すると、プロバイダー コマンドレットに追加される動的パラメーターを定義できます。 プロバイダーがベースの他の動的パラメーターを追加するなど、どのようなパスで、ユーザーを指定します、呼び出すときに、`Get-Item`または`Set-Item`プロバイダー コマンドレット。

## <a name="dynamic-parameter-methods"></a>動的パラメーター メソッド

によって、動的パラメーターのいずれかのように実装する動的パラメーターが定義されている、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)と[System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッド。 これらのメソッドは、スタンドアロンのコマンドレットのと同様の属性で装飾するパブリック プロパティを持つオブジェクトを返します。 実装の例を次に示します、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドは、証明書プロバイダーから取得されます。

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

プロバイダーのコマンドレットの静的パラメーターとは異なり、スタンドアロンのコマンドレットでパラメーターが定義されている同じ方法でこれらのパラメーターの特性を指定できます。 証明書プロバイダーから取得した動的パラメーター クラスの例を次に示します。

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

動的パラメーターを追加するために使用する静的パラメーターの一覧を示します。

`Clear-Content` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`実装することでクリア クリア コマンドレットのパラメーター、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッド。

`Clear-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Clear-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)メソッド。

`Clear-ItemProperty` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Clear-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッド。

`Copy-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、 `Path`、 `Destination`、および`Recurse`のパラメーター、`Copy-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッド。

Get ChildItems コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`と`Recurse`のパラメーター、`Get-ChildItem`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)と[System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)メソッド。

`Get-Content` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Get-Content`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッド。

`Get-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Get-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッド。

`Get-ItemProperty` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`と`Name`のパラメーター、`Get-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッド。

`Invoke-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Invoke-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)メソッド。

`Move-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`と`Destination`のパラメーター、`Move-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)メソッド。

`New-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、 `Path`、 `ItemType`、および`Value`のパラメーター、`New-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)メソッド。

`New-ItemProperty` コマンドレットによってトリガーされる動的パラメーターを定義することができます、 `Path`、 `Name`、 `PropertyType`、および`Value`のパラメーター、`New-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)メソッド。

`New-PSDrive` コマンドレットによってトリガーされる動的パラメーターを定義することができます、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)によって返されるオブジェクト、`New-PSDrive`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッド。

`Remove-Item` によってトリガーされる動的パラメーターを定義することができます、`Path`と`Recurse`のパラメーター、`Remove-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッド。

`Remove-ItemProperty` によってトリガーされる動的パラメーターを定義することができます、`Path`と`Name`のパラメーター、`Remove-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッド。

`Rename-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`と`NewName`のパラメーター、`Rename-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッド。

`Rename-ItemProperty` によってトリガーされる動的パラメーターを定義することができます、 `Path`、 `Name`、および`NewName`のパラメーター、`Rename-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッド。

`Set-Content` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Set-Content`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)メソッド。

`Set-Item` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`と`Value`のパラメーター、`Set-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッド。

`Set-ItemProperty` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`と`Value`のパラメーター、`Set-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッド。

`Test-Path` コマンドレットによってトリガーされる動的パラメーターを定義することができます、`Path`のパラメーター、`Test-Path`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultactiondynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters)メソッド。

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの記述](./writing-a-windows-powershell-provider.md)