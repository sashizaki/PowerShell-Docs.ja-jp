---
title: プロバイダーのサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9eb8eb64bbe585ebd8024c0215853ff04a5c3e54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778433"
---
# <a name="provider-samples"></a>プロバイダーのサンプル

このセクションには、Microsoft Access データベースにアクセスするプロバイダーのサンプルが含まれています。 これらのサンプルには、すべての基本プロバイダークラスから派生するプロバイダークラスが含まれています。

## <a name="in-this-section"></a>このセクションの内容

ここでは、次のトピックについて説明します。

[AccessDBProviderSample01 サンプル](./accessdbprovidersample01.md)このサンプルでは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスから直接派生するプロバイダークラスを宣言する方法を示します。 すべてを網羅しておく目的でここに含めておきます。

[AccessDBProviderSample02](./accessdbprovidersample02.md)このサンプルでは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) * メソッドと[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きし `New-PSDrive` て、コマンドレットとコマンドレットの呼び出しをサポートする方法を示しています。この例を次に示し `Remove-PSDrive` ます。 このサンプルのプロバイダークラスは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスから派生しています。

[AccessDBProviderSample03](./accessdbprovidersample03.md)このサンプルでは、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)およびコマンドレットの呼び出しをサポートするために、 [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きする方法について説明します。この例では、をオーバーライドしています。 `Get-Item` `Set-Item` このサンプルのプロバイダークラスは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスから派生しています。

[AccessDBProviderSample04](./accessdbprovidersample04.md)このサンプルでは、、、、およびの各コマンドレットの呼び出しをサポートするために、コンテナーメソッドを上書きする方法を示し `Copy-Item` `Get-ChildItem` `New-Item` `Remove-Item` ます。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダークラスは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生しています。

[AccessDBProviderSample05](./accessdbprovidersample05.md)このサンプルでは、およびコマンドレットの呼び出しをサポートするためにコンテナーメソッドを上書きする方法を示し `Move-Item` `Join-Path` ます。 これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。 このサンプルのプロバイダークラス[は、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生しています。

[AccessDBProviderSample06](./accessdbprovidersample06.md)このサンプル `Clear-Content` では、、 `Get-Content` 、およびコマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示し `Set-Content` ます。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダークラスは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを実装しています。この[クラスは、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生していますが、

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを記述する](./writing-a-windows-powershell-provider.md)
