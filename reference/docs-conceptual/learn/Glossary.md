---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: Windows PowerShell 用語集
ms.openlocfilehash: 1e2285bb49ed6a30fb5624ab3cf136cbf06401b5
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809198"
---
# <a name="windows-powershell-glossary"></a>Windows PowerShell 用語集

|期間|定義|
|--------|--------------|
|バイナリ モジュール|ルート モジュールがバイナリ モジュール ファイル (.dll) である Windows PowerShell モジュール。 バイナリ モジュールにはモジュール マニフェストが含まれる場合と、含まれない場合があります。|
|共有パラメーター|Windows PowerShell エンジンによってすべてのコマンドレット、高度な関数、およびワークフローに追加されるパラメーター。|
|ドット ソース|Windows PowerShell では、コマンドの前にドットとスペースを入力することによってコマンドを開始すること。 ドット ソースのコマンドは、新しいスコープではなく、現在のスコープで実行されます。 コマンドが作成するすべての変数、エイリアス、関数、またはドライブは、現在のスコープで作成され、コマンドが完了すると使用できるようになります。|
|動的モジュール|メモリ内にのみ存在するモジュール。 New-Module コマンドレットと Import-PSSession コマンドレットは動的モジュールを作成します。|
|動的パラメーター|Windows PowerShell コマンドレット、関数、または特定の条件下のスクリプトに追加されるパラメーター。 コマンドレット、関数、プロバイダー、およびスクリプトは動的パラメーターを追加できます。|
|書式設定ファイル|拡張子が .format.ps1xml で、Windows PowerShell がどのように .NET Framework 型に基づいてオブジェクオを表示するかを定義する Windows PowerShell XML ファイル。|
|グローバル セッション状態|Windows PowerShell セッションのユーザーがアクセスできるデータを含むセッション状態。|
|host|Windows PowerShell エンジンがユーザーとの通信に使用するインターフェイス。 たとえば、ホストは Windows PowerShell とユーザー間でプロンプトが処理される方法を指定します。|
|ホスト アプリケーション|Windows PowerShell エンジンをそのプロセスに読み込み、操作を実行するのに使用するプログラム。|
|入力処理メソッド|コマンドが入力として受信するレコードを処理するのに使用できるメソッド。 入力処理メソッドには、BeginProcessing メソッド、ProcessRecord メソッド、EndProcessing メソッド、および StopProcessing メソッドが含まれます。|
|マニフェスト モジュール|マニフェストがあり、RootModule キーが空の Windows PowerShell モジュール。|
|モジュール マニフェスト|モジュールのコンテンツを説明し、モジュールが処理される方法を制御する Windows PowerShell データ ファイル (.psd1)。|
|モジュール セッション状態|Windows PowerShell モジュールのパブリック データとプライベート データを含むセッション状態。 このセッション状態のプライベート データは、Windows PowerShell セッションのユーザーは使用できません。|
|終了しないエラー|Windows PowerShell でのコマンドの処理の継続が停止しないエラー。|
|名詞|Windows PowerShell コマンドレット名でハイフンの後に続く単語。 名詞は、コマンドレットの処理対象のリソースを説明します。|
|パラメーター セット|特定のアクションを実行するために同じコマンドで使用できるパラメーターのグループ。|
|パイプ|Windows PowerShell で、前のコマンドの結果を、入力としてパイプラインの次のコマンドに送信するためのもの。|
|pipeline|パイプライン演算子 (&#124;) (ASCII 124) によって接続された一連のコマンド。 各パイプライン演算子は、前のコマンドの結果を入力として次のコマンドに送信します。|
|PSSession|ユーザーによって作成され、管理され、閉じられる Windows PowerShell セッションの一種。|
|ルート モジュール|モジュール マニフェスト内の RootModule キーで指定されたモジュール。|
|実行空間|Windows PowerShell で、パイプラン内の各コマンドが実行される操作環境。|
|スクリプト ブロック|Windows PowerShell プログラミング言語で、1 つの単位として使用できるステートメントまたは表現のコレクション。 スクリプト ブロックは引数を受け取り、値を返すことができます。|
|スクリプト モジュール|ルート モジュールがスクリプト モジュール ファイル (.psm1) である Windows PowerShell モジュール。 スクリプト モジュールにはモジュール マニフェストが含まれる場合と、含まれない場合があります。|
|スクリプト モジュール ファイル|Windows PowerShell スクリプトを含むファイル。 スクリプトは、スクリプト モジュールがエクスポートするメンバーを定義します。 スクリプト モジュール ファイルのファイル名拡張子は .psm1 です。|
|シェル|コマンドをオペレーティング システムに渡すのに使用されるコマンド インタープリター。|
|スイッチ パラメーター|引数を受け取らないパラメーター。|
|終了エラー|Windows PowerShell でのコマンドの処理を停止するエラー。|
|transaction|作業のアトミック単位。 トランザクションでの作業は全体として完了する必要があります。トランザクションの一部が失敗すると、トランザクション全体が失敗します。|
|型ファイル|拡張子が .ps1xml で、Microsoft .NET Framework 型のプロパティを Windows PowerShell で拡張する Windows PowerShell XML ファイル。|
|Verb|Windows PowerShell コマンドレット名でハイフンの前に使用される単語。 動詞はコマンドレットが実行するアクションを説明します。|
|Windows PowerShell|IT 管理者に包括的な制御とシステム管理タスクの自動化を提供するコマンド ライン シェルとタスク ベースのスクリプト技術。|
|Windows PowerShell コマンド|アクションを実行させるパイプライン内の要素。Windows PowerShell コマンドは、キーボードで入力されるか、プログラムで呼び出されます。|
|Windows PowerShell データ ファイル|.psd1 ファイル名拡張子を持つテキスト ファイル。 Windows PowerShell では、モジュール マニフェスト データの格納や、スクリプトの国際化のための翻訳された文字列の格納など、さまざまな目的でデータ ファイルを使用します。|
|Windows PowerShell ドライブ|データ ストアに直接アクセスできる仮想ドライブ。 Windows PowerShell プロバイダーによって定義されるか、コマンド ラインで作成されます。 コマンド ラインで作成されたドライブは、セッション固有のドライブであり、セッションが閉じられたときに失われます。|
|Windows PowerShell Integrated Scripting Environment (ISE)|Windows PowerShell ホスト アプリケーション。分かりやすくて、構文がカラーで表記された、ユニコード準拠の環境で、コマンドを実行し、スクリプトを書き、テストし、デバッグすることができます。|
|Windows PowerShell モジュール|Windows PowerShell コードをパーティション分割、整理、抽象化するための再利用可能な自己完結型の単位。 モジュールには、1 つの単位としてインポートできるコマンドレット、プロバイダー、関数、変数、その他の種類のリソースを含めることができます。|
|Windows PowerShell プロバイダー|特化されたデータ ストアのデータを Windows PowerShell で利用できるようにし、そのデータを表示および管理できるようにするための Microsoft .NET Framework ベースのプログラム。|
|Windows PowerShell スクリプト|Windows PowerShell 言語で記述されたスクリプト。|
|Windows PowerShell スクリプト ファイル|.ps1 拡張子を持ち、Windows PowerShell 言語で記述されたスクリプトを含むファイル。|
|Windows PowerShell スナップイン|Windows PowerShell 環境に追加できるコマンドレット、プロバイダー、および Microsoft .NET Framework の型のセットを定義するリソース。|
|Windows PowerShell ワークフロー|A workflow is a sequence of programmed, connected steps that perform long-running tasks or require the coordination of multiple steps across multiple devices or managed nodes. Windows PowerShell ワークフローを使用することで、IT 担当者や開発者は、マルチデバイス管理アクティビティのシーケンス (ワークフロー内の 1 つのタスク) をワークフローとして作成できます。 Windows PowerShell ワークフローを使用すると、Windows PowerShell スクリプトと XAML ファイルの両方をワークフローとして適応し実行できます。|
