# RefreshMode と ConfigurationMode の出現頻度は互いの倍数である必要はありません

[こちら](http://blogs.msdn.com/b/powershell/archive/2013/12/09/understanding-meta-configuration-in-windows-powershell-desired-state-configuration.aspx)のブログで説明されているように、以前のバージョンの DSC では、LCM は `RefreshFrequencyMins` と `ConfigurationModeFrequencyMins` を互いの倍数として処理します。 WMF 5.0 RTM では、これらのプロパティは互いに独立して処理されます。 次の表では、この動作を示しています。

**プル** モードの動作: 

|                                  |**メタ構成の値**|**メタ構成が適用された後の値**|**プルの発生頻度 (分)**|**構成の適用頻度 (分)**|
|----------------------------------|-------------------------------|---------------------------------------------|------------------------------------|------------------------------------------------|
|**ConfigurationModeFrequencyMins**|70                             |70                                           |                                    |70                                              |
|**RefreshFrequencyMins**          |40                             |40                                           |40                                  |                                                |

**プッシュ** モードの動作:

|                                  |**メタ構成の値**|**メタ構成が適用された後の値**|**構成の適用頻度 (分)**|
|----------------------------------|-------------------------------|---------------------------------------------|------------------------------------------------|
|**ConfigurationModeFrequencyMins**|70                             |70                                           |70                                              |
|**RefreshFrequencyMins**          |40                             |40                                           |                                                |
<!--HONumber=Mar16_HO2-->
