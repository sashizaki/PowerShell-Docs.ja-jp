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
ms.openlocfilehash: aa67bb605f90c1ea40323b4583766069ff1226fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359991"
---
# <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

このサンプルで[は、](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) Setitem * メソッドと `Set-Item` コマンドレット `Get-Item` の呼び出しをサポートするように、 [*](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きする方法を示します。この例では、これらのメソッドをオーバーライドします。 このサンプルのプロバイダークラスは、system.servicemodel[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスから派生しています。

## <a name="demonstrates"></a>使用例

> [!IMPORTANT]
> プロバイダークラスは、ほとんどの場合、次のいずれかのクラスから派生し、他のプロバイダーインターフェイスを実装する可能性があります。
>
> -   ...........[プロバイダー](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラス。
> -   [Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスを提供します。 「 [AccessDBProviderSample04](./accessdbprovidersample04.md)」を参照してください。
> -   ...... [.。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 「 [AccessDBProviderSample05](./accessdbprovidersample05.md)」を参照してください。
>
> プロバイダーの機能に基づいて派生するプロバイダークラスを選択する方法の詳細については、「 [Windows PowerShell プロバイダーの設計](./provider-types.md)」を参照してください。

このサンプルは、次の操作方法を示します。

- `CmdletProvider` 属性を宣言しています。

- System.servicemodel[プロバイダークラスから派生した](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)プロバイダークラスを定義しています。

- [Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを上書きして `New-PSDrive` コマンドレットの動作を変更し、ユーザーが新しいドライブを作成できるようにします。 (このサンプルでは、`New-PSDrive` コマンドレットに動的パラメーターを追加する方法については説明しません)。

- 既存のドライブの削除をサポートするように[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを上書きします。

- `Get-Item` コマンドレットの動作を変更して、ユーザーがデータストアから項目を取得できるようにする[には、このメソッドを](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)上書きします。 (このサンプルでは、`Get-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。

- [Setitem *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)メソッドを上書きして、`Set-Item` コマンドレットの動作を変更し、ユーザーがデータストア内の項目を更新できるようにしています。 (このサンプルでは、`Get-Item` コマンドレットに動的パラメーターを追加する方法については説明しません)。

- `Test-Path` コマンドレットの動作を変更するには、........................ [Itemexists *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)メソッドを上書きします。 (このサンプルでは、`Test-Path` コマンドレットに動的パラメーターを追加する方法については説明しません)。

- 指定されたパスが有効かどうかを判断するために、system.string. [Isvalidpath *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)メソッドを上書きしています。

## <a name="example"></a>例

このサンプルでは、Microsoft Access データベースの項目を取得および設定するために必要なメソッドを上書きする方法を示します。

[!code-csharp[AccessDBProviderSample03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L976 "AccessDBProviderSample03.cs")]

## <a name="see-also"></a>参照

[システムの................](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[Containercmdletprovider (システム管理)](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[システムの管理...。](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[Windows PowerShell プロバイダーの設計](./provider-types.md)
