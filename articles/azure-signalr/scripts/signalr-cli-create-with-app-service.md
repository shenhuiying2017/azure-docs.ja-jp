---
title: Azure CLI スクリプト サンプル - App Service で SignalR サービスを作成する | Microsoft Docs
description: Azure CLI スクリプト サンプル - App Service で SignalR サービスを作成する
services: signalr
documentationcenter: signalr
author: wesmc7777
manager: cfowler
editor: ''
tags: azure-service-management
ms.service: signalr
ms.devlang: azurecli
ms.topic: sample
ms.tgt_pltfrm: na
ms.workload: signalr
ms.date: 04/20/2018
ms.author: wesmc
ms.custom: mvc
ms.openlocfilehash: 6ac1646da4c952c78bfb787b0d6ab30f4876f36a
ms.sourcegitcommit: e221d1a2e0fb245610a6dd886e7e74c362f06467
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33766395"
---
# <a name="create-a-signalr-service-with-an-app-service"></a>App Service で SignalR サービスを作成する

このサンプル スクリプトでは、リアルタイムのコンテンツ更新をクライアントにプッシュするために使用される新しい Azure SignalR サービス リソースを作成します。 このスクリプトは、SignalR サービスを使用する ASP.NET Core Web アプリをホストする新しい Web アプリと App Service プランも追加します。 Web アプリは、*AzureSignalRConnectionString* という名前のアプリ設定で構成されて、新しい SignalR サービス リソースに接続します。

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]

[!INCLUDE [cloud-shell-try-it.md](../../../includes/cloud-shell-try-it.md)]

CLI をローカルにインストールして使用する場合、この記事では、Azure CLI バージョン 2.0 以降を実行していることが要件です。 バージョンを確認するには、`az --version` を実行します。 インストールまたはアップグレードする必要がある場合は、「[Azure CLI 2.0 のインストール]( /cli/azure/install-azure-cli)」を参照してください。 

## <a name="sample-script"></a>サンプル スクリプト

このスクリプトでは、Azure CLI の *signalr* 拡張機能を使用します。 このサンプル スクリプトを使用する前に、次のコマンドを実行して Azure CLI の *signalr* 拡張機能をインストールします。

```azurecli-interactive
az extension add -n signalr
```

[!code-azurecli-interactive[main](../../../cli_scripts/azure-signalr/create-signalr-with-app-service/create-signalr-with-app-service.sh "Create a new Azure SignalR Service and Web App")]

新しいリソース グループに対して生成される実際の名前をメモしておきます。 これは出力に表示されます。 すべてのグループ リソースを削除するときに、そのリソース グループ名を使用します。

[!INCLUDE [cli-script-clean-up](../../../includes/cli-script-clean-up.md)]

## <a name="script-explanation"></a>スクリプトの説明

表内の各コマンドは、それぞれのドキュメントにリンクされています。 このスクリプトでは以下のコマンドを使用します。

| コマンド | メモ |
|---|---|
| [az group create](/cli/azure/group#az-group-create) | すべてのリソースを格納するリソース グループを作成します。 |
| [az signalr create](/cli/azure/signalr#az-signalr-create) | Azure SignalR サービスのリソースを作成します。 |
| [az signalr key list](/cli/azure/signalr/key#az-signalr-key-list) | SignalR でリアルタイム コンテンツの更新をプッシュするときにアプリケーションで使用されるキーを一覧表示します。 |
| [az appservice plan create](/cli/azure/appservice/plan#az-appservice-plan-create) | Web アプリをホストするための Azure App Service プランを作成します。 |
| [az webapp create](/cli/azure/webapp#az-webapp-create) | App Service ホスティング プランを使用して Azure Web アプリを作成します。 |
| [az webapp config appsettings set](/cli/azure/webapp/config/appsettings#az-webapp-config-appsettings-set) | Web アプリ用の新しいアプリ設定を追加します。 このアプリ設定は、SignalR 接続文字列を保存するために使用されます。 |

## <a name="next-steps"></a>次の手順

Azure CLI の詳細については、[Azure CLI のドキュメント](/cli/azure)のページをご覧ください。

Azure SignalR サービスのその他の CLI サンプル スクリプトは、[Azure SignalR サービスのドキュメント](../signalr-cli-samples.md)をご覧ください。
