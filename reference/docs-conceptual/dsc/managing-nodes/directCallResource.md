---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース メソッドの直接呼び出し
ms.openlocfilehash: cf237f638593706e5959e2bcc0d851b0e55baf0e
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954389"
---
# <a name="calling-dsc-resource-methods-directly"></a>DSC リソース メソッドの直接呼び出し

>適用先:Windows PowerShell 5.0

[Invoke DscResource](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource) コマンドレットを使用すると、DSC リソースの関数やメソッド (MOF ベースのリソースの **Get-TargetResource**、**Set-TargetResource**、**Test-TargetResource** 関数、またはクラスベースのリソースの **Get**、**Set**、**Test** メソッド) を直接呼び出すことができます。
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
- [MOF を使用したカスタム DSC リソースの記述](../resources/authoringResourceMOF.md)
- [PowerShell クラスを使用したカスタム DSC リソースの記述](../resources/authoringResourceClass.md)
- [DSC リソースのデバッグ](../troubleshooting/debugResource.md)