---
ms.date: 09/26/2017
contributor: keithb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PrereleaseModule
ms.openlocfilehash: 1fc08cbba90e3eb8ca7d280e4d279af1d8aa279f
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="prerelease-module-versions"></a>プレリリース モジュールのバージョン
バージョン 1.6.0 より、PowerShellGet および PowerShell ギャラリーで 1.0.0 以降のバージョンをプレリリースとしてタグ付けできるようになりました。 この機能より前は、プレリリース項目は 0 で始まるバージョンに制限されていました。 この機能の目的は、PowerShell バージョン 3 以降、または既存のバージョンの PowerShellGet との後方互換性を失わずに [SemVer v1.0.0](http://semver.org/spec/v1.0.0.html) のバージョン管理規則に対してより優れたサポートを提供することです。 このトピックでは、モジュールに固有の機能に焦点を当てています。 スクリプトの同等の機能は、「[プレリリース バージョンのスクリプト](../script/PrereleaseScript.md)」のトピックにあります。 これらの機能を使用して、パブリッシャーはモジュールまたはスクリプトをバージョン 2.5.0-alpha と識別し、プレリリース バージョンより優先される実稼働可能なバージョン 2.5.0 を後からリリースすることができます。

大まかには、プレリリースのモジュール機能には次のようなものがあります。

* モジュール マニフェストの PSData セクションに Prerelease 文字列を追加すると、モジュールがプレリリース バージョンとして識別されます。
モジュールが PowerShell ギャラリーに発行されると、このデータがマニフェストから抽出され、プレリリース項目を識別するために使用されます。
* プレリリース項目を取得するには、-AllowPrerelease フラグを Find-Module、Install-Module、Update-Module、Save-Module の PowerShellGet コマンドに追加する必要があります。
フラグが指定されていないと、プレリリース項目が表示されません。
* Find-Module、Get-InstalledModule、および PowerShell ギャラリーに表示されるモジュール バージョンは、2.5.0-alpha のように Prerelease 文字列が付加された 1 つの文字列として表示されます。

この機能の詳細については後述します。

この変更は、PowerShell に組み込まれているモジュール バージョンのサポートには影響せず、PowerShell 3.0、4.0、および 5 と互換性があります。

## <a name="identifying-a-module-version-as-a-prerelease"></a>モジュール バージョンをプレリリースとして識別する

PowerShellGet がプレリリース バージョンをサポートするには、モジュール マニフェスト内の 2 つのフィールドを使用する必要があります。

* プレリリース バージョンが使用される場合、モジュール マニフェストに含まれる ModuleVersion は 3 パートのバージョンで、既存の PowerShell バージョン管理に準拠している必要があります。 バージョンの形式は A.B.C になります。A、B、C はすべて整数です。
* Prerelease 文字列は、PrivateData の PSData セクションの、モジュール マニフェストに指定されます。
Prerelease 文字列の詳しい要件は後述します。

モジュールをプレリリースとして定義するモジュール マニフェストの例のセクションは、次のようになります。
```powershell
@{
    ModuleVersion = '2.5.0'
    #---
    PrivateData = @{
        PSData = @{
            Prerelease = 'alpha'
        }
    }
}
```

Prerelease 文字列の詳しい要件は次のとおりです。

* Prerelease 文字列は、Major.Minor.Build の ModuleVersion が 3 セグメントである場合にのみ指定できます。 これは、SemVer v1.0.0 と適合します。
* ハイフンは、ビルド番号と Prerelease 文字列の間の区切り文字です。 ハイフンは、Prerelease 文字列の最初の文字としてのみ含めることができます。
* Prerelease 文字列には ASCII 英数字 [0-9A-Za-z-] のみを含めることができます。 Prerelease 文字列はアルファベットで始めることをお勧めします。項目の一覧を見たときにプレリリース バージョンであることが識別しやすくなるためです。
* 現時点では、SemVer v1.0.0 の Prerelease 文字列のみがサポートされています。 Prerelease 文字列には (SemVer 2.0 では許可されている) ピリオドまたは + [.+] のどちらかを含めることは__できません__。
* サポートされている Prerelease 文字列には、-alpha、-alpha1、-BETA、-update20171020 などがあります。

__並べ替え順序およびインストール フォルダーへのプレリリース バージョン管理の影響__

並べ替え順序は、PowerShell ギャラリーへの発行時に重要なプレリリース バージョンを使用するときや、PowerShellGet コマンドを使用してモジュールをインストールするときに変更されます。
Prerelease 文字列が 2 つのモジュールに指定されている場合、並べ替え順序はハイフンの後の文字列部分に基づきます。 そのため、バージョン 2.5.0-alpha は 2.5.0-beta より小さく、2.5.0-beta は 2.5.0-gamma より小さくなります。
2 つのモジュールに同じ ModuleVersion が含まれ、うち 1 つに Prerelease 文字列が含まれる場合は、Prerelease 文字列のないモジュールが実稼働可能なバージョンと見なされ、(Prerelease 文字列を含む) プレリリース バージョンより後のバージョンとして並べ替えられます。
たとえば、2.5.0 と 2.5.0-beta を比較すると、2.5.0 バージョンの方が後だと見なされます。

PowerShell ギャラリーに発行すると、既定により、発行されているモジュールのバージョンが必ず PowerShell ギャラリーにある以前に発行されているバージョンよりも後のバージョンになります。

## <a name="finding-and-acquiring-prerelease-items-using-powershellget-commands"></a>PowerShellGet コマンドを使用してプレリリース項目を検索および取得する

Find-Module、Install-Module、Update-Module、Save-Module の PowerShellGet コマンドを使用してプレリリース項目を操作するには、-AllowPrerelease フラグを追加する必要があります。
-AllowPrerelease が指定されていると、プレリリース項目が存在する場合にはその項目が含まれます。
-AllowPrerelease フラグが指定されていないと、プレリリース項目が表示されません。

PowerShellGet モジュールのコマンドで、これに対する唯一の例外が Get-InstalledModule です。場合によっては Uninstall-Module も含まれます。

* Get-InstalledModule は常にモジュールのバージョン文字列にプレリリース情報を自動的に表示します。
* Uninstall-Module は__バージョンが指定されていない__場合に、既定でモジュールの最新のバージョンをアンインストールします。 この動作は変更されていません。 ただし、-RequiredVersion を使用してプレリリース バージョンが指定された場合は、-AllowPrerelease が必要になります。

## <a name="examples"></a>例
```powershell
# Assume the PowerShell Gallery has TestPackage module versions 1.8.0 and 1.9.0-alpha. If -AllowPrerelease is not specified, only version 1.8.0 will be returned.
C:\windows\system32> find-module TestPackage

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.8.0          TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> find-module TestPackage -AllowPrerelease

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.9.0-alpha    TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

# To install a prerelease, always specify -AllowPrerelease. Specifying a prerelease version string is not sufficient.

C:\windows\system32> Install-module TestPackage -RequiredVersion 1.9.0-alpha
PackageManagement\Find-Package : No match was found for the specified search criteria and module name 'TestPackage'.
Try Get-PSRepository to see all available registered module repositories.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PSModule.psm1:1455 char:3
+         PackageManagement\Find-Package @PSBoundParameters | Microsoft ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...ets.FindPackage:FindPackage) [Find-Package], Exceptio
   n
    + FullyQualifiedErrorId : NoMatchFoundForCriteria,Microsoft.PowerShell.PackageManagement.Cmdlets.FindPackage

# The previous command failed because -AllowPrerelease was not specified.
# Adding -AllowPrerelease will result in success.

C:\windows\system32> Install-module TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
C:\windows\system32> Get-InstalledModule TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

```

プレリリースが指定されているかどうかの違いしかない、モジュールのバージョンの同時インストールはサポートされません。
PowerShellGet を使用してモジュールをインストールすると、ModuleVersion を使用してフォルダー名が作成され、同じモジュールの異なるバージョンが同時にインストールされます。
Prerelease 文字列のない ModuleVersion がフォルダー名で使用されます。
ユーザーが MyModule バージョン 2.5.0-alpha をインストールすると、MyModule\2.5.0 フォルダーにインストールされます。
その後、ユーザーが 2.5.0-beta をインストールすると、2.5.0-beta バージョンがフォルダー MyModule\2.5.0 の内容を__上書き__します。
この方法の 1 つの利点が、実稼働可能バージョンのインストール後にプレリリース バージョンをアンインストールする必要がないことです。
以下の例は、予想すべき内容を示します。


``` powershell
C:\windows\system32> Get-InstalledModule TestPackage -AllVersions

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.8.0           TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.1.3.2         TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> find-module TestPackage -AllowPrerelease

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.9.0-beta     TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> Update-Module TestPackage -AllowPrerelease
C:\windows\system32> Get-InstalledModule TestPackage -AllVersions

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-beta      TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.8.0           TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.1.3.2         TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

```

-RequiredVersion が指定されていない場合、Uninstall-Module によってモジュールの最新バージョンが削除されます。
-RequiredVersion が指定されていて、これがプレリリースである場合、-AllowPrerelease をコマンドに追加する必要があります。

``` powershell
C:\windows\system32> Get-InstalledModule TestPackage -AllVersions

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
2.0.0-alpha1    TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.9.0-beta      TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.8.0           TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.1.3.2         TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> Uninstall-Module TestPackage -RequiredVersion 1.9.0-beta
Uninstall-Module : The '-AllowPrerelease' parameter must be specified when using the Prerelease string in
MinimumVersion, MaximumVersion, or RequiredVersion.
At line:1 char:1
+ Unnstall-Module TestPackage -RequiredVersion 1.9.0-beta
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Uninstall-Module], ArgumentException
    + FullyQualifiedErrorId : AllowPrereleaseRequiredToUsePrereleaseStringInVersion,Uninnstall-Module



C:\windows\system32> Uninstall-Module TestPackage -RequiredVersion 1.9.0-beta -AllowPrerelease
C:\windows\system32> Get-InstalledModule TestPackage -AllVersions

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
2.0.0-alpha1    TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.8.0           TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.1.3.2         TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> Uninstall-Module TestPackage
C:\windows\system32> Get-InstalledModule TestPackage -AllVersions

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.8.0           TestPackage                         PSGallery            Package used to validate changes to the PowerShe...
1.1.3.2         TestPackage                         PSGallery            Package used to validate changes to the PowerShe...


```



## <a name="more-details"></a>詳細情報
### <a name="prerelease-script-versionsscriptprereleasescriptmd"></a>[プレリリース バージョンのスクリプト](../script/PrereleaseScript.md)
### <a name="find-modulepsgetfind-modulemd"></a>[Find-Module](./psget_find-module.md)
### <a name="install-modulepsgetinstall-modulemd"></a>[Install-Module](./psget_install-module.md)
### <a name="save-modulepsgetsave-modulemd"></a>[Save-Module](./psget_save-module.md)
### <a name="update-modulepsgetupdate-modulemd"></a>[Update-Module](./psget_update-module.md)
### <a name="get-installedmodulepsgetget-installedmodulemd"></a>[Get-InstalledModule](./psget_get-installedmodule.md)
### <a name="uninstall-modulepsgetuninstall-modulemd"></a>[Uninstall-Module](./psget_uninstall-module.md)