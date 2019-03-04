---
title: コンソールのシェルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Make-Shell [PowerShell Programmer's Guide]
ms.assetid: 6c24dd44-a8ec-421d-ac86-90912e1a8cc6
caps.latest.revision: 5
ms.openlocfilehash: 7166881bd1403ea8c81ec2928321f6b93e3ac58d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853498"
---
# <a name="how-to-create-a-console-shell"></a>コンソール シェルを作成する方法

Windows PowerShell は、「make-キット」コンソール シェルがなく、拡張を作成するために使用するとも呼ばれます、ことをシェル ツールを提供します。 この新しいツールで作成されたシェルは、Windows PowerShell スナップインによって後で拡張できません。

## <a name="syntax"></a>構文

Make ファイル内で、シェルからを実行するために使用する構文を次に示します。

```
make-shell
  -out n.exe
  -namespace ns
  [ -lib libdirectory1[,libdirectory2,..] ]
  [ -reference ca1.dll[,ca2.dll,...] ]
  [ -formatdata fd1.format.ps1xml[,fd2.format.ps1xml,...] ]
  [ -typedata td1.type.ps1xml[,td2.type.ps1xml,...] ]
  [ -source c1.cs [,c2.cs,...] ]
  [ -authorizationmanager authorizationManagerType ]
  [ -win32icon i.ico ]
  [ -initscript p.ps1 ]
  [ -builtinscript s1.ps1[,s2.ps1,...] ]
  [ -resource resourcefile.txt ]
  [ -cscflags cscFlags ]
  [ -? | -help ]
```

## <a name="parameters"></a>パラメーター

次に、シェルのパラメーターの簡単な説明を示します。

> [!CAUTION]
> アセンブリへの UNC パスは、シェルによってサポートされていません。

|パラメーター|説明|
|---------------|-----------------|
|-n.exe アウト|必須。 生成するために、シェルの名前。 パスは、このパラメーターの一部として指定されます。<br /><br /> 指定されていない場合、シェルでこの値に".exe"が追加されます。 **注意が必要です。** 参照先の .dll ファイルと同じ名前では、出力ファイルを作成できません。 これを行う場合、シェルのツールは、コマンドレット ソース コードを含む .cs ファイルが上書きされますが、同じ名前の .cs ファイルを作成します。|
|名前空間の ns|必須。 派生クラスを使用する名前空間[System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) make キットが生成してコンパイルするクラス。|
|-lib libdirectory1[,libdirectory2,..]|Windows PowerShell アセンブリで指定されたアセンブリを含め、.NET アセンブリを検索するディレクトリ、`reference`パラメーター、別のアセンブリによって直接参照されるアセンブリと .NET のシステム アセンブリです。|
|-reference ca1.dll[,ca2.dll,...]|シェルに含めるアセンブリのコンマ区切りのリスト。 これらのアセンブリには、コマンドレットとプロバイダーのアセンブリだけでなくすべて読み込む必要のあるリソース アセンブリが含まれています。 このパラメーターが指定されていない場合、シェルが生成されますをコア コマンドレットと Windows PowerShell によって提供されるプロバイダーのみが含まれています。<br /><br /> その完全なパスを使用して、アセンブリを指定することができます、によって指定されたパスを使用するための検索それ以外の場合、`lib`パラメーター。|
|-formatdata fd1.format.ps1xml[,fd2.format.ps1xml,...]|シェルに含める形式のデータのコンマ区切りの一覧。 このパラメーターが指定されていない場合、シェルが生成されますを Windows PowerShell によって提供される形式のデータのみが含まれています。|
|-typedata td1.type.ps1xml[,td2.type.ps1xml,...]|シェルに含める型データのコンマ区切りの一覧。 このパラメーターが指定されていない場合、シェルが生成されますを Windows PowerShell によって提供される型のデータのみが含まれています。|
|-ソース c1.cs [,... c2.cs]|シェルの構築に必要な任意のソース コードを含むシェル開発者によって提供される、ファイルの名前。<br /><br /> ソース コード ファイルには、次のソース コードのいずれかを含めることができます。<br /><br /> -承認マネージャーの実装を既定の承認マネージャーのオーバーライドします。 (このでしたも指定するアセンブリにコンパイルされます。)<br />アセンブリ情報属性の宣言: AssemblyCompanyAttribute、assemblycopyrightattribute も、AssemblyFileVersionAttribute AssemblyInformationalVersionAttribute、AssemblyProductAttribute などとAssemblyTrademarkAttribute します。|
|-承認 authorizationManagerType|承認マネージャーの実装を含む型。 ソース コードで定義されているまたはアセンブリにコンパイルするには、この (で指定された、`reference`パラメーター)。 このパラメーターが指定されていない場合は、既定のセキュリティ マネージャーが使用されます。 名前空間を含む、完全な型名を指定する必要があります。|
|-win32icon i.ico|シェルの .exe ファイルのアイコン。 指定しない場合、シェルは、c# コンパイラは、(ある場合) を含むアイコンにがあります。|
|-initscript p.ps1|シェルの起動プロファイル。 ファイルが含まれる"としてでは、";シェルでの有効性チェックは行われません。|
|-builtinscript s1.ps1[,s2.ps1]|シェルの組み込みのスクリプトの一覧。 パスが、スクリプトの前にこれらのスクリプトが検出され、シェルがビルドされたら、その内容を変更ことはできません。<br /><br /> ファイルが含まれています"としてでは、";シェルでの有効性チェックは行われません。|
|-resource resourcefile.txt|シェルのヘルプとバナーのリソースを含む .txt ファイル。 最初のリソースは ShellHelp、という名前で、シェルが起動された場合に表示されるテキストが含まれています、`help`パラメーター。 ShellBanner、という名前の 2 つ目のリソースは、テキストと、シェルは対話モードで起動されたときに表示される著作権情報が含まれています。<br /><br /> このパラメーターが指定されていない、またはこれらのリソースが存在しない、汎用のヘルプとバナー使用されます。|
|-cscflags cscFlags|フラグを渡す必要がありますが、C#コンパイラ (csc.exe)。 これらはパススルー変更されません。 このパラメーターには、スペースが含まれている場合は、二重引用符で囲む必要があります。|
|-?<br /><br /> -ヘルプ|著作権メッセージと、シェル コマンド ライン オプションが表示されます。|
|-詳細|シェルの作成中には、詳細情報を表示します。|

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)