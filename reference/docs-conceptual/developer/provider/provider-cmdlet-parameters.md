---
title: プロバイダーコマンドレット parameters |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d09eaa-924f-4e2b-adfb-14bb729090dd
caps.latest.revision: 8
ms.openlocfilehash: ad7f9737c646dd5cea5abb14b828236e40feac5a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366311"
---
# <a name="provider-cmdlet-parameters"></a>コマンドレット コマンドレットのパラメーター

プロバイダーコマンドレットには、コマンドレットをサポートするすべてのプロバイダーが使用できる一連の静的パラメーターと、ユーザーがプロバイダーコマンドレットの特定の静的パラメーターに特定の値を指定したときに追加される動的パラメーターのセットが付属しています。

## <a name="provider-cmdlet-static-parameters"></a>プロバイダーコマンドレットの静的パラメーター

静的パラメーターは、Windows PowerShell によって定義されます。 これらのパラメーターの大規模なセットは、すべてのプロバイダー間で一貫性を提供し、より簡単な開発環境を提供するために、Windows PowerShell によって実装されます。 これらのパラメーターの例としては、`Get-Item` コマンドレットの `literalPath`、`exclude`、`include` の各パラメーターがあります。 これらのパラメーターの小さなセットを上書きして、プロバイダーに固有のアクションを提供できます。 これらのパラメーターの例としては、`Set-Item` コマンドレットの `Path` と `Value` パラメーターがあります。 プロバイダーコマンドレットで上書きできるパラメーターの一覧を次に示します。

`Clear-Content` コマンドレットを使用すると、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを実装することによって、`Clear-Content` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Clear-Item` コマンドレットを使用すると、`Clear-Item` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。そのためには、[このメソッドを](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)実装します。

`Clear-ItemProperty` コマンドレットを使用すると、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)メソッドを実装することによって、`Clear-ItemProperty` コマンドレットの `Path` および `Name` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Copy-Item` コマンドレットを使用すると、 [ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)を実装することによって、`Copy-Item` コマンドレットの `Path`、`Destination`、および `Recurse` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。b.

ChildItems コマンドレットは、 [Containercmdletprovider Getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)を実装することによって、`Get-ChildItem` コマンドレットの `Path` および `Recurse` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。と[Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッドを提供しているとします。

`Get-Content` コマンドレットを使用すると、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを実装することによって、`Get-Content` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Get-Item` コマンドレットを使用すると、`Get-Item` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。これを行うには、[このメソッドを](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)実装します。

`Get-ItemProperty` コマンドレットを使用すると、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッドを実装することによって、`Get-ItemProperty` コマンドレットの `Path` および `Name` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Invoke-Item` コマンドレットを使用すると、 [Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッドを実装することによって、`Invoke-Item` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Move-Item` コマンドレットを使用すると、`Move-Item` コマンドレットの `Path` パラメーターと `Destination` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。そのためには、[このメソッドを](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)実装します。

`New-Item` コマンドレットでは、 [Containercmdletprovider Newitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)を実装することによって、`New-Item` コマンドレットの `Path`、`ItemType`、および `Value` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。b.

`New-ItemProperty` コマンドレットを使用すると、`Value` コマンドレットの `Path`、`Name`、`PropertyType`、および `New-ItemProperty` パラメーターに渡された値をプロバイダーがどのように使用するかを定義でき[ます。](/dotnet/api/Microsoft.PowerShell.Commands.RegistryProvider.NewProperty)b.

`Remove-Item`、 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドを実装することによって、`Remove-Item` コマンドレットの `Path` および `Recurse` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Remove-ItemProperty`、 [Idynamicpropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)を実装することによって、`Remove-ItemProperty` コマンドレットの `Path` および `Name` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。b.

`Rename-Item` コマンドレットでは、 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)メソッドを実装することによって、`Rename-Item` コマンドレットの `Path` および `NewName` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Rename-ItemProperty`、Idynamicpropertycmdletprovider * を実装することによって`Path`、`Rename-ItemProperty` コマンドレットの 、`NewName`、および `Name` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)メソッド。

`Set-Content` コマンドレットを使用すると、 [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドを実装することによって、`Set-Content` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Set-Item` コマンドレットでは、 [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを実装することによって、`Set-Item` コマンドレットの `Path` および `Value` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Set-ItemProperty` コマンドレットでは、 [Ipropertycmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドを実装することによって、`Set-Item` コマンドレットの `Path` および `Value` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

`Test-Path` コマンドレットを使用すると、 [Invokedefaultaction *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッドを実装することによって、`Test-Path` コマンドレットの `Path` パラメーターに渡された値をプロバイダーがどのように使用するかを定義できます。

また、これらのパラメーターの特性を指定することはできません。これらのパラメーターが省略可能か必須かなど、これらのパラメーターにエイリアスを指定したり、検証属性を指定したりすることはできません。 これに対して、`Parameters` 属性などの属性を使用して、スタンドアロンのコマンドレットでパラメーターの特性を指定することができます。

## <a name="provider-cmdlet-dynamic-parameters"></a>プロバイダーコマンドレット動的パラメーター

コマンドレットプロバイダーの動的パラメーターは、スタンドアロンのコマンドレットの動的プロバイダーに似ています。 どちらの場合も、パラメーターは、ユーザーが `path` パラメーターなどの既定のパラメーターのいずれかに特定の値を指定すると、コマンドレットに追加されます。 ただし、動的パラメーターの追加をトリガーするために、すべての静的パラメーターを使用できるわけではありません。 動的パラメーターの詳細については、「[プロバイダーコマンドレット動的パラメーター](./provider-cmdlet-dynamic-parameters.md)」を参照してください。

## <a name="see-also"></a>参照

[プロバイダーコマンドレット動的パラメーター](./provider-cmdlet-dynamic-parameters.md)

[Windows PowerShell プロバイダーの作成](./writing-a-windows-powershell-provider.md)