---
title: Azure Service Fabric CLI (sfctl) スクリプトの削除のサンプル
description: Azure Service Fabric CLI を使用した Azure Service Fabric クラスターからのアプリケーションの削除
services: service-fabric
documentationcenter: ''
author: thraka
manager: timlt
editor: ''
tags: azure-service-management
ms.assetid: ''
ms.service: service-fabric
ms.workload: multiple
ms.devlang: na
ms.topic: sample
ms.date: 12/06/2017
ms.author: adegeo
ms.custom: mvc
ms.openlocfilehash: 83f2fc52debd24afd97a391466cb5a0b1a8cd93c
ms.sourcegitcommit: 266fe4c2216c0420e415d733cd3abbf94994533d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34642718"
---
# <a name="remove-an-application-from-a-service-fabric-cluster"></a>Service Fabric クラスターからのアプリケーションの削除

このサンプル スクリプトは、実行中の Service Fabric アプリケーション インスタンスを削除し、クラスターからアプリケーションの種類とバージョンの登録を解除します。  アプリケーション インスタンスを削除すると、そのアプリケーションに関連付けられている実行中のサービス インスタンスもすべて削除されます。 次に、アプリケーション ファイルがイメージ ストアから削除されます。 

必要に応じて、[Service Fabric CLI](../service-fabric-cli.md) をインストールします。

## <a name="sample-script"></a>サンプル スクリプト

[!code-sh[main](../../../cli_scripts/service-fabric/remove-application/remove-application.sh "Remove an application from a cluster")]

## <a name="next-steps"></a>次の手順

詳細については、[Service Fabric CLI ドキュメント](../service-fabric-cli.md)をご覧ください。

その他の Azure Service Fabric 用 Service Fabric CLI サンプルは、[Service Fabric CLI のサンプル](../samples-cli.md)のページにあります。
