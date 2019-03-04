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
ms.openlocfilehash: fd013384a4b588bcdb397d7771425fe5c031c48f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856698"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

このサンプルの呼び出しをサポートするためにコンテナー メソッドを上書きする方法を示しています、 `Copy-Item`、 `Get-ChildItem`、 `New-Item`、および`Remove-Item`コマンドレット。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> ほとんどの場合、プロバイダー クラスの継承元、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

このサンプルでは、次の項目を示しています。

- 宣言、`CmdletProvider`属性。

- 派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。

- 上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Copyitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)メソッドの動作を変更する、`Copy-Item`コマンドレットに渡してアイテムを別の 1 つの場所にコピーするユーザーを許可します。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Copy-Item`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Getchilditems*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)ユーザーが、親アイテムの子項目を取得する Get ChildItems コマンドレットの動作を変更する方法. (このサンプルは、Get ChildItems コマンドレットに動的パラメーターを追加する方法を表示はされません)。

- 上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Getchildnames*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)メソッド Get ChildItems コマンドレットの動作を変更するときに、`Name`コマンドレットのパラメーターを指定します。

- 上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Newitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)メソッドの動作を変更する、`New-Item`コマンドレットは、ユーザーがデータ ストアに項目を追加します。 (このサンプルで動的パラメーターを追加する方法が表示されない、`New-Item`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Containercmdletprovider.Removeitem*](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)メソッドの動作を変更する、`Remove-Item`コマンドレット。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Remove-Item`コマンドレットです)。

## <a name="example"></a>例

このサンプルでは、コピー、作成、および子の親項目の項目を取得するためのメソッドと同様に、項目を削除するためのメソッドを上書きする方法を示します。

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a>参照

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーのデザイン](./provider-types.md)