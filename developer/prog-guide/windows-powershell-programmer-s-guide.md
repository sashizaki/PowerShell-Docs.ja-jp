---
title: Windows PowerShell プログラマ&#39;ガイド |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows PowerShell Programmer's Guide
ms.assetid: f3aaf667-af84-4ea8-a5ad-d454d0d700b8
caps.latest.revision: 9
ms.openlocfilehash: 75425fbd38141fc82dd834835912c357ecfa6d2b
ms.sourcegitcommit: 0ca836d1044e46d3a7dcbc69fa93d84f74848559
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920392"
---
# <a name="windows-powershell-programmer39s-guide"></a>Windows PowerShell プログラマ&#39;ガイド

このプログラマー ガイドは、システム管理者のコマンドライン管理環境を提供することに関心がある開発者を対象とします。 Windows PowerShell では、一方で Windows PowerShell のほとんどの作業を実行する、.NET オブジェクトを公開する管理コマンドを構築するための簡単な方法を提供します。

従来の開発では、パラメーターのパーサーをパラメーター バインダー、フィルター、および各コマンドによって公開されるその他のすべての機能を記述する必要は。 Windows PowerShell コマンドを記述しやすくには、次を提供します。

- 強力な Windows PowerShell ランタイムを (実行エンジン)、独自のパーサーと、自動的にコマンドのパラメーターをバインドするためのメカニズムです。

- 書式設定およびコマンド ライン インタープリター (CLI) を使用してコマンドの結果を表示するためのユーティリティです。

- 格納されているデータにアクセスするが簡単にする (Windows PowerShell プロバイダー) を通じて機能の高レベルのサポート。

  ほとんどのコストでは、リッチ コマンドまたは管理者に包括的なコマンド ライン エクスペリエンスを提供するコマンドのセットによって、.NET オブジェクトを表すことができます。

  次のセクションでは、Windows PowerShell の主要な概念と用語について説明します。 これらの概念と開発を開始する前に用語を理解します。

## <a name="about-windows-powershell"></a>Windows PowerShell について

Windows PowerShell は、開発で使用できるコマンドのいくつかの種類を定義します。 これらのコマンドが含まれます: 関数、フィルター、スクリプト、エイリアス、および実行可能ファイル (アプリケーション)。 このガイドで説明するメイン コマンドの種類は、「コマンドレット」と呼ばれる単純な小さなコマンドです。 Windows PowerShell では、一連のコマンドレットを提供し、環境に合わせてコマンドレットのカスタマイズを完全にサポートします。 Windows PowerShell ランタイムは、パイプラインを使用して、コマンドレットと同様に、すべてのコマンドの種類を処理します。

に加えて、コマンドは、Windows PowerShell は、コマンドレットの使用可能な特定のセットを構成するさまざまなカスタマイズ可能な Windows PowerShell プロバイダーをサポートします。 シェルが Windows PowerShell で提供されるホスト アプリケーション (Windows PowerShell.exe) 内で動作するが、特定の要件を満たすために開発できるカスタム ホスト アプリケーションからもアクセスできます。 詳細については、次を参照してください。 [Windows PowerShell のしくみ](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。

### <a name="windows-powershell-cmdlets"></a>Windows PowerShell コマンドレット

コマンドレットは、Windows PowerShell 環境で使用される軽量コマンドです。 Windows PowerShell ランタイムは、コマンドラインで提供されている自動化スクリプトのコンテキスト内でこれらのコマンドレットを呼び出すし、Windows PowerShell ランタイムも呼び出されたプログラムで Windows PowerShell Api を使用します。

コマンドレットの詳細については、次を参照してください。 [Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)します。

### <a name="windows-powershell-providers"></a>Windows PowerShell プロバイダー

管理タスクを実行するには、ユーザーは、データ ストア (ファイル システム、Windows レジストリ、または証明書ストアなど) に格納されているデータを確認する必要があります。 これらの操作を容易にするには、Windows PowerShell は、Windows レジストリなどの特定のデータ ストアへのアクセスに使用できる Windows PowerShell プロバイダーと呼ばれるモジュールを定義します。 各プロバイダーは、データ ストアの対称的なビューを付与するために関連するコマンドレットのセットをサポートします。

Windows PowerShell は、Windows PowerShell プロバイダーにいくつかの既定値を提供します。 たとえば、レジストリ プロバイダーは、ナビゲーション、および Windows レジストリの操作をサポートします。 レジストリ キーは、項目として表され、レジストリ値がプロパティとして扱われます。

」の説明に従って、独自の Windows PowerShell プロバイダーを記述する必要な場合があります、ユーザーにアクセスする必要のあるデータ ストアを公開する場合[Windows PowerShell プロバイダーを作成する](./how-to-create-a-windows-powershell-provider.md)します。 詳細については aboutWindows PowerShell プロバイダーを参照してください。 [Windows PowerShell のしくみ](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。

### <a name="host-application"></a>ホスト アプリケーション

Windows PowerShell には、既定のホスト アプリケーション powershell.exe、ユーザーと対話し、コンソール ウィンドウを使用して、Windows PowerShell ランタイムをホストするコンソール アプリケーションが含まれています。

ほとんどはする必要があります Windows powershell では、ホスト アプリケーションを作成するカスタマイズはサポートされています。 独自のアプリケーションが必要がありますが、1 つのケースは、既定のホスト アプリケーションによって提供されるインターフェイスよりも優れている GUI インターフェイスの要件がある場合です。 コマンドラインで、GUI を基にする場合に、カスタム アプリケーションをすることもできます。 詳細については、次を参照してください。 [Windows PowerShell ホスト アプリケーションを作成する方法](http://msdn.microsoft.com/en-us/d31355c9-a270-4b09-8f0c-35a7392a7d07)します。

### <a name="windows-powershell-runtime"></a>Windows PowerShell ランタイム

Windows PowerShell ランタイムは、コマンドの処理を実装する実行エンジンです。 ホスト アプリケーションと Windows PowerShell コマンドとプロバイダー間のインターフェイスを提供するクラスが含まれています。 Windows PowerShell ランタイムは、シェルは、コマンドが実行される運用環境は、現在の Windows PowerShell セッションの実行空間オブジェクトとして実装されます。 操作の詳細を参照してください。 [Windows PowerShell のしくみ](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。

### <a name="windows-powershell-language"></a>Windows PowerShell 言語

Windows PowerShell 言語では、スクリプトの機能とコマンドを実行するためのメカニズムを提供します。 完全なスクリプトについては、Windows PowerShell で出荷された、Windows PowerShell 言語のリファレンスを参照してください。

### <a name="extended-type-system-ets"></a>拡張型システム (ETS)

Windows PowerShell では、さまざまな .NET などのさまざまなオブジェクト、および XML オブジェクトへのアクセスを提供します。 その結果、オブジェクトの種類の一般的な抽象化を提示する、シェルは、拡張型システム (ETS) を使用します。 ETS の大半の機能は、ユーザーに対して透過的ですが、スクリプトまたは .NET 開発者は次の目的で使用します。

- 特定のオブジェクトのメンバーのサブセットを表示します。 Windows PowerShell では、いくつかの特定のオブジェクトの種類の「対応」のビューを提供します。

- 既存のオブジェクトにメンバーを追加します。

- シリアル化されたオブジェクトにアクセスします。

- 書き込みは、オブジェクトをカスタマイズします。

  ETS を使用して作成できます柔軟な新しい「型」を Windows PowerShell 言語と互換性があります。 .NET 開発者は場合、スクリプトに適用するなど、Windows PowerShell 言語と同じセマンティクスを使用してオブジェクトを使用する、オブジェクトを評価するかどうかを判断することは`true`します。

  ETS と Windows PowerShell がオブジェクトを使用する方法の詳細については、次を参照してください。 [Windows PowerShell オブジェクトの概念](http://msdn.microsoft.com/en-us/12700631-be23-4e6b-9bf0-81ea0d166353)します。

## <a name="programming-for-windows-powershell"></a>Windows PowerShell 用のプログラミング

Windows PowerShell では、コマンド、プロバイダー、および .NET Framework を使用して他のプログラム モジュールのコードを定義します。 限りません Microsoft Visual Studio の使用で Windows powershell では、独自のモジュールを作成するこのツールで実行するこのガイドで提供されているサンプルが知られています。 クラスの継承と、属性の使用をサポートする任意の .NET 言語を使用することができます。 場合によっては、Windows PowerShell の Api は、プログラミング言語のジェネリック型にアクセスできる必要があります。

## <a name="programmers-reference"></a>プログラマー リファレンス

Windows PowerShell 向けの開発時の参照を次を参照してください。、 [Windows PowerShell SDK](../windows-powershell-reference.md)します。

## <a name="getting-started-using-windows-powershell"></a>Windows PowerShell の使用を開始します。

Windows PowerShell シェルを使用して起動する方法の詳細については、次を参照してください。、 [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell) Windows PowerShell に付属します。 クイック リファレンスの三つ折ドキュメントはコマンドレットの使用に関する入門書としても提供されます。

## <a name="contents-of-this-guide"></a>このガイドの内容

|トピック|定義|
|-----------|----------------|
|[Windows PowerShell プロバイダーを作成する方法](./how-to-create-a-windows-powershell-provider.md)|このセクションでは、Windows PowerShell 用 Windows PowerShell プロバイダーを作成する方法について説明します。|
|[Windows PowerShell ホスト アプリケーションを作成する方法](http://msdn.microsoft.com/en-us/d31355c9-a270-4b09-8f0c-35a7392a7d07)|このセクションでは、独自のカスタム ホストを実装するホスト アプリケーションを作成する方法と、実行空間を操作するホスト アプリケーションを作成する方法について説明します。|
|[Windows PowerShell スナップインを作成する方法](../cmdlet/how-to-create-a-windows-powershell-snap-in.md)|このセクションでは、アセンブリ内のすべてのコマンドレットとプロバイダーの登録に使用するスナップインを作成する方法とカスタム スナップインで作成する方法について説明します。|
|[コンソール シェルを作成する方法](./how-to-create-a-console-shell.md)|このセクションでは、コンソールのシェルがなく、拡張を作成する方法について説明します。|
|[Windows PowerShell の概念](./windows-powershell-concepts.md)|このセクションには、開発者の視点から Windows PowerShell を理解するのに役立つ概念情報が含まれています。|

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
