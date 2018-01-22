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

PowerShell Core は次のプラットフォームで公式サポートされています。

* Windows 7、8.1、10
* Windows Server 2008 R2、2012 R2、2016
* [Windows Server 半期チャネル][semi-annual]
* Ubuntu 14.04、16.04、17.04
* Debian 8.7 以降および 9
* CentOS 7
* Red Hat Enterprise Linux 7
* OpenSUSE 42.2
* Fedora 25、26
* macOS 10.12 以降

弊社のコミュニティでは、次のプラットフォーム用のパッケージも提供していますが、正式にはサポートされていません。

* Arch Linux
* Kali Linux
* AppImage (複数の Linux プラットフォームで機能)

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
