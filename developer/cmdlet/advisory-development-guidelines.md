---
title: アドバイザリ開発のガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79c9bcbc-a2eb-4253-a4b8-65ba54ce8d01
caps.latest.revision: 9
ms.openlocfilehash: 871a74a084da3c7ec36767b7195461e0e7290cb9
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056568"
---
# <a name="advisory-development-guidelines"></a>お勧めする開発ガイドライン

このセクションでは、適切な開発とユーザー エクスペリエンスを確保するために考慮すべきガイドラインについて説明します。 場合によって次のように適用される場合がありますとありますでない場合があります。

## <a name="design-guidelines"></a>デザイン ガイドライン

- [InputObject パラメーター (AD01) のサポートします。](./advisory-development-guidelines.md#AD01)

- [Force パラメーター (AD02) のサポート](./advisory-development-guidelines.md#AD02)

- [Windows PowerShell (AD03) を使って資格情報を処理します。](./advisory-development-guidelines.md#AD03)

- [エンコード パラメーター (AD04) をサポートします。](./advisory-development-guidelines.md#AD04)

- [テスト コマンドレットは、ブール値 (AD05) を返す必要があります。](./advisory-development-guidelines.md#AD05)

## <a name="code-guidelines"></a>コードのガイドライン

- [次のコマンドレットのクラスの名前付け規則 (AC01)](./advisory-development-guidelines.md#AC01)

- [パイプラインの入力には、BeginProcessing メソッド (AC02) が上書きされない場合](./advisory-development-guidelines.md#AC02)

- [StopProcessing メソッド (AC03) をオーバーライドしている停止要求を処理するには](./advisory-development-guidelines.md#AC03)

- [IDisposable インターフェイス (AC04) の実装します。](./advisory-development-guidelines.md#AC04)

- [シリアル化に適したパラメーターの型 (AC05) を使用して、](./advisory-development-guidelines.md#AC05)

- [SecureString を使用して、機密性の高いデータ (AC06)](./advisory-development-guidelines.md#AC06)

## <a name="design-guidelines"></a>デザイン ガイドライン

コマンドレットを設計するときに、次のガイドラインを検討してください。 自分の状況に適用されるデザインのガイドラインを検索するときに必ずのようなガイドラインについては、コードのガイドラインを確認してください。

### <a name="support-an-inputobject-parameter-ad01"></a>InputObject パラメーター (AD01) のサポートします。

Windows PowerShell は、Microsoft .NET Framework オブジェクトを直接機能するため、.NET Framework オブジェクトがある多くの場合、完全に一致する型、ユーザーがする必要がありますが、特定の操作を実行します。 `InputObject` 標準の入力としてこのようなオブジェクトを取得するパラメーターの名前です。 サンプルではたとえば、**停止 Proc**コマンドレット、 [StopProc チュートリアル](./stopproc-tutorial.md)定義、`InputObject`型パイプラインから入力をサポートしているプロセスのパラメーター。 ユーザーは、プロセス オブジェクトのセットを取得、操作を停止するには厳密なオブジェクトを選択、およびに渡して、**停止 Proc**直接コマンドレット。

### <a name="support-the-force-parameter-ad02"></a>Force パラメーター (AD02) のサポート

場合によっては、コマンドレットは、要求された操作を実行してから、ユーザーを保護する必要があります。 このようなコマンドレットをサポートする必要があります、`Force`パラメーターをユーザーが、ユーザーが操作を実行するアクセス許可を持っている場合、その保護を上書きできるようにします。

たとえば、 [Remove-item](/powershell/module/microsoft.powershell.management/remove-item)コマンドレットが読み取り専用ファイルを正常に削除しません。 ただし、このコマンドレットをサポートしています、`Force`パラメーターため、ユーザーは読み取り専用ファイルの削除を強制できますの。 場合は、読み取り専用属性を変更するアクセス許可をユーザーが既に存在して、ユーザーがファイルを削除を使用して、`Force`パラメーターは、操作を簡略化します。 ただし、ユーザーが、ファイルを削除するアクセス許可を持っていない場合、`Force`パラメーターが影響を与えません。

### <a name="handle-credentials-through-windows-powershell-ad03"></a>Windows PowerShell (AD03) を使って資格情報を処理します。

コマンドレットを定義する必要があります、`Credential`を資格情報を表すパラメーター。 このパラメーターは、型でなければなりません[System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential)と資格情報の属性宣言を使用して定義する必要があります。 このサポートでは、完全な資格情報が直接指定されていないときにユーザー名、パスワード、または両方のユーザーが自動的に表示されます。 資格情報の属性の詳細については、次を参照してください。[資格情報の属性宣言](./credential-attribute-declaration.md)します。

### <a name="support-encoding-parameters-ad04"></a>エンコード パラメーター (AD04) をサポートします。

コマンドレットは、読み取るか、またはへの書き込みや、ファイル システム内のファイルからの読み取りなどのバイナリ形式からテキストを書き込む場合、コマンドレットに Encoding パラメーターをバイナリ形式でテキストをエンコードする方法を指定するには。

### <a name="test-cmdlets-should-return-a-boolean-ad05"></a>テスト コマンドレットは、ブール値 (AD05) を返す必要があります。

リソースに対してテストを実行するコマンドレットが返す必要があります、 [System.Boolean](/dotnet/api/System.Boolean)条件式で使えるようにをパイプラインに入力します。

## <a name="code-guidelines"></a>コードのガイドライン

コマンドレットのコードを記述する場合は、次のガイドラインを検討してください。 自分の状況に適用されるガイドラインを検索するときに必ずのようなガイドラインについては、デザイン ガイドラインを確認してください。

### <a name="follow-cmdlet-class-naming-conventions-ac01"></a>次のコマンドレットのクラスの名前付け規則 (AC01)

次の標準的な名前付け規則によって、コマンドレットの発見しやすくすることし、ユーザーがコマンドレットによって実行と正確に理解する際に役立ちます。 この方法は、コマンドレットはパブリック型であるために、Windows PowerShell を使用して他の開発者にとって特に重要です。

#### <a name="define-a-cmdlet-in-the-correct-namespace"></a>正しい Namespace でコマンドレットを定義します。

通常、.NET Framework 名前空間に追加されるでコマンドレットのクラスを定義する"。コマンド"コマンドレットを実行する製品を表す名前空間にします。 Windows PowerShell に含まれているコマンドレットを定義するなど、`Microsoft.PowerShell.Commands`名前空間。

#### <a name="name-the-cmdlet-class-to-match-the-cmdlet-name"></a>コマンドレット名と一致するコマンドレット クラスの名前します。

コマンドレットを実装する .NET Framework クラス、名前を付けるときに、クラスの名前を"*\<動詞 >**\<名詞 >**\<コマンド >*"、を交換します。*\<動詞 >* と*\<名詞 >* プレース ホルダーを動詞と名詞コマンドレット名に使用します。 たとえば、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットがという名前のクラスによって実装される`GetProcessCommand`します。

### <a name="if-no-pipeline-input-override-the-beginprocessing-method-ac02"></a>パイプラインの入力には、BeginProcessing メソッド (AC02) が上書きされない場合

処理を実装する必要があります、コマンドレットが、パイプラインからの入力を受け付けない場合、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッド。 このメソッドの使用は、Windows PowerShell のコマンドレット間で順序を維持するためにできます。 パイプラインの残りのコマンドレットは、これらの処理を起動するチャンスを取得する前に、パイプラインの最初のコマンドレットは常にそのオブジェクトを返します。

### <a name="to-handle-stop-requests-override-the-stopprocessing-method-ac03"></a>StopProcessing メソッド (AC03) をオーバーライドしている停止要求を処理するには

上書き、 [System.Management.Automation.Cmdlet.StopProcessing](/dotnet/api/System.Management.Automation.Cmdlet.StopProcessing)メソッド コマンドレットは、停止信号を処理できるようにします。 一部のコマンドレットの操作を完了する時間がかかるし、時間など、コマンドレットが実行時間の長い RPC 呼び出しでスレッドをブロックするときに、Windows PowerShell ランタイムへの呼び出しの間で渡すことができます。 呼び出しを行うコマンドレットが含まれます、 [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド、およびその他のフィードバック完了までに時間がかかる場合がありますメカニズム。 このような場合、ユーザーは、これらのコマンドレットに停止シグナルを送信する必要があります。

### <a name="implement-the-idisposable-interface-ac04"></a>IDisposable インターフェイス (AC04) の実装します。

コマンドレットに (パイプラインに書き込まれます) の破棄されていないオブジェクトがある場合は、によって、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドでは、コマンドレットは、その他のオブジェクトの破棄を必要があります。 例では、コマンドレットがファイル ハンドルを開いた場合、その[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)メソッドと保持で使用するためのハンドルを開く、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)処理の最後に終了する方法、このハンドルが。

Windows PowerShell ランタイムが常に呼び出していない、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)メソッド。 たとえば、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)コマンドレットを途中の操作をキャンセルするか、コマンドレットのすべての部分でエラーが発生した場合は、終了した場合、メソッドは呼び出されません可能性があります。 したがって、オブジェクトのクリーンアップが必要なコマンドレットの .NET Framework クラスを完全に実装[System.IDisposable](/dotnet/api/System.IDisposable)インターフェイス パターン、ファイナライザーを含む、Windows PowerShell ランタイムは、両方を呼び出すことができます、[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)と[System.IDisposable.Dispose*](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。

### <a name="use-serialization-friendly-parameter-types-ac05"></a>シリアル化に適したパラメーターの型 (AC05) を使用して、

リモート コンピューターで、コマンドレットの実行をサポートするには、クライアント コンピューターで簡単にシリアル化し、サーバー コンピューターにリハイド レートする型を使用します。 次の種類は、シリアル化に適したです。

プリミティブの種類:

- Byte、SByte、10 進数、単一、Double、Int16、Int32、Int64、Uint16、UInt32、および UInt64。

- ブール値、Guid、Byte、TimeSpan、DateTime、Uri、およびバージョン。

- Char、String、XmlDocument です。

組み込みの rehydratable 型:

- PSPrimitiveDictionary

- スイッチ パラメーター

- PSListModifier

- PSCredential

- IPAddress, MailAddress

- CultureInfo

- X509Certificate2、X500DistinguishedName

- DirectorySecurity、FileSecurity、RegistrySecurity

他の種類:

- SecureString

- コンテナー (リストとディクショナリが上記の型の)

### <a name="use-securestring-for-sensitive-data-ac06"></a>SecureString を使用して、機密性の高いデータ (AC06)

常に機密データを処理するときに使用して、 [System.Security.Securestring](/dotnet/api/System.Security.SecureString)データ型。 これには、パイプラインに機密データを返すことに加えて、パラメーターにパイプラインの入力が含まれます。

## <a name="see-also"></a>参照

[必要な開発のガイドライン](./required-development-guidelines.md)

[強くお勧めします開発のガイドライン](./strongly-encouraged-development-guidelines.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
