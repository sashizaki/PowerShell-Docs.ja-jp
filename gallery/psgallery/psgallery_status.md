---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: psgallery_status
ms.openlocfilehash: 08d09ce83b5133598152186e12fc8ced90c36a88
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
<a name="powershell-gallery-status"></a>PowerShell ギャラリーの状態
=========================
## <a name="10102017---powershell-gallery-unavailable-for-2-hours-101017"></a>2017/10/10 - PowerShell ギャラリーが 2017/10/10 に 2 時間にわたり利用不能に

__影響の概要__: PowerShell ギャラリーで 2017 年 10 月 10 日午後 5 時頃 (PDT) から長時間にわたって待機時間が大幅に増加し、接続障害が断続的に発生しました。 この問題の解決にあたり、午後 10 時頃 (PDT) から 2 時間にわたってサイトがオフラインとなりました。 サイトは、2017 年 10 月 11 日午前 0 時の直前に復旧されました。

__根本原因__: 待機時間が増加した根本原因は現在も調査中です。

__解決策__: 直接的な問題への対応のため、Web サービスをオフラインにして復元する必要がありました。

__次のステップ__: 本来の問題の根本原因を調査中です。

## <a name="06012017---deploy-to-azure-automation-currently-unavailable"></a>2017/06/01 - Azure Automation へのデプロイが現在使用できない

__影響の概要__: PowerShell ギャラリーからの Azure Automation に関係する項目のデプロイは現在使用できません。  Azure Automation 内の PowerShell ギャラリーからのアイテムのインポートは引き続き使用できます。

__根本原因__: 他のアイテムに依存関係があり、Azure Automation に以前にデプロイされているアイテムは、Azure Automation にはデプロイされません。 エンジニアは、Azure Automation への機能的なデプロイに関係するアイテムのために ARM テンプレートを生成する方法の問題点を確認しました。

__解決策__: エンジニアが問題の解決に取り組んでいます。  現在のユーザーの回避策は、Azure Automation 内の PowerShell ギャラリーからアイテムをインポートすることです。

__次のステップ__: エンジニアは、まもなく修正プログラムをリリースします。  それまでは、お勧めした回避策をご使用ください。


## <a name="04112017---users-unable-to-log-in-with-azure-active-directory-aad-accounts"></a>2017/04/11 - ユーザーが Azure Active Directory (AAD) アカウントでログインできません

__影響の概要__: 一部のユーザーが Azure AD アカウントを使用して PowerShell ギャラリーにログインすることできませんでした。

__根本的な原因__: AAD とより安全にやりとりするために更新している途中で、変更できなかった設定がありました。
変更を検証するために行われたテストに特定の種類の AAD アカウントが含まれておらず、そのような状態で展開が進みました。

__解決__: 不足している設定をエンジニアが特定し、問題を修正しました。

__次の手順__: 幅広い AAD アカウントの種類が含まれるようにテストを修正する予定です。

## <a name="03272017---resolved-unable-to-see-individual-module-and-script-pages"></a>2017/03/27 - 解決済み - 個々のモジュールとスクリプトのページを表示できません

__影響の概要__: https://www.powershellgallery.com の個々のモジュールとスクリプト ページへのダイレクト リンクが破損していました。 この問題はすべての地域で報告されていました。 この問題は、どの PowerShellGet コマンドレットにも影響を与えていませんでした。すなわち、Install-Module、Install-Script、Update-Module、Update-Script、Publish-Module、Publish-Script は引き続き動作していました。

__根本的な原因__: エンジニアは、ページ上にある Facebook などのソーシャル メディア ボタンの表示が原因であることが確認されています。

__解決策__: エンジニアは、Facebook のカウント情報を無効にして問題を解決しました。

__次のステップ__: 内部的な追跡の問題をオープンにし、Facebook API の使用内容を修正しました。

## <a name="12152016---unable-to-send-emails-via-powershellgallery-website"></a>2016 年 12 月 15 日 - PowerShellGallery Web サイトからメールを送信できない

__影響の概要__: 2016 年 12 月 13 日と 2016 年 12 月 15 日に、[Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] から送信されたメッセージが、PowerShell ギャラリーの管理者に届きませんでした。
__根本的な原因__: SMTP サーバーでの認証の問題でした。
__解決策__: 認証の問題を解決し、SMTP サーバーへの接続を復元しました。
__次の手順__: この間に [Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] のリンクを使って cgadmin@microsoft.com にメールを送り、返信がない場合は、もう一度やり直してください。 ご不便をおかけして申し訳ございませんでした。



## <a name="8102016---resolved-unable-to-send-emails-to-cgadminmicrosoftcom"></a>2016 年 8 月 10 日 - 解決: 電子メールを cgadmin@microsoft.com に送信できない

__影響の概要__: 2016 年 8 月 5 日から 2016 年 8 月 10 日までの期間中、お客様による cgadmin@microsoft.com に電子メールの送信、または [お問い合わせ先] 機能の使用ができませんでした。
__根本的な原因__: エンジニアは、電子メール アカウントの構成の変更に原因があることを突き止めました。
__解決策__: エンジニアは、構成の問題を解決するための作業を行いました。
__次の手順__: この期間中に [お問い合わせ先] リンクを使用、または cgadmin@microsoft.com にメールを送信したお客様には応答できていませんので、やり直してください。 ご不便をおかけして申し訳ございませんでした。



## <a name="7132016---download-items-failed"></a>2016 年 7 月 13 日 - アイテムのダウンロードに失敗しました

__影響の概要__: 2016 年 7 月 11 日から 2016 年 7 月 13 日までの期間中に一部のお客様で、PowerShell ギャラリーからアイテムをダウンロードする際に問題が発生しました。 この問題は、Install-Module/Install-Script および Save-Module/Save-Script から返された次のエラー メッセージに示されていたようです。

```powershell
PS C:\> Install-Module xStorage
PackageManagement\Install-Package : Package 'xStorage' failed to be installed because:
End of Central Directory record could not be found. At C:\Program
Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1375 char:21 + ...
$null = PackageManagement\Install-Package @PSBoundParameters +
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ + CategoryInfo : InvalidResult:
(xStorage:String) [Install-Package], Exception + FullyQualifiedErrorId : Package '{0}'
failed to be installed because: {1},Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

__暫定的な根本原因__: エンジニアは、2016 年 7 月 11 日に PowerShell ギャラリーに展開した Azure コンテンツ配信ネットワーク (CDN) に関係する問題であることを突き止めました。
__対応策__: エンジニアは、PowerShell ギャラリーで Azure CDN を無効にしました。
__次の手順__: 根本原因を調査し、今後の問題発生を防止するためのソリューションを開発します。


## <a name="5192016---download-items-failed"></a>2016 年 5 月 19 日 - アイテムのダウンロードに失敗しました
__影響の概要__: 2016 年 5 月 17 日から 2016 年 5 月 19 日までの期間中に一部のお客様で、PowerShell ギャラリーからアイテムをダウンロードする際に問題が発生しました。 この問題は、Install-Module/Install-Script および Save-Module/Save-Script から返された次のエラー メッセージに示されていたようです。

```powershell
VERBOSE: Hash for package 'AzureRM.OperationalInsights' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='AzureRM.OperationalInsights', version='1.0.8',
destination='C:\Users\jbritt\AppData\Local\Temp\2\1741355729'
WARNING: Package 'AzureRM.OperationalInsights' failed to be installed because:
End of Central Directory record could not be found.
WARNING: Dependent Package 'AzureRM.OperationalInsights' failed to install.
WARNING: Package 'AzureRM' failed to install.
VERBOSE: Module 'AzureRM.Network' was saved successfully.
VERBOSE: Saving the dependency module 'AzureRM.NotificationHubs' with version '1.0.8' for the
module 'AzureRM'.
VERBOSE: Module 'AzureRM.NotificationHubs' was saved successfully.
PackageManagement\Save-Package : Unable to save the module 'AzureRM'. At C:\Program
Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1187 char:21 +
$null = PackageManagement\Save-Package @PSBoundParameters +
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ +
CategoryInfo : InvalidOperation: (Microsoft.Power...ets.SavePackage:SavePackage)
[Save-Package], Exception + FullyQualifiedErrorId : ProviderFailToDownloadFile,
Microsoft.PowerShell.PackageManagement.Cmdlets.SavePackage
```

__暫定的な根本原因__: エンジニアは、2016 年 5 月 17 日に PowerShell ギャラリーに展開した Azure コンテンツ配信ネットワーク (CDN) の基になるプロバイダーで障害が発生したことを突き止めました。
__対応策__: エンジニアは、PowerShell ギャラリーで Azure CDN を無効にしました。
__次の手順__: 根本原因を調査し、今後の問題発生を防止するためのソリューションを開発します。