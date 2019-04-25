---
title: Windows PowerShell リファレンス |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows PowerShell SDK
ms.assetid: cbba4879-bcac-484a-9906-4bbe2cd1eb33
caps.latest.revision: 11
ms.openlocfilehash: 86595ebaac32318a4e3b9a3c4b295c73fb2e1c75
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080500"
---
# <a name="windows-powershell-reference"></a>Windows PowerShell リファレンス

Windows PowerShell は、管理の自動化用に設計された Microsoft .NET Framework に接続されている環境です。 Windows PowerShell コマンドを構築、ソリューションを作成およびグラフィカル ユーザー インターフェイス ベースの管理ツールを作成するための新しいアプローチを提供します。

Windows PowerShell では、コマンドの実行によってシステム リソースの管理を自動化するシステム管理者を使用できます。 直接またはスクリプトを使用します。

## <a name="developer-audience"></a>対象となる開発者

Windows PowerShell ソフトウェア開発キット (SDK) は、Windows PowerShell で提供される Api に関するリファレンス情報を必要とするコマンドの開発者向けに書き込まれます。 Command の開発者では、Windows PowerShell を使用して、コマンドと Windows PowerShell で実行できるタスクの拡張プロバイダーの両方を作成します。

## <a name="windows-powershell-resources"></a>Windows PowerShell のリソース

だけでなく、Windows PowerShell SDK は、次のリソースは、詳細を提供します。

[Windows PowerShell ファースト](/powershell/scripting/getting-started/getting-started-with-windows-powershell)Windows PowerShell の概要を提供します: 言語、コマンドレット、プロバイダー、およびオブジェクトを使用します。

[Windows PowerShell モジュールの記述](./module/writing-a-windows-powershell-module.md)管理者、スクリプトの開発者、およびパッケージ化し、Windows PowerShell モジュールを使用して、Windows PowerShell のソリューションを配布する必要があるコマンドレットの開発者情報と例を提供します。

[Windows PowerShell コマンドレットの記述](./cmdlet/writing-a-windows-powershell-cmdlet.md)コマンドレットを設計する場合に、プログラム マネージャーおよびコマンドレットのコードを実装している開発者向け情報とコード例を提供します。

[Windows PowerShell チームのブログ](https://blogs.msdn.microsoft.com/PowerShell/)から学んだり、他の Windows PowerShell ユーザーと共同作業を行うに最適なリソースです。 Windows PowerShell チームのブログを読むし、Windows PowerShell ユーザー フォーラム (microsoft.public.windows.powershell) に参加します。 Windows Live Search を使用すると、その他の Windows PowerShell のブログとリソースを検索できます。 次に、専門知識を開発するときは自由に、アイデアを提供します。

[PowerShell モジュール ブラウザー](/powershell/module/)コマンド ライン ヘルプ トピックの最新バージョンを提供します。

## <a name="class-libraries"></a>クラス ライブラリ

[System.Management.Automation](/dotnet/api/System.Management.Automation)この名前空間は Windows PowerShell のルート名前空間。 クラス、列挙型、およびカスタム コマンドレットを実装するために必要なインターフェイスが含まれています。 具体的には、 [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)クラスは、基本クラスするすべてのコマンドレットからクラスを派生する必要があります。 コマンドレットの詳細についてを参照してください。

[System.Management.Automation.Provider](/dotnet/api/System.Management.Automation.Provider)この名前空間には、クラス、列挙型、および Windows PowerShell プロバイダーを実装するために必要なインターフェイスが含まれています。 具体的には、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)クラスは、基本クラスをすべての Windows PowerShell からプロバイダー クラスを派生する必要があります。

[Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands)コマンドレットと Windows PowerShell によって実装されるプロバイダーのクラスがこの名前空間に含まれています。 同様に、お勧めを作成すること、 *YourName*します。実装するこれらのコマンドレットの名前空間のコマンドです。

[System.Management.Automation.Host](/dotnet/api/System.Management.Automation.Host)この名前空間には、クラス、列挙型、およびコマンドレットを使用して、ユーザーと Windows PowerShell の間の相互作用を定義するインターフェイスが含まれています。

[System.Management.Automation.Internal](/dotnet/api/System.Management.Automation.Internal)この名前空間には、その他の名前空間のクラスによって使用される基本クラスが含まれています。 たとえば、 [System.Management.Automation.Internal.Cmdletmetadataattribute](/dotnet/api/System.Management.Automation.Internal.CmdletMetadataAttribute)クラスの基本クラスは、 [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)クラス。

[System.Management.Automation.Runspaces](/dotnet/api/System.Management.Automation.Runspaces)この名前空間には、クラス、列挙型、および Windows PowerShell 実行空間を作成するために使用するインターフェイスが含まれています。 このコンテキストでは、Windows PowerShell 実行空間を 1 つまたは複数の Windows PowerShell パイプラインがコマンドレットを呼び出すコンテキストです。 つまり、コマンドレットは、Windows PowerShell 実行空間のコンテキスト内で動作します。 詳細については aboutWindows PowerShell 実行空間を参照してください。 [Windows PowerShell 実行空間](http://msdn.microsoft.com/en-us/a1582cfe-f06d-4aff-adc6-71f49a860ce9)します。
