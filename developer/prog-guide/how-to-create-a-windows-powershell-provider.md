---
title: Windows PowerShell プロバイダーを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- providers [PowerShell Programmer's Guide]
- providers [PowerShellProgrammer's Guide], creating
- Windows PowerShell Programmer's Guide, providers
ms.assetid: 863e48e9-7206-4c6a-a59a-2ab2d30396bc
caps.latest.revision: 5
ms.openlocfilehash: 06910f32752668f13400f9be0767a2179133df04
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081752"
---
# <a name="how-to-create-a-windows-powershell-provider"></a>Windows PowerShell プロバイダーを作成する方法

このセクションでは、Windows PowerShell プロバイダーを作成する方法について説明します。 2 つの方法で、Windows PowerShell プロバイダーを見なすことができます。 ユーザーには、プロバイダーは、格納されたデータのセットを表します。 たとえば、格納されているデータには、インターネット インフォメーション サービス (IIS) メタベース、Microsoft Windows レジストリ、Windows ファイル システム、Active Directory、および Windows PowerShell によって格納される変数とエイリアス データができます。

開発者には、Windows PowerShell プロバイダーは、ユーザー データとの間、ユーザーがアクセスする必要があるインターフェイスです。 この観点からは、このセクションで説明されているプロバイダーの種類ごとには、特定の基底クラスと Windows PowerShell ランタイムの一般的な方法でユーザーに特定のコマンドレットを公開できるようにするインターフェイスのセットがサポートしています。

## <a name="providers-provided-by-windows-powershell"></a>Windows PowerShell によって提供されるプロバイダー

Windows PowerShell では、既知のデータ ストアへのアクセスに使用されるいくつかのプロバイダー (FileSystem プロバイダー、レジストリ プロバイダーでは、Alias プロバイダーなど) を提供します。 Windows PowerShell によって提供されるプロバイダーの詳細については、オンライン ヘルプにアクセスして、次のコマンドを使用します。

**PS > get-help about_providers**

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a>Windows PowerShell のパスを使用して、格納されたデータにアクセスします。

Windows PowerShell プロバイダーは、Windows PowerShell パスを使用してプログラムでのコマンドを Windows PowerShell ランタイムにアクセスできます。 ほとんどの場合、これらのパスは、プロバイダーを介してデータに直接アクセスに使用されます。 ただし、いくつかのパスは、データにアクセスする Windows PowerShell 以外のアプリケーション プログラミング インターフェイス (Api) を使用するコマンドレットを許可するプロバイダーの内部のパスに解決できます。 Windows PowerShell 内での Windows PowerShell プロバイダーの動作方法の詳細については、次を参照してください。 [Windows PowerShell のしくみ](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)します。

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a>ドライブの Windows PowerShell を使用して、プロバイダー コマンドレットを公開します。

Windows PowerShell プロバイダーは、仮想の Windows PowerShell ドライブを使用して、サポートされているコマンドレットを公開します。 Windows PowerShell には、Windows PowerShell ドライブに対して次の規則が適用されます。

- ドライブの名前は、任意の英数字のシーケンスを指定できます。

- "Root"と呼ばれる、パス上の任意の有効なポイントでは、ドライブを指定できます。

- ドライブは、ファイル システムだけでなく、格納されているデータを実装できます。

- 各ドライブでは、独自の現在の作業場所ドライブ間で移行するときに、コンテキストを保持するユーザーを許可するが保持されます。

## <a name="in-this-section"></a>このセクションの内容

次の表は、相互に構築するコード例が含まれるトピックを一覧表示します。 以降、2 番目のトピックでは、基本的な Windows PowerShell プロバイダーを初期化し、Windows PowerShell ランタイムによって初期化されていない、次のトピックでは、データにアクセスするための機能を追加します、次のトピックでは、データ (を操作するための機能を追加します。格納されているデータの項目)、これにします。

|トピック|定義|
|-----------|----------------|
|[Windows PowerShell プロバイダーのデザイン](./designing-your-windows-powershell-provider.md)|このトピックでは、Windows PowerShell プロバイダーを実装する前に考慮事項について説明します。 Windows PowerShell プロバイダーの基本クラスと使用されるインターフェイスをまとめたものです。|
|[基本的な Windows PowerShell プロバイダーを作成します。](./creating-a-basic-windows-powershell-provider.md)|このトピックでは、Windows PowerShell プロバイダーにより、プロバイダーを初期化して、Windows PowerShell ランタイムを作成する方法を示します。|
|[Windows PowerShell ドライブ プロバイダーを作成します。](./creating-a-windows-powershell-drive-provider.md)|このトピックでは、Windows PowerShell ドライブをデータ ストアにアクセスするユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。|
|[Windows PowerShell 項目プロバイダーを作成します。](./creating-a-windows-powershell-item-provider.md)|このトピックでは、ユーザーがデータ ストア内のアイテムを操作できる Windows PowerShell プロバイダーを作成する方法を示します。|
|[Windows PowerShell コンテナー プロバイダーを作成します。](./creating-a-windows-powershell-container-provider.md)|このトピックでは、複数レイヤーのデータ ストアで作業するユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。|
|[Windows PowerShell ナビゲーション プロバイダーを作成します。](./creating-a-windows-powershell-navigation-provider.md)|このトピックでは、階層的にデータ ストアの項目を移動するユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。|
|[Windows PowerShell コンテンツ プロバイダーを作成します。](./creating-a-windows-powershell-content-provider.md)|このトピックでは、データ ストア内のアイテムのコンテンツを操作するユーザーのための Windows PowerShell プロバイダーを作成する方法を示します。|
|[Windows PowerShell プロパティ プロバイダーを作成します。](./creating-a-windows-powershell-property-provider.md)|このトピックでは、ユーザーがデータ ストア内のアイテムのプロパティを操作できる Windows PowerShell プロバイダーを作成する方法を示します。|

## <a name="see-also"></a>参照

[Windows PowerShell の動作](http://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)
