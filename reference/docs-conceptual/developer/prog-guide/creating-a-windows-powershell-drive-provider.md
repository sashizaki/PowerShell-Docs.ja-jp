---
title: Windows PowerShell ドライブプロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- drive providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], drive provider
- drives [PowerShell Programmer's Guide]
ms.assetid: 2b446841-6616-4720-9ff8-50801d7576ed
caps.latest.revision: 6
ms.openlocfilehash: 2e3d97e224b06bdf36ac0bc1237911e029ea762d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366831"
---
# <a name="creating-a-windows-powershell-drive-provider"></a>Windows PowerShell ドライブ プロバイダーを作成する

このトピックでは、windows PowerShell ドライブを介してデータストアにアクセスする方法を提供する Windows PowerShell ドライブプロバイダーを作成する方法について説明します。 この種類のプロバイダーは、Windows PowerShell ドライブプロバイダーとも呼ばれます。 プロバイダーによって使用される Windows PowerShell ドライブは、データストアに接続する手段を提供します。

ここに記載されている Windows PowerShell ドライブプロバイダーは、Microsoft Access データベースへのアクセスを提供します。 このプロバイダーの場合、Windows PowerShell ドライブはデータベースを表し (ドライブプロバイダーに任意の数のドライブを追加することができます)、ドライブの最上位のコンテナーはデータベースのテーブルを表し、コンテナーの項目は次の行を表します。テーブル。

## <a name="defining-the-windows-powershell-provider-class"></a>Windows PowerShell プロバイダークラスの定義

Drive プロバイダーは、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基底クラスから派生する .net クラスを定義する必要があります。 このドライブプロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

この例では、" [System.](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute) ......" 属性で、プロバイダーのわかりやすい名前と、プロバイダーが windows に公開する windows PowerShell 固有の機能を指定していることに注意してください。コマンド処理中の PowerShell ランタイム。 プロバイダー機能に使用できる値は、system.servicemodel[機能](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)の列挙型によって定義されます。 このドライブプロバイダーは、これらの機能のいずれもサポートしていません。

## <a name="defining-base-functionality"></a>基本機能の定義

「 [Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)」で説明されているように、 [Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスは、 [system](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) ..........プロバイダーの初期化と初期化解除に必要なメソッドを定義します。 セッション固有の初期化情報を追加し、プロバイダーによって使用されるリソースを解放するための機能を実装するには、「[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」を参照してください。 ただし、ほとんどのプロバイダー (ここで説明するプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。

## <a name="creating-drive-state-information"></a>ドライブの状態情報の作成

すべての Windows PowerShell プロバイダーはステートレスであると見なされます。つまり、ドライブプロバイダーは、プロバイダーを呼び出すときに、Windows PowerShell ランタイムが必要とする状態情報を作成する必要があります。

このドライブプロバイダーの場合、状態情報には、ドライブ情報の一部として保持されているデータベースへの接続が含まれます。 次に示すコードは、この情報がドライブを説明する[system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)オブジェクトにどのように格納されるかを示しています。

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a>ドライブの作成

Windows PowerShell ランタイムがドライブを作成できるようにするには、ドライブプロバイダーが[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを実装する必要があります。 次のコードは、このドライブプロバイダーの[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッドを実装する方法を示しています。

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

このメソッドをオーバーライドするには、次の操作を行う必要があります。

- [System.management.automation.psdriveinfo *](/dotnet/api/System.Management.Automation.PSDriveInfo.Root)メンバーが存在し、データストアへの接続が可能であることを確認します。

- @No__t-0 コマンドレットをサポートするために、ドライブを作成し、接続メンバーを設定します。

- 提案されたドライブの[system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)オブジェクトを検証します。

- ドライブを説明する[system.management.automation.psdriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)オブジェクトを、必要なパフォーマンスまたは信頼性の情報で変更するか、ドライブを使用して呼び出し元に追加のデータを提供します。

- [WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドを使用してエラーを処理した後、`null` を返します。

  このメソッドは、メソッドに渡されたドライブ情報またはプロバイダー固有のバージョンのいずれかを返します。

## <a name="attaching-dynamic-parameters-to-newdrive"></a>動的パラメーターを NewDrive にアタッチしています

ドライブプロバイダーでサポートされている @no__t 0 のコマンドレットでは、追加のパラメーターが必要になる場合があります。 これらの動的パラメーターをコマンドレットにアタッチするために、プロバイダーは[Drivecmdletprovider. Newdrivedynamicparameters *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッドを実装します。 このメソッドは、コマンドレットクラスや[system.string オブジェクトと](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)同様に解析属性を持つプロパティとフィールドを持つオブジェクトを返します。

このドライブプロバイダーは、このメソッドをオーバーライドしません。 ただし、次のコードは、このメソッドの既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a>ドライブの取り外し

データベース接続を閉じるには、ドライブプロバイダーが[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを実装している必要があります。 このメソッドは、プロバイダー固有の情報をクリーンアップした後に、ドライブへの接続を閉じます。

次のコードは、このドライブプロバイダーの[Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッドを実装する方法を示しています。

[!code-csharp[AccessDBProviderSample02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

ドライブを削除できる場合、メソッドは `drive` パラメーターを使用してメソッドに渡された情報を返す必要があります。 ドライブを削除できない場合、メソッドは例外を書き込み、`null` を返します。 プロバイダーがこのメソッドをオーバーライドしない場合、このメソッドの既定の実装は、入力として渡されたドライブ情報だけを返します。

## <a name="initializing-default-drives"></a>既定のドライブの初期化

ドライブプロバイダーは、 [Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッドを実装して、ドライブをマウントしますが、 たとえば、コンピューターがドメインに参加している場合、Active Directory プロバイダーが既定の名前付けコンテキストのドライブをマウントすることがあります。

このメソッドは、初期化されたドライブまたは空のコレクションに関するドライブ情報のコレクションを返します。 このメソッドの呼び出しは、Windows PowerShell ランタイムによっ[て、プロバイダー](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)を初期化するために、を呼び出した後に実行されます。

このドライブプロバイダーでは、 [Drivecmdletprovider *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッドがオーバーライドされていません。 ただし、次のコードは、空のドライブコレクションを返す既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a>InitializeDefaultDrives の実装に関する注意事項

すべてのドライブプロバイダーは、ユーザーが見つけやすいように、ルートドライブをマウントする必要があります。 ルートドライブには、他のマウントされたドライブのルートとして機能する場所が一覧表示される場合があります。 たとえば、Active Directory プロバイダーは、ルート分散システム環境 (DSE) の `namingContext` 属性で見つかった名前付けコンテキストを一覧表示するドライブを作成する場合があります。 これは、ユーザーが他のドライブのマウントポイントを検出するのに役立ちます。

## <a name="code-sample"></a>コードサンプル

完全なサンプルコードについては、「 [AccessDbProviderSample02 のコードサンプル](./accessdbprovidersample02-code-sample.md)」を参照してください。

## <a name="testing-the-windows-powershell-drive-provider"></a>Windows PowerShell ドライブプロバイダーのテスト

Windows PowerShell プロバイダーが Windows PowerShell に登録されている場合は、コマンドラインでサポートされているコマンドレットを実行してテストできます。これには、派生によって使用可能なコマンドレットも含まれます。 サンプルドライブプロバイダーをテストしてみましょう。

1. @No__t-0 コマンドレットを実行してプロバイダーの一覧を取得し、AccessDB ドライブプロバイダーが存在することを確認します。

   **PS > `Get-PSProvider`**

   次の出力が表示されます。

   ```output
   Name                 Capabilities                  Drives
   ----                 ------------                  ------
   AccessDB             None                          {}
   Alias                ShouldProcess                 {Alias}
   Environment          ShouldProcess                 {Env}
   FileSystem           Filter, ShouldProcess         {C, Z}
   Function             ShouldProcess                 {function}
   Registry             ShouldProcess                 {HKLM, HKCU}
   ```

2. オペレーティングシステムの**管理ツール**の **[データソース]** 部分にアクセスして、データベースのデータベースサーバー名 (DSN) が存在することを確認します。 **[USER DSN]** テーブルで、 **[MS Access Database]** をダブルクリックし、ドライブパス C:\ps\northwind.mdb. を追加します。

3. サンプルドライブプロバイダーを使用して新しいドライブを作成します。

   **PS > psdrive-name mydb-root c:\ps\northwind.mdb-psprovider AccessDb**

   次の出力が表示されます。

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. 接続を検証します。 接続はドライブのメンバーとして定義されているため、Get PDDrive コマンドレットを使用して確認できます。

   > [!NOTE]
   > ユーザーは、その対話にコンテナー機能を必要とするため、プロバイダーをドライブとして操作することはできません。 詳細については、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」を参照してください。

   **PS > (psdrive mydb). 接続**

   次の出力が表示されます。

   ```output
   ConnectionString  : Driver={Microsoft Access Driver (*.mdb)};DBQ=c:\ps\northwind.mdb
   ConnectionTimeout : 15
   Database          : c:\ps\northwind
   DataSource        : ACCESS
   ServerVersion     : 04.00.0000
   Driver            : odbcjt32.dll
   State             : Open
   Site              :
   Container         :
   ```

5. ドライブを取り外し、シェルを終了します。

   **PS > psdrive mydb**

   **PS > 終了**

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの作成](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーを設計する](./designing-your-windows-powershell-provider.md)

[基本的な Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)
