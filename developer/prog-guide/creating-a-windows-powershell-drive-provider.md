---
title: Windows PowerShell ドライブ プロバイダーの作成 |Microsoft Docs
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
ms.openlocfilehash: 174d3a6860790295e1b73f32d9c1bad46b653917
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055651"
---
# <a name="creating-a-windows-powershell-drive-provider"></a>Windows PowerShell ドライブ プロバイダーを作成する

このトピックでは、Windows PowerShell ドライブをデータ ストアにアクセスする手段を提供する Windows PowerShell ドライブ プロバイダーを作成する方法について説明します。 この種類のプロバイダーは、"Windows PowerShell ドライブ プロバイダー"とも呼ばれます。 プロバイダーによって使用される Windows PowerShell ドライブでは、データ ストアに接続するための手段を提供します。

ここで説明されている Windows PowerShell ドライブ プロバイダーでは、Microsoft Access データベースへのアクセスを提供します。 このプロバイダーでは、Windows PowerShell ドライブを表します (ドライブ プロバイダーにドライブの任意の数を追加することは)、データベース ドライブの最上位のコンテナーは、データベース内のテーブルを表し、コンテナーの項目が内の行を表しますテーブル。

このトピックのセクションの一覧を示します。 Windows PowerShell ドライブ プロバイダーの記述に慣れていない場合に、出現する順序でこれらのセクションが読み取られます。 ただし、ドライブ プロバイダーの作成に習熟する場合は、直接」に進んでください必要な情報。

- [Windows PowerShell プロバイダー クラスを定義します。](#Defining-the-Windows-PowerShell-Provider-Class)

- [基本機能を定義します。](#Defining-Base-Functionality)

- [ドライブの状態情報の作成](#Creating-Drive-State-Information)

- [ドライブの作成](#Creating-a-Drive)

- [NewDrive に動的パラメーターを追加](#Attaching-Dynamic-Parameters-to-NewDrive)

- [ドライブを削除します。](#Removing-a-Drive)

- [ドライブの既定の初期化](#Initializing-Default-Drives)

- [コード サンプル](#Code-Sample)

- [Windows PowerShell ドライブ プロバイダーのテスト](#Testing-the-Windows-PowerShell-Drive-Provider)

## <a name="defining-the-windows-powershell-provider-class"></a>Windows PowerShell プロバイダー クラスを定義します。

ドライブは、プロバイダーから派生する .NET クラスを定義する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。 このドライブ プロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L29-L30 "AccessDBProviderSample02.cs")]

この例では、注意、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性は、プロバイダーと Windows PowerShell の特定の機能のわかりやすい名前を指定するプロバイダーコマンドの処理中に、Windows PowerShell ランタイムに公開されます。 によって、プロバイダーの機能の有効な値が定義されている、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 このドライブ プロバイダーは、これらの機能のいずれかのことをサポートしません。

## <a name="defining-base-functionality"></a>基本機能を定義します。

」の説明に従って[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスから派生、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基本クラスを初期化し、プロバイダーの初期化解除に必要なメソッドを定義します。 セッション固有の初期化情報を追加して、プロバイダーによって使用されているリソースを解放するための機能を実装するを参照してください。[基本的な Windows PowerShell プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。 ただし、ほとんどのプロバイダー (ここで説明されているプロバイダーを含む) は、この Windows PowerShell によって提供される機能の既定の実装を使用できます。

## <a name="creating-drive-state-information"></a>ドライブの状態情報の作成

すべての Windows PowerShell プロバイダーは、ドライブは、プロバイダーが、プロバイダーを呼び出すときに、Windows PowerShell ランタイムで必要なすべての状態情報を作成する必要があることを意味する、ステートレスで考慮されます。

このドライブ プロバイダーの状態情報には、ドライブ情報の一部として保持されているデータベースへの接続が含まれています。 この情報を格納する方法を示すコードをここでは、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)ドライブを表すオブジェクト。

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L130-L151 "AccessDBProviderSample02.cs")]

## <a name="creating-a-drive"></a>ドライブの作成

ドライブを作成するには、Windows PowerShell ランタイムを許可するドライブのプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)メソッド。 次のコードの実装を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)このドライブ プロバイダーのメソッド。

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L42-L84 "AccessDBProviderSample02.cs")]

このメソッドのオーバーライドは、次の操作を行います。

- いることを確認、 [System.Management.Automation.PSDriveinfo.Root*](/dotnet/api/System.Management.Automation.PSDriveInfo.Root)メンバーが存在して、データ ストアへの接続を作成できます。

- ドライブを作成しのサポートに、接続メンバーを設定、`New-PSDrive`コマンドレット。

- 検証、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)提案されたドライブのオブジェクト。

- 変更、 [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo)任意の必要なパフォーマンスと信頼性については、ドライブを記述するオブジェクトまたはドライブを使用して呼び出し元の余分なデータを提供します。

- 使用してエラーを処理、 [System.Management.Automation.Provider.Cmdletprovider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError)メソッドと戻り値`null`します。

  このメソッドは、そのプロバイダーに固有のバージョンのメソッドに渡されたいずれかのドライブ情報を返します。

## <a name="attaching-dynamic-parameters-to-newdrive"></a>NewDrive に動的パラメーターを追加

`New-PSDrive`ドライブは、プロバイダーでサポートされているコマンドレットは、追加のパラメーターを必要があります。 これらの動的パラメーターをコマンドレットに添付するプロバイダーを実装、 [System.Management.Automation.Provider.Drivecmdletprovider.Newdrivedynamicparameters*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)メソッド。 このメソッドは、プロパティと、コマンドレット クラスのように属性を解析してフィールドを持つオブジェクトを返しますまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。

このドライブ プロバイダーは、このメソッドをオーバーライドしません。 ただし、次のコードは、このメソッドの既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters](Msh_samplestestcmdlets#testprovidernewdrivedynamicparameters)]  -->

## <a name="removing-a-drive"></a>ドライブを削除します。

データベース接続を閉じるには、ドライブのプロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)メソッド。 このメソッドは、任意のプロバイダーに固有の情報をクリーンアップした後は、ドライブへの接続を閉じます。

次のコードの実装を示しています、 [System.Management.Automation.Provider.Drivecmdletprovider.Removedrive*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)このドライブ プロバイダーのメソッド。

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L91-L116 "AccessDBProviderSample02.cs")]

メソッドをメソッドに渡される情報を返す必要があります、ドライブが削除できる場合、`drive`パラメーター。 メソッドが例外を記述する必要があります、戻りますドライブを削除できない場合は`null`します。 プロバイダーがこのメソッドをオーバーライドしない場合、このメソッドの既定の実装はだけ入力として渡さドライブ情報を返します。

## <a name="initializing-default-drives"></a>ドライブの既定の初期化

ドライブ プロバイダーの実装して、 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)ドライブをマウントするメソッド。 たとえば、Active Directory プロバイダーは、名前付けコンテキストをコンピューターがドメインに参加している場合、既定のドライブをマウントする可能性があります。

このメソッドは、初期化済みのドライブのドライブについてのコレクションまたは空のコレクションを返します。 Windows PowerShell ランタイムの呼び出し後にこのメソッドの呼び出しが行われた、 [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)プロバイダーを初期化します。

このドライブ プロバイダーをオーバーライドしない、 [System.Management.Automation.Provider.Drivecmdletprovider.Initializedefaultdrives*](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)メソッド。 ただし、次のコードは、空のドライブのコレクションを返します既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testproviderinitializedefaultdrives](Msh_samplestestcmdlets#testproviderinitializedefaultdrives)]  -->

#### <a name="things-to-remember-about-implementing-initializedefaultdrives"></a>InitializeDefaultDrives の実装に関する注意点

すべてのドライブ プロバイダーは、見つけやすさと、ユーザーを支援するルート ドライブをマウントする必要があります。 ルート ドライブでは、その他のマウントされたドライブのルートとして機能する場所を一覧表示可能性があります。 たとえば、Active Directory プロバイダーを作成、ドライブにある名前付けコンテキストを一覧表示する、`namingContext`ルート分散システム環境 (DSE) の属性。 これにより、ユーザーが他のドライブのマウント ポイントを検出できます。

## <a name="code-sample"></a>コード サンプル

完全なサンプル コードでは、次を参照してください。 [AccessDbProviderSample02 コード サンプル](./accessdbprovidersample02-code-sample.md)します。

## <a name="testing-the-windows-powershell-drive-provider"></a>Windows PowerShell ドライブ プロバイダーのテスト

Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録しているときに、派生で利用できる任意のコマンドレットなど、コマンドラインでサポートされているコマンドレットを実行してテストできます。 サンプルのドライブのプロバイダーをテストしてみましょう。

1. 実行、 `Get-PSProvider` AccessDB ドライブ プロバイダーが存在することを確認するプロバイダーの一覧を取得するコマンドレット。

   **PS> `Get-PSProvider`**

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

2. アクセスして、データベースのデータベース サーバー名 (DSN) が存在することを**データソース**の部分、**管理ツール**オペレーティング システム。 **ユーザー DSN**テーブルをダブルクリックします**MS Access データベース**C:\ps\northwind.mdb ドライブ パスを追加します。

3. サンプルのドライブのプロバイダーを使用して新しいドライブを作成します。

   **PS> new-psdrive -name mydb -root c:\ps\northwind.mdb -psprovider AccessDb**

   次の出力が表示されます。

   ```output
   Name     Provider     Root                   CurrentLocation
   ----     --------     ----                   ---------------
   mydb     AccessDB     c:\ps\northwind.mdb
   ```

4. 接続を検証します。 接続は、ドライブのメンバーとして定義されている、ために、Get PDDrive コマンドレットを使用してチェックできます。

   > [!NOTE]
   > プロバイダーは、その操作のコンテナーの機能をニーズに応じて、ユーザーはドライブとしてプロバイダーとやり取りまだことはできません。 詳細については、次を参照してください。 [Windows PowerShell コンテナー プロバイダーを作成する](./creating-a-windows-powershell-container-provider.md)します。

   **PS > (である get-psdrive mydb) .connection**

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

5. ドライブを削除し、シェルを終了します。

   **PS > - remove-psdrive mydb**

   **PS > 終了**

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーを設計します。](./designing-your-windows-powershell-provider.md)

[基本的な Windows PowerShell プロバイダーを作成します。](./creating-a-basic-windows-powershell-provider.md)