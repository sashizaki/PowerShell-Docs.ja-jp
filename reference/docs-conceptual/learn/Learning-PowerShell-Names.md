---
ms.date: 08/24/2018
keywords: PowerShell, コマンドレット
title: PowerShell コマンド名の学習
ms.assetid: b4d0fd22-8298-4ee6-82ae-9b6f2907c986
ms.openlocfilehash: 8d50ca03f98ed4ca8f9c09c83ae57afbf0d7888d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086427"
---
# <a name="learning-powershell-command-names"></a>PowerShell コマンド名の学習

大半のコマンドライン インターフェイスに共通して言えることは、コマンドやパラメーターの名前を覚えるために多大な時間と労力が必要であるという点です。 問題は、パターン化されているものが少ししかないことです。 定期的に使う必要があるコマンドとパラメーターを覚えるための唯一の方法は、記憶することです。

新しいコマンドやパラメーターを使用する場合は、必ず既に備えている知識を活用できるわけではありません。 新しい名前を検索して調べる必要があります。 従来は、コマンドライン インターフェイスは小規模なツール セットから始まって、そこに増補していくことで拡張されました。 このことから、標準的な構造が存在しない理由は容易にわかります。
各コマンドは別個のツールなので、このことは、コマンド名にとっては理に適っているようです。 PowerShell は、コマンド名を扱いやすい方法を備えています。

## <a name="learning-command-names-in-traditional-shells"></a>従来のシェルのコマンド名を覚える

ほとんどのコマンドは、サービスやプロセスなど、オペレーティング システムまたはアプリケーションの各種要素を管理する目的で作成されています。 コマンド名は、同じ系統のコマンド (コマンド ファミリ) だからといって、必ずしも決まったパターンがあるわけではありません。 たとえば、Windows システムでは、`net start` コマンドと `net stop` コマンドを使用して、サービスを開始したり停止したりできます。 **Sc.exe** は、Windows に対応するもう 1 つのサービス制御ツールです。 その名前は、**net.exe** サービス コマンドの命名パターンには準拠していません。 プロセス管理用のコマンドはどうでしょうか。Windows には、プロセスを一覧表示するための **tasklist.exe** コマンドや、プロセスを強制終了するための **taskkill.exe** コマンドが存在します。

これらのコマンドのパラメーター仕様も不規則です。 `net start` コマンドを使用して、リモート コンピューター上でサービスを開始することはできません。 **sc.exe** コマンドは、リモート コンピューター上でサービスを開始できます。 ただし、リモート コンピューターを指定するには、二重のバックスラッシュを名前の前に付与する必要があります。 DC01 という名前のリモート コンピューター上でスプーラー サービスを開始するには、`sc.exe \\DC01 start spooler` と入力します。
DC01 で実行されているタスクを一覧表示するには、**/S** パラメーターとバックスラッシュを付与していないコンピューター名を使用します。 たとえば、`tasklist /S DC01` のように指定します。

> [!NOTE]
> PowerShell v6 以前では、`sc` は `Set-Content` コマンドレットのエイリアスでした。 そのため、v6 より前のバージョンの PowerShell で **sc.exe** コマンドを実行するには、ファイル名拡張子 **exe** を含んだ完全なファイル名 **sc.exe** を含める必要があります。

サービスとプロセスは、ライフ サイクルが明確に定義されているコンピューター上で管理できる要素の例です。 サービスとプロセスを開始または停止したり、現在実行中のサービスやプロセスすべてを一覧表示したりできます。 サービスとプロセスの間には、技術上は重大な区別がありますが、サービスとプロセスで実行されるアクションは、概念的には同じです。 また、パラメーターを指定して動作をカスタマイズするときの選択肢も、概念的に似ている場合があります。

PowerShell ではこの類似性を活かして、コマンドレットを理解して使用するために知っておく必要がある個々の名前の数を減らしました。

## <a name="cmdlets-use-verb-noun-names-to-reduce-command-memorization"></a>コマンドレットには覚えやすいように "動詞-名詞" 形式の命名規則が使用される

PowerShell では、「動詞-名詞」の命名体系を採用しています。 各コマンドレットの名前は、標準的な動詞を特定の名詞とハイフンでつないで表記されます。 PowerShell の動詞は必ずしも文法上の動詞とは一致しませんが、PowerShell における特定の動作を表しています。 名詞については、ほぼ文法上の名詞と同じと考えてかまいません。 システムを管理するうえで重要な、特定の種類のオブジェクトを表します。 実際、名前を動詞と名詞に分けることにより、格段に覚えやすくなります。そのことは、例をいくつか考えてみればすぐに納得できます。

PowerShell には、推奨される標準的な動詞のセットがあります。 名詞に対する制約は少ないですが、常に動詞のアクションの対象を表します。 PowerShell には、`Get-Process`、`Stop-Process`、`Get-Service`、および `Stop-Service` のようなコマンドがあります。

この名詞と動詞 2 つずつの例では、一貫性のおかげで覚えやすくなるという実感は、それほどありません。 これを動詞と名詞 10 個 ずつの標準化されたセットに拡大します。 この場合、覚える単語は 20 個だけですが、
単語を組み合わせることで、個々のコマンド名として 100 通りが成立します。

名前を読めば、PowerShell コマンドの動作を簡単に理解できます。 コンピューターをシャット ダウンするコマンドは、`Stop-Computer` です。 ネットワーク上にあるすべてのコンピューターを一覧表示するコマンドは、`Get-Computer` です。 システム日付を取得するコマンドは、`Get-Date` です。

`Get-Command` の **Verb** パラメーターを使って、特定の動詞を含むすべてのコマンドを一覧表示できます。 たとえば、`Get` という動詞が使用されているすべてのコマンドレットを表示するには、次のように入力します。

```
PS> Get-Command -Verb Get

CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Get-Acl                         Get-Acl [[-Path] <String[]>]...
Cmdlet          Get-Alias                       Get-Alias [[-Name] <String[]...
Cmdlet          Get-AuthenticodeSignature       Get-AuthenticodeSignature [-...
Cmdlet          Get-ChildItem                   Get-ChildItem [[-Path] <Stri...
...
```

**Noun** パラメーターを使用すると、同じ種類のオブジェクトに影響を及ぼすコマンド ファミリを表示できます。 たとえば、サービスの管理に使用できるコマンドを表示するには、次のコマンドを実行します。

```
PS> Get-Command -Noun Service

CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Get-Service                     Get-Service [[-Name] <String...
Cmdlet          New-Service                     New-Service [-Name] <String>...
Cmdlet          Restart-Service                 Restart-Service [-Name] <Str...
Cmdlet          Resume-Service                  Resume-Service [-Name] <Stri...
Cmdlet          Set-Service                     Set-Service [-Name] <String>...
Cmdlet          Start-Service                   Start-Service [-Name] <Strin...
Cmdlet          Stop-Service                    Stop-Service [-Name] <String...
Cmdlet          Suspend-Service                 Suspend-Service [-Name] <Str...
...
```

## <a name="cmdlets-use-standard-parameters"></a>コマンドレットでは標準的なパラメーターが使用される

前述のように、従来のコマンドライン インターフェイスで使用されるコマンドには、必ずしもパラメーター名に一貫性はありません。 パラメーターは 1 文字または略称で表記されることが多く、簡単に入力できるという利点はありますが、未経験のユーザーには決してわかりすいものではありません。

従来のほとんどのコマンドライン インターフェイスとは異なり、PowerShell では、パラメーターが直接処理されます。また、パラメーターへのこの直接アクセスは、パラメーター名を標準化する開発者向けのガイドラインに準拠して使用されます。 このガイドラインは役立ちますが、すべてのコマンドレットが標準に準拠していることを保証するわけではありません。

また、PowerShell では、パラメーターの区切り記号も標準化しています。 PowerShell コマンドでは、パラメーター名の前には常に '-' が付加されます。 次の例を確認してください。

```powershell
Get-Command -Name Clear-Host
```

パラメーターの名前は **Name** ですが、コマンド ライン上でパラメーターとして使用される場合は、`-Name` と入力されています。

以降、標準的なパラメーター名と使用法について、一般的な特徴をいくつか取り上げます。

### <a name="the-help-parameter-"></a>ヘルプ パラメーター (?)

任意のコマンドレットで `-?` パラメーターを指定すると、PowerShell によりコマンドレットのヘルプが表示されます。
コマンドレットは実行されません。

### <a name="common-parameters"></a>共通パラメーター

PowerShell には、複数の*共通パラメーター*があります。 これらのパラメーターは、PowerShell エンジンによって制御されます。 共通パラメーターは、常に同じように動作します。 共通パラメーターには、**WhatIf**、**Confirm**、**Verbose**、**Debug**、**Warn**、**ErrorAction**、**ErrorVariable**、**OutVariable**、**OutBuffer** などがあります。

### <a name="recommended-parameter-names"></a>推奨されるパラメーター名

PowerShell のコア コマンドレットでは、類似のパラメーターに対して標準名を使用しています。 これらの標準名の使用は強制ではありませんが、標準化を推進するための明確なガイドラインがあります。

たとえば、コンピューターを参照するパラメーターに推奨される名前は、Server、Host、System、Node や、それ以外の共通の別名ではなく、**ComputerName** です。 推奨される他の重要なパラメーター名としては、**Force**、**Exclude**、**Include**、**PassThru**、**Path**、および **CaseSensitive** があります。
