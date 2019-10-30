---
title: アドバイザリ開発ガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79c9bcbc-a2eb-4253-a4b8-65ba54ce8d01
caps.latest.revision: 9
ms.openlocfilehash: 980b488800587e31286e2ca2ece924e07f8af3f3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370041"
---
# <a name="advisory-development-guidelines"></a>お勧めする開発ガイドライン

このセクションでは、適切な開発とユーザーエクスペリエンスを確保するために考慮する必要があるガイドラインについて説明します。 場合によっては、適用される場合もあれば、ない場合もあります。

## <a name="design-guidelines"></a>設計ガイドライン

コマンドレットを設計するときは、次のガイドラインを考慮する必要があります。 状況に当てはまる設計ガイドラインが見つかったら、同様のガイドラインのコードガイドラインを確認してください。

### <a name="support-an-inputobject-parameter-ad01"></a>InputObject パラメーター (AD01) のサポート

Windows PowerShell は Microsoft .NET Framework オブジェクトで直接動作するため、ユーザーが特定の操作を実行するために必要な型と正確に一致する .NET Framework オブジェクトを使用できます。 `InputObject` は、このようなオブジェクトを入力として受け取るパラメーターの標準名です。 たとえば、 [Stopproc チュートリアル](./stopproc-tutorial.md)の**Stop proc**コマンドレットの例では、パイプラインからの入力をサポートする Process 型の `InputObject` パラメーターを定義しています。 ユーザーは、一連のプロセスオブジェクトを取得し、それらを操作して、停止するオブジェクトを正確に選択し、そのオブジェクトを**Stop Proc**コマンドレットに直接渡すことができます。

### <a name="support-the-force-parameter-ad02"></a>Force パラメーター (AD02) のサポート

場合によっては、コマンドレットでユーザーが要求された操作を実行できないように保護する必要があります。 このようなコマンドレットは、ユーザーが操作を実行するアクセス許可を持っている場合に、ユーザーがその保護をオーバーライドできるようにするために、`Force` パラメーターをサポートする必要があります。

たとえば、項目の[削除](/powershell/module/microsoft.powershell.management/remove-item)コマンドレットは、通常、読み取り専用ファイルを削除しません。 ただし、このコマンドレットは `Force` パラメーターをサポートしているので、ユーザーは読み取り専用ファイルを強制的に削除できます。 読み取り専用属性を変更するアクセス許可がユーザーに既に与えられていて、ユーザーがそのファイルを削除した場合は、`Force` パラメーターを使用すると操作が簡略化されます。 ただし、ファイルを削除する権限がユーザーに与えられていない場合、`Force` パラメーターを指定しても効果はありません。

### <a name="handle-credentials-through-windows-powershell-ad03"></a>Windows PowerShell (AD03) を使用して資格情報を処理する

コマンドレットでは、資格情報を表すために `Credential` パラメーターを定義する必要があります。 このパラメーターは[、型が system.servicemodel で、](/dotnet/api/System.Management.Automation.PSCredential) Credential 属性の宣言を使用して定義されている必要があります。 このサポートによって、ユーザーは、パスワードのユーザー名を入力するか、完全な資格情報が直接指定されていない場合の両方に対して自動的にプロンプトが表示されます。 Credential 属性の詳細については、「 [Credential 属性の宣言](./credential-attribute-declaration.md)」を参照してください。

### <a name="support-encoding-parameters-ad04"></a>パラメーターのエンコード (AD04) のサポート

ファイルシステム内のファイルへの書き込みやファイルからの読み取りなど、バイナリ形式のテキストの読み取りまたは書き込みを行うコマンドレットでは、バイナリ形式でテキストをエンコードする方法を指定する Encoding パラメーターをコマンドレットに設定する必要があります。

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a>テストコマンドレットはブール値 (AD05) を返す必要があります

リソースに対してテストを実行するコマンドレットは、条件式で使用できるように、システムのブール型をパイプラインに返す必要があり[ます。](/dotnet/api/System.Boolean)

## <a name="code-guidelines"></a>コードのガイドライン

コマンドレットコードを記述するときは、次のガイドラインを考慮する必要があります。 状況に当てはまるガイドラインが見つかった場合は、設計ガイドラインで同様のガイドラインを確認してください。

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a>コマンドレットクラスの名前付け規則に従う (AC01)

標準的な名前付け規則に従うことで、コマンドレットをより見つけやすくなり、コマンドレットの動作を正確に理解することができます。 この方法は、コマンドレットがパブリック型であるため、Windows PowerShell を使用する他の開発者にとって特に重要です。

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a>正しい名前空間のコマンドレットを定義する

通常は、"を追加する .NET Framework 名前空間のコマンドレットのクラスを定義します。コマンドレットを実行する製品を表す名前空間を指定します。 たとえば、Windows PowerShell に含まれているコマンドレットは、`Microsoft.PowerShell.Commands` 名前空間で定義されています。

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a>コマンドレット名と一致するようにコマンドレットクラスの名前を指定します

コマンドレットを実装する .NET Framework クラスに名前を付けた場合は、クラスに " *\<Verb > **\<Noun >*** \<Command *" という*名前を付けます。ここで > \<Verb プレースホルダーと *>* \<Noun プレースホルダーを置き換えます。コマンドレット名に使用される動詞と名詞。 たとえば、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットは、`GetProcessCommand` というクラスによって実装されます。

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a>パイプライン入力が BeginProcessing メソッドをオーバーライドしない場合 (AC02)

コマンドレットがパイプラインからの入力を受け付けない場合は、処理を実行する必要があります。そのためには、[このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)使用します。 この方法を使用すると、Windows PowerShell でコマンドレット間の順序を維持することができます。 パイプラインの最初のコマンドレットは、パイプラインの残りのコマンドレットが処理を開始する前に、常にそのオブジェクトを返します。

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a>停止要求を処理するには、StopProcessing メソッド (AC03) をオーバーライドします。

コマンドレットが停止シグナルを処理できるように、[このメソッドをオーバーライドします](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing)。 一部のコマンドレットでは、操作が完了するまでに長い時間がかかります。また、コマンドレットが長時間の RPC 呼び出しでスレッドをブロックしている場合など、Windows PowerShell ランタイムの呼び出しの間に長い時間がかかることがあります。 これには、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドへの呼び出しを実行するコマンドレット、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド、および完了までに時間がかかるその他のフィードバックメカニズムが含まれている必要があります. このような場合、ユーザーはこれらのコマンドレットに停止シグナルを送信することが必要になる場合があります。

### <a name="implement-the-idisposable-interface-ac04"></a>IDisposable インターフェイス (AC04) を実装する

コマンドレット[に、(](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)パイプラインに書き込まれる) の破棄されないオブジェクトが含まれている場合、コマンドレットでは追加のオブジェクトの破棄が必要になることがあります。 たとえば、コマンドレットによって、ファイルハンドルがその[システム](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)の "管理.............................................. [...](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) ..............処理の終了時に終了します。

Windows PowerShell ランタイムで[は、必ずしも system.servicemodel メソッドが](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)呼び出されるわけではありません。 たとえば、コマンドレットが操作の途中で取り消された場合、またはコマンドレットのいずれかの部分で終了エラーが発生した場合、[このメソッドは](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)呼び出されないことがあります。 したがって、オブジェクトのクリーンアップを必要とするコマンドレットの .NET Framework クラスは、ファイナライザーを含む完全な [system.servicemodel](/dotnet/api/System.IDisposable) インターフェイスパターンを実装する必要があります。これにより、Windows PowerShell ランタイムは、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)処理の最後に、システムの.... コマンドレットと system.servicemodel [System.IDisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose)メソッドを実行します。

### <a name="use-serialization-friendly-parameter-types-ac05"></a>シリアル化に対応したパラメーターの型 (AC05) を使用する

リモートコンピューターでコマンドレットを実行できるようにするには、クライアントコンピューターで簡単にシリアル化できる型を使用し、その後でサーバーコンピューター上で復元することができます。 次の型はシリアル化に適しています。

プリミティブ型:

- Byte、SByte、Decimal、Single、Double、Int16、Int32、Int64、Uint16、UInt32、および UInt64。

- ブール値、Guid、Byte []、TimeSpan、DateTime、Uri、Version。

- Char、String、XmlDocument。

組み込みの rehydratable 型:

- PSPrimitiveDictionary

- SwitchParameter

- PSListModifier

- PSCredential

- IPAddress、MailAddress

- CultureInfo

- X509Certificate2、System.security.cryptography.x509certificates.x500distinguishedname

- DirectorySecurity、System.security.accesscontrol.filesecurity、RegistrySecurity

その他の種類:

- SecureString

- コンテナー (上記の種類のリストとディクショナリ)

### <a name="use-securestring-for-sensitive-data-ac06"></a>機密データに SecureString を使用する (AC06)

機微なデータを処理するときは、常に[Securestring](/dotnet/api/System.Security.SecureString)データ型を使用します。 これには、パラメーターへのパイプライン入力だけでなく、機密データをパイプラインに返すこともできます。

## <a name="see-also"></a>参照

[必要な開発ガイドライン](./required-development-guidelines.md)

[開発に関する推奨事項](./strongly-encouraged-development-guidelines.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
