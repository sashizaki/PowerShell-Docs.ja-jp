---
title: プロバイダーのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4933dad-fec9-4337-a1a9-9dc16ee87cc3
caps.latest.revision: 9
ms.openlocfilehash: 1e7aeb5bcb6bd5a2845648c3327e2245e6c428ba
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080936"
---
# <a name="provider-samples"></a>プロバイダーのサンプル

このセクションには、Microsoft Access データベースにアクセスするプロバイダーのサンプルが含まれます。 これらのサンプルには、すべてのプロバイダーの基本クラスから派生するプロバイダー クラスが含まれます。

## <a name="in-this-section"></a>このセクションの内容

このセクションには、次のトピックがあります。

[AccessDBProviderSample01 サンプル](./accessdbprovidersample01.md)から直接派生するプロバイダー クラスを宣言する方法を示します、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラス。 すべてを網羅しておく目的でここに含めておきます。

[AccessDBProviderSample02](./accessdbprovidersample02.md)このサンプルを上書きする方法を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)と[System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド呼び出しをサポートする、`New-PSDrive`と`Remove-PSDrive`コマンドレット。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラス。

[AccessDBProviderSample03](./accessdbprovidersample03.md)このサンプルを上書きする方法を示しています、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッド呼び出しをサポートする、`Get-Item`と`Set-Item`コマンドレット。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。

[AccessDBProviderSample04](./accessdbprovidersample04.md)への呼び出しをサポートするためにコンテナー メソッドを上書きする方法を示します、 `Copy-Item`、 `Get-ChildItem`、 `New-Item`、および`Remove-Item`コマンドレット。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。

[AccessDBProviderSample05](./accessdbprovidersample05.md)への呼び出しをサポートするためにコンテナー メソッドを上書きする方法を示します、`Move-Item`と`Join-Path`コマンドレット。 これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。

[AccessDBProviderSample06](./accessdbprovidersample06.md)呼び出しをサポートするコンテンツのメソッドを上書きする方法を示します、 `Clear-Content`、 `Get-Content`、および`Set-Content`コマンドレット。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス、およびその実装、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの記述](./writing-a-windows-powershell-provider.md)