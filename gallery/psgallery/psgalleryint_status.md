---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "ギャラリー, PowerShell, コマンドレット, PSGallery"
title: psgalleryint_status
ms.openlocfilehash: 0b2f1ebcb365fcd24438a028a9c8181449266a8b
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a name="powershell-gallery-status"></a>PowerShell ギャラリーの状態
=========================

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


