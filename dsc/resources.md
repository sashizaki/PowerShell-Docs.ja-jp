# DSC リソース

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。 リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。

リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。  リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。  

次のトピックでは、DSC リソースについて説明します。

- [組み込み DSC リソース](builtInResource.md)
- [カスタム DSC リソースのビルド](authoringResource.md)
- [Linux 用組み込み DSC リソース](lnxBuiltInResources.md)<!--HONumber=Feb16_HO4-->
