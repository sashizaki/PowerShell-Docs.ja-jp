---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psgallery_status
ms.technology: powershell
ms.openlocfilehash: 40ebfa510abe647d80a85fa15f0b777d697ffdfb
ms.sourcegitcommit: 26c3acb3dae9f7c3868a5f0d6144e9e1a0d02557
translationtype: HT
---
<a name="powershell-gallery-status"></a>PowerShell ギャラリーの状態
=========================


## <a name="12152016---unable-to-send-emails-via-powershellgallery-website"></a>2016 年&12; 月&15; 日 - PowerShellGallery Web サイトからメールを送信できない

__影響の概要__: 2016 年 12 月 13 日と 2016 年 12 月 15 日に、[Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] から送信されたメッセージが、PowerShell ギャラリーの管理者に届きませんでした。  
__根本的な原因__: SMTP サーバーでの認証の問題でした。  
__解決策__: 認証の問題を解決し、SMTP サーバーへの接続を復元しました。  
__次の手順__: この間に [Contact Owners (所有者に連絡)]、[Manage Owners (所有者の管理)]、[サポートに連絡]、または [不正使用を報告] のリンクを使って cgadmin@microsoft.com にメールを送り、返信がない場合は、もう一度やり直してください。 ご不便をおかけして申し訳ございませんでした。  



## <a name="8102016---resolved-unable-to-send-emails-to-cgadminmicrosoftcom"></a>2016 年&8; 月&10; 日 - 解決: 電子メールを cgadmin@microsoft.com に送信できない

__影響の概要__: 2016 年 8 月 5 日から 2016 年 8 月 10 日までの期間中にお客様は cgadmin@microsoft.com, に電子メールを送信することも、[お問い合わせ先] 機能を使用することもできませんでした。  
__根本的な原因__: エンジニアは、電子メール アカウントの構成の変更に原因があることを突き止めました。  
__解決策__: エンジニアは、構成の問題を解決するための作業を行いました。  
__次の手順__: この期間中に [お問い合わせ先] リンクを使用、または cgadmin@microsoft.com にメールを送信したお客様には応答できていませんので、やり直してください。 ご不便をおかけして申し訳ございませんでした。



## <a name="7132016---download-items-failed"></a>2016 年&7; 月&13; 日 - アイテムのダウンロードに失敗しました

__影響の概要__: 2016 年 7 月 11 日から 2016 年 7 月 13 日までの期間中に一部のお客様で、PowerShell ギャラリーからアイテムをダウンロードする際に問題が発生しました。 この問題は、Install-Module/Install-Script および Save-Module/Save-Script から返された次のエラー メッセージに示されていたようです。

```PowerShell
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


## <a name="5192016---download-items-failed"></a>2016 年&5; 月&19; 日 - アイテムのダウンロードに失敗しました
__影響の概要__: 2016 年 5 月 17 日から 2016 年 5 月 19 日までの期間中に一部のお客様で、PowerShell ギャラリーからアイテムをダウンロードする際に問題が発生しました。 この問題は、Install-Module/Install-Script および Save-Module/Save-Script から返された次のエラー メッセージに示されていたようです。

```PowerShell
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

