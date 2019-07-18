---
title: プロバイダー コマンドレットのパラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d09eaa-924f-4e2b-adfb-14bb729090dd
caps.latest.revision: 8
ms.openlocfilehash: ad7f9737c646dd5cea5abb14b828236e40feac5a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081140"
---
# <a name="provider-cmdlet-parameters"></a>コマンドレット コマンドレットのパラメーター

プロバイダー コマンドレットは、静的パラメーター コマンドレットをサポートするすべてのプロバイダーを利用できる、ユーザーが特定の値プロバイダー コマンドレットの特定の静的パラメーターを指定する場合に追加されたも動的パラメーターのセットに付属します。

## <a name="provider-cmdlet-static-parameters"></a>プロバイダー コマンドレットの静的パラメーター

静的パラメーターは、Windows PowerShell によって定義されます。 これらのパラメーターの大規模なセットは、すべてのプロバイダーに一貫性を提供し、単純な開発エクスペリエンスを提供する Windows PowerShell によって実装されます。 これらのパラメーターの例、 `literalPath`、 `exclude`、および`include`のパラメーター、`Get-Item`コマンドレット。 これらのパラメーターの小さなセットを上書きすると、プロバイダーに固有のアクションを提供します。 これらのパラメーターの例、`Path`と`Value`のパラメーター、`Set-Item`コマンドレット。 プロバイダー コマンドレットの上書き可能なパラメーターの一覧を示します。

`Clear-Content` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Clear-Content`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッド。

`Clear-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Clear-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)メソッド。

`Clear-ItemProperty` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Name`のパラメーター、`Clear-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッド。

`Copy-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、 `Path`、 `Destination`、および`Recurse`のパラメーター、`Copy-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッド。

Get ChildItems のコマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Recurse`のパラメーター、`Get-ChildItem`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)と[System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッド。

`Get-Content` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Get-Content`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッド。

`Get-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Get-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッド。

`Get-ItemProperty` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Name`のパラメーター、`Get-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッド。

`Invoke-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Invoke-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッド。

`Move-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Destination`のパラメーター、`Move-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッド。

`New-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、 `Path`、 `ItemType`、および`Value`のパラメーター、`New-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッド。

`New-ItemProperty` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、 `Path`、 `Name`、 `PropertyType`、および`Value`のパラメーター、`New-ItemProperty`コマンドレットを実装することによって、 [Microsoft.PowerShell.Commands.Registryprovider.Newproperty*](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty)メソッド。

`Remove-Item` ご利用のプロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Recurse`のパラメーター、`Remove-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッド。

`Remove-ItemProperty` ご利用のプロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Name`のパラメーター、`Remove-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)メソッド。

`Rename-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`NewName`のパラメーター、`Rename-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッド。

`Rename-ItemProperty` ご利用のプロバイダーに渡される値を使用する方法を定義することができます、 `Path`、 `NewName`、および`Name`のパラメーター、`Rename-ItemProperty`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)メソッド。

`Set-Content` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Set-Content`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッド。

`Set-Item` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Value`のパラメーター、`Set-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッド。

`Set-ItemProperty` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`と`Value`のパラメーター、`Set-Item`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッド。

`Test-Path` コマンドレット、プロバイダーに渡される値を使用する方法を定義することができます、`Path`のパラメーター、`Test-Path`コマンドレットを実装することによって、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッド。

さらに、省略可能または必須、されるかどうかなど、これらのパラメーターの特性を指定することはできずするこれらのパラメーターのエイリアスを提供したり、検証属性のいずれかを指定します。 などの属性を使用して、これに対し、スタンドアロンのコマンドレットでパラメーターの特性を指定することができます、`Parameters`属性。

## <a name="provider-cmdlet-dynamic-parameters"></a>プロバイダー コマンドレットの動的パラメーター

コマンドレットのプロバイダーの動的パラメーターは、スタンドアロンのコマンドレットのプロバイダーを動的に似ています。 ユーザーなどの既定のパラメーターのいずれかの特定の値を指定する場合は、パラメーターをコマンドレットに追加するようどちらの場合で、`path`パラメーター。 ただし、動的パラメーターの追加をトリガーするすべての静的パラメーター使用できます。 動的パラメーターの詳細については、次を参照してください。[プロバイダー コマンドレットの動的パラメーター](./provider-cmdlet-dynamic-parameters.md)します。

## <a name="see-also"></a>参照

[プロバイダー コマンドレットの動的パラメーター](./provider-cmdlet-dynamic-parameters.md)

[Windows PowerShell プロバイダーの記述](./writing-a-windows-powershell-provider.md)