---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリー アカウントを作成する
ms.openlocfilehash: 3ec9ad8f979fc0b88fbee72fc28ad1e3394eb01d
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
## <a name="creating-a-powershell-gallery-account"></a>PowerShell ギャラリー アカウントを作成する

PowerShell ギャラリー アカウントは、PowerShell ギャラリーに何らかのアイテムを公開する前に登録する必要があります。
PowerShell ギャラリー アカウントは、Azure Active Directory のメールが有効なアカウント、または Microsoft のメール アカウント (ドメインが outlook.com、hotmail.com など) に紐付けられている必要があります。

PowerShell ギャラリー アカウントを作成するには、https://PowerShellGallery.com にアクセスして [Register]\(登録\) をクリックしてください (下の図をご覧ください)。

![新規アカウントの作成](../../Images/CreatingAccount-Register.png)

Azure Active Directory アカウントを使用する場合は、次のページで [職場または学校アカウント] を選択し、ご利用のアカウントでログインします。
Microsoft アカウント (Outlook.com や Hotmail.com などのドメイン) を使用する場合、[個人アカウント] を選択してログインします。

ログインすると、PowerShell ギャラリーで使用するユーザー名を入力するよう求めるメッセージが表示されます。
リンクされている利用規約とプライバシー ポリシーを確認したら、ユーザー名を入力して [登録] をクリックします。

注: このアカウント名は、一度作成すると変更できません。
これに関連するその他の詳細については、「[アイテムの所有者を管理する](https://msdn.microsoft.com/powershell/gallery/psgallery/managing-item-owners)」をご覧ください。

## <a name="recommended-practices-for-powershell-gallery-accounts"></a>PowerShell ギャラリー アカウントの推奨プラクティス

PowerShell ギャラリー アカウントで使用されるメール アカウントを積極的に監視することが重要です。
PowerShell ギャラリー アイテムの所有者とのやりとりはすべて、ご利用の PowerShell ギャラリー アカウントに関連付けられたアドレスでのメールで行われます。
Microsoft からアイテムの所有者に連絡がとれない場合、特定の状況下では、運用チームにアイテムの削除を求めることがあります。

PowerShell ギャラリーに公開を行う組織が、その目的で Outlook.com や別の Microsoft アカウントのドメインを使用して一意のアカウントを作成することは頻繁にあります。
多くの場合、そのアカウントは定期的に監視されません。
こうした場合のベスト プラクティスは、Outlook の転送機能を使用して、アイテム所有者の監視対象となる別のアカウント (通常は組織内のアカウント) にメールを送信することです。

1 つのアイテムに複数の所有者が関連付けられている場合、PowerShell ギャラリーから発生するやりとりはすべて、すべての所有者に送信されます。
アイテムへの所有者の追加について詳しくは、「[アイテムの所有者を管理する](https://msdn.microsoft.com/powershell/gallery/psgallery/managing-item-owners)」をご覧ください。