---
title: プロバイダーのコマンドレット |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2465420-0970-4408-9ee5-260cf444cb67
caps.latest.revision: 8
ms.openlocfilehash: e6a0711cff6a550100f584fb64ae7f59f71a3cfb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854768"
---
# <a name="provider-cmdlets"></a>プロバイダー コマンドレット

データ ストアを管理するユーザーが実行できるコマンドレット、プロバイダー コマンドレットと呼ばれます。 これらのコマンドレットをサポートするには、基本プロバイダー クラスとインターフェイスで定義されているメソッドの一部を上書きする必要があります。

## <a name="provider-cmdlets"></a>プロバイダーのコマンドレット

ユーザーが実行できる、プロバイダー コマンドレットを次に示します。

### <a name="psdrive-cmdlets"></a>PSDrive コマンドレット

- `Get-PSDrive`:このコマンドレットは、現在のセッションでの Windows PowerShell ドライブを返します。 このコマンドレットをサポートする任意のメソッドを上書きする必要はありません。

- `New-PSDrive`:このコマンドレットは、データ ストアにアクセスする Windows PowerShell ドライブを作成するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッド。

- `Remove-PSDrive`:このコマンドレットは、データ ストアにアクセスする Windows PowerShell ドライブを削除するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド。

### <a name="item-cmdlets"></a>項目のコマンドレット

- `Clear-Item`:このコマンドレットは、データ ストア内の項目の値を削除するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)メソッド。

- `Copy-Item`:このコマンドレットは、別の 1 つの場所から項目をコピーするユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Copyitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)と[System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッド。

- `Get-Item`:このコマンドレットは、データ ストアからデータを取得できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッド。

- `Get-ChildItem`:このコマンドレットは、親アイテムの子項目を取得するユーザーを使用できます。 このコマンドレットをサポートするために、次のメソッドを上書きします。

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- `Invoke-Item`:このコマンドレットは、項目によって指定された既定のアクションを実行するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)と[System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッド。

- `Move-Item`:このコマンドレットは、1 つの場所から別の場所に項目を移動するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)と[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)メソッド。

- `New-ItemProperty`:このコマンドレットは、データ ストアに新しい項目を作成するユーザーを使用できます。

- `Remove-Item`:このコマンドレットは、データ ストアから項目を削除するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)と[System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッド。

- `Rename-Item`:このコマンドレットは、データ ストア内のアイテムの名前を変更するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Renameitem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)と[System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッド。

- `Set-Item`:このコマンドレットは、データ ストア内の項目の値を更新するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッド。

### <a name="item-content-cmdlets"></a>項目のコンテンツのコマンドレット

- `Add-Content`:このコマンドレットは、コンテンツ項目を追加するユーザーを使用できます。

- `Clear-Content`:このコマンドレットは、項目から項目を削除することがなくコンテンツを削除するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)と[System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッド。

- `Get-Content`:このコマンドレットは、項目のコンテンツを取得するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)と[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッド。 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドが返す、 [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)を定義するインターフェイスコンテンツの読み取りに使用するメソッド。

- `Set-Content`:このコマンドレットは、項目のコンテンツを更新するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)と[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)メソッド。 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドが返す、 [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)を定義するインターフェイスコンテンツの書き込みに使用するメソッド。

### <a name="item-property-cmdlets"></a>項目プロパティのコマンドレット

- `Clear-ItemProperty`:このコマンドレットは、プロパティの値を削除するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)と[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッド。

- `Copy-ItemProperty`:このコマンドレットは、1 つの場所からプロパティとその値をコピーするユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters)メソッド。

- `Get-ItemProperty`:このコマンドレットは、アイテムのプロパティを取得します。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)と[System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッド。

- `Move-ItemProperty`:このコマンドレットは、1 つの場所からプロパティとその値を移動するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters)メソッド。

- `New-ItemProperty`:このコマンドレットは、新しいプロパティを作成し、その値を設定できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)メソッド。

- `Remove-ItemProperty`:このコマンドレットは、プロパティとその値を削除するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッド。

- `Rename-ItemProperty`:このコマンドレットは、プロパティの名前を変更するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッド。

- `Set-ItemProperty`:このコマンドレットは、アイテムのプロパティを更新するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)と[System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッド。

### <a name="location-cmdlets"></a>Location コマンドレット

- `Get-Location`:現在の作業場所に関する情報を取得します。 このコマンドレットをサポートする任意のメソッドを上書きする必要はありません。

- `Pop-Location`:このコマンドレットは、最後にスタックにプッシュする場所を現在の場所を変更します。 このコマンドレットをサポートする任意のメソッドを上書きする必要はありません。

- `Push-Location`:このコマンドレットは、(「スタック」) の場所の一覧の先頭に、現在の場所を追加します。 このコマンドレットをサポートする任意のメソッドを上書きする必要はありません。

- `Set-Location`:このコマンドレットは、指定した場所に、現在の場所を設定します。 このコマンドレットをサポートする任意のメソッドを上書きする必要はありません。

### <a name="path-cmdlets"></a>パス コマンドレット

- `Join-Path`:このコマンドレットは、プロバイダーの内部パスを作成する親と子パス セグメントを結合するユーザーを使用できます。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッド。

- `Convert-Path`:このコマンドレットは、パスを Windows PowerShell パスから Windows PowerShell プロバイダー パスに変換します。

- `Split-Path`:指定されたパス部分を返します。

- `Resolve-Path`:パス中のワイルドカード文字を解決し、パスの内容を表示します。

- `Test-Path`:このコマンドレットは、パスのすべての要素が存在するかどうかを判断します。 このコマンドレットをサポートするためには、上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)と[System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)メソッド。

### <a name="psprovider-cmdlets"></a>PSProvider コマンドレット

- `Get-PSProvider`:このコマンドレットは、セッションで使用できるプロバイダーに関する情報を返します。 このコマンドレットをサポートする任意のメソッドを上書きする必要はありません。