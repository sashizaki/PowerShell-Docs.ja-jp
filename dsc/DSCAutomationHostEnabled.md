
---
タイトル:   DSCAutomationHostEnabled レジストリ キー ms.date:  2016-05-16 キーワード:  powershell,DSC 説明:  
ms.topic:  記事 作成者: eslesar マネージャー: dongill ms.prod:  powershell
---

>適用先: Windows PowerShell 5.0

# <a name="dscautomationhostenabled-registry-key"></a>DSCAutomationHostEnabled レジストリ キー

DSC は、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies** の下の **DSCAutomationHostEnabled** というレジストリ キーを使用してコンピューターの起動時に自動的に構成を行います。
DSCAutomationHostEnabled では、次の 3 つのモードがサポートされます。

|  DSCAutomationHostEnabled の値  |  説明   | 
|---|---| 
0 | 起動時にコンピューターの構成を行いません。 |
1 で保護されたプロセスとして起動されました | 起動時にコンピューターの構成を行います。 |
2 | コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。 これは、既定値です。 |

## <a name="see-also"></a>参照

この機能を使用して初回起動時に構成を実行する方法の例については、「[DSC を使用した初回起動時の仮想マシンの構成](bootstrapDsc.md)」をご覧ください。


