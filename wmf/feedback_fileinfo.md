# FileInfo オブジェクトの更新
ファイルのバージョン情報は、特にファイルにパッチが適用された場合に、解釈を間違えやすいデータです。 今回の WMF Production Preview リリースでは、FileInfo オブジェクトに新しいスクリプト プロパティとして **FileVersionRaw** および **ProductVersionRaw** が追加されました。 powershell.exe で各プロパティがどのように表示されるかを次の例に示します。

PS C:\\&gt; Get-Process -Id $pid -FileVersionInfo | fl \*version\* -Force

FileVersionRaw : 10.0.10055.0

ProductVersionRaw : 10.0.10055.0

FileVersion : 10.0.10055.0 (fbl\_srv2.150402-1826)

ProductVersion : 10.0.10055.0
<!--HONumber=Mar16_HO2-->
