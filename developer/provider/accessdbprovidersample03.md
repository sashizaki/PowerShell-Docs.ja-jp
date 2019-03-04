---
title: AccessDBProviderSample03 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e576199-49c7-4355-9686-f9ed40c64a5f
caps.latest.revision: 10
ms.openlocfilehash: 57b6cfaa5f29300c60a5a745797111b6beba3133
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859408"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

このサンプルを上書きする方法を示しています、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)と[System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッド呼び出しをサポートする、`Get-Item`と`Set-Item`コマンドレット。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。
>
> -   [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。
> -   [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。 参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。
> -   [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。 参照してください[AccessDBProviderSample05](./accessdbprovidersample05.md)します。
>
> プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。

このサンプルでは、次の項目を示しています。

- 宣言、`CmdletProvider`属性。

- 派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。

- 上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドの動作を変更する、`New-PSDrive`コマンドレットは、ユーザーが新しいドライブを作成できるようにします。 (このサンプルで動的パラメーターを追加する方法が表示されない、`New-PSDrive`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを既存のドライブの削除をサポートします。

- 上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)メソッドの動作を変更する、`Get-Item`コマンドレットは、ユーザーがデータ ストアから項目を取得できるようにします。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Get-Item`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Setitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドの動作を変更する、`Set-Item`コマンドレットは、ユーザーがデータ ストア内の項目を更新できるようにします。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Get-Item`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Itemexists*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドの動作を変更する、`Test-Path`コマンドレット。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Test-Path`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Itemcmdletprovider.Isvalidpath*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドを指定されたパスが有効であるかを判断します。

## <a name="example"></a>例

このサンプルでは、取得および Microsoft Access データの基本項目を設定するために必要なメソッドを上書きする方法を示します。

[!code-csharp[AccessDBProviderSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a>参照

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーのデザイン](./provider-types.md)