---
title: Windows PowerShell ナビゲーション プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- navigation providers [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], navigation provider
ms.assetid: 8bd3224d-ca6f-4640-9464-cb4d9f4e13b1
caps.latest.revision: 5
ms.openlocfilehash: 40454f880b57d5b3a8a8ded21c8c97aebba027fe
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055072"
---
# <a name="creating-a-windows-powershell-navigation-provider"></a>Windows PowerShell ナビゲーション プロバイダーを作成する

このトピックでは、データ ストアを移動できる Windows PowerShell ナビゲーション プロバイダーを作成する方法について説明します。 この種類のプロバイダーには、再帰的なコマンド、入れ子になったコンテナー、および相対パスがサポートしています。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider05.cs)。 ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、[Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)を参照してください。

ここで説明されているプロバイダーでは、ドライブとして Access データベースのユーザーのハンドルが有効に、ユーザーがデータベース内のデータ テーブルに移動できるようにします。 独自のナビゲーション プロバイダーを作成するときに、ナビゲーションのために必要なドライブ修飾パス、相対パスの正規化、データ ストアと子の名前を取得し、アイテムの親パスを取得し、テストするメソッドのアイテムを移動するメソッドを実装できます。アイテムを識別するために、コンテナーです。

> [!CAUTION]
> 注意この設計が、名前の ID を持つフィールドを持つデータベースを想定していると、フィールドの型がなければなりません。

次の一覧には、このトピックのセクションが含まれています。 Windows PowerShell ナビゲーション プロバイダーの記述に慣れていない場合は、出現する順序では、この情報を読み込みます。 ただし、Windows PowerShell ナビゲーション プロバイダーの作成に習熟する場合は、直接」に進んでください必要な情報。

- [PS ナビゲーション プロバイダー クラスを定義します。](#Define-the-Windows-PowerShell-provider)

- [基本機能を定義します。](#Defining-Base-Functionality)

- [PS パスを作成します。](#Creating-a-Windows-PowerShell-Path)

- [親パスを取得します。](#Retrieving-the-Parent-Path)

- [子のパス名を取得します。](#Retrieve-the-Child-Path-Name)

- [項目がコンテナーであるを決定します。](#Determining-if-an-Item-is-a-Container)

- [アイテムを移動します。](#Moving-an-Item)

- [動的パラメーターをアタッチ、`Move-Item`コマンドレット](#Attaching-Dynamic-Parameters-to-the-Move-Item-Cmdlet)

- [相対パスの正規化](#Normalizing-a-Relative-Path)

- [コード サンプル](#Code-Sample)

- [オブジェクトの種類を定義して、書式設定](#Defining-Object-Types-and-Formatting)

- [Windows PowerShell プロバイダーのビルド](#Building-the-Windows-PowerShell-provider)

- [Windows PowerShell プロバイダーのテスト](#Testing-the-Windows-PowerShell-provider)

## <a name="define-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーを定義します。

Windows PowerShell ナビゲーション プロバイダーから派生する .NET クラスを作成する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基本クラス。 このセクションで説明されているナビゲーション プロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L31-L32 "AccessDBProviderSample05.cs")]

なお、このプロバイダーで、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、2 つのパラメーターが含まれています。 最初のパラメーターには、Windows PowerShell で使用されるプロバイダーのわかりやすい名前を指定します。 2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell の特定機能を指定します。 このプロバイダーに追加される Windows PowerShell の特定の機能はありません。

## <a name="defining-base-functionality"></a>基本機能を定義します。

」の説明に従って[デザイン、PS プロバイダー](./designing-your-windows-powershell-provider.md)、 [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)基底クラスが別のプロバイダーが提供されるその他のいくつかのクラスから派生機能。 Windows PowerShell ナビゲーション プロバイダーでは、そのため、する必要があります定義のすべてのクラスが提供する機能。

セッション固有の初期化情報を追加して、プロバイダーによって使用されているリソースを解放するための機能を実装するを参照してください。[基本的な PS プロバイダーを作成する](./creating-a-basic-windows-powershell-provider.md)します。 ただし、ほとんどのプロバイダー (ここで説明されているプロバイダーを含む) は、Windows PowerShell によって提供されるこの機能の既定の実装を使用できます。

を使用、Windows PowerShell ドライブをデータ ストアへのアクセスを取得するには、のメソッドを実装する必要があります、 [System.Management.Automation.Provider.Drivecmdletprovider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、[Windows PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)を参照してください。

プロバイダーの取得、設定、および消去の項目などのデータ ストアの項目を操作するによって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、[Windows PowerShell 項目プロバイダーを作成する](./creating-a-windows-powershell-item-provider.md)を参照してください。

子項目、または、データ ストアとして作成、コピー、名前の変更、およびアイテムを削除するメソッドの名前を取得するには、によって提供されるメソッドを実装する必要があります、 [System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)基本クラス。 これらのメソッドの実装の詳細については、[Windows PowerShell コンテナー プロバイダーを作成する](./creating-a-windows-powershell-container-provider.md)を参照してください。

## <a name="creating-a-windows-powershell-path"></a>Windows PowerShell パスの作成

Windows PowerShell ナビゲーション プロバイダーでは、プロバイダーの内部の Windows PowerShell パスを使用して、データ ストアの項目を移動します。 プロバイダーの内部パス プロバイダーを作成する必要があります実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)結合パス コマンドレットからをサポートするメソッドを呼び出します。 このメソッドは、親と子パス間のプロバイダー固有のパス区切り記号を使用して、プロバイダーの内部パスに、親と子パスを結合します。

既定の実装はでパスを受け取り「/」または"\\「へのパスの区切り文字を正規化パスの区切り文字として」\\"を含む文字列を返します、親と子パス部分を組み合わせて、それらの間の区切り記号、結合されたパス。

このナビゲーション プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、の既定の実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッド。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermakepath](Msh_samplestestcmdlets#testprovidermakepath)]  -->

#### <a name="things-to-remember-about-implementing-makepath"></a>MakePath の実装に関する注意点

実装に、次の条件が適用[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath):

- 実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)メソッドは、プロバイダーの名前空間で有効な完全修飾パスとしてパスを検証する必要があります。 各パラメーターは、パスの一部を表すことができますのみと、結合の部分では、完全修飾パスが生成されないことに注意します。 たとえば、 [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)で"windows \system32"が表示される可能性があります、filesystem プロバイダーのメソッド、`parent`パラメーターは、「月」で、 `child`パラメーター。 メソッドは、これらの値を結合、"\\"区切り記号および返します"windows\system32\abc.dll"、完全修飾ファイル システム パスではないです。

  > [!IMPORTANT]
  > 呼び出しで指定されたパスの一部[System.Management.Automation.Provider.Navigationcmdletprovider.Makepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)プロバイダーの名前空間で使用できない文字が含まれます。 これらの文字がワイルドカードの展開の使用はほとんどの場合と、このメソッドの実装は削除されません。

## <a name="retrieving-the-parent-path"></a>親パスを取得します。

Windows PowerShell ナビゲーション プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)の指定された親パーツ全体または一部を取得するメソッドプロバイダー固有のパス。 メソッドでは、パスの子の一部を削除し、親のパス部分を返します。 `root`パラメーターが、ドライブのルートへの完全修飾パスを指定します。 このパラメーターは、null または、マウントされたドライブは取得操作で使用されていない場合は、空にすることができます。 ルートが指定されている場合、メソッドは、ルートと同じツリー内のコンテナーにパスを返す必要があります。

サンプル ナビゲーション プロバイダーは、このメソッドをオーバーライドしませんが、既定の実装を使用します。 両方を使用してパスを受け入れる「/」と"\\"パスの区切り記号として。 のみがへのパスを最初に正規化"\\"区切り記号、オフ、最後に、親のパスを分割"\\"親パスを返します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetparentpath](Msh_samplestestcmdlets#testprovidergetparentpath)]  -->

#### <a name="to-remember-about-implementing-getparentpath"></a>GetParentPath の実装に関する注意

実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)メソッドは、プロバイダーの名前空間のパスの区切り記号の構文上のパスを分割する必要があります。 Filesystem プロバイダーがこのメソッドを使用して、最後の検索などの"\\"を区切り記号の左側にすべてのものを返します。

## <a name="retrieve-the-child-path-name"></a>子のパス名を取得します。

ナビゲーション プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)アイテムの子の名前 (リーフ要素) を取得するメソッドがある、指定された完全なまたは部分的なプロバイダー固有のパス。

サンプル ナビゲーション プロバイダーは、このメソッドをオーバーライドしません。 既定の実装は、以下に示します。 両方を使用してパスを受け入れる「/」と"\\"パスの区切り記号として。 のみがへのパスを最初に正規化"\\"区切り記号、オフ、最後に、親のパスを分割"\\"し、パスの一部の子の名前を返します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidergetchildname](Msh_samplestestcmdlets#testprovidergetchildname)]  -->

#### <a name="things-to-remember-about-implementing-getchildname"></a>GetChildName の実装に関する注意点

実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)メソッドは、パスの区切り文字の構文上のパスを分割する必要があります。 指定されたパスにパスの区切り記号が含まれていない場合、メソッドが変更されていないパスを返す必要があります。

> [!IMPORTANT]
> このメソッドの呼び出しで指定されたパスは、プロバイダーの名前空間では無効な文字があります。 これらの文字はワイルドカードの展開または正規表現の照合に使用される可能性が最も高いと、このメソッドの実装は削除されません。

## <a name="determining-if-an-item-is-a-container"></a>項目がコンテナーであるを決定します。

ナビゲーション プロバイダーを実装できる、 [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)メソッドを指定されたパスが、コンテナーを示すかどうかを判断します。 パスには、それ以外の場合するコンテナー、および false が表している場合は true を返します。 ユーザーが、このメソッドを使用する必要があります、`Test-Path`コマンドレットに指定されたパス。

次のコードは、 [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)サンプル ナビゲーション プロバイダーで実装します。 指定されたパスが正しいことと、テーブルが存在し、パスには、コンテナーが示されている場合は true を返すかどうか、メソッドを確認します。

[!code-csharp[AccessDBProviderSample05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs#L847-L872 "AccessDBProviderSample05.cs")]

#### <a name="things-to-remember-about-implementing-isitemcontainer"></a>IsItemContainer の実装に関する注意点

.NET クラスは、ナビゲーション プロバイダーはから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言する可能性があります、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 この場合は、実装の[System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)渡されたパスが要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 [System.Management.Automation.Provider.Cmdletprovider.Exclude*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Exclude)プロパティ。

## <a name="moving-an-item"></a>アイテムを移動します。

サポート、`Move-Item`コマンドレット、ナビゲーションは、プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッド。 このメソッドで指定された項目の移動、`path`パラメーターで指定されたパスにあるコンテナーを`destination`パラメーター。

サンプル ナビゲーション プロバイダーをオーバーライドしない、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッド。 既定の実装を次に示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitem](Msh_samplestestcmdlets#testprovidermoveitem)]  -->

#### <a name="things-to-remember-about-implementing-moveitem"></a>MoveItem の実装に関する注意点

.NET クラスは、ナビゲーション プロバイダーはから ExpandWildcards、フィルター、インクルード、または除外するには、プロバイダーの機能を宣言する可能性があります、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 この場合は、実装の[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)渡されたパスが要件を満たしていることを確認する必要があります。 これを行うには、メソッドがプロパティにアクセス適切なたとえば、 **CmdletProvider.Exclude**プロパティ。

既定では、このメソッドのオーバーライドする必要がありますオブジェクトを移動できません既存のオブジェクトに対する場合を除き、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 たとえば、filesystem プロバイダーはコピーしません c:\temp\abc.txt c:\bar.txt の既存のファイルにしない限り、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティに設定されて`true`します。 パスが指定されている場合、`destination`パラメーターが存在し、コンテナー、 [System.Management.Automation.Provider.Cmdletprovider.Force*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Force)プロパティは必要ありません。 この場合、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)によって示される項目を移動する必要があります、`path`でコンテナーにパラメーターが示される、`destination`子としてパラメーター。

実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッドを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)データ ストアに変更を加える前に、戻り値を確認します。 このメソッドは、操作の実行の確認が変更されたシステム状態、たとえば、ファイルを削除するときに使用されます。 [System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)コマンドライン設定や ユーザー設定変数を考慮して、Windows PowerShell ランタイムで、ユーザーに変更するリソースの名前を送信します。何をユーザーに表示するかを決定します。

呼び出し後[System.Management.Automation.Provider.Cmdletprovider.ShouldProcess](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)返します`true`、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)メソッドを呼び出す必要があります、 [System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)メソッド。 このメソッドは、操作を続行するかどうかにフィードバックを許可するユーザーにメッセージを送信します。 ご利用のプロバイダーを呼び出す必要があります[System.Management.Automation.Provider.Cmdletprovider.ShouldContinue](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldContinue)危険性のあるシステムの変更、追加のチェックとして。

## <a name="attaching-dynamic-parameters-to-the-move-item-cmdlet"></a>Move-item コマンドレットに動的パラメーターを追加

場合によって、`Move-Item`コマンドレットが実行時に動的に提供される追加のパラメーターが必要です。 これらの動的パラメーターを提供するナビゲーション プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)必要なパラメーター値を取得するメソッド返された場合、指定されたパスにある項目を持つプロパティとフィールドを解析してオブジェクト属性コマンドレット クラスのように、または[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。

このナビゲーション プロバイダーは、このメソッドを実装していません。 ただし、次のコードは、既定の実装の[System.Management.Automation.Provider.Navigationcmdletprovider.Moveitemdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters](Msh_samplestestcmdlets#testprovidermoveitemdynamicparameters)]  -->

## <a name="normalizing-a-relative-path"></a>相対パスの正規化

ナビゲーション プロバイダーの実装、 [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)に完全修飾パスを正規化する方法が示されている、`path`パラメーター指定されたパスを基準として、`basePath`パラメーター。 メソッドは、正規化されたパスの文字列表現を返します。 書き込むエラーである場合、`path`パラメーターが存在しないパスを指定します。

サンプル ナビゲーション プロバイダーは、このメソッドをオーバーライドしません。 既定の実装を次に示します。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplestestcmdlets#testprovidernormalizepath](Msh_samplestestcmdlets#testprovidernormalizepath)]  -->

#### <a name="things-to-remember-about-implementing-normalizerelativepath"></a>NormalizeRelativePath の実装に関する注意点

実装[System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)解析する必要があります、`path`パラメーターが、これは純粋な構文の解析を使用する必要はありません。 パスを使用して、データ ストアのパス情報を検索し、パスを作成するには、このメソッドには、大文字と小文字が一致するデザインすることが推奨され、パスの構文を標準化します。

## <a name="code-sample"></a>コード サンプル

完全なサンプル コードでは、[AccessDbProviderSample05 コード サンプル](./accessdbprovidersample05-code-sample.md)を参照してください。

## <a name="defining-object-types-and-formatting"></a>オブジェクトの種類を定義して、書式設定

プロバイダーに既存のオブジェクトにメンバーを追加したり、新しいオブジェクトを定義することができます。 詳細については、[を拡張するオブジェクトの種類と書式](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)を参照してください。

## <a name="building-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーの構築

詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)を参照してください。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録しているときに、派生で利用できるコマンドレットなど、コマンドラインでサポートされているコマンドレットを実行してテストできます。 この例では、サンプルのナビゲーション プロバイダーをテストします。

1. 新しいシェルを実行し、使用、`Set-Location`を Access データベースを示すためにパスを設定するコマンドレットです。

   ```powershell
   Set-Location mydb:
   ```

2. 今すぐ実行、`Get-Childitem`コマンドレットを使用可能なデータベース テーブルにはデータベースのアイテムの一覧を取得します。 テーブルごとに、このコマンドレットは、テーブル行の数を取得します。

   ```powershell
   Get-ChildItem | Format-Table rowcount,name -AutoSize
   ```

   ```output
   RowCount   Name
   --------   ----
        180   MSysAccessObjects
          0   MSysACEs
          1   MSysCmdbars
          0   MSysIMEXColumns
          0   MSysIMEXSpecs
          0   MSysObjects
          0   MSysQueries
          7   MSysRelationships
          8   Categories
         91   Customers
          9   Employees
       2155   Order Details
        830   Orders
         77   Products
          3   Shippers
         29   Suppliers
   ```

3. 使用して、`Set-Location`コマンドレットを再度従業員データのテーブルの場所を設定します。

   ```powershell
   Set-Location Employees
   ```

4. ここで使用して、 `Get-Location` Employees テーブルへのパスを取得するコマンドレットです。

   ```powershell
   Get-Location
   ```

   ```output
   Path
   ----
   mydb:\Employees
   ```

5. 使用して、`Get-Childitem`コマンドレットにパイプする、`Format-Table`コマンドレット。 この一連のコマンドレットでは、テーブルの行には、従業員のデータ テーブルの項目を取得します。 書式設定される指定に従って、`Format-Table`コマンドレット。

   ```powershell
   Get-ChildItem | Format-Table rownumber,psiscontainer,data -AutoSize
   ```

   ```output
   RowNumber   PSIsContainer   Data
   ---------   --------------   ----
   0           False            System.Data.DataRow
   1           False            System.Data.DataRow
   2           False            System.Data.DataRow
   3           False            System.Data.DataRow
   4           False            System.Data.DataRow
   5           False            System.Data.DataRow
   6           False            System.Data.DataRow
   7           False            System.Data.DataRow
   8           False            System.Data.DataRow
   ```

6. 今すぐ実行することができます、`Get-Item`従業員データのテーブルの行 0 の項目を取得するコマンドレットです。

   ```powershell
   Get-Item 0
   ```

   ```output
   PSPath        : AccessDB::C:\PS\Northwind.mdb\Employees\0
   PSParentPath  : AccessDB::C:\PS\Northwind.mdb\Employees
   PSChildName   : 0
   PSDrive       : mydb
   PSProvider    : System.Management.Automation.ProviderInfo
   PSIsContainer : False
   Data           : System.Data.DataRow
   RowNumber      : 0
   ```

7. 使用して、`Get-Item`コマンドレットを再度従業員のデータ行 0 内の項目を取得します。

   ```powershell
   (Get-Item 0).data
   ```

   ```output
   EmployeeID      : 1
   LastName        : Davis
   FirstName       : Sara
   Title           : Sales Representative
   TitleOfCourtesy : Ms.
   BirthDate       : 12/8/1968 12:00:00 AM
   HireDate        : 5/1/1992 12:00:00 AM
   Address         : 4567 Main Street
                     Apt. 2A
   City            : Buffalo
   Region          : NY
   PostalCode      : 98052
   Country         : USA
   HomePhone       : (206) 555-9857
   Extension       : 5467
   Photo           : EmpID1.bmp
   Notes           : Education includes a BA in psychology from
                     Colorado State University. She also completed "The
                     Art of the Cold Call."  Nancy is a member of
                     Toastmasters International.
   ReportsTo       : 2
   ```

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[デザイン、Windows PowerShell プロバイダー](./designing-your-windows-powershell-provider.md)

[オブジェクトの種類を拡張して、書式設定](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[コンテナーの Windows PowerShell プロバイダーを実装します。](./creating-a-windows-powershell-container-provider.md)

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)