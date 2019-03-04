---
title: ロール ベースの承認の構成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2933a6ca-fe92-4ba2-97ee-ef0f0d5fdfcf
caps.latest.revision: 8
ms.openlocfilehash: b73284adb4bf228510bf8134aa4c6a10561b7ea2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859598"
---
# <a name="configuring-role-based-authorization"></a>ロール ベースの認可を構成する

このトピックでは、ロール ベースの承認ポリシーの実装サンプルを構成する方法を示します、 [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization)で説明されているインターフェイス[を実装するカスタムManagement OData IIS 拡張機能の承認](./implementing-custom-authorization-for-a-management-odata-web-service.md)します。

この例では、承認ポリシーを定義する管理 OData のサンプル アプリケーションによって使用される XML ファイルを構成します。 2 つのロールが作成され、それらのロールとワークフローが含まれる別の Windows PowerShell モジュールを関連付けます。 XML ファイルを定義するスキーマに記載されている[承認構成スキーマの役割に基づいた](./role-based-authorization-configuration-schema.md)します。

## <a name="modifying-the-rbacconfigurationxml-file"></a>RBacConfiguration.xml ファイルを変更します。

このファイルは、アプリケーションの承認ポリシーを定義します。 使用してロールが定義されている`Group`ノード。 A`Group`ノードには、そのグループに割り当てられたユーザーが実行できる Windows PowerShell コマンドが定義されています。 使用してユーザーがグループに割り当てられている`User`ノード。

これらの例では、管理者にモジュールを追加`Group`ノード、各グループにユーザーを追加します。

#### <a name="adding-a-module-to-a-group-node"></a>モジュール、グループ ノードを追加します。

1. という名前のファイルを作成する**RBacConfiguration.xml**テキスト エディターでします。 このファイルは、web サービスのアプリケーションのメイン ディレクトリに保存する必要があります。 ファイルに次のテキストを挿入します。

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <RbacConfiguration>
     <Groups>
       <!--Group consists of the following:
         Name:  Name of the group
         UserName (Optional): Windows Identity user name
         Password (Optional): Password of the Windows user name
         DomainName (Optional): Domain for the user. For local machine account either do not include them or give the machine name. Do not give empty string
         MapIncomingUser (Optional): Boolean value indicating whether to execute cmdlet in the context of network client.

         User credentials and MapIncomingUser=true are exclusive.
       -->
       <Group Name="NonAdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Set-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
       </Group>
       <Group Name="AdminGroup" MapIncomingUser="true">
         <Cmdlets>
           <Cmdlet>Get-Service</Cmdlet>
           <Cmdlet>Get-Process</Cmdlet>
           <Cmdlet>Get-Item</Cmdlet>
           <Cmdlet>New-Item</Cmdlet>
           <Cmdlet>Get-Command</Cmdlet>
           <Cmdlet>ConvertTo-Xml</Cmdlet>
           <Cmdlet>ConvertTo-Json</Cmdlet>
           <Cmdlet>ConvertFrom-Json</Cmdlet>
         </Cmdlets>
         <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
       </Group>
     </Groups>
     <Users>
       <!-- User consists of the following :
         Name: Name of the user. If a user is from a cer
         AuthenticationType: Authentication type used.
         DomainName (Optional): Domain for the user
       -->
       <User Name="localNonAdmin" AuthenticationType="Basic" GroupName="NonAdminGroup" />
       <User Name="localAdmin" AuthenticationType="Basic" GroupName="AdminGroup" />
     </Users>
   </RbacConfiguration>
   ```

2. ファイルには 2 つ`Group`ノード。 この例で使用される 2 つのロールを表すこれら、 `NonAdminGroup` 、`AdminGroup`ロール。

   終了後に直接`Cmdlets`最初のタグ`Group`ノードで、次の XML を追加します。

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a>ユーザー、グループ ノードを追加します。

1. 開く、 **RBacConfiguration.xml**テキスト エディターでファイル。 このファイルは、c: フォルダーにある\\\inetpub\wwwroot\Modata インストールする前に、エンドポイント名を変更しなかった場合。

2. 終了タグの直後後、`Users`ノード、次の XML を追加します。

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. 直接 XML は、前の手順で追加後、は、次の XML を追加します。

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```