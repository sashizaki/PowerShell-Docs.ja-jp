---
ms.date: 12/11/2018
contributor: JKeithB, SydneyhSmith
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: 互換性のある PowerShell エディションまたはオペレーティング システムを使用してパッケージ
ms.openlocfilehash: 8230866561d3021379a48cc2c83fb4104a4058c1
ms.sourcegitcommit: d396d0e4cfe3d279f399c17e7337380a31d373ac
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2018
ms.locfileid: "53747706"
---
# <a name="packages-with-compatible-powershell-editions-or-operating-systems"></a>互換性のある PowerShell エディションまたはオペレーティング システムを使用してパッケージ

バージョン 5.1 以降、機能セットとプラットフォーム互換性が異なる別エディションの PowerShell が用意されています。

## <a name="searching-by-powershell-edition"></a>PowerShell のエディションでの検索 
Powershell の 2 つのエディションは次のとおりです。
- **Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。
- **コア エディション:**.NET Core 上に構築され、スクリプトおよび Nano Server などの Windows や Windows IoT の縮小エディションで実行されている PowerShell のバージョンを対象とするモジュールとの互換性を提供します。

### <a name="powershell-gallery-allows-you-to-filter-packages-compatible-for-specific-powershell-editions"></a>PowerShell ギャラリーでは、特定の PowerShell エディションの互換性のあるパッケージをフィルター処理できます。

パッケージが互換性のある場合は、指定した PSEditions ' PowerShell Editions' の一部として表示されているページを表示するパッケージとパッケージの結果。
PowerShell を使用して互換性のあるパッケージを検索することもできます。

![PSEditions での項目表示ページ](../../Images/packagedisplaypagewithpseditions.PNG)

### <a name="search-for-packages-in-the-gallery-ui-that-work-on-powershell-core"></a>PowerShell Core で機能するギャラリー UI でのパッケージを検索します。

Tags:"PSEdition_Desktop" と Tags:"PSEdition_Core" を使用して PowerShell ギャラリー上のパッケージをフィルター処理します。

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a>Tags:"PSEdition_Core" を使用して PowerShell Core エディションと互換性のある項目を検索します。

![Core PSEdition と互換性のある項目の検索](../../Images/searchresultswithpseditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a>Tags:"PSEdition_Desktop" を使用して PowerShell Desktop エディションと互換性のある項目を検索します。

![Desktop PSEdition と互換性のある項目の検索](../../Images/searchresultswithpseditionsdesktop.PNG)

### <a name="search-for-packages-to-find-compatible-editions-using-powershell"></a>PowerShell を使用して互換性のあるエディションを検索するパッケージを検索します。
PowerShell のエディションと OS のフィルター処理するタグを指定することができます。 使用する、`Find-Package`コマンドレットを指定する、 `-Tag` edition (およびの OS) を指定するパラメーター対象としています。
このように：

```powershell
# Find modules compatible with PowerShell Core:
Find-Module -Tag PSEdition_Core

# Find modules compatible with PowerShell Core on Linux:
Find-Module -Tag PSEdition_Core, Linux
```

## <a name="searching-by-operating-system"></a>オペレーティング システムでの検索 

PowerShell Core は、Windows、Linux、および MacOS の使用可能なであるために、これらのオペレーティング システムの任意の組み合わせのギャラリー内のパッケージを設計する場合があります。 ギャラリー UI には、オペレーティング システムでタグ付けされたパッケージを検索するのに searchs に次のタグを使用します。

- タグ:"Windows"
- タグ:"Linux"
- タグ:"MacOS" 

これらのタグを指定することができます`Find-Module`(およびその他の PowerShellGet モジュールのコマンドレット) 次のようにします。

```powershell
# Find Modules compatible with Windows
Find-Module -Tag Linux
```

## <a name="searching-for-multiple-compatibilities"></a>複数の互換性の検索

構文を使用して複数の互換性のあるパッケージを探すことができます。 

タグ"Compatibility1""Compatibility2" 

たとえば、Windows と Linux の両方のマシンで実行される PowerShell Core の互換性を持つパッケージを探している場合は、検索タグを使用します。

タグ"PSEdition_Core""Linux"の"Windows" 

PowerShell を使用して検索するに使用することができます、 `Find-Module` (および PowerShellGet モジュールの他のコマンドレット) 次のようにします。

```powewrshell
# Find scripts compatible with PowerShell Core, Windows, and Linux
Find-Script -Tag PSEdition_Core,Linux,Windows

# Find modules compatible with PowerSHellCore and MacOS
Find-Module -Tag PSEdition_Core,MacOS
```

## <a name="more-details-on-authoring-and-finding-the-packages-with-compatible-powershell-editions"></a>互換性のある PowerShell エディションが含まれるパッケージの作成と検索に関する詳細

- [PSEditions が含まれるモジュール](../../concepts/module-psedition-support.md)
- [PSEditions のスクリプト](../../concepts/script-psedition-support.md)
