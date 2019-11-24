---
title: AccessDBProviderSample04 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: 7096f8066568c214a5902f6943a2c093932d3b56
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366341"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

このサンプルでは、コンテナーメソッドを上書きして、`Copy-Item`、`Get-ChildItem`、`New-Item`、および `Remove-Item` コマンドレットの呼び出しをサポートする方法を示します。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダークラスは、 [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生しています。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダークラスは、ほとんどの場合、[システム](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)から派生することがあります。

このサンプルでは、次のことを示します。

- `CmdletProvider` 属性を宣言しています。

- [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスから派生したプロバイダークラスを定義しています。

- [ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドを上書きして、ユーザーが1つの場所から別の場所に項目をコピーできるようにする `Copy-Item` コマンドレットの動作を変更します。 (このサンプルでは、`Copy-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。

- [Getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)メソッドを上書きして、ChildItems コマンドレットの動作を変更します。これにより、ユーザーは親項目の子項目を取得できるようになります。 (このサンプルでは、ChildItems コマンドレットに動的パラメーターを追加する方法については説明しません)。

- コマンドレットの `Name` パラメーターが指定されている場合に、ChildItems コマンドレットの動作を変更するには、 [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッドを上書きします。

- [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドを上書きして、ユーザーがデータストアに項目を追加できるようにする `New-Item` コマンドレットの動作を変更します ()。 (このサンプルでは、`New-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。

- [Containercmdletprovider *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドを上書きして、`Remove-Item` コマンドレットの動作を変更しています。 (このサンプルでは、`Remove-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。

## <a name="example"></a>例

このサンプルでは、項目をコピー、作成、および削除するために必要なメソッドと、親項目の子項目を取得するメソッドを上書きする方法を示します。

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a>関連項目

[システムの................](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[Containercmdletprovider (システム管理)](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[システムの管理...。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーの設計](./provider-types.md)
