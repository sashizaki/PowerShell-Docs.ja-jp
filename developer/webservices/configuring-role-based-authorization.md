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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080681"
---
# <a name="configuring-role-based-authorization"></a><span data-ttu-id="03aff-102">ロール ベースの認可を構成する</span><span class="sxs-lookup"><span data-stu-id="03aff-102">Configuring Role-based Authorization</span></span>

<span data-ttu-id="03aff-103">このトピックでは、ロール ベースの承認ポリシーの実装サンプルを構成する方法を示します、 [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization)で説明されているインターフェイス[を実装するカスタムManagement OData IIS 拡張機能の承認](./implementing-custom-authorization-for-a-management-odata-web-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="03aff-103">This topic demonstrates how to configure the role-based authorization policy for the sample implementation of the [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) interface described in [Implementing Custom Authorization for Management OData IIS Extension](./implementing-custom-authorization-for-a-management-odata-web-service.md).</span></span>

<span data-ttu-id="03aff-104">この例では、承認ポリシーを定義する管理 OData のサンプル アプリケーションによって使用される XML ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="03aff-104">In this example, you will configure an XML file that is used by the sample Management OData application to define the authorization policy.</span></span> <span data-ttu-id="03aff-105">2 つのロールが作成され、それらのロールとワークフローが含まれる別の Windows PowerShell モジュールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="03aff-105">You will create two roles and associate different Windows PowerShell modules that contain workflows with those roles.</span></span> <span data-ttu-id="03aff-106">XML ファイルを定義するスキーマに記載されている[承認構成スキーマの役割に基づいた](./role-based-authorization-configuration-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="03aff-106">The schema that defines the XML file is listed at [Role-Based Authorization Configuration Schema](./role-based-authorization-configuration-schema.md).</span></span>

## <a name="modifying-the-rbacconfigurationxml-file"></a><span data-ttu-id="03aff-107">RBacConfiguration.xml ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="03aff-107">Modifying the RBacConfiguration.xml File</span></span>

<span data-ttu-id="03aff-108">このファイルは、アプリケーションの承認ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="03aff-108">This file defines the authorization policy for the application.</span></span> <span data-ttu-id="03aff-109">使用してロールが定義されている`Group`ノード。</span><span class="sxs-lookup"><span data-stu-id="03aff-109">Roles are defined by using `Group` nodes.</span></span> <span data-ttu-id="03aff-110">A`Group`ノードには、そのグループに割り当てられたユーザーが実行できる Windows PowerShell コマンドが定義されています。</span><span class="sxs-lookup"><span data-stu-id="03aff-110">A `Group` node defines the Windows PowerShell commands that users assigned to that group can run.</span></span> <span data-ttu-id="03aff-111">使用してユーザーがグループに割り当てられている`User`ノード。</span><span class="sxs-lookup"><span data-stu-id="03aff-111">Users are assigned to groups by using `User` nodes.</span></span>

<span data-ttu-id="03aff-112">これらの例では、管理者にモジュールを追加`Group`ノード、各グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="03aff-112">In these examples, you will add a module to the Administrator `Group` node, and add a user to each group.</span></span>

#### <a name="adding-a-module-to-a-group-node"></a><span data-ttu-id="03aff-113">モジュール、グループ ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="03aff-113">Adding a Module to a Group Node</span></span>

1. <span data-ttu-id="03aff-114">という名前のファイルを作成する**RBacConfiguration.xml**テキスト エディターでします。</span><span class="sxs-lookup"><span data-stu-id="03aff-114">Create a file named **RBacConfiguration.xml** in a text editor.</span></span> <span data-ttu-id="03aff-115">このファイルは、web サービスのアプリケーションのメイン ディレクトリに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03aff-115">This file should be saved to the main application directory for your web service.</span></span> <span data-ttu-id="03aff-116">ファイルに次のテキストを挿入します。</span><span class="sxs-lookup"><span data-stu-id="03aff-116">Insert the following text in the file.</span></span>

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

2. <span data-ttu-id="03aff-117">ファイルには 2 つ`Group`ノード。</span><span class="sxs-lookup"><span data-stu-id="03aff-117">The file contains two `Group` nodes.</span></span> <span data-ttu-id="03aff-118">この例で使用される 2 つのロールを表すこれら、 `NonAdminGroup` 、`AdminGroup`ロール。</span><span class="sxs-lookup"><span data-stu-id="03aff-118">These represent the two roles used in this example, the `NonAdminGroup` and the `AdminGroup` roles.</span></span>

   <span data-ttu-id="03aff-119">終了後に直接`Cmdlets`最初のタグ`Group`ノードで、次の XML を追加します。</span><span class="sxs-lookup"><span data-stu-id="03aff-119">Directly after the closing `Cmdlets` tag in the first `Group` node, add the following XML:</span></span>

   ```xml
   <Modules>
           <Module>C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ServerManager\ServerManager.psd1</Module>
         </Modules>
   ```

#### <a name="adding-a-user-to-a-group-node"></a><span data-ttu-id="03aff-120">ユーザー、グループ ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="03aff-120">Adding a User to a Group Node</span></span>

1. <span data-ttu-id="03aff-121">開く、 **RBacConfiguration.xml**テキスト エディターでファイル。</span><span class="sxs-lookup"><span data-stu-id="03aff-121">Open the **RBacConfiguration.xml** file in a text editor.</span></span> <span data-ttu-id="03aff-122">このファイルは、c: フォルダーにある\\\inetpub\wwwroot\Modata インストールする前に、エンドポイント名を変更しなかった場合。</span><span class="sxs-lookup"><span data-stu-id="03aff-122">This file is located in the folder C:\\\inetpub\wwwroot\Modata  if you did not change the endpoint name before installation.</span></span>

2. <span data-ttu-id="03aff-123">終了タグの直後後、`Users`ノード、次の XML を追加します。</span><span class="sxs-lookup"><span data-stu-id="03aff-123">Directly after the closing tag in the `Users` node, add the following XML:</span></span>

   ```xml
   <User Name="UserName" GroupName="AdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```

3. <span data-ttu-id="03aff-124">直接 XML は、前の手順で追加後、は、次の XML を追加します。</span><span class="sxs-lookup"><span data-stu-id="03aff-124">Directly after the XML added in the previous step, add the following XML:</span></span>

   ```xml
   <User Name="UserName" GroupName="NonAdminGroup" AuthenticationType="Basic" DomainName="DomainName"/>
   ```