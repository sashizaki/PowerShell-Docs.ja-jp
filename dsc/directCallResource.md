---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース メソッドの直接呼び出し
ms.openlocfilehash: dbf0a4ada4c6cc2e7d65698b87a5a29a2ea84781
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="calling-dsc-resource-methods-directly"></a>DSC リソース メソッドの直接呼び出し

>適用先: Windows PowerShell 5.0

[Invoke DscResource](https://technet.microsoft.com/library/mt517869.aspx) コマンドレットを使用すると、DSC リソースの関数やメソッド (MOF ベースのリソースの **Get-TargetResource**、**Set-TargetResource**、**Test-TargetResource** 関数、またはクラスベースのリソースの **Get**、**Set**、**Test** メソッド) を直接呼び出すことができます。
これは、DSC リソースを使用するサード パーティが使用したり、リソースの開発中に役立つツールとして利用したりできます。

通常このコマンドレットは、メタ構成プロパティ `refreshMode = 'Disabled'` と組み合わせて使用されますが、どの **refreshMode** が設定されているかに関係なく使用できます。

**Invoke-DscResource** コマンドレットを呼び出すときに、**Method** パラメーターを使用して、呼び出すメソッドまたは関数を指定します。 リソースのプロパティを指定するには、ハッシュ テーブルを、**Property** パラメーターの値として渡します。

リソースのメソッドを直接呼び出す例を次に示します。

## <a name="ensure-a-file-is-present"></a>ファイルが存在することを確認します

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
                            DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
                            Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="test-that-a-file-is-present"></a>ファイルが存在することをテストします

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## <a name="get-the-contents-of-file"></a>ファイルの内容を取得します

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```

>**注:** 複合リソースのメソッドを直接呼び出すことはできません。 代わりに、複合リソースの基になるリソースのメソッドを呼び出してください。

## <a name="see-also"></a>参照
- [MOF を使用したカスタム DSC リソースの記述](authoringResourceMOF.md)
- [PowerShell クラスを使用したカスタム DSC リソースの記述](authoringResourceClass.md)
- [DSC リソースのデバッグ](debugResource.md)