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
ms.openlocfilehash: 2fe5c82bc4516574c48fe7effb8bcc60ea6d0bbf
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977473"
---
# <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

このサンプルでは、`Clear-Content`、`Get-Content`、および `Set-Content` コマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示します。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダークラスは、 [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを実装しています。この[クラスは、system.servicemodel クラスの](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスから派生していますが、

## <a name="demonstrates"></a>例

> [!IMPORTANT]
> プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。
>
> -   ...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。 「 [AccessDBProviderSample03](./accessdbprovidersample03.md)」を参照してください。
> -   [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。 「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。
> -   ...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)
>
> プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。

このサンプルは、次の操作方法を示します。

- `CmdletProvider` 属性を宣言しています。
- [Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスを宣言する、system.servicemodel クラスから派生したプロバイダークラスを定義します。[このクラスは](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)、このクラスから派生します。
- [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)メソッドを上書きして、`Clear-Content` コマンドレットの動作を変更し、ユーザーが項目からコンテンツを削除できるようにしています。 (このサンプルでは、`Clear-Content` コマンドレットに動的パラメーターを追加する方法については説明しません)。
- [Icontentcmdletprovider *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)メソッドを上書きして、`Get-Content` コマンドレットの動作を変更し、ユーザーが項目の内容を取得できるようにしています。 (このサンプルでは、`Get-Content` コマンドレットに動的パラメーターを追加する方法については説明しません)。
- `Set-Content` コマンドレットの動作を変更して、ユーザーが項目の内容を更新できるようにするには、[このメソッドを上書きします](/dotnet/api/Microsoft.PowerShell.Commands.FileSystemProvider.GetContentWriter)。 (このサンプルでは、`Set-Content` コマンドレットに動的パラメーターを追加する方法については説明しません)。

## <a name="example"></a>例

このサンプルでは、Microsoft Access データベースの項目の内容をクリア、取得、および設定するために必要なメソッドを上書きする方法を示します。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a>参照

[システムの................](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[Containercmdletprovider (システム管理)](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[システムの管理...。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーの設計](./provider-types.md)
