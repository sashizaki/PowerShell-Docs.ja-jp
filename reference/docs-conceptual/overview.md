---
ms.date: 08/27/2018
keywords: powershell,コマンドレット
title: PowerShell スクリプト
ms.openlocfilehash: 281f2e798b3d3fa1c150b079d633cb7e8490dcec
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "62058490"
---
# <a name="powershell"></a>PowerShell

PowerShell は、.NET 上に構築されたタスクベースのコマンド ライン シェルおよびスクリプト言語です。
PowerShell は、システム管理者およびパワー ユーザーが、オペレーティング システム (Linux、macOS、および Windows) とプロセスを管理するタスクを迅速に自動化するのに役立ちます。

PowerShell コマンドを使用すると、コマンド ラインからコンピューターを管理できます。 PowerShell プロバイダーを使用すると、レジストリや証明書ストアなどのデータ ストアに、ファイル システムにアクセスする場合と同じくらい簡単にアクセスできます。 PowerShell には、豊富な式パーサーと、完全に開発されたスクリプト言語があります。

## <a name="powershell-is-open-source"></a>オープン ソースの PowerShell

PowerShell ベースのソース コードは現在、GitHub で入手可能であり、コミュニティ投稿が可能です。
[GitHub の PowerShell のソース](https://github.com/powershell/powershell)を参照してください。

「[PowerShell を入手](https://github.com/PowerShell/PowerShell#get-powershell)」で必要なものから開始できます。
または、「[はじめに](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell)」からクイック ツアーを開始します。

## <a name="powershell-design-goals"></a>PowerShell の設計目標

PowerShell は、従来からの問題を排除し、新しい機能を追加することにより、コマンド ラインおよびスクリプト環境を改善することを目的として設計されています。

### <a name="discoverability"></a>Discoverability (探索可能性)

PowerShell では、簡単にその機能を見つけられます。 たとえば、Windows サービスを表示したり変更したりするコマンドレットの一覧を検索するには、次のように入力します。

```powershell
Get-Command *-Service
```

タスクを実行するコマンドレットが見つかったら、`Get-Help` コマンドレットを使用して、コマンドレットの詳細を確認することができます。 たとえば、`Get-Service` コマンドレットのヘルプを表示するには、次のように入力します。

```powershell
Get-Help Get-Service
```

ほとんどのコマンドレットでは、操作が加えられて表示用のテキストとしてレンダリングできるオブジェクトが返されます。 コマンドレットの出力を完全に理解するには、`Get-Member` コマンドレットにその出力をパイプ処理します。 たとえば、次のコマンドは、`Get-Service` コマンドレットによって出力されるオブジェクトのメンバーについての情報を表示します。

```powershell
Get-Service | Get-Member
```

### <a name="consistency"></a>一貫性

システム管理は複雑な作業になる場合があります。 一貫性のあるインターフェースを備えたツールを使用することで、システム管理に特有の複雑な作業を制御しやすくなります。 残念ながら、コマンド ライン ツールもスクリプト可能なコンポーネント オブジェクト モデル (COM) オブジェクトも一貫性に優れてはいません。

PowerShell の持つ一貫性は、その主要な利点の 1 つです。 たとえば、`Sort-Object` コマンドレットの使用法を習得すると、その知識を利用してあらゆるコマンドレットの出力を並べ替えることができます。 コマンドレットごとに異なる並べ替えルーチンを習得する必要はありません。

さらに、コマンドレットの開発者は、コマンドレットの並べ替え機能を設計する必要はありません。 PowerShell では、一貫性を適用する基本的な機能を、フレームワークに対して提供しています。 フレームワークを使用すると、開発者に委ねられている一部の選択肢は利用できなくなります。 ただし、その見返りとして、コマンドレットの開発はずっと簡単になります。

### <a name="interactive-and-scripting-environments"></a>対話型環境とスクリプト環境

Windows コマンド プロンプトは、コマンドライン ツールと基本的なスクリプトへのアクセスを備えた対話型シェルを提供しています。 Windows Script Host (WSH) は、スクリプトを作成できるコマンドライン ツールと COM 自動化オブジェクトを備えていますが、対話型シェルは提供していません。

PowerShell では、対話型シェルとスクリプト環境を組み合わせています。 PowerShell では、コマンド ライン ツール、COM オブジェクト、および .NET クラス ライブラリにアクセスできます。 この機能の組み合わせによって、対話型ユーザー、スクリプトの作成者、およびシステム管理者が利用できる機能が拡張されます。

### <a name="object-orientation"></a>オブジェクト指向

PowerShell は、テキストではなくオブジェクトに基づいています。 コマンドの出力は、オブジェクトです。 出力されたオブジェクトは、パイプライン経由で、別のコマンドに入力として送信できます。

このパイプラインは、他のシェルの使用経験があるユーザーにとって使い慣れたインターフェイスを提供しています。 PowerShell では、テキストではなくオブジェクトを送信することによって、この概念を拡張します。

### <a name="easy-transition-to-scripting"></a>スクリプトへの移行が容易

PowerShell のコマンドは見つけやすいので、対話的なコマンドの入力からスクリプトの作成および実行へと、簡単に移行できます。 PowerShell のトランスクリプトと履歴を利用して、コマンドをファイルにコピーして、簡単にスクリプトとして使用できます。
