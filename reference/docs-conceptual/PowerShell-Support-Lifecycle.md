---
title: PowerShell Core のサポート ライフサイクル
description: PowerShell Core のサポートを管理するポリシー
ms.date: 08/06/2018
ms.openlocfilehash: 178e5c43520f9a392ca219b9f785eb18b1ec5436
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086972"
---
# <a name="powershell-core-support-lifecycle"></a>PowerShell Core のサポート ライフサイクル

PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。
そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。

ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。
サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。

## <a name="community-support"></a>コミュニティ サポート

GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。
また、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーがサポートしてくれる場合もあります。
コミュニティによりご自身の問題が短期間で対処または解決されることは保証できません。
早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。

## <a name="lifecycle-of-powershell-core"></a>PowerShell Core のライフサイクル

PowerShell Core には、[Microsoft Modern Lifecycle Policy][modern] が導入されています。
このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。

PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (例:6.0、6.1、6.2 など。)

> [!IMPORTANT]
> 引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。

たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。

> [!IMPORTANT]
> サポートを受け続けるには、それぞれの新しいパッチ バージョンのリリース後 30 日以内に更新する必要があります。

たとえば、PowerShell Core 6.1 を実行していて 2019 年 2 月 19 日に 6.1.3 がリリースされた場合、サポートを維持するには、リリースの 30 日後である 2019 年 3 月 21 日までに PowerShell Core 6.1.3 に更新する必要があります。
必要な修正プログラムが見つかった場合、その修正プログラムは次の累積的な更新プログラムでリリースされます。

![PowerShell Core のブランチ ライフサイクル][lifecycle-chart]

Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することを Microsoft の義務としています。

最終的に、PowerShell Core では "長期サービス" のアプローチを採用する予定です。
このサービスのアプローチでは、特定のブランチ/バージョン の 6.x のサポートを維持するために、サービスとセキュリティの更新だけが必要になります。

## <a name="supported-platforms"></a>サポートされているプラットフォーム

お使いの PowerShell Core のバージョンが公式にサポートされているプラットフォームについては、次の表をご覧ください。

また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。
これらのパッケージは、表の中で `Community` とマークされています。

`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。

|                                                   | 6.1         | 6.2         |
|---------------------------------------------------|:-----------:|:-----------:|
| Windows 7、8.1、10                            | サポート   | サポート   |
| Windows Server 2008 R2、2012 R2、2016             | サポート   | サポート   |
| [Windows Server 半期チャネル][semi-annual] | サポート   | サポート   |
| Ubuntu 16.04 および 18.04                            | サポート   | サポート   |
| Ubuntu 18.10 (Snap パッケージを使用)                   | コミュニティ   | コミュニティ   |
| Debian 9                                          | サポート   | サポート   |
| CentOS 7                                          | サポート   | サポート   |
| Red Hat Enterprise Linux 7                        | サポート   | サポート   |
| openSUSE 42.3                                     | サポート   | サポート   |
| Fedora 28                                         | サポート   | サポート   |
| macOS 10.12 以降                                      | サポート   | サポート   |
| Arch                                              | コミュニティ   | コミュニティ   |
| Raspbian                                          | コミュニティ   | コミュニティ   |
| Kali                                              | コミュニティ   | コミュニティ   |
| AppImage (複数の Linux プラットフォームで機能)     | コミュニティ   | コミュニティ   |
| [Snap パッケージ](https://snapcraft.io/powershell)   | 注を参照    | 注を参照    |

> [!NOTE]
> パッケージを実行しているディストリビューションと同様に、スナップ パッケージがサポートされます。

## <a name="powershell-release-end-of-life"></a>PowerShell リリースのサポート終了

[PowerShell Core のライフサイクル](#lifecycle-of-powershell-core)に基づき、さまざまなリリースがサポートされなくなる日付を次の表に示します。

| バージョン | サポート終了                   |
|---------|-------------------------------|
| 6.0     | 2019 年 2 月 13 日             |
| 6.1     | 2019 年 9 月 28 日            |
| 6.2     | 6.3 のリリースから 6 か月後   |

## <a name="platforms-which-are-out-of-support"></a>サポート対象外のプラットフォーム

プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core でもそのプラットフォームのバージョンがサポートされなくなります。
アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。

そのため、ディストリビューションの所有者によって次のバージョンのサポートは終了され、サポートされていません。

| OS       | バージョン | 有効期限切れ                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| Fedora   | 24      | [2017 年 8 月](https://fedoramagazine.org/fedora-24-eol/)                                    |
| Fedora   | 25      | [2017 年 12 月](https://fedoramagazine.org/fedora-25-end-life/)                             |
| Fedora   | 26      | [2018 年 5 月](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| openSUSE | 42.1    | [2017 年 5 月](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| openSUSE | 42.2    | [2018 年 1 月](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| Ubuntu   | 16.10   | [2017 年 7 月](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| Ubuntu   | 17.04   | [2018 年 1 月](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| Ubuntu   | 17.10   | [2018 年 7 月](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| Debian   | 8       | [2018 年 6 月](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| Fedora   | 27      | [2018 年 11 月](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| Ubuntu   | 14.04   | [2019 年 4 月](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a>ライセンスに関する注意事項

PowerShell Core は [MIT ライセンス][]の下で提供されます。
このライセンスの下で、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。
コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。

## <a name="windows-powershell-module"></a>Windows PowerShell モジュール

PowerShell Core のサポートに製品モジュールが含まれることは、そのモジュールで明示的に PowerShell Core をサポートしている場合を除いて、ありません。
たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することはサポートの対象外です。

ただし、PowerShell Core 対応であることが明示されていないモジュールの場合でも、サポート対象となることがあります。
[`WindowsPSModulePath`][] モジュールをインストールすることで、Windows PowerShell `PSModulePath` を PowerShell Core `PSModulePath` に追加できます。

最初に、PowerShell ギャラリーから `WindowsPSModulePath` モジュールをインストールします。

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

このモジュールをインストールしたら、次のように `Add-WindowsPSModulePath` コマンドレットを実行して、Windows PowerShell `PSModulePath` を PowerShell Core に追加します。

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a>試験的な機能

[試験的な機能][]には[コミュニティ サポート](#community-support)のみが与えられます。

[Premier]: https://www.microsoft.com/en-us/microsoftservices/support.aspx
[enterprise-agreement]: https://www.microsoft.com/en-us/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/en-us/licensing/licensing-programs/software-assurance-default.aspx
[コミュニティ サポート]: https://github.com/powershell/powershell/issues
[Microsoft コミュニティ]: https://answers.microsoft.com/
[PowerShell Tech コミュニティ]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[サポート]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
[MIT ライセンス]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[`WindowsPSModulePath`]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[試験的な機能]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
