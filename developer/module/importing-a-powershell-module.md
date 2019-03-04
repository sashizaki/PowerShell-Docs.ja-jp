---
title: PowerShell モジュールをインポートする |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 697791b3-2135-4a39-b9d7-8566ed67acf2
caps.latest.revision: 13
ms.openlocfilehash: bb5d036e5658c365a4fafa2cac05c0bba9f87019
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854058"
---
# <a name="importing-a-powershell-module"></a>PowerShell モジュールをインポートする

1 回、モジュールがインストールされているシステムでは、するモジュールをインポートするする可能性があります。 インポートでは、ユーザーは、PowerShell セッションでそのモジュールにアクセスできるように、モジュールをアクティブ メモリに読み込まれるプロセスです。 PowerShell 2.0 への呼び出しでは、新しくインストールした PowerShell モジュールをインポートすることができます[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット。 PowerShell 3.0 では、PowerShell は暗黙的に関数またはモジュールのコマンドレットのいずれかがユーザーによって呼び出されると、モジュールをインポートすることです。 両方のバージョンが PowerShell がそれを検索することがある場所で、モジュールをインストールすることを想定して ことに注意してください。詳細については、次を参照してください。 [PowerShell モジュールのインストール](./installing-a-powershell-module.md)します。 モジュール マニフェストを使用するには、モジュールのどの部分をエクスポートすると、制限してのパラメーターを使用して、`Import-Module`呼び出し箇所は、インポートを制限します。

## <a name="importing-a-snap-in-powershell-10"></a>スナップイン (PowerShell 1.0) をインポートします。

モジュールが PowerShell 1.0 ではありませんでした。 代わりに、登録、スナップインを使用する必要がありました。ただし、これは使用しないでこの時点では、このテクノロジを使用するモジュールは、通常のインストールおよびインポートする方が簡単に。 詳細については、次を参照してください。 [、Windows PowerShell スナップインを作成する方法](../cmdlet/how-to-create-a-windows-powershell-snap-in.md)します。

## <a name="importing-a-module-with-import-module-powershell-20"></a>モジュールのインポート (PowerShell 2.0) を持つモジュールをインポートします。

PowerShell 2.0 では、適切に名前付き[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット モジュールをインポートします。 このコマンドレットを実行しているときに Windows PowerShell がで指定したディレクトリ内の指定したモジュールの検索、`PSModulePath`変数。 Windows PowerShell が次の順序でファイルを検索し、指定されたディレクトリが見つかった場合: モジュールのマニフェスト ファイル (.psd1)、スクリプト モジュール ファイル (.psm1)、バイナリ モジュール ファイル (.dll)。 検索するディレクトリを追加する方法の詳細については、次を参照してください。 [PSModulePath インストール パスを変更する](./modifying-the-psmodulepath-installation-path.md)します。 次のコードでは、モジュールをインポートする方法について説明します。

```powershell
Import-Module myModule
```

MyModule に存在していたことと仮定すると、 `PSModulePath`PowerShell を使用して、myModule をアクティブなメモリに読み込むとします。 MyModule が上に存在しない場合、`PSModulePath`パスも明示的に指示するには PowerShell がどこに。

```powershell
Import-Module -Name C:\myRandomDirectory\myModule -Verbose
```

使用することも、モジュールからエクスポートされる内容と、アクティブなメモリにインポートされる内容を識別するためには、verbose パラメーター。 エクスポートとインポートの両方を制限するユーザーに公開される情報: 違いは、可視性を制御します。 基本的には、エクスポートは、モジュール内のコードによって制御されます。 これに対し、インポートは、によって制御されます、`Import-Module`呼び出します。 詳細については、次を参照してください。**を制限するメンバーがインポートされたこと**、後述します。

## <a name="implicitly-importing-a-module-powershell-30"></a>モジュール (PowerShell 3.0) を暗黙的にインポートします。

Windows PowerShell 3.0 以降では、モジュールは自動的にインポート コマンドレットまたは関数、モジュールでは、コマンドで使用される場合。 この機能は、値に含まれるディレクトリのモジュールに対して、 **PSModulePath**環境変数。 保存しないモジュールの有効なパスでただし場合、読み込むことができます、明示的なを使用して[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)上記で説明したオプション。

次のアクションのトリガーとも呼ばれます「モジュールの自動読み込みします」、モジュールの自動インポート

- コマンドでは、コマンドレットを使用します。 たとえば、入力`Get-ExecutionPolicy`を含む Microsoft.PowerShell.Security モジュールをインポート、`Get-ExecutionPolicy`コマンドレット。

- 使用して、 [Get-command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)コマンドを取得するコマンドレットです。  たとえば、入力`Get-Command Get-JobTrigger`インポート、 **PSScheduledJob**モジュールを含む、`Get-JobTrigger`コマンドレット。 A`Get-Command`ワイルドカード文字を含むコマンドの検出と見なされます、モジュールのインポートはトリガーされません。

- 使用して、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットのヘルプを取得するコマンドレットです。 たとえば、入力`Get-Help Get-WinEvent`を含む Microsoft.PowerShell.Diagnostics モジュールをインポート、`Get-WinEvent`コマンドレット。

モジュールの自動インポートをサポートするために、`Get-Command`モジュールは、セッションにインポートされていない場合でもすべてのコマンドレットと、インストールされているすべてのモジュールで関数をコマンドレットが取得されます。 詳細については、のヘルプ トピックを参照してください、 [Get-command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)コマンドレット。

## <a name="the-importing-process"></a>インポート プロセス

モジュールの新しいセッション状態が作成されたモジュールがインポートされるときに、 [System.Management.Automation.PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo)メモリ内オブジェクトを作成します。 セッション状態がインポートされている各モジュールの作成 (ルート モジュールと入れ子になったモジュールを含む)。 任意の入れ子になったモジュールによって、ルート モジュールにエクスポートされたすべてのメンバーを含む、ルート モジュールからエクスポートされるメンバーは、呼び出し元のセッション状態にインポートされます。

モジュールからエクスポートされたメンバーのメタデータでは、ModuleName プロパティがあります。 このプロパティには、それらをエクスポートするモジュールの名が設定されます。

> [!WARNING]
> 場合は、エクスポートされたメンバーの名前は、承認されていない動詞を使用して、または警告が表示されているメンバーの名前は文字の制限を使用する場合と、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットを実行します。

既定で、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットは、パイプラインにオブジェクトを返しません。 ただし、このコマンドレットをサポートしています、`PassThru`を返すために使用するパラメーター、 [System.Management.Automation.PSModuleInfo](/dotnet/api/System.Management.Automation.PSModuleInfo)にインポートされている各モジュールのオブジェクト。 ホストに出力を送信するユーザーを実行する必要があります、 [Write-host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host)コマンドレット。

## <a name="restricting--the-members-that-are-imported"></a>インポートされたメンバーを制限します。

使用してモジュールをインポートするときに、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット、既定メンバーが、セッションにインポートされたすべてのエクスポート時のモジュールで任意のコマンドを含むエクスポート、入れ子になったモジュールがモジュールにします。 既定では、変数およびエイリアスはエクスポートされません。 エクスポートされるメンバーを制限するには、[モジュール マニフェスト](./how-to-write-a-powershell-module-manifest.md)します。 インポートされているメンバーを制限するには、次のパラメーターを使用して、`Import-Module`コマンドレット。

- `Function`:このパラメーターは、エクスポートされる関数を制限します。 (モジュール マニフェストを使用している場合は、参照 FunctionsToExport キー)。

- `Cmdlet`:このパラメーターに制限されます (使用する場合、モジュール マニフェストを参照してください、CmdletsToExport キー。) にエクスポートされるコマンドレット

- `Variable`:このパラメーターに制限されます (使用する場合、モジュール マニフェストを参照してください、VariablesToExport キー。) にエクスポートされる変数

- `Alias`:このパラメーター (使用する場合、モジュール マニフェストを参照してください、AliasesToExport キー。) にエクスポートされるエイリアスを制限します。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの記述](./writing-a-windows-powershell-module.md)
