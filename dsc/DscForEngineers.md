---
ms.date: 10/13/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: エンジニア向けの Desired State Configuration の概要
ms.openlocfilehash: 30ce8bbb8bd3ea69dbf8ca509ecf523eb8fd915f
ms.sourcegitcommit: bad40d59598ae5597051fa381986316a2d9bf6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271077"
---
# <a name="desired-state-configuration-overview-for-engineers"></a>エンジニア向けの Desired State Configuration の概要

このドキュメントは、開発および運用チームに対して PowerShell Desired State Configuration (DSC) の利点を説明するためのものです。
より大まかな DSC のメリットについては、「[意思決定者向け Desired State Configuration の概要](decisionMaker.md)」を参照してください。

## <a name="benefits-of-desired-state-configuration"></a>Desired State Configuration の利点

DSC の存在理由は次のとおりです。

- Windows でのスクリプト作成の複雑さを軽減する
- イテレーションの速度を上げる

"継続的展開" という概念の重要性が高まりつつあります。
継続的展開とは、展開を頻繁に、場合によっては 1 日に何回もできることを指します。
こうした展開の目的は修正ではなく、公開されたものを迅速に取得することにあります。
できる限りスムーズかつ確実に、新機能を開発から運用に移行することで、新しいビジネス ロジックの価値実現にかかる時間を短縮できます。

クラウド コンピューティングへの移行に伴い、最終状態の環境をテキストとして宣言し展開エンジンに公開する、"宣言" テンプレート モデルを活用した展開ソリューションが必要とされています。
この展開方法では、展開をいつでも継続的に繰り返して最終状態を確保できるため、エラーの脅威に対する復元性を持ちながら急速な変更を大規模に行うことができます。
こうした変化への対応として、このような作業のスタイルを自動化によりサポートするツールやサービスが作成されました。

DSC は、宣言的かつべき等的 (反復可能) な展開、構成、適合を実現するプラットフォームです。
DSC プラットフォームを使用することで、データ センターの各コンポーネントの構成を適切に保ち、エラーを回避するとともに配置の失敗による費用の損失を抑えることができます。
DSC では、アプリケーション コードの一部として DSC 構成を処理することで継続的配置を可能にします。
DSC 構成はアプリケーションの一部として更新し、アプリケーションの展開に必要な知識をいつでも使用可能な最新の状態に保つ必要があります。

## <a name="i-have-powershell-why-do-i-need-desired-state-configuration"></a>"PowerShell はありますが、なぜ Desired State Configuration が必要なのですか?"

DSC 構成では、意図 ("何をやりたいか") と実行 ("どのようにやりたいか") が切り離されます。
つまり、実行のロジックはリソースに含まれるということです。
ある機能の DSC リソースが用意されていれば、ユーザーがその機能を実装または配置する方法を知る必要はありません。
これにより、ユーザーは配置の構造に集中できるようになります。

たとえば、次のような PowerShell スクリプトがあるとします。
```powershell
# Create a share in Windows Server 8
New-SmbShare -Name MyShare -Path C:\Demo\Temp -FullAccess Alice -ReadAccess Bob
```
このスクリプトはシンプルでわかりやすく、直線的です。
しかし、このスクリプトを運用環境に移そうとすると、いくつかの問題が発生します。
このスクリプトを続けて 2 回実行したらどうなるでしょうか。
また、Bob がこの共有へのフル アクセスをすでに所有していた場合にはどうなるでしょうか。

こうした問題に対処するため、"実際の" バージョンのスクリプトは次のようなものになります。
```powershell
# But actually creating a share in an idempotent way would be

$shareExists = $false
$smbShare = Get-SmbShare -Name $Name -ErrorAction SilentlyContinue
if($smbShare -ne $null)
{
    Write-Verbose -Message "Share with name $Name exists"
    $shareExists = $true
}

if ($shareExists -eq $false)
{
    Write-Verbose "Creating share $Name to ensure it is Present"
    New-SmbShare @psboundparameters
}
else
{
    # Need to call either Set-SmbShare or *ShareAccess cmdlets
    if ($psboundparameters.ContainsKey("ChangeAccess"))
    {
       #...etc, etc, etc
    }
}
```

ロジックやエラー処理が増えたため、スクリプトが複雑になっています。
このスクリプトがわかりにくくなった理由は、目的ではなく*実行方法*を記載したためです。

DSC ではやりたいことを記載し、基になるロジックを抽象化することができます。

```powershell
# A configuration is a special kind of PowerShell function
Configuration Sample_Share
{
   Import-DscResource -Module xSmbShare
   # Nodes are the endpoint we wish to configure
   # A Configuration block can have zero or more Node blocks
   Node $NodeName
   {
      # Next, specify one or more resource blocks
      # Resources are simply PowerShell modules that
      # implement the logic of "how" to execute a task
      xSmbShare MySMBShare
      {
          Ensure      = "Present"
          Name        = "MyShare"
          Path        = "C:\Demo\Temp"
          ReadAccess  = "Bob"
          FullAccess  = "Alice"
          Description = "This is an updated description for this share"
      }
   }
}
#Run the function to compile the configuration
Sample_Share
#Pass the configuration to the nodes we defined and configure them
Start-DscConfiguration Sample_Share
```

このスクリプトの書式は整えられており、読みやすくなっています。
ロジックのパスとエラー処理は[リソース](resources.md)実装の部分にまだ残されていますが、スクリプト作成者が気づくことはありません。

## <a name="separating-environment-from-structure"></a>構造からの環境の分離

DevOps の一般的なパターンでは、展開用の環境を複数用意します。
たとえば、新しいコードを素早く試作するための "開発" 環境があるとします。
"開発" 環境のコードは "テスト" 環境に移されて、別のユーザーが新機能の検証を行います。
最後に、コードは "運用"、つまり実際のサイト運用環境に移されます。

DSC 構成では、[構成データ](configData.md)を使用することでこのような開発 - テスト - 運用のパイプラインに対応します。
これにより、構成の構造と管理対象ノードとの差異がさらに抽象化されます。
たとえば、SQL サーバー、IIS サーバー、中間層サーバーが必要な構成を定義するとします。
この構成の各部分をどのようなノードに収容するかにかかわらず、これら 3 つの要素は常に存在します。
構成データを使用することで、開発環境では 3 つの要素すべてを同一のマシンにポイントし、テスト環境では 3 つの異なるマシンに分離して、最終的に運用環境ですべての運用サーバーにポイントすることができます。
複数の環境に展開するには、対象となる環境用の適切な構成データを指定して **Start-DscConfiguration** を呼び出します。

## <a name="see-also"></a>参照

[構成](configurations.md)

[構成データ](configData.md)

[リソース](resources.md)
