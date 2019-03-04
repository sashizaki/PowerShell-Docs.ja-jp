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
ms.openlocfilehash: 31ee7222c35e82ee58d6d56f710792dbc5cb24d7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858628"
---
# <a name="windows-powershell-provider-overview"></a>Windows PowerShell プロバイダーの概要

Windows PowerShell プロバイダーにより、ファイル システムと同様に、マウントされたドライブの場合と同様に公開する任意のデータ ストアです。 たとえば、組み込みレジストリ プロバイダーを使用すると、移動する場合と同様に、レジストリを移動、`c`コンピューターのドライブです。 プロバイダーをオーバーライドできますも、`Item`コマンドレット (たとえば、 `Get-Item`、`Set-Item`など) ファイルと同様に、データ ストアにデータを扱うことができ、ディレクトリは、ファイル システムを移動するときとして扱われるようにします。 詳細については、プロバイダーとドライブ、および Windows PowerShell の組み込みプロバイダーは、次を参照してください。 [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)します。
Windows PowerShell プロバイダーにより、ファイル システムと同様に、マウントされたドライブの場合と同様に公開する任意のデータ ストアです。 たとえば、組み込みレジストリ プロバイダーを使用すると、移動する場合と同様に、レジストリを移動、`c`コンピューターのドライブです。 プロバイダーをオーバーライドできますも、`Item`コマンドレット (たとえば、 `Get-Item`、`Set-Item`など) ファイルと同様に、データ ストアにデータを扱うことができ、ディレクトリは、ファイル システムを移動するときとして扱われるようにします。 詳細については、プロバイダーとドライブ、および Windows PowerShell の組み込みプロバイダーは、次を参照してください。 [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)します。

## <a name="providers-and-drives"></a>プロバイダーとドライブ

プロバイダーは、アクセス、移動、およびドライブが、プロバイダーによって定義された型のデータ ストア (またはデータ ストアの一部) の特定のエントリ ポイントを指定のデータ ストアを編集するために使用するロジックを定義します。 たとえば、レジストリ プロバイダーでは、ハイブとレジストリの場合は、キーにアクセスできます。 し、HKLM と HKCU ドライブがレジストリ内の対応するハイブを指定します。 HKLM と HKCU の両方のドライブは、レジストリ プロバイダーを使用します。

プロバイダーを作成する場合は、既定のドライブのドライブ、プロバイダーが使用可能なときに自動的に作成されるを指定できます。 また、そのプロバイダーを使用して、新しいドライブを作成するメソッドを定義します。

## <a name="type-of-providers"></a>プロバイダーの種類

さまざまなレベルの機能を提供しているプロバイダーのいくつかの種類あります。 プロバイダーがの子孫のいずれかから派生するクラスとして実装されている、 [System.Management.Automation.Sessionstatecategory.Cmdletprovider](/dotnet/api/System.Management.Automation.SessionStateCategory.CmdletProvider)クラス。 プロバイダーのさまざまな種類については、次を参照してください。[プロバイダー型](./provider-types.md)します。

## <a name="provider-cmdlets"></a>プロバイダー コマンドレット

プロバイダーは、そのプロバイダーのドライブで使用されるときに、これらのコマンドレットのカスタム ビヘイビアーの作成、コマンドレットに対応するメソッドを実装できます。 でプロバイダーの種類に応じてさまざまなコマンドレットのセットを使用できます。 プロバイダーでカスタマイズ可能なコマンドレットの完全な一覧を参照してください。[プロバイダー コマンドレット](./provider-cmdlets.md)します。

## <a name="provider-paths"></a>プロバイダー パス

ユーザーは、ファイル システムなどのプロバイダー ドライブを移動します。 このため、ファイル システムのナビゲーションで使用するパスに対応するパスの構文の想定されます。 ユーザーは、プロバイダー コマンドレットを実行すると、アクセスする項目へのパスを指定します。 指定されたパスは、いくつかの方法で解釈できます。 プロバイダーは、次のパスの種類の 1 つ以上をサポートする必要があります。

### <a name="drive-qualified-paths"></a>ドライブ修飾パス

ドライブ修飾パスは、項目の名前、コンテナーと、項目が、配置されているサブコンテナーおよびアイテムにアクセスする Windows PowerShell ドライブの組み合わせです。 (ドライブは、データ ストアにアクセスするために使用するプロバイダーによって定義されます。 このパスの後にコロン (:) ドライブ名で始まります。 たとえば次のようになります。`get-childitem C:`

### <a name="provider-qualified-paths"></a>プロバイダーで修飾されたパス

Windows PowerShell エンジンを初期化して、プロバイダーの初期化を解除できるように、プロバイダーはプロバイダーで修飾されたパスをサポートする必要があります。 ユーザーが初期化し、FileSystem プロバイダーの初期化を解除して、次のプロバイダーで修飾されたパスを定義するので、たとえば、:`FileSystem::\\uncshare\abc\bar`します。

### <a name="provider-direct-paths"></a>プロバイダーの直接パス

Windows PowerShell プロバイダーへのリモート アクセスを許可するのには、現在の場所、Windows PowerShell プロバイダーに直接渡すプロバイダー直接パスをサポートしてする必要があります。 たとえば、レジストリの Windows PowerShell プロバイダーを使用できます`\\server\regkeypath`プロバイダー ダイレクト パスとして。

### <a name="provider-internal-paths"></a>プロバイダーの内部パス

プロバイダー コマンドレットを Windows PowerShell 以外のアプリケーション プログラミング インターフェイス (Api) を使用してデータにアクセスできるように、Windows PowerShell プロバイダーは、プロバイダーの内部パスをサポートする必要があります。 後にこのパスが示される、"::"プロバイダーで修飾されたパスにします。 たとえば、ファイル システムの Windows PowerShell プロバイダーのプロバイダーの内部パスは`\\uncshare\abc\bar`します。

## <a name="overriding-cmdlet-parameters"></a>コマンドレットのパラメーターをオーバーライドします。

プロバイダーによっては、一部のプロバイダーに固有コマンドレットの動作をオーバーライドできます。 オーバーライド可能なパラメーターの一覧と、プロバイダー クラスでオーバーライドする方法は、次を参照してください[プロバイダー コマンドレットのパラメーター。](./provider-cmdlet-parameters.md)

## <a name="dynamic-parameters"></a>動的パラメーター

プロバイダーは、ユーザーがコマンドレットの静的パラメーターのいずれかの特定の値を指定すると、プロバイダー コマンドレットに追加される動的パラメーターを定義できます。 プロバイダーは、1 つ以上の動的パラメーターのメソッドを実装することで。 動的パラメーター、およびそれらを実装するために使用するメソッドを追加するために使用できるコマンドレットのパラメーターの一覧は、次を参照してください。[プロバイダー コマンドレットの動的パラメーター](./provider-cmdlet-dynamic-parameters.md)します。

## <a name="provider-capabilities"></a>プロバイダーの機能

[System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙型は、さまざまなプロバイダーをサポートする機能を定義します。 ワイルドカードを使用する、項目をフィルター処理、およびトランザクションをサポートする機能が含まれます。 プロバイダーの機能を指定するには、一連の値を追加、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙型で、論理と組み合わせて`OR`操作として、 [System.Management.Automation.Provider.Cmdletproviderattribute.Providercapabilities*](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities)プロパティ (属性の 2 番目のパラメーター) の[System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)プロバイダー クラスの属性。 次の属性が、プロバイダーがサポートするように指定するなど、 [System.Management.Automation.Provider.Providercapabilities.Shouldprocess](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities.ShouldProcess)と[System.Management.Automation.Provider.Providercapabilities.Transactions](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities.Transactions)機能します。

```csharp
[CmdletProvider(RegistryProvider.ProviderName, ProviderCapabilities.ShouldProcess | ProviderCapabilities.Transactions)]

```

## <a name="provider-cmdlet-help"></a>プロバイダー コマンドレットのヘルプ

プロバイダーを記述する場合、独自のヘルプをサポートするプロバイダーのコマンドレットを実装できます。 これには、各プロバイダー コマンドレットまたは複数のバージョンの場合は、プロバイダー コマンドレットが機能します動的パラメーターの使用に基づいて異なる方法でヘルプ トピックの 1 つのヘルプ トピックが含まれます。 プロバイダーに固有コマンドレットのヘルプをサポートするために、プロバイダーを実装する必要があります、 [System.Management.Automation.Provider.Icmdletprovidersupportshelp](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp)インターフェイス。

Windows PowerShell エンジンの呼び出し、 [System.Management.Automation.Provider.Icmdletprovidersupportshelp.Gethelpmaml*](/dotnet/api/System.Management.Automation.Provider.ICmdletProviderSupportsHelp.GetHelpMaml)プロバイダー コマンドレット ヘルプ トピックを表示するメソッド。 エンジンが実行されている場合、ユーザーが指定されているコマンドレットの名前を提供します、`Get-Help`コマンドレットと、ユーザーの現在のパス。 ご利用のプロバイダーは、別のドライブに同じプロバイダー コマンドレットの異なるバージョンを実装している場合、現在のパスが必要です。 メソッドは、コマンドレットのヘルプの XML を含む文字列を返す必要があります。

PSMAML XML を使用してヘルプ ファイルのコンテンツが書き込まれます。 これは、スタンドアロンのコマンドレットのヘルプ コンテンツを記述するために使用される同じ XML スキーマです。 カスタム コマンドレット、プロバイダーのヘルプ ファイルへのヘルプの内容を追加で、`CmdletHelpPaths`要素。 次の例は、`command`要素では、1 つのプロバイダー コマンドレット、プロバイダー コマンドレットの名前を指定する方法を示しているプロバイダー。 サポートしています

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

[プロバイダーのコマンドレット](./provider-cmdlets.md)

[Windows PowerShell プロバイダーの記述](./writing-a-windows-powershell-provider.md)