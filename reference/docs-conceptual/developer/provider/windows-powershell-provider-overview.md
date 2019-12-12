---
title: Windows PowerShell プロバイダーの概要 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82244fbd-07b9-47f3-805c-3fb90ebbf58a
caps.latest.revision: 13
ms.openlocfilehash: 81f6c8cd75ccea9e711cd8f6d6daa6cca5a499a0
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366291"
---
# <a name="windows-powershell-provider-overview"></a>Windows PowerShell プロバイダーの概要

Windows PowerShell プロバイダーを使用すると、マウントされたドライブのように、任意のデータストアをファイルシステムとして公開できます。 たとえば、組み込みレジストリプロバイダーを使用すると、コンピューターの `c` ドライブを移動する場合と同様に、レジストリ内を移動することができます。 プロバイダーは、`Item` コマンドレット (`Get-Item`、`Set-Item`など) をオーバーライドすることもできます。これにより、データストア内のデータをファイルやディレクトリと同様に処理できるようになります。 プロバイダーとドライブ、および Windows PowerShell の組み込みプロバイダーの詳細については、「 [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)」を参照してください。

## <a name="providers-and-drives"></a>プロバイダーとドライブ

プロバイダーは、データストアへのアクセス、移動、および編集に使用されるロジックを定義します。ドライブは、プロバイダーによって定義された型のデータストア (またはデータストアの一部) への特定のエントリポイントを指定します。 たとえば、レジストリプロバイダーを使用すると、レジストリのハイブとキーにアクセスできます。 HKLM ドライブと HKCU ドライブは、レジストリ内の対応するハイブを指定します。 HKLM および HKCU ドライブはどちらもレジストリプロバイダーを使用します。

プロバイダーを作成するときに、プロバイダーが利用可能になったときに自動的に作成される既定のドライブドライブを指定できます。 また、そのプロバイダーを使用する新しいドライブを作成するためのメソッドを定義します。

## <a name="type-of-providers"></a>プロバイダーの種類

プロバイダーにはいくつかの種類があり、それぞれに異なるレベルの機能が用意されています。 プロバイダーは、 [SessionStateCategory](/dotnet/api/system.management.automation.sessionstatecategory?view=pscore-6.2.0)のいずれかの**プロバイダー**クラスの子孫から派生するクラスとして実装されます。 さまざまな種類のプロバイダーの詳細については、「[プロバイダーの種類](./provider-types.md)」を参照してください。

## <a name="provider-cmdlets"></a>プロバイダー コマンドレット

プロバイダーは、コマンドレットに対応するメソッドを実装し、そのプロバイダーのドライブで使用されている場合に、これらのコマンドレットのカスタム動作を作成できます。 プロバイダーの種類に応じて、異なる一連のコマンドレットを使用できます。 プロバイダーでカスタマイズ可能なコマンドレットの完全な一覧については、「[プロバイダーコマンドレット](./provider-cmdlets.md)」を参照してください。

## <a name="provider-paths"></a>プロバイダーのパス

ユーザーは、ファイルシステムなどのプロバイダーのドライブを移動します。 このため、ファイルシステムのナビゲーションで使用されるパスに対応するパスの構文が想定されています。 ユーザーは、プロバイダーコマンドレットを実行するときに、アクセスする項目へのパスを指定します。 指定されたパスは、いくつかの方法で解釈できます。 プロバイダーは、次のパスの種類の1つ以上をサポートする必要があります。

### <a name="drive-qualified-paths"></a>ドライブ修飾パス

ドライブ修飾パスは、項目名、項目が配置されているコンテナーとサブコンテナー、および項目のアクセスに使用される Windows PowerShell ドライブを組み合わせたものです。 (ドライブは、データストアへのアクセスに使用されるプロバイダーによって定義されます。 このパスの先頭には、ドライブ名とコロン (:) が続きます。 たとえば次のようになります。`get-childitem C:`

### <a name="provider-qualified-paths"></a>プロバイダー修飾パス

Windows PowerShell エンジンがプロバイダーを初期化および初期化解除できるようにするには、プロバイダーがプロバイダーによって修飾されたパスをサポートする必要があります。 たとえば、ユーザーは、次のプロバイダーによって修飾されたパスが定義されているため、ファイルシステムプロバイダーの初期化と初期化解除を行うことができます: `FileSystem::\\uncshare\abc\bar`。

### <a name="provider-direct-paths"></a>プロバイダー-直接パス

Windows PowerShell プロバイダーへのリモートアクセスを許可するには、現在の場所に対して Windows PowerShell プロバイダーに直接渡すプロバイダー-直接パスをサポートする必要があります。 たとえば、レジストリの Windows PowerShell プロバイダーでは、`\\server\regkeypath` をプロバイダーのダイレクトパスとして使用できます。

### <a name="provider-internal-paths"></a>プロバイダー-内部パス

プロバイダーコマンドレットが Windows PowerShell 以外のアプリケーションプログラミングインターフェイス (Api) を使用してデータにアクセスできるようにするには、Windows PowerShell プロバイダーがプロバイダー内部パスをサポートしている必要があります。 このパスは、プロバイダーによって修飾されたパスの "::" の後に示されます。 たとえば、プロバイダー-filesystem Windows PowerShell プロバイダーの内部パスは `\\uncshare\abc\bar`ます。

## <a name="overriding-cmdlet-parameters"></a>コマンドレットパラメーターのオーバーライド

プロバイダー固有のコマンドレットの動作は、プロバイダーによってオーバーライドされる場合があります。 オーバーライド可能なパラメーターの一覧と、それらをプロバイダークラスでオーバーライドする方法については、「[プロバイダーコマンドレットのパラメーター](./provider-cmdlet-parameters.md) 」を参照してください。

## <a name="dynamic-parameters"></a>動的パラメーター

プロバイダーは、ユーザーがコマンドレットのいずれかの静的パラメーターに特定の値を指定した場合に、プロバイダーコマンドレットに追加される動的パラメーターを定義できます。 プロバイダーは、1つまたは複数の動的パラメーターメソッドを実装することによってこれを行います。 動的パラメーターの追加に使用できるコマンドレットパラメーターの一覧と、それらを実装するために使用されるメソッドについては、「[プロバイダーコマンドレット動的パラメーター](./provider-cmdlet-dynamic-parameters.md)」を参照してください。

## <a name="provider-capabilities"></a>プロバイダーの機能

プロバイダーがサポートできるさまざまな機能が定義さ[れてい](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)ます ()。 これには、ワイルドカード、フィルター項目、およびサポートトランザクションを使用する機能が含まれます。 プロバイダーの機能を指定するには、論理 `OR` 操作と組み合わせて、System. automation. provider. [providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙型の値のリストを、プロバイダークラスの system.servicemodel................. [. プロバイダーの](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性[のプロパティ (](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities)属性の2番目のパラメーター) として追加します。 たとえば、次の属性では、プロバイダーがシステムの[管理](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities?view=pscore-6.2.0)をサポートしていることを指定しています。プロバイダーは、の**処理**と[システムの管理](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities?view=pscore-6.2.0)を実行します。

```csharp
[CmdletProvider(RegistryProvider.ProviderName, ProviderCapabilities.ShouldProcess | ProviderCapabilities.Transactions)]

```

## <a name="provider-cmdlet-help"></a>プロバイダーコマンドレットのヘルプ

プロバイダーを作成するときに、サポートするプロバイダーコマンドレットに独自のヘルプを実装できます。 これには、プロバイダーコマンドレットごとに1つのヘルプトピックが含まれています。また、プロバイダーコマンドレットの動作が動的パラメーターの使用方法によって異なる場合は、複数のバージョンのヘルプトピックがあります。 プロバイダーのコマンドレット固有のヘルプをサポートするには、プロバイダーが[Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp)インターフェイスを実装する必要があります。

Windows PowerShell エンジンは、 [Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml)を呼び出して、プロバイダーのコマンドレットのヘルプトピックを表示するためのメソッドを呼び出します。 エンジンは、`Get-Help` コマンドレットを実行するときにユーザーが指定したコマンドレットの名前と、ユーザーの現在のパスを提供します。 プロバイダーが異なるドライブに対して同じプロバイダーコマンドレットの異なるバージョンを実装している場合は、現在のパスが必要です。 メソッドは、コマンドレットヘルプの XML を含む文字列を返す必要があります。

ヘルプファイルの内容は、PSMAML XML を使用して書き込まれます。 これは、スタンドアロンのコマンドレットのヘルプコンテンツを記述するために使用される XML スキーマと同じです。 カスタムコマンドレットヘルプの内容を、`CmdletHelpPaths` 要素のプロバイダーのヘルプファイルに追加します。 次の例は、1つのプロバイダーコマンドレットの `command` 要素を示しています。また、プロバイダーが提供するプロバイダーコマンドレットの名前を指定する方法を示しています。 対応

```xml
<CmdletHelpPaths>
  <command:command>
    <command:details>
      <command:name>ProviderCmdletName</command:name>
      <command:verb>Verb</command:verb>
      <command:noun>Noun</command:noun>
    <command:details>
  </command:command>
<CmdletHelpPath>
```

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーの機能](./provider-types.md)

[プロバイダーコマンドレット](./provider-cmdlets.md)

[Windows PowerShell プロバイダーの作成](./writing-a-windows-powershell-provider.md)