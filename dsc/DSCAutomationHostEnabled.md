
DSC は、<b>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System</b> の下の <b>DSCAutomationHostEnabled</b> というレジストリ キーを使用してコンピューターの起動時に自動的に構成を行います。
DSCAutomationHostEnabled では、次の 3 つのモードがサポートされます。

|  DSCAutomationHostEnabled の値  |  説明   | 
|---|---| 
0 | 起動時にコンピューターの構成を行いません。 |
1 で保護されたプロセスとして起動されました | 起動時にコンピューターの構成を行います。 |
2 | コンピューターの構成は、DSC の状態が保留中または最新の場合にのみ行います。 これは、既定値です。 |




<!--HONumber=Oct16_HO2-->


