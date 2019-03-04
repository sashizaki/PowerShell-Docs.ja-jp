---
title: 基本的な Windows PowerShell プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base provider [PowerShell Programmer's Guide]
- providers [PowerShell Programmer's Guide], base provider
ms.assetid: 11eeea41-15c8-47ad-9016-0f4b72573305
caps.latest.revision: 7
ms.openlocfilehash: 19cc3817016d96e1412a5f3506e9d694ba55b48d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861768"
---
# <a name="creating-a-basic-windows-powershell-provider"></a>基本的な Windows PowerShell プロバイダーを作成する

このトピックでは、Windows PowerShell プロバイダーを作成する方法を学習するための開始点です。 ここで説明した基本的なプロバイダーが開始と停止、プロバイダーのメソッドを提供し、このプロバイダーには、データ ストアにアクセスするか、取得またはデータ ストアにデータを設定することはできませんで必要とされる基本的な機能が、すべてのプロバイダー。

以前は、「基本的なプロバイダーを説明したようにここでの開始と、プロバイダーを停止するメソッドを実装します。 Windows PowerShell ランタイムでは、プロバイダーを初期化して、これらのメソッドを呼び出します。

> [!NOTE]
> Windows PowerShell によって提供される AccessDBSampleProvider01.cs ファイルでは、このプロバイダーのサンプルが見つかります。

このトピックのセクションは、次のとおりです。

- [Windows PowerShell プロバイダー クラスを定義します。](#Defining-the-Windows-PowerShell-Provider-Class)

- [プロバイダー固有の状態情報を定義します。](#Defining-Provider-Specific-State-Information)

- [プロバイダーの初期化](#Initializing-the-Provider)

- [動的パラメーターを開始します。](#Start-Dynamic-Parameters)

- [プロバイダーの初期化解除](#Uninitializing-the-Provider)

- [コード サンプル](#Code-Sample)

- [Windows PowerShell プロバイダーのテスト](#Testing-the-Windows-PowerShell-Provider)

## <a name="defining-the-windows-powershell-provider-class"></a>Windows PowerShell プロバイダー クラスを定義します。

Windows PowerShell プロバイダーを作成する最初の手順では、その .NET クラスを定義します。 この基本的なプロバイダーと呼ばれるクラスを定義する`AccessDBProvider`から派生した、 [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基本クラス。

プロバイダーのクラスを配置することをお勧めしますが、 `Providers` API 名前空間、xxx などの名前空間。PowerShell.Providers します。 このプロバイダーを使用して、`Microsoft.Samples.PowerShell.Provider`名前空間、すべての Windows PowerShell プロバイダーのサンプルを実行します。

> [!NOTE]
> Windows PowerShell プロバイダーのクラスする必要があります明示的にパブリックと指定します。 Public としてマークされていないクラスは、内部には既定であり、Windows PowerShell ランタイムでは検出されません。

この基本的なプロバイダーのクラス定義を次に示します。

[!code-csharp[AccessDBProviderSample01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L23-L24 "AccessDBProviderSample01.cs")]

宣言する必要があります、クラス定義の直前、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)属性には、[CmdletProvider()] 構文を使用します。

必要に応じてさらに、クラスを宣言する属性のキーワードを設定することができます。 なお、 [System.Management.Automation.Provider.Cmdletproviderattribute](/dotnet/api/System.Management.Automation.Provider.CmdletProviderAttribute)ここで宣言された属性には、2 つのパラメーターが含まれています。 属性の最初のパラメーターには、プロバイダーは、ユーザーが後で変更できる既定のわかりやすい名前を指定します。 2 番目のパラメーターには、プロバイダーがコマンドの処理中に、Windows PowerShell ランタイムに公開する Windows PowerShell で定義されている機能を指定します。 によって、プロバイダーの機能の有効な値が定義されている、 [System.Management.Automation.Provider.Providercapabilities](/dotnet/api/System.Management.Automation.Provider.ProviderCapabilities)列挙体。 これは、基本プロバイダーであるためありませんの機能をサポートします。

> [!NOTE]
> Windows PowerShell プロバイダーの完全修飾名には、アセンブリの名前と、プロバイダーの登録時に Windows PowerShell によって決定するその他の属性が含まれています。

## <a name="defining-provider-specific-state-information"></a>プロバイダー固有の状態情報を定義します。

[System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider)基底クラスとすべての派生クラスはステートレスと見なされるため、Windows PowerShell ランタイムが必要なだけのプロバイダーのインスタンスを作成します。 そのため、ご利用のプロバイダーは、フル コントロール、プロバイダー固有のデータの状態のメンテナンスを必要とする場合にする必要がありますからクラスを派生、 [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)クラス。 派生クラスは、プロバイダー固有のデータは、Windows PowerShell ランタイムが呼び出すと、アクセスできるように、状態を維持するために必要なメンバーを定義する必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)プロバイダーを初期化します。

Windows PowerShell プロバイダーは、接続ベースの状態を維持することもできます。 接続の状態を維持する詳細については、次を参照してください。 [PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)します。

## <a name="initializing-the-provider"></a>プロバイダーの初期化

プロバイダーを Windows PowerShell ランタイムを初期化するために、 [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)メソッドは、Windows PowerShell の開始時にします。 プロバイダーがこのメソッドは、単純に返すの既定の実装を使用するほとんどの場合、 [System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)プロバイダーを記述するオブジェクト。 ただし、追加の初期化情報を追加する場合は、実装すること、独自[System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start) の修正バージョンを返すメソッド[System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)をプロバイダーに渡されるオブジェクト。 一般に、このメソッドは、指定された返します[System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo) 、または、変更されたオブジェクトが渡される[System.Management.Automation.Providerinfo](/dotnet/api/System.Management.Automation.ProviderInfo)オブジェクトその他の初期化情報が含まれています。

この基本的なプロバイダーは、このメソッドをオーバーライドしません。 ただし、次のコードは、このメソッドの既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStart](Msh_samplesaccessdbprov01#accessdbprov01ProviderStart)]  -->

」の説明に従って、プロバイダーはプロバイダー固有の情報の状態を保持できる[プロバイダーに固有のデータの状態を定義する](#Defining-Provider-Specific-State-Information)します。 この場合、実装をオーバーライドする必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)派生クラスのインスタンスを返すメソッド。

## <a name="start-dynamic-parameters"></a>動的パラメーターを開始します。

プロバイダーの実装、 [System.Management.Automation.Provider.Cmdletprovider.Start*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Start)メソッドは、追加のパラメーターを必要があります。 この場合、プロバイダーをオーバーライドする必要があります、 [System.Management.Automation.Provider.Cmdletprovider.Startdynamicparameters*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.StartDynamicParameters)メソッドおよびプロパティと解析を持つフィールドを持つオブジェクトの属性のような戻り値をcmdlet クラスまたは[System.Management.Automation.Runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)オブジェクト。

この基本的なプロバイダーは、このメソッドをオーバーライドしません。 ただし、次のコードは、このメソッドの既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters](Msh_samplesaccessdbprov01#accessdbprov01ProviderDynamicParameters)]  -->

## <a name="uninitializing-the-provider"></a>プロバイダーの初期化解除

Windows PowerShell プロバイダーで使用されるリソースを解放する、プロバイダー実装する独自[System.Management.Automation.Provider.Cmdletprovider.Stop*](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.Stop)メソッド。 このメソッドは、セッションの終了時のプロバイダーの初期化解除に Windows PowerShell ランタイムによって呼び出されます。

この基本的なプロバイダーは、このメソッドをオーバーライドしません。 ただし、次のコードは、このメソッドの既定の実装を示しています。

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesaccessdbprov01#accessdbprov01ProviderStop](Msh_samplesaccessdbprov01#accessdbprov01ProviderStop)]  -->

## <a name="code-sample"></a>コード サンプル

完全なサンプル コードでは、次を参照してください。 [AccessDbProviderSample01 コード サンプル](./accessdbprovidersample01-code-sample.md)します。

## <a name="testing-the-windows-powershell-provider"></a>Windows PowerShell プロバイダーのテスト

Windows PowerShell を使用した、Windows PowerShell プロバイダーを登録すると、コマンドラインでサポートされているコマンドレットを実行してテストすることができます。 この基本的なプロバイダーに、新しいシェルを実行し、使用、`Get-PSProvider`コマンドレットをプロバイダーの一覧を取得して AccessDb プロバイダーが存在することを確認します。

```powershell
Get-PSProvider
```

次の出力が表示されます。

```output
Name                 Capabilities                  Drives
----                 ------------                  ------
AccessDb             None                          {}
Alias                ShouldProcess                 {Alias}
Environment          ShouldProcess                 {Env}
FileSystem           Filter, ShouldProcess         {C, Z}
Function             ShouldProcess                 {function}
Registry             ShouldProcess                 {HKLM, HKCU}
```

## <a name="see-also"></a>参照

[Windows PowerShell プロバイダーを作成します。](./how-to-create-a-windows-powershell-provider.md)

[Windows PowerShell プロバイダーのデザイン](./designing-your-windows-powershell-provider.md)