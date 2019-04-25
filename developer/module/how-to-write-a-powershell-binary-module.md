---
title: PowerShell バイナリ モジュールを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb4e72e6-24c4-42b6-b7b9-a62585c17f26
caps.latest.revision: 15
ms.openlocfilehash: 9ddb3bc172c66314603d2be4df5192a76c92e05d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082228"
---
# <a name="how-to-write-a-powershell-binary-module"></a>PowerShell バイナリ モジュールを記述する方法

バイナリ モジュールには、コマンドレット クラスを含む任意のアセンブリ (.dll) を指定できます。 既定では、アセンブリ内のすべてのコマンドレットは、バイナリ モジュールのインポート時にインポートされます。 ただし、ルート モジュールがあるアセンブリのモジュール マニフェストを作成してインポートされたコマンドレットを制限することができます。 (たとえば、マニフェストの CmdletsToExport キーできるために必要なコマンドレットのみをエクスポートする。)さらに、バイナリ モジュールでは、追加のファイル、ディレクトリ構造、および 1 つのコマンドレットができないことに有用な管理の他の情報を含めることができます。

次の手順では、作成し、PowerShell バイナリ モジュールをインストールする方法について説明します。

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a>作成し、PowerShell バイナリ モジュールをインストールする方法

1. バイナリ PowerShell ソリューションの作成 (で記述されたコマンドレットなどC#) の機能を持つ必要があると適切に動作することを確認します。

   コードの観点からは、バイナリ モジュールの中核は、コマンドレット アセンブリだけです。 実際には、PowerShell は、1 つのコマンドレットのアセンブリを読み込みとアンロード、何も追加の作業、開発者の観点から、モジュールとして扱います。 コマンドレットの記述方法の詳細については、次を参照してください。 [Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)します。

2. 必要に応じて、ソリューションの残りの部分を作成: (その他のコマンドレットや、XML ファイル) と、モジュール マニフェストを説明します。

   ソリューション内のコマンドレットのアセンブリを記述するだけでなく、モジュール マニフェストは、モジュールをエクスポートおよびインポートする方法、どのようなコマンドレットを公開するか、および追加のファイルがモジュールに変わりますを記述できます。 前に述べたただし、PowerShell は、何も追加の作業のモジュールと同様にバイナリ コマンドレットを扱うことができます。 そのため、モジュール マニフェストは、主に 1 つのパッケージに複数のファイルを結合することや、特定のアセンブリのパブリケーションを明示的に制御するために便利です。 詳細については、次を参照してください。 [PowerShell モジュール マニフェストの記述方法](http://msdn.microsoft.com/en-us/abe4c24b-e64e-4a61-81d5-18c4fceba0b6)します。

   次のコードは、非常に単純C#をモジュールとして使用できるのと同じファイル内の 3 つのコマンドレットを含むコード ブロックです。

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. ソリューションをパッケージ化し、別の場所にパッケージを保存で PowerShell モジュールのパス。

   `PSModulePath`グローバル環境変数には、PowerShell がモジュールの検索に使用する既定のパスがについて説明します。 たとえば、システム上のモジュールを保存する共通のパスになります`%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`します。 既定のパスを使用しない場合は、インストール中に、モジュールの場所を明示的に記述する必要があります。 必要に応じて複数のアセンブリと、ソリューション ファイルを格納するフォルダーで、モジュールを保存するフォルダーを作成することを確認します。

   技術的には必要はありません、モジュールを任意の場所にインストールするに注意してください、 `PSModulePath` -これらは、PowerShell は、モジュールを検索する既定の場所だけです。 ただし、別の場所にモジュールを格納するための十分な理由がない限り、そのためのベスト プラクティスと見なされます。 詳細については、次を参照してください。 [PowerShell モジュールのインストール](./installing-a-powershell-module.md)と[PowerShell モジュールのインストール パスを変更する](./modifying-the-psmodulepath-installation-path.md)します。

4. 呼び出しで、モジュールを PowerShell にインポート[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)します。

   呼び出す[Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)アクティブ メモリに、モジュールが読み込まれます。 PowerShell 3.0 を使用してあり、後で、単に呼び出す場合はコードで、モジュールの名前もインポートされます。詳細については、次を参照してください。 [PowerShell モジュールをインポートする](./importing-a-powershell-module.md)します。

## <a name="importing-snap-in-assemblies-as-modules"></a>モジュールとスナップインからアセンブリをインポートします。

コマンドレットとプロバイダー スナップイン アセンブリ内に存在するは、バイナリ モジュールとして読み込むことができます。 スナップインでアセンブリがバイナリ モジュールとして読み込まれた場合は、コマンドレットとプロバイダー、スナップインでは、ユーザーが利用できるが、アセンブリ内のスナップイン クラスは無視され、スナップインが登録されていません。 その結果、Windows PowerShell によって提供されるスナップインでコマンドレットは、コマンドレットとプロバイダーがセッションに使用可能な場合でものスナップインで検出できません。

さらに、バイナリ モジュールの一部として、スナップインによって参照されている書式設定または種類のファイルをインポートできません。 書式設定と種類のファイルをインポートするには、モジュール マニフェストを作成する必要があります。 参照してください、 [PowerShell モジュールのマニフェストを作成する方法](http://msdn.microsoft.com/en-us/abe4c24b-e64e-4a61-81d5-18c4fceba0b6)します。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの記述](./writing-a-windows-powershell-module.md)
