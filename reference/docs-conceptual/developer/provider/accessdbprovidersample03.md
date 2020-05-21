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
ms.openlocfilehash: 87b6b82225354e77e908b4af2bad1039a29b2980
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83691981"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

このサンプルでは、 [System.Management.Automation.Provider.Itemcmdletprovider.Getitem*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)およびコマンドレットの呼び出しをサポートするために、 [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きする方法について説明します。この例では、をオーバーライドしています。 `Get-Item` `Set-Item` このサンプルのプロバイダークラスは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスから派生しています。

## <a name="demonstrates"></a>対象

> [!IMPORTANT]
> プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。
>
> - ...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。
> - [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。 「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。
> - ...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。
>
> プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。

このサンプルでは、次の方法を示します。

- 属性を宣言 `CmdletProvider` しています。
- System.servicemodel[プロバイダークラスから派生した](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)プロバイダークラスを定義しています。
- [Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを上書きしてコマンドレットの動作を変更し `New-PSDrive` 、ユーザーが新しいドライブを作成できるようにします。
  (このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `New-PSDrive` )。
- 既存のドライブの削除をサポートするように[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きします。
- このコマンドレットの動作を変更して、ユーザーがデータストアから項目を取得できるようにするには、このメソッドを上書き[します](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)。 `Get-Item` (このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Get-Item` )。
- [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きして、コマンドレットの動作を変更し `Set-Item` 、ユーザーがデータストア内の項目を更新できるようにしています。 (このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Get-Item` )。
- コマンドレットの動作を変更するには、system.servicemodel. [Itemexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドを上書きします。 `Test-Path` (このサンプルでは、コマンドレットに動的パラメーターを追加する方法については説明しません `Test-Path` )。
- 指定されたパスが有効かどうかを判断するために、system.string. [Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドを上書きしています。

## <a name="example"></a>例

このサンプルでは、Microsoft Access データベースの項目を取得および設定するために必要なメソッドを上書きする方法を示します。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-976":::

## <a name="see-also"></a>参照

[システムの................](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[Containercmdletprovider (システム管理)](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[システムの管理...。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーを設計する](./provider-types.md)
