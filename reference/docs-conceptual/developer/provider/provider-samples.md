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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366301"
---
# <a name="provider-samples"></a>プロバイダーのサンプル

このセクションには、Microsoft Access データベースにアクセスするプロバイダーのサンプルが含まれています。 これらのサンプルには、すべての基本プロバイダークラスから派生するプロバイダークラスが含まれています。

## <a name="in-this-section"></a>このセクションの内容

このセクションには、次のトピックがあります。

[AccessDBProviderSample01 サンプル](./accessdbprovidersample01.md)このサンプルでは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスから直接派生するプロバイダークラスを宣言する方法を示します。 すべてを網羅しておく目的でここに含めておきます。

[AccessDBProviderSample02](./accessdbprovidersample02.md)このサンプルでは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) * メソッドと[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きして、`New-PSDrive` と `Remove-PSDrive` のコマンドレットの呼び出しをサポートする方法を示します。この例では、. このサンプルのプロバイダークラスは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスから派生しています。

[AccessDBProviderSample03](./accessdbprovidersample03.md)このサンプルで[は、](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) Setitem * メソッドと `Set-Item` コマンドレット `Get-Item` の呼び出しをサポートするように、 [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きする方法を示します。この例では、これらのメソッドをオーバーライドします。 このサンプルのプロバイダークラスは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスから派生しています。

[AccessDBProviderSample04](./accessdbprovidersample04.md)このサンプルでは、コンテナーメソッドを上書きして、`Copy-Item`、`Get-ChildItem`、`New-Item`、および `Remove-Item` コマンドレットの呼び出しをサポートする方法を示します。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダークラスは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生しています。

[AccessDBProviderSample05](./accessdbprovidersample05.md)このサンプルでは、コンテナーメソッドを上書きして、`Move-Item` および `Join-Path` のコマンドレットの呼び出しをサポートする方法を示します。 これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。 このサンプルのプロバイダークラス[は、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生しています。

[AccessDBProviderSample06](./accessdbprovidersample06.md)このサンプルでは、`Clear-Content`、`Get-Content`、および `Set-Content` コマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示します。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダークラスは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを実装しています。この[クラスは、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生していますが、

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの作成](./writing-a-windows-powershell-provider.md)