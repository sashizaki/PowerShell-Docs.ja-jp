---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell モジュールを理解する
description: Windows PowerShell モジュールを理解する
ms.openlocfilehash: 882e9db59dc1bc8570676d1da7ce84c808d076e8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651147"
---
# <a name="understanding-a-windows-powershell-module"></a>Windows PowerShell モジュールを理解する

*モジュール* は、関連する Windows PowerShell の機能のセットであり、便利な単位としてグループ化されています (通常は1つのディレクトリに保存されます)。 関連するスクリプトファイル、アセンブリ、関連リソースのセットをモジュールとして定義することで、コードの参照、読み込み、永続化、および共有を、それ以外の場合よりもはるかに簡単に行うことができます。

モジュールの主な目的は、Windows PowerShell コードのモジュール化 (ie、再利用、および抽象化) を可能にすることです。 たとえば、モジュールを作成する最も基本的な方法は、単純に Windows PowerShell スクリプトを hbase-runner.psm1 ファイルとして保存することです。 これにより、スクリプトに含まれる関数と変数を制御 (ie、public または private) することができます。 スクリプトを hbase-runner.psm1 ファイルとして保存すると、特定の変数のスコープを制御することもできます。 最後に、 [インストールモジュール](/powershell/module/PowershellGet/Install-Module) などのコマンドレットを使用して、大規模なソリューションのための構成要素としてスクリプトを整理、インストール、および使用することもできます。

## <a name="module-components-and-types"></a>モジュールのコンポーネントと型

モジュールは、次の4つの基本コンポーネントで構成されています。

1. 何らかの種類のコードファイル-通常は、PowerShell スクリプトまたはマネージコマンドレットアセンブリです。

2. 他のアセンブリ、ヘルプファイル、スクリプトなど、上記のコードファイルで必要になる可能性のあるもの。

3. 上記のファイルについて説明し、作成者やバージョン管理情報などのメタデータを格納するマニフェストファイル。

4. 上記のすべてのコンテンツが格納され、PowerShell が十分に検出できる場所に配置されているディレクトリ。

   これらのコンポーネント自体は、実際には必要ないことに注意してください。 たとえば、モジュールは技術的には hbase-runner.psm1 ファイルに格納されているスクリプトに限定できます。 また、モジュールを使用することもできます。マニフェストファイルは、主に組織の目的で使用されます。 モジュールを動的に作成するスクリプトを記述することもできます。そのため、には何も格納するディレクトリは必要ありません。 以下のセクションでは、モジュールのさまざまな部分を組み合わせて使用できるモジュールの種類について説明します。

### <a name="script-modules"></a>スクリプト モジュール

名前が示すように、 *スクリプトモジュール* は、有効な Windows PowerShell コードを含むファイル (hbase-runner.psm1) です。 スクリプト開発者および管理者は、この種類のモジュールを使用して、関数、変数などを含むメンバーを持つモジュールを作成できます。 現時点では、スクリプトモジュールは、別の拡張機能を備えた Windows PowerShell スクリプトです。管理者は、これを使用して、インポート、エクスポート、および管理の機能を使用できます。

さらに、マニフェストファイルを使用して、データファイル、その他の依存モジュール、ランタイムスクリプトなどの他のリソースをモジュールに含めることができます。 マニフェストファイルは、オーサリングやバージョン管理情報などのメタデータの追跡にも役立ちます。

最後に、動的に作成されていない他のモジュールと同様に、スクリプトモジュールを PowerShell が十分に検出できるフォルダーに保存する必要があります。 通常、これは PowerShell モジュールのパスにあります。ただし、必要に応じて、モジュールがインストールされている場所を明示的に記述できます。 詳細については、「 [PowerShell スクリプトモジュールを記述する方法](./how-to-write-a-powershell-script-module.md)」を参照してください。

### <a name="binary-modules"></a>バイナリモジュール

*バイナリモジュール* は、C# などのコンパイル済みコードを含む .NET Framework アセンブリ (.dll) です。 コマンドレットの開発者は、この種類のモジュールを使用して、コマンドレットやプロバイダーなどを共有できます。 (既存のスナップインは、バイナリモジュールとしても使用できます)。バイナリモジュールを使用すると、スクリプトモジュールと比較して、より高速なコマンドレットを作成したり、Windows PowerShell スクリプトのコードを簡単にすることができない機能 (マルチスレッドなど) を使用したりすることができます。

スクリプトモジュールと同様に、マニフェストファイルをインクルードして、モジュールで使用される追加のリソースを記述したり、モジュールに関するメタデータを追跡したりすることができます。 同様に、バイナリモジュールを PowerShell モジュールパスのどこかのフォルダーにインストールすることをお勧めします。 詳細については、「 [PowerShell バイナリモジュールを記述する](./how-to-write-a-powershell-binary-module.md)方法」を参照してください。

### <a name="manifest-modules"></a>マニフェストモジュール

*マニフェストモジュール* は、マニフェストファイルを使用してすべてのコンポーネントを記述するモジュールですが、どのような種類のコアアセンブリまたはスクリプトも含まれていません。 (正式には、マニフェストモジュールは `ModuleToProcess` マニフェストの要素または要素を空のままに `RootModule` します)。ただし、依存アセンブリを読み込んだり、特定の処理前のスクリプトを自動的に実行する機能など、モジュールの他の機能を使用することもできます。 また、入れ子になったモジュール、アセンブリ、型、形式など、他のモジュールが使用するリソースをパッケージ化するための便利な方法として、マニフェストモジュールを使用することもできます。 詳細については、「 [PowerShell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。

### <a name="dynamic-modules"></a>動的モジュール

*動的モジュール* は、ファイルから読み込まれたり、ファイルに保存されたりしないモジュールです。 代わりに、 [新しいモジュール](/powershell/module/Microsoft.PowerShell.Core/New-Module) のコマンドレットを使用して、スクリプトによって動的に作成されます。 この種類のモジュールを使用すると、スクリプトで必要に応じてモジュールを作成し、永続ストレージに読み込んだり保存したりする必要がなくなります。 動的モジュールは、その性質上、有効期間が短いため、コマンドレットからアクセスすることはできません `Get-Module` 。 同様に、通常、モジュールマニフェストは必要ありません。また、関連するアセンブリを格納するために永続的なフォルダーが必要になることもありません。

## <a name="module-manifests"></a>モジュール マニフェスト

*モジュールマニフェスト* は、ハッシュテーブルを含む .psd1 ファイルです。 ハッシュテーブル内のキーと値は、次の処理を実行します。

- モジュールの内容と属性について説明します。

- 前提条件を定義します。

- コンポーネントの処理方法を決定します。

  マニフェストは、モジュールに必須ではありません。 モジュールは、スクリプトファイル (ps1)、スクリプトモジュールファイル (hbase-runner.psm1)、マニフェストファイル (.psd1)、書式設定と型ファイル (types.ps1xml)、コマンドレットとプロバイダーアセンブリ (.dll)、リソースファイル、ヘルプファイル、ローカリゼーションファイル、またはモジュールの一部としてバンドルされているその他の種類のファイルまたはリソースを参照できます。 国際化されたスクリプトの場合、モジュールフォルダーには、一連のメッセージカタログファイルも含まれます。 マニフェストファイルをモジュールフォルダーに追加する場合は、マニフェストを参照することによって、複数のファイルを1つの単位として参照できます。

  マニフェスト自体には、次のカテゴリの情報が記述されています。

- モジュールのバージョン番号、作成者、説明など、モジュールに関するメタデータ。

- Windows PowerShell のバージョン、共通言語ランタイム (CLR) のバージョン、必要なモジュールなど、モジュールをインポートするために必要な前提条件。

- 処理するディレクティブ (スクリプト、形式、型など)。

- エクスポートするエイリアス、関数、変数、コマンドレットなど、エクスポートするモジュールのメンバーに関する制限。

  詳細については、「 [PowerShell モジュールマニフェストを記述する方法](./how-to-write-a-powershell-module-manifest.md)」を参照してください。

## <a name="storing-and-installing-a-module"></a>モジュールの格納とインストール

スクリプト、バイナリ、またはマニフェストモジュールを作成したら、他のユーザーがアクセスできる場所に作業内容を保存できます。 たとえば、モジュールは、Windows PowerShell がインストールされているシステムフォルダーに格納することも、ユーザーフォルダーに格納することもできます。

一般に、変数に格納されているパスのいずれかを使用して、モジュールのインストール先を決定でき `$ENV:PSModulePath` ます。 これらのパスのいずれかを使用すると、ユーザーがコード内でモジュールを呼び出したときに、PowerShell が自動的にモジュールを検出して読み込むことができます。 モジュールを他の場所に格納する場合は、を呼び出すときに、モジュールの場所をパラメーターとして渡すことによって、PowerShell を明示的に認識でき `Install-Module` ます。

に関係なく、フォルダーのパスはモジュールの *ベース* (modulebase) と呼ばれ、スクリプト、バイナリ、またはマニフェストのモジュールファイルの名前はモジュールのフォルダー名と同じである必要があります。ただし、次の例外があります。

- コマンドレットによって作成される動的モジュールには、 `New-Module` コマンドレットのパラメーターを使用して名前を付けることができ `Name` ます。

- **`Import-Module` -Assembly** コマンドによってアセンブリオブジェクトからインポートされたモジュールには、という構文に従って名前が付けられます `"dynamic_code_module_" + assembly.GetName()` 。

  詳細については、「 [PowerShell モジュールのインストール](./installing-a-powershell-module.md) 」および「 [PSModulePath インストールパスの変更](./modifying-the-psmodulepath-installation-path.md)」を参照してください。

## <a name="module-cmdlets-and-variables"></a>モジュールのコマンドレットと変数

次のコマンドレットと変数は、モジュールの作成と管理のために Windows PowerShell によって提供されます。

[New-module](/powershell/module/Microsoft.PowerShell.Core/New-Module) コマンドレットこのコマンドレットは、メモリ内にのみ存在する新しい動的モジュールを作成します。 モジュールはスクリプトブロックから作成され、その関数や変数などのエクスポートされたメンバーは、セッションですぐに使用できるようになり、セッションが閉じられるまで使用可能な状態のままになります。

[New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest) コマンドレットは、新しいモジュールマニフェスト (.psd1) ファイルを作成し、その値を設定して、マニフェストファイルを指定されたパスに保存します。 このコマンドレットを使用して、手動で入力できるモジュールマニフェストテンプレートを作成することもできます。

[モジュールのインポート:](/powershell/module/Microsoft.PowerShell.Core/Import-Module) このコマンドレットは、現在のセッションに1つ以上のモジュールを追加します。

[Get モジュール](/powershell/module/Microsoft.PowerShell.Core/Get-Module) コマンドレットこのコマンドレットは、現在のセッションにインポートできるまたはインポート可能なモジュールに関する情報を取得します。

[Export-modulemember](/powershell/module/Microsoft.PowerShell.Core/Export-ModuleMember) コマンドレットこのコマンドレットは、スクリプトモジュール (hbase-runner.psm1) ファイルまたはコマンドレットを使用して作成された動的モジュールからエクスポートされるモジュールメンバー (コマンドレット、関数、変数、エイリアスなど) を指定し `New-Module` ます。

[モジュールの削除](/powershell/module/Microsoft.PowerShell.Core/Remove-Module) コマンドレットは、現在のセッションからモジュールを削除します。

[New-modulemanifest](/powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest) コマンドレットこのコマンドレットは、モジュールマニフェストファイル (.psd1) に示されているファイルが、指定されたパスに実際に存在することを確認することによって、モジュールのコンポーネントを正確に記述していることを検証します。

$PSScriptRoot この変数には、スクリプトモジュールの実行元のディレクトリが含まれています。 これにより、スクリプトでモジュールパスを使用して他のリソースにアクセスできるようになります。

$env:P SModulePath この環境変数には、Windows PowerShell モジュールが格納されているディレクトリの一覧が含まれています。 Windows PowerShell は、モジュールを自動的にインポートし、モジュールのヘルプトピックを更新するときに、この変数の値を使用します。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールを記述する](./writing-a-windows-powershell-module.md)
