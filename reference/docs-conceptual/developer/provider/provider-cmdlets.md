---
title: プロバイダーコマンドレット |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2465420-0970-4408-9ee5-260cf444cb67
caps.latest.revision: 8
ms.openlocfilehash: e6a0711cff6a550100f584fb64ae7f59f71a3cfb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72359981"
---
# <a name="provider-cmdlets"></a>プロバイダー コマンドレット

データストアを管理するためにユーザーが実行できるコマンドレットは、プロバイダーコマンドレットと呼ばれます。 これらのコマンドレットをサポートするには、基本プロバイダーのクラスおよびインターフェイスで定義されているいくつかのメソッドを上書きする必要があります。

## <a name="provider-cmdlets"></a>プロバイダーコマンドレット

ユーザーが実行できるプロバイダーコマンドレットを次に示します。

### <a name="psdrive-cmdlets"></a>PSDrive コマンドレット

- `Get-PSDrive`:このコマンドレットは、現在のセッションの Windows PowerShell ドライブを返します。 このコマンドレットをサポートするために、メソッドを上書きする必要はありません。

- `New-PSDrive`:このコマンドレットを使用すると、ユーザーはデータストアにアクセスするための Windows PowerShell ドライブを作成できます。 このコマンドレットをサポートするには、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と Drivecmdletprovider の各メソッドを上書きします。このコマンドレットをサポートするには、 [Newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドを上書きします。

- `Remove-PSDrive`:このコマンドレットを使用すると、データストアにアクセスする Windows PowerShell ドライブをユーザーが削除できます。 このコマンドレットをサポートするには、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きします。

### <a name="item-cmdlets"></a>項目のコマンドレット

- `Clear-Item`:このコマンドレットを使用すると、ユーザーはデータストア内の項目の値を削除できます。 このコマンドレットをサポートするには、次のように、 [system](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) .................... [..](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)

- `Copy-Item`:このコマンドレットを使用すると、ユーザーは1つの場所から別の場所に項目をコピーできます。 このコマンドレットをサポートするには、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドと[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)メソッドを上書きします。このコマンドレットをサポートするには、次のようにします。

- `Get-Item`:このコマンドレットを使用すると、ユーザーはデータストアからデータを取得できます。 このコマンドレットをサポートするには、 [Getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)メソッドと....................[メソッドを上書き](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)します。

- `Get-ChildItem`:このコマンドレットを使用すると、ユーザーは親項目の子項目を取得できます。 このコマンドレットをサポートするには、次のメソッドを上書きします。

  - [Containercmdletprovider. Getchilditems * を行います。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [Containercmdletprovider. Getchilditemsdynamicparameters * を行います。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [Containercmdletprovider. Getchildnames * のようになります。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [Containercmdletprovider のようにします。 Getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- `Invoke-Item`:このコマンドレットは、ユーザーが項目によって指定された既定のアクションを実行できるようにします。 このコマンドレットをサポートするには、 [Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)と[Invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)の各メソッドを上書きします。このコマンドレットをサポートするには、次のようにします。

- `Move-Item`:このコマンドレットを使用すると、ユーザーは1つの場所から別の場所に項目を移動できます。 このコマンドレットをサポートするには、次のように[して、](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) [system.](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) ......................................。

- `New-ItemProperty`:このコマンドレットを使用すると、ユーザーはデータストアに新しい項目を作成できます。

- `Remove-Item`:このコマンドレットを使用すると、ユーザーはデータストアから項目を削除できます。 このコマンドレットをサポートするには、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドと[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)メソッドを上書きします。このコマンドレットをサポートするには、次のようにします。

- `Rename-Item`:このコマンドレットを使用すると、ユーザーはデータストア内の項目の名前を変更できます。 このコマンドレットをサポートするには、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)および[Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)の各メソッドを上書きします。このコマンドレットをサポートするには、次のようにします。

- `Set-Item`:このコマンドレットを使用すると、ユーザーはデータストア内の項目の値を更新できます。 このコマンドレットをサポートするには、 [Setitem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)と[Setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)の各メソッドを上書きします。このコマンドレットをサポートするには、次のようにします。

### <a name="item-content-cmdlets"></a>項目のコンテンツのコマンドレット

- `Add-Content`:このコマンドレットを使用すると、ユーザーはコンテンツを項目に追加できます。

- `Clear-Content`:このコマンドレットを使用すると、項目を削除せずに項目の内容を削除できます。 このコマンドレットをサポートするには、Icontentcmdletprovider メソッドと[Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)メソッドを上書きします。このコマンドレットの[内容](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)は次のようになります。

- `Get-Content`:このコマンドレットは、ユーザーが項目のコンテンツを取得できるようにします。 このコマンドレットをサポートするには、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)と[Icontentcmdletprovider パラメーター](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)を上書きして、このコマンドレットをサポートします。このコマンドレットは、メソッド. [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドは、コンテンツの読み取りに使用されるメソッドを定義する[Icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader)インターフェイスを返します。このインターフェイスは、コンテンツの読み取りに使用されます。

- `Set-Content`:このコマンドレットを使用すると、ユーザーは項目のコンテンツを更新できます。 このコマンドレットをサポートするには、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)と Icontentcmdletprovider を上書きします。 [Getcontentwriterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)は、このコマンドレットをサポートします。メソッド. [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)メソッドは、コンテンツの書き込みに使用されるメソッドを定義する[Icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)インターフェイスを返します。このインターフェイスは、このインターフェイスを提供します。

### <a name="item-property-cmdlets"></a>Item プロパティのコマンドレット

- `Clear-ItemProperty`:このコマンドレットを使用すると、ユーザーはプロパティの値を削除できます。 このコマンドレットをサポートするには、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)と[Ipropertycmdletprovider パラメーター](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)を上書きして、このコマンドレットをサポートするようにします。メソッド.

- `Copy-ItemProperty`:このコマンドレットを使用すると、ユーザーはプロパティとその値を1つの場所から別の場所にコピーできます。 このコマンドレットをサポートするには、 [Idynamicpropertycmdletprovider プロパティ](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty)を上書きし[、Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters)メソッド (system.object メソッド) を提供します。

- `Get-ItemProperty`:このコマンドレットは、項目のプロパティを取得します。 このコマンドレットをサポートするには、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)メソッドと[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)メソッドを上書きします。このコマンドレットについては、「」をご利用ください。

- `Move-ItemProperty`:このコマンドレットを使用すると、ユーザーはプロパティとその値を1つの場所から別の場所に移動できます。 このコマンドレットをサポートするには、 [Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty)を上書きし[ます。Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters)メソッド (system.object メソッド) を提供します。

- `New-ItemProperty`:このコマンドレットを使用すると、ユーザーは新しいプロパティを作成し、その値を設定できます。 このコマンドレットをサポートするには、 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty)と Idynamicpropertycmdletprovider パラメーターを上書きして、このコマンドレットを次のように上書きします。 [System.Management.Automation.Provider.Idynamicpropertycmdletprovider.Newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)メソッド。

- `Remove-ItemProperty`:このコマンドレットを使用すると、ユーザーはプロパティとその値を削除できます。 このコマンドレットをサポートするには、 [Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)を上書きし[ます。Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)メソッドを管理します。このメソッドは、

- `Rename-ItemProperty`:このコマンドレットを使用すると、ユーザーはプロパティの名前を変更できます。 このコマンドレットをサポートするには、 [Idynamicpropertycmdletprovider プロパティ](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)を上書きし[、Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)メソッドを管理していることをご相談ください。

- `Set-ItemProperty`:このコマンドレットを使用すると、ユーザーは項目のプロパティを更新できます。 このコマンドレットをサポートするには、 [Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)メソッドと[Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)メソッドを上書きします。このコマンドレットについては、「」をご利用ください。

### <a name="location-cmdlets"></a>Location コマンドレット

- `Get-Location`:現在の作業場所に関する情報を取得します。 このコマンドレットをサポートするために、メソッドを上書きする必要はありません。

- `Pop-Location`:このコマンドレットは、現在の場所を最後にスタックにプッシュした場所に変更します。 このコマンドレットをサポートするために、メソッドを上書きする必要はありません。

- `Push-Location`:このコマンドレットは、現在の場所を場所の一覧 ("スタック") の先頭に追加します。 このコマンドレットをサポートするために、メソッドを上書きする必要はありません。

- `Set-Location`:このコマンドレットは、現在の作業場所を指定した場所に設定します。 このコマンドレットをサポートするために、メソッドを上書きする必要はありません。

### <a name="path-cmdlets"></a>Path コマンドレット

- `Join-Path`:このコマンドレットを使用すると、ユーザーは親と子のパスセグメントを組み合わせて、プロバイダーの内部パスを作成できます。 このコマンドレットをサポートするには、次のように[して、](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) system.string メソッドを上書きします。

- `Convert-Path`:このコマンドレットは、Windows PowerShell パスのパスを Windows PowerShell プロバイダーのパスに変換します。

- `Split-Path`:指定されたパス部分を返します。

- `Resolve-Path`:パス中のワイルドカード文字を解決し、パスの内容を表示します。

- `Test-Path`:このコマンドレットは、パスのすべての要素が存在するかどうかを確認します。 このコマンドレットをサポートするには、[システム](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)の....................... [...](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) ................

### <a name="psprovider-cmdlets"></a>PSProvider コマンドレット

- `Get-PSProvider`:このコマンドレットは、セッションで使用可能なプロバイダーに関する情報を返します。 このコマンドレットをサポートするために、メソッドを上書きする必要はありません。