---
title: Windows PowerShell プロバイダーのデザイン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide], designing
ms.assetid: 11d20319-cc40-4227-b810-4af33372b182
caps.latest.revision: 10
ms.openlocfilehash: 711a85e9b2eade7b9095d7560f53610e709e380a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081820"
---
# <a name="designing-your-windows-powershell-provider"></a>Windows PowerShell プロバイダーを設計する

製品または構成データベースに移動するか、参照、ユーザーがするなどの格納されたデータのセットを公開している場合は、Windows PowerShell プロバイダーを実装する必要があります。 さらに、お使いの製品は、複数レベルのコンテナーではない場合でも、コンテナーを提供する場合理にかなって Windows PowerShell プロバイダーを実装します。 たとえば、コマンドレット動詞のコピー、移動、名前変更、新しい、または削除は、製品、または構成データの操作として意味を行う場合は、Windows PowerShell コンテナー プロバイダーを実装する可能性があります。

## <a name="windows-powershell-paths-identify-your-provider"></a>Windows PowerShell パスは、プロバイダーを識別します。

Windows PowerShell ランタイムでは、Windows PowerShell パスを使用して、適切な Windows PowerShell プロバイダーにアクセスします。 コマンドレットでは、これらのパスのいずれかを指定します、ランタイムは、関連付けられているデータ ストアへのアクセスに使用するプロバイダーを認識します。 これらのパスには、ドライブ修飾パス、プロバイダーで修飾されたパス、プロバイダーの直接パス、およびプロバイダーの内部パスが含まれます。 それぞれの Windows PowerShell プロバイダーは、これらのパスの 1 つ以上をサポートする必要があります。

Windows PowerShell パスの詳細については、Windows PowerShell のしくみを参照してください。

### <a name="defining-a-drive-qualified-path"></a>ドライブ修飾パスを定義します。

物理ドライブにあるデータにアクセスするユーザーを許可するには、Windows PowerShell プロバイダーは、ドライブ修飾パスをサポートする必要があります。 このパスの後にコロン (:)、たとえば、mydrive:\abc\bar ドライブ名で始まります。

### <a name="defining-a-provider-qualified-path"></a>プロバイダーで修飾されたパスの定義

Windows PowerShell ランタイムを初期化して、プロバイダーの初期化を解除できるように、Windows PowerShell プロバイダーはプロバイダーで修飾されたパスをサポートする必要があります。 たとえば、FileSystem::\\\uncshare\abc\bar は Windows PowerShell によって提供された、filesystem プロバイダーのプロバイダーで修飾されたパス。

### <a name="defining-a-provider-direct-path"></a>プロバイダーの直接パスを定義します。

Windows PowerShell プロバイダーへのリモート アクセスを許可するのには、現在の場所、Windows PowerShell プロバイダーに直接渡すプロバイダー直接パスをサポートしてする必要があります。 たとえば、レジストリの Windows PowerShell プロバイダーを使用できます\\\server\regkeypath プロバイダー ダイレクト パスとして。

### <a name="defining-a-provider-internal-path"></a>プロバイダーの内部パスの定義

プロバイダー コマンドレットを Windows PowerShell 以外のアプリケーション プログラミング インターフェイス (Api) を使用してデータにアクセスできるように、Windows PowerShell プロバイダーは、プロバイダーの内部パスをサポートする必要があります。 後にこのパスが示される、"::"プロバイダーで修飾されたパスにします。 たとえば、ファイル システムの Windows PowerShell プロバイダーのプロバイダーの内部パスは\\\uncshare\abc\bar します。

## <a name="changing-stored-data"></a>格納されたデータを変更します。

基になるデータ ストアを変更するメソッドをオーバーライドするときに常に呼び出し、 [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)メソッド、項目の最新バージョンを変更します。メソッド。 項目オブジェクトをなど、ユーザーが、PassThru パラメーターを指定した場合、パイプラインに渡される必要があるかどうか、プロバイダーのインフラストラクチャを決定します。 (パフォーマンス) コストのかかる操作である最新の項目を取得する場合は、実際に結果の項目を記述する必要があるかどうかを Context.PassThru プロパティをテストできます。

## <a name="choose-a-base-class-for-your-provider"></a>プロバイダーの基本クラスを選択します。

Windows PowerShell では、多数の独自の Windows PowerShell プロバイダーを実装するために使用できる基本クラスを提供します。 プロバイダーを設計するとき、要件に最も適していますが、このセクションで説明されている、基本クラスを選択します。

各 Windows PowerShell プロバイダーの基底クラスで一連のコマンドレットを使用できます。 このセクションには、コマンドレットがについて説明しますが、そのパラメーターのについては説明しません。

セッション状態を使用して、Windows PowerShell ランタイムの場所のいくつかのコマンドレットを使用できるように、特定の Windows PowerShell プロバイダーなど、 `Get-Location`、 `Set-Location`、 `Pop-Location`、および`Push-Location`コマンドレット。 使用することができます、`Get-Help`コマンドレットをこれらの場所のコマンドレットに関する情報を取得します。

### <a name="cmdletprovider-base-class"></a>CmdletProvider 基本クラス

[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスは、基本的な Windows PowerShell プロバイダーを定義します。 このクラスは、プロバイダーの宣言をサポートし、さまざまなプロパティとすべての Windows PowerShell プロバイダーを使用できるメソッドを提供します。 クラスは、によって呼び出される、`Get-PSProvider`コマンドレットをセッションのすべての利用可能なプロバイダーを一覧表示します。 セッション状態でこのコマンドレットの実装が提供されています。

> [!NOTE]
> Windows PowerShell プロバイダーは、Windows PowerShell 言語のすべてのスコープで利用できます。

### <a name="drivecmdletprovider-base-class"></a>DriveCmdletProvider 基本クラス

[System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)クラスは、新しいドライブを追加、既存のドライブを削除および既定のドライブを初期化するための操作をサポートする Windows PowerShell ドライブ プロバイダーを定義します。 たとえば、Windows PowerShell によって提供される、FileSystem プロバイダーでは、ハード ドライブと CD/DVD デバイス ドライブなど、マウントされているすべてのボリュームのドライブを初期化します。

このクラスから派生、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基本クラス。 次の表は、このクラスによって公開されているコマンドレットを一覧表示します。 で示されているだけでなく、`Get-PSDrive`コマンドレット (セッション状態によって公開される) が利用可能なドライブを取得するために使用される関連するコマンドレット。

|コマンドレット|定義|
|------------|----------------|
|`New-PSDrive`|セッションの新しいドライブを作成し、ドライブの情報をストリーミングします。|
|`Remove-PSDrive`|セッションからドライブを削除します。|

### <a name="itemcmdletprovider-base-class"></a>ItemCmdletProvider 基本クラス

[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)クラスは、データ ストアの個々 のアイテムに対して操作を実行する Windows PowerShell 項目プロバイダーを定義し、任意のコンテナーを想定していないか、ナビゲーション機能します。 このクラスから派生、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。 次の表は、このクラスによって公開されているコマンドレットを一覧表示します。

|コマンドレット|定義|
|------------|----------------|
|`Clear-Item`|指定した位置に項目の現在のコンテンツをクリアし、"clear"に、プロバイダーによって指定された値に置き換えられます。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Get-Item`|指定された場所から項目を取得し、結果のオブジェクトをストリームします。|
|`Invoke-Item`|指定されたパスにある項目の既定のアクションを呼び出します。|
|`Set-Item`|値を持つ指定した位置に項目を設定します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Resolve-Path`|Windows PowerShell のパス、およびストリーム パス情報のワイルドカードを解決します。|
|`Test-Path`|指定されたパスをテストし、返します`true`が存在する場合と`false`それ以外の場合。 このコマンドレットがサポートするために実装されている、`IsContainer`のパラメーター、 [System.Management.Automation.Provider.Cmdletprovider.Writeitemobject*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteItemObject)メソッド。|

### <a name="containercmdletprovider-base-class"></a>ContainerCmdletProvider 基本クラス

[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)クラスは、ユーザーに、データ ストアの項目のコンテナーを公開する Windows PowerShell コンテナー プロバイダーを定義します。 Windows PowerShell コンテナー プロバイダーがその中の項目を含む 1 つのコンテナー (入れ子になったコンテナーがありません) がある場合にのみ使用できることに注意します。 入れ子になったコンテナーがある場合は、Windows PowerShell ナビゲーション プロバイダーを実装する必要があります。

このクラスから派生、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基本クラス。 次の表では、このクラスによって実装されるコマンドレットを定義します。

|コマンドレット|定義|
|------------|----------------|
|`Copy-Item`|別の 1 つの場所から項目をコピーします。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Get-Childitem`|指定した位置に子項目を取得し、オブジェクトとしてストリーム送信します。|
|`New-Item`|指定した位置に新しい項目を作成し、結果のオブジェクトをストリームします。|
|`Remove-Item`|指定された場所から項目を削除します。|
|`Rename-Item`|指定した位置にある項目の名前を変更します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|

### <a name="navigationcmdletprovider-base-class"></a>NavigationCmdletProvider 基本クラス

[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)クラスは、1 つ以上のコンテナーを使用するアイテムの操作を実行する Windows PowerShell ナビゲーション プロバイダーを定義します。 このクラスから派生、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基本クラス。 次の表は、このクラスによって公開されているコマンドレットを一覧表示します。

|コマンドレット|定義|
|------------|----------------|
|結合パス|パスの間でプロバイダーに固有の区切り記号を使用して、1 つのパスには、2 つのパスを結合します。 このコマンドレットは、文字列をストリームします。|
|`Move-Item`|指定した場所に項目を移動します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|

関連するコマンドレットは、Windows PowerShell によって提供される基本的な解析パス コマンドレットです。 このコマンドレットをサポートするために Windows PowerShell パスの解析に使用できます、`Parent`パラメーター。 親パスの文字列をストリーミングします。

## <a name="select-provider-interfaces-to-support"></a>サポートするプロバイダーのインターフェイスを選択します。

Windows PowerShell の基本クラスのいずれかから派生するだけでなく、Windows PowerShell プロバイダーは、1 つ以上の次のプロバイダー インターフェイスから派生することによって他の機能をサポートできます。 このセクションでは、それらのインターフェイスと各によってサポートされているコマンドレットを定義します。 インターフェイスでサポートされているコマンドレットのパラメーターについては説明しません。 コマンドレットのパラメーター情報を使用してオンラインがある、`Get-Command`と`Get-Help`コマンドレット。

### <a name="icontentcmdletprovider"></a>IContentCmdletProvider

[System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)インターフェイスは、データ項目のコンテンツの操作を実行するコンテンツ プロバイダーを定義します。 次の表には、このインターフェイスによって公開されるコマンドレットが一覧表示します。

|コマンドレット|定義|
|------------|----------------|
|`Add-Content`|指定した項目の内容を指定された値の長さを追加します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Clear-Content`|指定した項目のコンテンツを"clear"の値に設定します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Get-Content`|指定した項目の内容を取得し、結果のオブジェクトをストリームします。|
|`Set-Content`|指定した項目の既存のコンテンツを置き換えます。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|

### <a name="ipropertycmdletprovider"></a>IPropertyCmdletProvider

[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)インターフェイスは、データ ストアで項目のプロパティに対する操作を実行する Windows PowerShell プロバイダーをプロパティを定義します。 次の表には、このインターフェイスによって公開されるコマンドレットが一覧表示します。

> [!NOTE]
> `Path`これらのコマンドレットのパラメーターをプロパティを識別するのではなく項目へのパスを示します。

|コマンドレット|定義|
|------------|----------------|
|`Clear-ItemProperty`|指定した項目のプロパティを"clear"の値に設定します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Get-ItemProperty`|指定した項目からプロパティを取得し、結果のオブジェクトをストリームします。|
|`Set-ItemProperty`|値を持つ指定した項目のプロパティを設定します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|

### <a name="idynamicpropertycmdletprovider"></a>IDynamicPropertyCmdletProvider

[System.Management.Automation.Provider.Idynamicpropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider)から派生したインターフェイス[System.Management.Automation.Provider.Ipropertycmdletprovider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)を定義します。サポートされているそのコマンドレットの動的パラメーターを指定するプロバイダー。 この種類のプロバイダーは、対象のプロパティを定義して、新しいプロパティ操作など、実行時に操作を処理します。 このような操作項目のプロパティを静的に定義することはできません。 次の表には、このインターフェイスによって公開されるコマンドレットが一覧表示します。

|コマンドレット|定義|
|------------|----------------|
|`Copy-ItemProperty`|別のアイテムに指定された項目からプロパティをコピーします。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`Move-ItemProperty`|指定された項目からプロパティを別のアイテムに移動します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|
|`New-ItemProperty`|指定されたアイテムにプロパティを作成し、結果のオブジェクトをストリーム転送します。|
|`Remove-ItemProperty`|指定した項目のプロパティを削除します。|
|`Rename-ItemProperty`|指定した項目のプロパティの名前を変更します。 しない限り、このコマンドレットが、パイプラインを介して出力オブジェクトを渡していないその`PassThru`パラメーターを指定します。|

### <a name="isecuritydescriptorcmdletprovider"></a>ISecurityDescriptorCmdletProvider

[System.Management.Automation.Provider.Isecuritydescriptorcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ISecurityDescriptorCmdletProvider)インターフェイスをプロバイダーにセキュリティ記述子の機能を追加します。 このインターフェイスは、データ ストア内のアイテムのセキュリティ記述子の情報の設定を取得できます。 次の表には、このインターフェイスによって公開されるコマンドレットが一覧表示します。

|コマンドレット|定義|
|------------|----------------|
|`Get-Acl`|たとえば、オペレーティング システムのリソースを保護するためにセキュリティ記述子、ファイルまたはオブジェクトの一部であるアクセス制御リスト (ACL) に含まれる情報を取得します。|
|`Set-Acl`|ACL の情報を設定します。 インスタンスの形式では[System.Security.Accesscontrol.Objectsecurity](/dotnet/api/System.Security.AccessControl.ObjectSecurity)で指定されたパスの指定された項目。 このコマンドレットは、Windows PowerShell プロバイダーは、セキュリティ情報の設定をサポートしている場合、レジストリ、またはその他のプロバイダー項目の場合は、ファイル、キー、およびサブキーに関する情報を設定できます。|

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell の動作](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Windows PowerShell SDK](../windows-powershell-reference.md)