---
title: 開発のガイドラインに必要な |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41d2b308-a36a-496f-8542-666b6a21eedc
caps.latest.revision: 19
ms.openlocfilehash: 3f6bcd2e4ef4d9c404b3a5deeaa9f25d3fa42ec1
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056517"
---
# <a name="required-development-guidelines"></a>必要な開発ガイドライン

次のガイドラインは、コマンドレットを記述するときに従う必要があります。 コマンドレットとコマンドレット コードの記述に関するガイドラインを設計するためのガイドラインに区切られます。 次のガイドラインに従わない場合、コマンドレットは失敗する可能性し、コマンドレットを使用するときに、ユーザーがエクスペリエンスの低下を必要があります。

## <a name="in-this-topic"></a>このトピックの内容

### <a name="design-guidelines"></a>デザイン ガイドライン

- [承認された動詞 (RD01) のみを使用](./required-development-guidelines.md#use-only-approved-verbs-rd01)

- [コマンドレット名:使用できない文字 (RD02)](./required-development-guidelines.md#cmdlet-names-characters-that-cannot-be-used-rd02)

- [使用できないパラメーター名 (RD03)](./required-development-guidelines.md#parameters-names-that-cannot-be-used-rd03)

- [確認要求 (RD04) をサポートします。](./required-development-guidelines.md#support-confirmation-requests-rd04)

- [Force パラメーターを対話型セッション (RD05) のサポートします。](./required-development-guidelines.md#support-force-parameter-for-interactive-sessions-rd05)

- [ドキュメント出力オブジェクト (RD06)](./required-development-guidelines.md#document-output-objects-rd06)

### <a name="code-guidelines"></a>コードのガイドライン

- [コマンドレットまたは PSCmdlet クラス (RC01) から派生します。](./required-development-guidelines.md#derive-from-the-cmdlet-or-pscmdlet-classes-rc01)

- [コマンドレット属性 (RC02) を指定します。](./required-development-guidelines.md#specify-the-cmdlet-attribute-rc02)

- [処理方法 (RC03) の入力をオーバーライドします。](./required-development-guidelines.md#override-an-input-processing-method-rc03)

- [OutputType 属性 (RC04) を指定します。](./required-development-guidelines.md#specify-the-outputtype-attribute-rc04)

- [出力オブジェクト (RC05) へのハンドルを保持していません。](./required-development-guidelines.md#do-not-retain-handles-to-output-objects-rc05)

- [エラーを確実に処理 (RC06)](./required-development-guidelines.md#handle-errors-robustly-rc06)

- [Windows PowerShell モジュールを使用して、コマンドレット (RC07) をデプロイするには](./required-development-guidelines.md#use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07)

## <a name="design-guidelines"></a>デザイン ガイドライン

次のガイドラインは、コマンドレットとその他のコマンドレットを使用しての間で一貫性のあるユーザー エクスペリエンスを実現するためのコマンドレットを設計するときに従う必要があります。 自分の状況に適用されるデザインのガイドラインを検索するときに必ずのようなガイドラインについては、コードのガイドラインを確認してください。

### <a name="use-only-approved-verbs-rd01"></a>承認された動詞 (RD01) のみを使用

Windows PowerShell によって提供される動詞の認識されたセットからコマンドレット属性で指定された動詞があります。 禁止されている類義語の 1 つできません。 次のコマンドレットの動詞を指定する列挙型によって定義されている定数の文字列を使用します。

- [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)

- [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)

- [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)

- [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

- [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

- [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)

- [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)

承認された動詞名の詳細については、[コマンドレット動詞](./approved-verbs-for-windows-powershell-commands.md)を参照してください。

ユーザーには、検出し、必要なコマンドレット名のセットが必要があります。 ユーザーが迅速に評価のコマンドレットの処理と、システムの機能を簡単に検出できるように、適切な動詞を使用します。 名前が"start"で始まるシステムなど、次のコマンド ライン コマンドがすべてのコマンドの一覧を取得します。`get-command start-*`します。 他のコマンドレットから、コマンドレットを区別するために、コマンドレットの名詞を使用します。 名詞は、操作を実行するリソースを示します。 操作自体は、動詞によって表されます。

### <a name="cmdlet-names-characters-that-cannot-be-used-rd02"></a>コマンドレット名:使用できない文字 (RD02)

コマンドレットの名前、ときに使用しないでください、次の特殊文字のいずれか。

|文字|名前|
|---------------|----------|
|#|シャープ記号|
|、|コンマ|
|()|かっこ|
|{}|中かっこ|
|[]|角かっこ|
|&|アンパサンド|
|-|ハイフン**に注意してください。** 名詞、動詞を分離するハイフンを使用できますが、文字列、動詞または名詞内は使用できません。|
|/|スラッシュ マーク|
|\|円記号|
|$|ドル記号|
|^|キャレット|
|;|セミコロン|
|:|コロン|
|"|二重引用符|
|'|単一引用符|
|<>|山かっこ|
|&#124;|垂直バー|
|?|疑問符 (?)|
|@|アット マーク|
|' | バック ティック (アクサン グラーブ)|
|*|アスタリスク|
|%|パーセント記号|
|+|プラス記号|
|=|等号|
|~|チルダ|

### <a name="parameters-names-that-cannot-be-used-rd03"></a>使用できないパラメーター名 (RD03)

Windows PowerShell には、すべてのコマンドレットのパラメーターとは特定の状況で追加された追加のパラメーターの共通セットが提供されています。 独自のコマンドレットを設計するときに、次の名前を使用することはできません。確認、Debug、ErrorAction、ErrorVariable、OutVariable、OutBuffer、WarningAction、WarningVariable、WhatIf、UseTransaction と詳細な。 これらのパラメーターの詳細については、[パラメーターの共通名](./common-parameter-names.md)を参照してください。

### <a name="support-confirmation-requests-rd04"></a>確認要求 (RD04) をサポートします。

システムを変更する操作を実行するコマンドレットを呼び出す必要がある、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 、確認を要求し、特殊なケースで呼び出すメソッドを[System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッド。 (、 [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドは、後でのみ呼び出す必要があります、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドが呼び出されます)。

これらを呼び出すコマンドレットが設定して、確認要求をサポートしていることを指定する必要があります、`SupportsShouldProcess`コマンドレット属性のキーワード。 この属性を設定する方法についての詳細については、[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)を参照してください。

> [!NOTE]
> コマンドレット クラスのコマンドレットの属性は、コマンドレットの呼び出しをサポートしていることを示す場合、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)への呼び出しにメソッドをおよびコマンドレットが失敗した、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッドでは、ユーザーが予期せず、システムを変更する可能性があります。

使用して、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)システム変更のメソッド。 ユーザー設定と`WhatIf`パラメーター コントロール、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。 これに対し、 [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)呼び出しは、危険性のある変更の追加チェックを実行します。 このメソッドは、任意のユーザー設定によって制御されていない、または`WhatIf`パラメーター。 コマンドレットを呼び出す場合、 [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)が、メソッド、`Force`これら 2 つのメソッドへの呼び出しを省略して、操作を続行するパラメーター。 これは、機能は、非対話型のスクリプトとホストで使用するコマンドレットができるので重要です。

コマンドレットは、これらの呼び出しをサポート、ユーザーがかどうか、アクションを実行する必要があります実際に確認できます。 たとえば、 [Stop-process](/powershell/module/microsoft.powershell.management/stop-process)コマンドレットの呼び出し、 [System.Management.Automation.Cmdlet.ShouldContinue*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドの一連のシステムでは、Winlogon などの重要なプロセスを停止する前に、プロセス。

これらのメソッドのサポートに関する詳細については、[確認を要求する](./requesting-confirmation-from-cmdlets.md)を参照してください。

### <a name="support-force-parameter-for-interactive-sessions-rd05"></a>Force パラメーターを対話型セッション (RD05) のサポートします。

コマンドレットを対話的に使用する場合常に強制するパラメーターを指定のプロンプトや入力の行の読み取りなど、対話型のアクションを上書きする)。 これは、機能は、非対話型のスクリプトとホストで使用するコマンドレットができるので重要です。 次のメソッドは、対話型のホストによって実装できます。

- [System.Management.Automation.Host.PSHostUserInterface.Prompt*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.Prompt)

- [System.Management.Automation.Host.Pshostuserinterface.PromptForChoice](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForChoice)

- [System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection.PromptForChoice](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection.PromptForChoice)

- [System.Management.Automation.Host.Pshostuserinterface.PromptForCredential*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.PromptForCredential)

- [System.Management.Automation.Host.Pshostuserinterface.ReadLine*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLine)

- [System.Management.Automation.Host.Pshostuserinterface.ReadLineAsSecureString*](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.ReadLineAsSecureString)

### <a name="document-output-objects-rd06"></a>ドキュメント出力オブジェクト (RD06)

Windows PowerShell では、パイプラインに書き込まれるオブジェクトを使用します。 ユーザーの各コマンドレットによって返されるオブジェクトを利用するためには、返されるオブジェクトを文書化する必要があり、、返されるオブジェクトのメンバーの使用を文書化する必要があります。

## <a name="code-guidelines"></a>コードのガイドライン

コマンドレットのコードを記述する場合は、次のガイドラインを従う必要があります。 自分の状況に適用されるコードのガイドラインを検索するときに必ずのようなガイドラインについては、デザイン ガイドラインを確認してください。

### <a name="derive-from-the-cmdlet-or-pscmdlet-classes-rc01"></a>コマンドレットまたは PSCmdlet クラス (RC01) から派生します。

コマンドレットは、いずれかから派生する必要があります、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)または[System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)基本クラス。 派生したコマンドレット、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラスは、Windows PowerShell ランタイムに依存しません。 これらは、任意の Microsoft .NET Framework 言語から直接呼び出すことができます。 派生したコマンドレット、 [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)クラスは、Windows PowerShell ランタイムに依存します。 そのため、実行空間内で実行されます。

実装するすべてのコマンドレット クラスは、パブリック クラスである必要があります。 これらのコマンドレット クラスの詳細については、[コマンドレットの概要](./cmdlet-overview.md)を参照してください。

### <a name="specify-the-cmdlet-attribute-rc02"></a>コマンドレット属性 (RC02) を指定します。

Windows PowerShell で認識されるコマンドレットのコマンドレットの属性を持つ、.NET Framework クラスを装飾する必要があります。 この属性は、次のコマンドレットの機能を指定します。

- コマンドレットを識別する動詞-名詞形式のペア。

- 複数のパラメーター セットが指定されたときに使用される既定のパラメーター セット。 既定のパラメーター セットは、Windows PowerShell がどのパラメーターのセットを使用するかを判断するのに十分な情報を持っていない場合に使用されます。

- コマンドレットがへの呼び出しをサポートしているかを示す、 [System.Management.Automation.Cmdlet.ShouldProcess*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)メソッド。 このメソッドでは、コマンドレットは、システムに変更を加える前に、ユーザーに確認メッセージが表示されます。 確認要求が行われる方法の詳細については、[確認を要求する](./requesting-confirmation-from-cmdlets.md)を参照してください。

- 確認メッセージに関連付けられているアクションの影響のレベル (または重大度) を示します。 ほとんどの場合、メディアの既定値を使用する必要があります。 影響のレベルがユーザーに表示される確認要求に与える影響の詳細については、[確認を要求する](./requesting-confirmation-from-cmdlets.md)を参照してください。

コマンドレットの属性を宣言する方法の詳細については、[CmdletAttribute 宣言](./cmdlet-attribute-declaration.md)を参照してください。

### <a name="override-an-input-processing-method-rc03"></a>処理方法 (RC03) の入力をオーバーライドします。

Windows PowerShell 環境に参加するコマンドレットのオーバーライドする必要あります、次の少なくとも 1 つ*入力処理メソッド*します。

[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドは、1 回と前処理機能を提供するために使用されます。

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドは、複数回と、レコードの機能を提供するために使用されます。

[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッドは 1 つの時間と処理後の機能を提供するために使用されます。

### <a name="specify-the-outputtype-attribute-rc04"></a>OutputType 属性 (RC04) を指定します。

(Windows PowerShell 2.0 で導入) の OutputType 属性には、コマンドレットをパイプラインに返す .NET Framework 型を指定します。 コマンドレットの出力の種類を指定することでは、コマンドレットによって返される、やすく他のコマンドレットでオブジェクトをようにします。 この属性を使用して、コマンドレット クラスを修飾することの詳細については、[OutputType 属性宣言](./outputtype-attribute-declaration.md)を参照してください。

### <a name="do-not-retain-handles-to-output-objects-rc05"></a>出力オブジェクト (RC05) へのハンドルを保持していません。

コマンドレットに渡されるオブジェクトへのすべてのハンドルを保持する必要があります、 [System.Management.Automation.Cmdlet.WriteObject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッド。 これらのオブジェクトがパイプラインでは、次のコマンドレットに渡されるまたはスクリプトで使用されます。 オブジェクトへのハンドルを保持する場合、2 つのエンティティは、各オブジェクトは、エラーが発生を所有します。

### <a name="handle-errors-robustly-rc06"></a>エラーを確実に処理 (RC06)

管理環境は本質的に検出し、重要な変更を管理しているシステムになります。 そのため、コマンドレットがエラーを正しく処理することが重要です。 エラー レコードの詳細については、[Windows PowerShell のエラー報告](./error-reporting-concepts.md)を参照してください。

- エラーは、コマンドレットが、複数のレコードを処理する続行できない、ときに、終了エラーが発生します。 コマンドレットを呼び出す必要があります、 [System.Management.Automation.Cmdlet.ThrowTerminatingError*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)メソッドを参照する、 [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。 コマンドレットによって、例外がキャッチされない場合、Windows PowerShell ランタイム自体は以下の情報を含む終了エラーをスローします。

- コマンドレット (たとえば、a レコードの別のプロセスによって生成される)、パイプラインから読み込まれているレコードを呼び出す必要があります次の操作を停止しない未終了エラーを[System.Management.Automation.Cmdlet.WriteError*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを参照する、 [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクト。 終了しないエラーの例は、特定のプロセスが停止に失敗した場合に発生するエラーです。 呼び出す、 [System.Management.Automation.Cmdlet.WriteError*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドが一貫して要求されたアクションを実行して、失敗した特定のアクションの情報を保持するユーザーを使用します。 コマンドレットが処理されない各レコードできるだけ独立しています。

- [System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)によって参照されるオブジェクト、 [System.Management.Automation.Cmdlet.ThrowTerminatingError*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)と[System.Management.Automation.Cmdlet.WriteError*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドには、基本的に、例外が必要です。 使用して例外を判断する場合は、.NET Framework デザイン ガイドラインに従います。 エラーは、既存の例外と同じである意味場合、は、その例外を使用して、またはその例外から派生します。 それ以外の場合、新しい例外またはから直接例外階層を派生、 [System.Exception](/dotnet/api/System.Exception)型。

[System.Management.Automation.ErrorRecord](/dotnet/api/System.Management.Automation.ErrorRecord)オブジェクトでは、ユーザーのエラーをグループ化するエラー カテゴリも必要です。 値を設定して、カテゴリに基づいてエラーを表示できます、 `$ErrorView` CategoryView にシェル変数。 可能なカテゴリが定義されている、 [System.Management.Automation.ErrorCategory](/dotnet/api/System.Management.Automation.ErrorCategory)列挙体。

- コマンドレットは、新しいスレッドを作成し、そのスレッドで実行されているコードがハンドルされない例外をスローした場合、Windows PowerShell は、エラーはキャッチできないと、プロセスが終了します。

- オブジェクトには、未処理の例外が発生した、デストラクターでコードが含まれて、Windows PowerShell は、エラーはキャッチできないと、プロセスが終了します。 これは、オブジェクトが未処理の例外が発生する Dispose メソッドを呼び出す場合にも発生します。

### <a name="use-a-windows-powershell-module-to-deploy-your-cmdlets-rc07"></a>Windows PowerShell モジュールを使用して、コマンドレット (RC07) をデプロイするには

Windows PowerShell モジュールをパッケージ化し、コマンドレットのデプロイを作成します。 モジュールのサポートは、Windows PowerShell 2.0 で導入されました。 (これは非常に便利なコマンドレットをテストする場合)、バイナリ モジュール ファイルとして直接、コマンドレット クラスが含まれているアセンブリを使用することができますか、コマンドレットのアセンブリを参照するモジュール マニフェストを作成することができます。 (追加することできますも既存のスナップイン アセンブリ モジュールを使用する場合。)モジュールの詳細については、[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)を参照してください。

## <a name="see-also"></a>参照

[強くお勧めします開発のガイドライン](./strongly-encouraged-development-guidelines.md)

[アドバイザリ開発のガイドライン](./advisory-development-guidelines.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
