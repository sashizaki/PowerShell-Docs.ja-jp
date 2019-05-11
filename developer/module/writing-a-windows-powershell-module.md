---
title: Windows PowerShell モジュールの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfbccc5b-2b2b-432a-a971-9f8ab503cdc3
caps.latest.revision: 17
ms.openlocfilehash: 0b7263ea19745e902fff04b993933e443d4d6333
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229350"
---
# <a name="writing-a-windows-powershell-module"></a>Windows PowerShell モジュールを記述する

管理者、スクリプトの開発者、およびパッケージ化して、Windows PowerShell コマンドレットを配布する必要があるコマンドレットの開発者は、このドキュメントが書き込まれます。 Windows PowerShell モジュールを使用すると、パッケージ化し、コンパイル済みの言語を使用せずに、Windows PowerShell のソリューションを配布できます。

Windows PowerShell モジュールは、パーティションに有効にする、整理、および再利用可能な自己完結型の単位に、Windows PowerShell コードを抽象化します。 これらの再利用可能なユニットでは、他のユーザーと直接モジュールを簡単に共有できます。 スクリプトを開発している場合、カスタムのスクリプト ベースのアプリケーションを作成するサード パーティ モジュールも再パッケージ化できます。 モジュール、Perl、Python などの他のスクリプト言語でモジュールのような再パッケージ化し、複数のコンポーネントが抽象化を有効にする追加の特典で再利用可能な再頒布可能パッケージのコンポーネントを使用する実稼働可能なスクリプト ソリューションを有効にします。カスタム ソリューションを作成します。

その最も基本的な Windows PowerShell は、有効な Windows PowerShell スクリプト コードをモジュールとして .psm1 ファイルに保存を扱います。 PowerShell では、モジュールとして任意のコマンドレットがバイナリ アセンブリも自動的に扱います。 ただし、ソリューション全体を一緒にバンドルするモジュール (またはより具体的には、モジュール マニフェスト) を使用することができますも。 次のシナリオでは、Windows PowerShell モジュールの一般的な用途について説明します。

### <a name="libraries"></a>ライブラリ

パッケージ化し、一般的なタスクを実行する関数のまとまりのあるライブラリを配布するのには、モジュールを使用できます。 通常、これらの関数の名前は、それらに使用される一般的なタスクを反映した 1 つまたは複数の名詞を共有します。 これらの関数はパブリックおよびプライベート メンバーを持つことで、.NET Framework のクラスに似ていますにも。 たとえば、ライブラリでは、ファイル転送の一連の関数を含めることができます。 この場合、一般的なタスクを反映した名詞は"file です"可能性があります。

### <a name="configuration"></a>構成

特定のコマンドレット、プロバイダー、関数、および変数を追加して、環境をカスタマイズするモジュールを使用できます。

### <a name="compiled-code-development-and-distribution"></a>コンパイル済みコードの開発と配布

コマンドレットとプロバイダーの開発者は、テストして、スナップインを作成しなくても、コンパイル済みコードを配布するモジュールを使用できます。(バイナリ モジュール) をモジュールとしてコンパイルされたコードを含むアセンブリをインポート、作成し、スナップインを登録する必要はありません。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールを理解します。](./understanding-a-windows-powershell-module.md)

[PowerShell スクリプト モジュールを記述する方法](./how-to-write-a-powershell-script-module.md)

[PowerShell バイナリ モジュールを記述する方法](./how-to-write-a-powershell-binary-module.md)

[PowerShell モジュールのマニフェストを作成する方法](how-to-write-a-powershell-module-manifest.md)

[PSModulePath インストール パスの変更](./modifying-the-psmodulepath-installation-path.md)

[PowerShell モジュールをインポートします。](./importing-a-powershell-module.md)

[PowerShell モジュールのインストール](./installing-a-powershell-module.md)
