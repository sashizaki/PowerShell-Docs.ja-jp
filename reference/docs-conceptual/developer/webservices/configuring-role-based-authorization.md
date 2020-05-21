---
title: ロールベースの承認を構成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2933a6ca-fe92-4ba2-97ee-ef0f0d5fdfcf
caps.latest.revision: 8
ms.openlocfilehash: 2c9d6040b7a9c17dc5204c8eb835fd69780f62c5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564259"
---
# <a name="configuring-role-based-authorization"></a>ロール ベースの認可を構成する

このトピックでは、「 [Management ODATA IIS 拡張機能のカスタム承認を実装](./implementing-custom-authorization-for-a-management-odata-web-service.md)する」で説明されている[Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization)インターフェイスのサンプル実装に対して、ロールベースの承認ポリシーを構成する方法について説明します。

この例では、サンプル管理 OData アプリケーションで使用される XML ファイルを構成して、承認ポリシーを定義します。 2つのロールを作成し、ワークフローを含むさまざまな Windows PowerShell モジュールをそれらのロールに関連付けます。 XML ファイルを定義するスキーマは、「[ロールベースの承認構成スキーマ](./role-based-authorization-configuration-schema.md)」に記載されています。

## <a name="modifying-the-rbacconfigurationxml-file"></a>RBacConfiguration .xml ファイルの変更

このファイルは、アプリケーションの承認ポリシーを定義します。 ロールは、ノードを使用して定義され `Group` ます。 `Group`ノードは、そのグループに割り当てられたユーザーが実行できる Windows PowerShell コマンドを定義します。 ユーザーは、ノードを使用してグループに割り当てられ `User` ます。

これらの例では、[管理者] ノードにモジュールを追加 `Group` し、各グループにユーザーを追加します。

#### <a name="adding-a-module-to-a-group-node"></a>グループノードへのモジュールの追加

1. テキストエディターで、 **Rbacconfiguration**という名前のファイルを作成します。 このファイルは、web サービスのメインアプリケーションディレクトリに保存する必要があります。 ファイルに次のテキストを挿入します。

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

2. このファイルには2つのノードが含まれてい `Group` ます。 これらは、この例で使用される2つのロール、 `NonAdminGroup` およびロールを表し `AdminGroup` ます。

   最初のノードの終了タグのすぐ後 `Cmdlets` `Group` に、次の XML を追加します。

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a>グループノードへのユーザーの追加

1. テキストエディターで、 **Rbacconfiguration .xml**ファイルを開きます。 このファイルは、 \\ インストール前にエンドポイント名を変更しなかった場合は、C: \inetpub\wwwroot\Modata フォルダーにあります。

2. ノードの終了タグのすぐ後 `Users` に、次の XML を追加します。

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. 前の手順で追加した XML のすぐ後に、次の XML を追加します。

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```
