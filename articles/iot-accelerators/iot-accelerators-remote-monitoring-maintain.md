---
title: リモート監視ソリューションでのデバイスのトラブルシューティング - Azure | Microsoft Docs
description: このチュートリアルでは、トラブルシューティングを行ってリモート監視ソリューションでのデバイスの問題を修復する方法を示します。
author: dominicbetts
manager: timlt
ms.author: dobett
ms.service: iot-accelerators
services: iot-accelerators
ms.date: 05/01/2018
ms.topic: conceptual
ms.openlocfilehash: 9a620d91238393ba0bde89f521f790b58ab35baf
ms.sourcegitcommit: 266fe4c2216c0420e415d733cd3abbf94994533d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34628074"
---
# <a name="troubleshoot-and-remediate-device-issues"></a>トラブルシューティングを行ってデバイスの問題を修復する

このチュートリアルでは、トラブルシューティングを行ってデバイスの問題を修復するために、ソリューションの **[メンテナンス]** ページを使用する方法を示します。 これらの機能を紹介するために、このチュートリアルでは Contoso IoT アプリケーションのシナリオを使用します。

Contoso は、フィールド内の新しい**プロトタイプ** デバイスをテストしています。 Contoso の運用者であるあなたは、テスト中に**プロトタイプ** デバイスがダッシュボード上で予期せぬ温度アラートをトリガーしていることに気付きます。 今すぐこの異常のある**プロトタイプ** デバイスの動作を調査する必要があります。

このチュートリアルで学習する内容は次のとおりです。

>[!div class="checklist"]
> * **[メンテナンス]** ページを使用してアラートを調査する
> * デバイス メソッドを呼び出して問題を修復する

## <a name="prerequisites"></a>前提条件

このチュートリアルを実行するには、お使いの Azure サブスクリプションにリモート監視ソリューションのインスタンスをデプロイしておく必要があります。

まだリモート監視ソリューションをデプロイしていない場合は、「[リモート監視ソリューション アクセラレータをデプロイする](iot-accelerators-remote-monitoring-deploy.md)」チュートリアルを実行する必要があります。

## <a name="use-the-maintenance-dashboard"></a>メンテナンス ダッシュボードの使用

**[ダッシュボード]** ページに、**プロトタイプ** デバイスに関連付けられたルールから生じる予期しない温度アラートがあることに気付きます。

![ダッシュボードに表示されているアラート](./media/iot-accelerators-remote-monitoring-maintain/dashboardalarm.png)

問題をさらに調査するため、アラートの横にある **[Explore Alert] (アラートの確認)** オプションを選択します。

![ダッシュボードでアラートを確認する](./media/iot-accelerators-remote-monitoring-maintain/dashboardexplorealarm.png)

アラートの詳細ビューには、以下が表示されます。

* アラートがトリガーされた時間
* アラートに関連付けられているデバイスに関する状態の情報
* アラートに関連付けられているデバイスのテレメトリ

![[アラートの詳細]](./media/iot-accelerators-remote-monitoring-maintain/maintenancealarmdetail.png)

アラートを確認するには、**[Alert occurrences] (発生したアラート)**、**[Acknowledge] (確認)** を選択します。 このアクションにより、他の運用者は、アラートが確認済みであり、対応中であることを知ることができます。

![アラートを確認する](./media/iot-accelerators-remote-monitoring-maintain/maintenanceacknowledge.png)

アラートを確認すると、発生の状態は **[承認済み]** に変わります。

一覧では、温度アラートを発生させた**プロトタイプ** デバイスを表示できます。

![アラートの原因となったデバイスを一覧表示する](./media/iot-accelerators-remote-monitoring-maintain/maintenanceresponsibledevice.png)

## <a name="remediate-the-issue"></a>問題を修復する

**プロトタイプ** デバイスの問題を修復するには、デバイスで **DecreaseTemperature** メソッドを呼び出す必要があります。

デバイスに対処するには、デバイスの一覧でデバイスを選択して、**[ジョブ]** を選択します。 **プロトタイプ** デバイス モデルでは、デバイスでサポートする必要のある 6 つのメソッドを指定します。

![デバイスでサポートされているメソッドを表示する](./media/iot-accelerators-remote-monitoring-maintain/maintenancemethods.png)

**DecreaseTemperature** を選択して、ジョブの名前を **DecreaseTemperature** に設定します。 **[適用]** を選択します。

![温度を低下させるジョブを作成する](./media/iot-accelerators-remote-monitoring-maintain/maintenancecreatejob.png)

**[メンテナンス]** ページでジョブの状態を追跡するには、**[ジョブ]** を選択します。 **[ジョブ]** ビューを使用して、ソリューション内のすべてのジョブとメソッドの呼び出しを追跡します。

![温度を低下させるジョブを監視する](./media/iot-accelerators-remote-monitoring-maintain/maintenancerunningjob.png)

特定のジョブまたはメソッドの呼び出しの詳細を表示するには、**[ジョブ]** ビューの一覧で選択します。

![ジョブの詳細を表示する](./media/iot-accelerators-remote-monitoring-maintain/maintenancejobdetail.png)

## <a name="next-steps"></a>次の手順

このチュートリアルで説明する内容は次のとおりです。

<!-- Repeat task list from intro -->
>[!div class="checklist"]
> * **[メンテナンス]** ページを使用してアラートを調査する
> * デバイス メソッドを呼び出して問題を修復する

ここではデバイスの問題の管理方法を説明しました。推奨する次のステップは、[シミュレートされたデバイスを使用したソリューションのテスト](iot-accelerators-remote-monitoring-test.md)の方法の学習です。

<!-- Next tutorials in the sequence -->