---
title: AccessDBProviderSample06 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46dc0657-110f-4367-8bb6-a95dca2c5016
caps.latest.revision: 8
ms.openlocfilehash: f020f023f9a379ff8a610edb7d5dcfe207170394
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080987"
---
# <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

このサンプルは、呼び出しをサポートするコンテンツのメソッドを上書きする方法を示します、 `Clear-Content`、 `Get-Content`、および`Set-Content`コマンドレット。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダー クラスから派生、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス、およびその実装、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダー クラスは、ほとんどの場合、次のクラスのいずれかから派生され、可能性があるその他のプロバイダーのインターフェイスが実装されます。
>
> -   [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。 参照してください[AccessDBProviderSample03](./accessdbprovidersample03.md)します。
> -   [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラス。 参照してください[AccessDBProviderSample04](./accessdbprovidersample04.md)します。
> -   [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラス。
>
> プロバイダーの機能に基づくから派生するを参照しているプロバイダー クラスの選択の詳細については[Your Windows PowerShell プロバイダーの設計](./provider-types.md)します。

このサンプルでは、次の項目を示しています。

- 宣言、`CmdletProvider`属性。

- 派生するプロバイダー クラスを定義する、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)とクラスを宣言、 [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイス。

- 上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Clearcontent*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドの動作を変更する、`Clear-Content`コマンドレットは、ユーザーが項目の内容を削除できるようにします。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Clear-Content`コマンドレットです)。

- 上書き、 [System.Management.Automation.Provider.Icontentcmdletprovider.Getcontentreader*](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドの動作を変更する、`Get-Content`コマンドレットは、ユーザーが項目のコンテンツを取得できるようにします。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Get-Content`コマンドレットです。)。

- 上書き、 [Microsoft.PowerShell.Commands.Filesystemprovider.Getcontentwriter*](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter)メソッドの動作を変更する、`Set-Content`コマンドレットは、ユーザーが項目のコンテンツを更新できるようにします。 (このサンプルで動的パラメーターを追加する方法が表示されない、`Set-Content`コマンドレットです)。

## <a name="example"></a>例

このサンプルでは、clear、取得、および Microsoft Access データの基本項目の内容を設定するためのメソッドを上書きする方法を示します。

[!code-csharp[AccessDBProviderSample06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L2399 "AccessDBProviderSample06.cs")]

## <a name="see-also"></a>参照

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーのデザイン](./provider-types.md)