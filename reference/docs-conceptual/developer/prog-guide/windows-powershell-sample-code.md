---
title: Windows PowerShell のサンプルコード |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8dcbe6d8760d77666a8191ca78416ef63dfebdeb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786936"
---
# <a name="windows-powershell-sample-code"></a>Windows PowerShell サンプル コード

Windows PowerShell®のサンプルは、Windows SDK を通じて入手できます。 このセクションには、Windows SDK のサンプルに含まれているサンプルコードが含まれています。

> [!NOTE]
> Windows SDK がインストールされると、すべての Windows PowerShell サンプルが使用可能になる**サンプル**ディレクトリが作成されます。 一般的なインストールディレクトリは**C:\Program て SDKs\Windows\v6.0**です。 Windows PowerShell を起動し、 **「cd Samples\SysMgmt\PowerShell」** と入力して、Windows powershell Samples ディレクトリを見つけます。 このドキュメントでは、Windows PowerShell Samples ディレクトリをと呼び **\<PowerShell Samples>** ます。

## <a name="sample-code-listing"></a>サンプルコードリスト

|                                    サンプル コード                                    |                                                                                                                                           説明                                                                                                                                           |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AccessDbProviderSample01 コード サンプル](./accessdbprovidersample01-code-sample.md) | これは、「基本的な[Windows PowerShell プロバイダーの作成](./creating-a-basic-windows-powershell-provider.md)」で説明されているプロバイダーです。                                                                                                                                                            |
| [AccessDbProviderSample02 コード サンプル](./accessdbprovidersample02-code-sample.md) | これは、「 [Windows PowerShell ドライブプロバイダーの作成](./creating-a-windows-powershell-drive-provider.md)」で説明されているプロバイダーです。                                                                                                                                                            |
| [AccessDbProviderSample03 コード サンプル](./accessdbprovidersample03-code-sample.md) | これは、「 [Windows PowerShell 項目プロバイダーの作成](./creating-a-windows-powershell-item-provider.md)」で説明されているプロバイダーです。                                                                                                                                                              |
| [AccessDbProviderSample04 コード サンプル](./accessdbprovidersample04-code-sample.md) | これは、「 [Windows PowerShell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」で説明されているプロバイダーです。                                                                                                                                                    |
| [AccessDbProviderSample05 コード サンプル](./accessdbprovidersample05-code-sample.md) | これは、「 [Windows PowerShell ナビゲーションプロバイダーの作成](./creating-a-windows-powershell-navigation-provider.md)」で説明されているプロバイダーです。                                                                                                                                                  |
| [AccessDbProviderSample06 コード サンプル](./accessdbprovidersample06-code-sample.md) | これは、「 [Windows PowerShell コンテンツプロバイダーを作成](./creating-a-windows-powershell-content-provider.md)する」で説明されているプロバイダーです。                                                                                                                                                        |
| [GetProc01 コード サンプル](./getproc01-code-samples.md)                             | これは、 `Get-Process` 「[最初のコマンドレットの作成](../cmdlet/creating-a-cmdlet-without-parameters.md)」で説明されている基本的なコマンドレットのサンプルです。                                                                                                                                                     |
| [GetProc02 コード サンプル](./getproc02-code-samples.md)                             | これは、 `Get-Process` 「[コマンドライン入力を処理するパラメーターの追加](../cmdlet/adding-parameters-that-process-command-line-input.md)」で説明されているコマンドレットのサンプルです。                                                                                                                       |
| [GetProc03 コード サンプル](./getproc03-code-samples.md)                             | これは、 `Get-Process` 「[パイプライン入力を処理するパラメーターの追加](../cmdlet/adding-parameters-that-process-pipeline-input.md)」で説明されているコマンドレットのサンプルです。                                                                                                                               |
| [GetProc04 コード サンプル](./getproc04-code-samples.md)                             | これは、 `Get-Process` 「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されているコマンドレットのサンプルです。                                                                                                                |
| [GetProc05 コード サンプル](./getproc05-code-samples.md)                             | この `Get-Process` コマンドレットは、「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されているコマンドレットに似ています。                                                                                                     |
| [StopProc01 コード サンプル](./stopproc01-code-samples.md)                           | これは、 `Stop-Process` 「[システムを変更するコマンドレットの作成](../cmdlet/creating-a-cmdlet-that-modifies-the-system.md)」で説明されているコマンドレットのサンプルです。                                                                                                                                    |
| [StopProcessSample04 コード サンプル](./stopprocesssample04-code-samples.md)         | これは、 `Stop-Process` 「[コマンドレットにパラメーターセットを追加する](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)」で説明されているコマンドレットのサンプルです。                                                                                                                                                      |
| [Runspace01 コード サンプル](./runspace01-code-samples.md)                           | これらは、「[指定されたコマンドを実行するコンソールアプリケーションの作成](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)」で説明されている実行空間のコードサンプルです。                                                                                      |
| [Runspace02 コード サンプル](./runspace02-code-samples.md)                           | このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、 `Get-Process` コマンドレットを同期的に実行します。                                                                                                            |
| [RunSpace03 コード サンプル](./runspace03-code-samples.md)                           | これらは、「指定されたスクリプトを実行するコンソールアプリケーションの作成」で説明されている実行空間のコードサンプルです。                                                                                                                                                                         |
| [RunSpace04 コード サンプル](./runspace04-code-samples.md)                           | これは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して終了エラーを生成するスクリプトを実行する実行空間のコードサンプルです。                                                                         |
| [RunSpace05 コード サンプル](./runspace05-code-sample.md)                             | これは、「 [RunspaceConfiguration を使用した実行空間の構成](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)」で説明されている Runspace05 サンプルのソースコードです。                                                                                                           |
| [RunSpace06 コード サンプル](./runspace06-code-sample.md)                             | これは、「 [Windows PowerShell スナップインを使用して実行空間を構成](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83)する」で説明されている Runspace06 サンプルのソースコードです。                                                                                                    |
| [RunSpace07 コード サンプル](./runspace07-code-sample.md)                             | これは、「[パイプラインにコマンドを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)」で説明されている Runspace07 サンプルのソースコードです。                                                                                              |
| [RunSpace08 コード サンプル](./runspace08-code-sample.md)                             | これは、「[コマンドにパラメーターを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)」で説明されている Runspace08 サンプルのソースコードです。                                                                                             |
| [RunSpace09 コード サンプル](./runspace09-code-sample.md)                             | これは、「[パイプラインを非同期に呼び出すコンソールアプリケーションの作成](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)」で説明されている Runspace09 サンプルのソースコードです。                                                                                        |
| [RunSpace10 コード サンプル](./runspace10-code-sample.md)                             | これは Runspace10 サンプルのソースコードであり、コマンドレットを[Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration)に追加し、変更された構成情報を使用して実行空間を作成します。 |

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
