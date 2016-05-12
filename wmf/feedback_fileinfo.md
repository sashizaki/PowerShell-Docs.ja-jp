# FileInfo オブジェクトの更新
ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。 この WMF 5.0 リリースでは、**FileVersionRaw** および **ProductVersionRaw**  
スクリプト プロパティが FileInfo オブジェクトに新しく追加されました。 powershell.exe に対して表示されるプロパティを次に示します ($pid は PowerShell プロセスの ID であるとします)。

```powershell
PS C:\> Get-Process -Id $pid -FileVersionInfo | fl *version* -Force


FileVersionRaw    : 10.0.10586.117
ProductVersionRaw : 10.0.10586.117
FileVersion       : 10.0.10586.117 (th2_release.160212-2359)
ProductVersion    : 10.0.10586.117


<!--HONumber=Apr16_HO3-->


