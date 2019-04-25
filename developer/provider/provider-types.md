---
title: プロバイダーの種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523a8e1-42e4-4633-887f-fb74b3464561
caps.latest.revision: 12
ms.openlocfilehash: 37689571eb1650e5991af2e7002cd037ae99dd68
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080912"
---
# <a name="provider-types"></a>プロバイダーの種類

プロバイダーは、(Windows PowerShell によって提供される)、プロバイダーのコマンドレットが操作を実行する方法を変更することで、基本的な機能を定義します。 たとえば、プロバイダーがの既定の機能を使用できます、`Get-Item`コマンドレット、または、データ ストアから項目を取得するときにそのコマンドレットの動作を変更できます。 このトピックで説明されているプロバイダーの機能には、特定のプロバイダーの基底クラスとインターフェイスのメソッドを上書きすることで定義されている機能が含まれています。

> [!NOTE]
> Windows PowerShell によって事前定義されているプロバイダーの機能を参照してください。[プロバイダー機能](http://msdn.microsoft.com/en-us/864e4807-554a-4016-80ea-bf643a090fc6)します。

## <a name="drive-enabled-providers"></a>ドライブが有効なプロバイダー

ドライブが有効なプロバイダーは、ユーザーが利用できる既定のドライブを指定し、ユーザーが追加またはドライブを削除できるようにします。 によって既定のドライブをデータ ストアへのアクセスが必要なために、ほとんどの場合は、プロバイダーはドライブが有効なプロバイダーです。 ただし、独自のプロバイダーを記述する場合は可能性がありますか、しないにすることを作成し、ドライブを削除するユーザーを許可します。

ドライブが有効なプロバイダーを作成するには、プロバイダー クラスから派生する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスまたはそのクラスから派生した別のクラス。 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスは、次のメソッドのプロバイダーの既定のドライブを実装およびサポートを定義、`New-PSDrive`と`Remove-PSDrive`コマンドレット。 ほとんどの場合、プロバイダー コマンドレットをサポートする必要がありますを上書きするなど、コマンドレットを呼び出すため、Windows PowerShell エンジンが呼び出されるメソッド、`NewDrive`のメソッド、`New-PSDrive`コマンドレット、および必要に応じてなどの2番目のメソッドを上書きできます`NewDriveDynamicParameters`、動的パラメーターをコマンドレットに追加するためです。

- [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッドは、プロバイダーが使用されるたびに、ユーザーに提供される既定のドライブを定義します。

- [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドご利用のプロバイダーのサポートを定義、`New-PSDrive`プロバイダー コマンドレット。 このコマンドレットは、データ ストアにアクセスするドライブを作成するユーザーを使用できます。

- [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドは、プロバイダーのサポートを定義、`Remove-PSDrive`プロバイダー コマンドレット。 このコマンドレットは、データ ストアからドライブを削除するユーザーを使用できます。

## <a name="item-enabled-providers"></a>項目が有効なプロバイダー

項目が有効なプロバイダーは、取得、設定、またはデータ ストア内の項目をオフにするユーザーを許可します。 "Item"は、ユーザーはアクセスしたり、個別に管理するデータ ストアの要素です。 項目が有効なプロバイダーを作成するには、プロバイダー クラスから派生する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスまたはそのクラスから派生した別のクラス。

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスは、特定のプロバイダー コマンドレットを実装するために、次のメソッドを定義します。 ほとんどの場合、プロバイダー コマンドレットをサポートする必要がありますを上書きするなど、コマンドレットを呼び出すため、Windows PowerShell エンジンが呼び出されるメソッド、`ClearItem`のメソッド、`Clear-Item`コマンドレット、および必要に応じてなどの2番目のメソッドを上書きできます`ClearItemDynamicParameters`、動的パラメーターをコマンドレットに追加するためです。

- [System.Management.Automation.Provider.Itemcmdletprovider.Clearitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Clearitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)メソッドご利用のプロバイダーのサポートを定義、`Clear-Item`プロバイダー コマンドレット。 このコマンドレットは、データ ストア内の項目の値を削除するユーザーを使用できます。

- [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Getitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドを定義する方法プロバイダーがサポートする、`Get-Item`プロバイダー コマンドレット。 このコマンドレットは、データ ストアからデータを取得できます。

- [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Setitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)メソッドを定義する方法プロバイダーがサポートする、`Set-Item`プロバイダー コマンドレット。 このコマンドレットは、データ ストア内の項目の値を更新するユーザーを使用できます。

- [System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)と[System.Management.Automation.Provider.Itemcmdletprovider.Invokedefaultaction*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)メソッドご利用のプロバイダーのサポートを定義、`Invoke-Item`プロバイダー コマンドレット。 このコマンドレットは、項目によって指定された既定のアクションを実行するユーザーを使用できます。

- [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)と[System.Management.Automation.Provider.Itemcmdletprovider.Itemexistsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)メソッドご利用のプロバイダーのサポートを定義、`Test-Path`プロバイダー コマンドレット。 このコマンドレットは、パスのすべての要素が存在するかどうかを判断するユーザーを使用できます。

  プロバイダーのコマンドレットを実装するために使用する方法だけでなく、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスは、次のメソッドも定義します。

- [System.Management.Automation.Provider.Itemcmdletprovider.Expandpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ExpandPath)メソッドには、プロバイダー パスを指定するときに、ワイルドカードを使用できます。

- [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)パスが構文的および意味的有効なプロバイダーのかを判断するために使用します。

## <a name="container-enabled-providers"></a>コンテナーが有効なプロバイダー

コンテナーが有効なプロバイダーは、コンテナーである項目を管理するユーザーを許可します。 コンテナーは、共通の親項目の子項目のグループです。 コンテナーが有効なプロバイダーを作成するには、プロバイダー クラスから派生する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスまたはそのクラスから派生した別のクラス。

> [!IMPORTANT]
> コンテナーが有効なプロバイダーは、入れ子になったコンテナーを含むデータ ストアにアクセスできません。 コンテナーの子項目が別のコンテナーの場合は、ナビゲーションが有効なプロバイダーを実装する必要があります。

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスは、特定のプロバイダー コマンドレットを実装するために、次のメソッドを定義します。 ほとんどの場合、プロバイダー コマンドレットをサポートする必要がありますを上書きするなど、コマンドレットを呼び出すため、Windows PowerShell エンジンが呼び出されるメソッド、`CopyItem`のメソッド、`Copy-Item`コマンドレット、および必要に応じてなどの2番目のメソッドを上書きできます`CopyItemDynamicParameters`、動的パラメーターをコマンドレットに追加するためです。

- [System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)と[System.Management.Automation.Provider.Containercmdletprovider.Copyitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Copy-Item`プロバイダー コマンドレット。 このコマンドレットは、別の 1 つの場所から項目をコピーするユーザーを使用できます。

- [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)と[System.Management.Automation.Provider.Containercmdletprovider.Getchilditemsdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Get-ChildItem`プロバイダー コマンドレット。 このコマンドレットは、親アイテムの子項目を取得するユーザーを使用できます。

- [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)と[System.Management.Automation.Provider.Containercmdletprovider.Getchildnamesdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Get-ChildItem`プロバイダー コマンドレット場合その`Name`パラメーターを指定します。

- [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)と[System.Management.Automation.Provider.Containercmdletprovider.Newitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)メソッドは、プロバイダーのサポートを定義、`New-Item`プロバイダー コマンドレット。 このコマンドレットは、データ ストアに新しい項目を作成するユーザーを使用できます。

- [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)と[System.Management.Automation.Provider.Containercmdletprovider.Removeitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Remove-Item`プロバイダー コマンドレット。 このコマンドレットは、データ ストアから項目を削除するユーザーを使用できます。

- [System.Management.Automation.Provider.Containercmdletprovider.Renameitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)と[System.Management.Automation.Provider.Containercmdletprovider.Renameitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Rename-Item`プロバイダー コマンドレット。 このコマンドレットは、データ ストア内のアイテムの名前を変更するユーザーを使用できます。

  プロバイダーのコマンドレットを実装するために使用する方法だけでなく、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスは、次のメソッドも定義します。

- [System.Management.Automation.Provider.Containercmdletprovider.Haschilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)項目に子項目があるかどうかを判断するプロバイダー クラスでメソッドを使用できます。

- [System.Management.Automation.Provider.Containercmdletprovider.Convertpath*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.ConvertPath)メソッドは、指定されたパスから新しいプロバイダーに固有のパスを作成するプロバイダー クラスで使用できます。

## <a name="navigation-enabled-providers"></a>ナビゲーションが有効なプロバイダー

ナビゲーションが有効なプロバイダーは、データ ストア内の項目を移動するユーザーを許可します。 ナビゲーションが有効なプロバイダーを作成するには、プロバイダー クラスから派生する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスは、特定のプロバイダー コマンドレットを実装するために、次のメソッドを定義します。 ほとんどの場合、プロバイダー コマンドレットをサポートする必要がありますを上書きするなど、コマンドレットを呼び出すため、Windows PowerShell エンジンが呼び出されるメソッド、`MoveItem`のメソッド、`Move-Item`コマンドレット、および必要に応じてなどの2番目のメソッドを上書きできます`MoveItemDynamicParameters`、動的パラメーターをコマンドレットに追加するためです。

- [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)と[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Move-Item`プロバイダー コマンドレット。 このコマンドレットは、ストア内の 1 つの場所から別の場所に項目を移動するユーザーを使用できます。

- [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドは、プロバイダーのサポートを定義、`Join-Path`プロバイダー コマンドレット。 このコマンドレットは、プロバイダーの内部パスを作成する親と子パス セグメントを結合するユーザーを使用できます。

  プロバイダーのコマンドレットを実装するために使用する方法だけでなく、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスは、次のメソッドも定義します。

- [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)メソッドは、パスの子ノードの名前を抽出します。

- [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドが親のパス部分を抽出します。

- [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドは、項目は、コンテナー項目かどうかを判断します。 このコンテキストでは、コンテナーは、共通の親項目の下の子項目のグループです。

- [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)メソッドのパスが指定の基本パスに関連する項目を返します。

## <a name="content-enabled-providers"></a>コンテンツが有効なプロバイダー

プロバイダーのコンテンツが有効なアクセス許可をオフに、取得、またはデータ ストアで項目の内容を設定します。 たとえば、FileSystem プロバイダーを使用すると、オフにして、取得、ファイル システム内のファイルの内容を設定できます。 コンテンツが有効なプロバイダーを作成する、プロバイダー クラスのメソッドを実装する必要があります、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。

[System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスは、特定のプロバイダー コマンドレットを実装するために、次のメソッドを定義します。 ほとんどの場合、プロバイダー コマンドレットをサポートする必要がありますを上書きするなど、コマンドレットを呼び出すため、Windows PowerShell エンジンが呼び出されるメソッド、`ClearContent`のメソッド、`Clear-Content`コマンドレット、および必要に応じてなどの2番目のメソッドを上書きできます`ClearContentDynamicParameters`、動的パラメーターをコマンドレットに追加するためです。

- [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)と[System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontentdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Clear-Content`プロバイダー コマンドレット。 このコマンドレットは、項目を削除することがなく、項目のコンテンツを削除するユーザーを使用できます。

- [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)と[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreaderdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Get-Content`プロバイダー コマンドレット。 このコマンドレットは、項目のコンテンツを取得するユーザーを使用できます。 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドが返す、 [System.Management.Automation.Provider.Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)を定義するインターフェイスコンテンツの読み取りに使用するメソッド。

- [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)と[System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriterdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Set-Content`プロバイダー コマンドレット。 このコマンドレットは、項目のコンテンツを更新するユーザーを使用できます。 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentwriter*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドが返す、 [System.Management.Automation.Provider.Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)を定義するインターフェイスコンテンツの書き込みに使用するメソッド。

## <a name="property-enabled-providers"></a>プロパティが有効なプロバイダー

プロパティが有効なプロバイダーは、データ ストア内の項目のプロパティを管理するユーザーを許可します。 プロパティが有効なプロバイダーを作成する、プロバイダー クラスのメソッドを実装する必要があります、 [System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider)インターフェイス。 ほとんどの場合、プロバイダー コマンドレットをサポートする必要がありますを上書きするなど、コマンドレットを呼び出すため、Windows PowerShell エンジンが呼び出されるメソッド、`ClearProperty`クリア プロパティ コマンドレット、および必要に応じてメソッドがなどの2番目のメソッドを上書きできます`ClearPropertyDynamicParameters`、動的パラメーターをコマンドレットに追加するためです。

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイスは、特定のプロバイダー コマンドレットを実装するために、次のメソッドを定義します。

- [System.Management.Automation.Provider.Ipropertycmdletprovider.Clearproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)と[System.Management.Automation.Provider.Ipropertycmdletprovider.Clearpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Clear-ItemProperty`プロバイダー コマンドレット。 このコマンドレットは、プロパティの値を削除するユーザーを使用できます。

- [System.Management.Automation.Provider.Ipropertycmdletprovider.Getproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)と[System.Management.Automation.Provider.Ipropertycmdletprovider.Getpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Get-ItemProperty`プロバイダー コマンドレット。 このコマンドレットは、項目のプロパティを取得するユーザーを使用できます。

- [System.Management.Automation.Provider.Ipropertycmdletprovider.Setproperty*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)と[System.Management.Automation.Provider.Ipropertycmdletprovider.Setpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Set-ItemProperty`プロバイダー コマンドレット。 このコマンドレットは、アイテムのプロパティを更新するユーザーを使用できます。

  [System.Management.Automation.Provider.Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider)インターフェイスは、特定のプロバイダー コマンドレットを実装するために、次のメソッドを定義します。

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copyproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Copypropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Copy-ItemProperty`プロバイダー コマンドレット。 このコマンドレットは、1 つの場所からプロパティとその値をコピーするユーザーを使用できます。

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Moveproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Movepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Move-ItemProperty`プロバイダー コマンドレット。 このコマンドレットは、1 つの場所からプロパティとその値を移動するユーザーを使用できます。

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`New-ItemProperty`プロバイダー コマンドレット。 このコマンドレットは、新しいプロパティを作成し、その値を設定できます。

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removeproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Removepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Remove-ItemProperty`コマンドレット。 このコマンドレットは、プロパティとその値を削除するユーザーを使用できます。

- [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renameproperty*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)と[System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Renamepropertydynamicparameters*](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッドは、プロバイダーのサポートを定義、`Rename-ItemProperty`コマンドレット。 このコマンドレットは、プロパティの名前を変更するユーザーを使用できます。

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの記述](./writing-a-windows-powershell-provider.md)