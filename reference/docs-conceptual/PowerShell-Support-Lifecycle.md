---
title: PowerShell Core のサポート ライフサイクル
description: PowerShell Core のサポートを管理するポリシー
ms.date: 08/06/2018
ms.openlocfilehash: 2e0ca1b9c133e6f316a40aff13365d0489059165
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403494"
---
# <a name="powershell-core-support-lifecycle"></a>PowerShell Core のサポート ライフサイクル

PowerShell Core は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。
そのため、PowerShell Core は Windows 7/8.1/10 や Windows Server のライセンス契約には含まれていません。

ただし、PowerShell Core は、[Premier][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約ではサポートされています。
サポート依頼で問題を報告して PowerShell Core の[サポート][]を受け、それに対して支払うこともできます。

GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。
あるいは、一般的な [Microsoft コミュニティ][]や Microsoft [PowerShell Tech コミュニティ][]で他のコミュニティ メンバーが助けてくれることがあります。
問題が短期間で解決されることは保証できません。
早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。

## <a name="lifecycle-of-powershell-core"></a>PowerShell Core のライフサイクル

PowerShell Core には、[Microsoft Modern Lifecycle Policy][modern] が導入されています。
このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。

PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されます (6.0、6.1、6.2 など)

> [!IMPORTANT]
> 引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。

たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。

![PowerShell Core のブランチ ライフサイクル][lifecycle-chart]

Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することをマイクロソフトの義務としています。

ゆくゆくは PowerShell Core に "Long Term Servicing" 手法を導入することをマイクロソフトは期待しています。この手法では、特定の 6.x ブランチ/バージョンのサポートを維持するために、サービス更新とセキュリティ更新だけが必要になります。

## <a name="supported-platforms"></a>サポートされているプラットフォーム

お使いの PowerShell Core のバージョンが公式にサポートされているプラットフォームを確認するには、次の表をご覧ください。

また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。
これらのパッケージは、表の中で `Community` とマークされています。

`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。

|                                                   | 6.0         | 6.1         |
|---------------------------------------------------|:-----------:|:-----------:|
| Windows 7、8.1、10                            | サポート   | サポート   |
| Windows Server 2008 R2、2012 R2、2016             | サポート   | サポート   |
| [Windows Server 半期チャネル][semi-annual] | サポート   | サポート   |
| Ubuntu 14.04 および 16.04                           | サポート   | サポート   |
| Ubuntu 18.04                                      |             | サポート   |
| Ubuntu 18.10 (Snap パッケージを使用)                   |             | コミュニティ   |
| Debian 8.7 以降および 9                                | サポート   | サポート   |
| CentOS 7                                          | サポート   | サポート   |
| Red Hat Enterprise Linux 7                        | サポート   | サポート   |
| OpenSUSE 42.3                                     | サポート   | サポート   |
| Fedora 27                                         | サポート   | サポート   |
| Fedora 28                                         |             | サポート   |
| macOS 10.12 以降                                      | サポート   | サポート   |
| Arch                                              | コミュニティ   | コミュニティ   |
| Raspbian                                          | Experimental| コミュニティ   |
| Kali                                              | コミュニティ   | コミュニティ   |
| AppImage (複数の Linux プラットフォームで機能)     | コミュニティ   | コミュニティ   |
| [Snap パッケージ](https://snapcraft.io/powershell)   | 注を参照    | 注を参照    |

> [!NOTE]
> Snap パッケージは、一定期間、試験段階になります。  その後、Snap で新しいサポートの問題が発生しないことが確認されたら、お客様がパッケージを実行しているディストリビューションをサポートがフォローします。

## <a name="platform-which-are-out-of-support"></a>サポート対象外のプラットフォーム

プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core もまたそのプラットフォームのバージョンをサポートしなくなります。 アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。

そのため、次のバージョンのサポートはディストリビューションの所有者によって終了され、現在はサポートされていません。

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

## <a name="notes-on-licensing"></a>ライセンスに関する注意事項

PowerShell Core は [MIT ライセンス][]の下で提供されます。
このライセンスの下では、また、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。
コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。

## <a name="windows-powershell-module"></a>Windows PowerShell モジュール

PowerShell Core のサポートが他の製品モジュールに適用されることは、そのモジュールが PowerShell Core 対応であることが明示されている場合を除いてありません。
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
