---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psget_moduledependencypopulation
ms.technology: powershell
ms.openlocfilehash: 3d89dddf2fc31a9fdb1a57f21baaf757990989c7
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
translationtype: HT
---
# <a name="logic-for-preparing-the-module-dependencies-during-publish-operation"></a>発行操作中にモジュールの依存関係を準備するためのロジック
1.  RequiredModules の一部として一覧表示されているモジュールは、依存関係として見なされます。
2.  NestedModules の一部として一覧表示されているモジュール (モジュール ベースが指定されたモジュール ベースの下にないモジュール) は、依存関係として見なされます。

3.  上記の依存関係は同じターゲット リポジトリで利用できる必要があります。それ以外の場合、発行操作を実行するとエラーが発生します。
    たとえば、'SnippetPx' をリポジトリで使用できない場合は、以下のエラーがスローされます。
    ```powershell
    Publish-PSArtifactUtility : PowerShellGet cannot resolve the module dependency 'SnippetPx' of the module 'TypePx' on the repository 'LocalRepo'. Verify that the dependent module 'SnippetPx' is available in the repository 'LocalRepo'. If this dependent
    'SnippetPx' is managed externally, add it to the ExternalModuleDependencies entry in the PSData section of the module manifest.
    ```
4.  一部のモジュールの依存関係は外部で管理できます。その場合は、モジュール マニフェストの PSData セクション内の ExternalModuleDependencies エントリに追加する必要があります。
    上記のエラー メッセージの後半部分
    ```powershell
    If this dependent 'SnippetPx' is managed externally, add it to the ExternalModuleDependencies entry in the PSData section of the module manifest.
    ```

*モジュールのインストール時に、上記の準備された依存関係一覧が依存関係のインストールに使用されます。*

*発行操作中にモジュールの依存関係がシステムの $env:PSModulePath で使用可能なことを確認してください。*

