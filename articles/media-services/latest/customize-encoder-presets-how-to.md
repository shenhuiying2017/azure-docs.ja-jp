---
title: Azure Media Services v3 を使用するカスタム変換のエンコード | Microsoft Docs
description: このトピックでは、Azure Media Services v3 を使用して、カスタム変換をエンコードする方法を示します。
services: media-services
documentationcenter: ''
author: Juliako
manager: cflower
editor: ''
ms.service: media-services
ms.workload: ''
ms.topic: article
ms.custom: ''
ms.date: 05/17/2018
ms.author: juliako
ms.openlocfilehash: d298070877a366d04b2df1ef8ac63b08f8771de0
ms.sourcegitcommit: 266fe4c2216c0420e415d733cd3abbf94994533d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34660151"
---
# <a name="how-to-encode-with-a-custom-transform"></a>カスタム変換を使用してエンコードする方法

Azure Media Services でエンコードする場合、[ファイルのストリーミング](stream-files-tutorial-with-api.md)に関するチュートリアルに示されている業界のベスト プラクティスに基づき、推奨される組み込みプリセットのいずれかを使用して、すぐに作業を開始することができます。また、特定のシナリオやデバイスの要件を対象とする場合には、カスタム プリセットを作成することを選択できます。 

> [!Note]
> Azure Media Services v3 では、エンコード ビット レートはすべてビット/秒単位となります。 これは、REST v2 Media Encoder Standard のプリセットとは異なります。 たとえば、v2 のビットレートは 128 として指定されますが、v3 では 128000 となります。

## <a name="download-the-sample"></a>サンプルのダウンロード

次のコマンドを使って、.NET Core サンプルが含まれる GitHub リポジトリを、ご利用のコンピューターに複製します。  

 ```bash
 git clone https://github.com/Azure-Samples/media-services-v3-dotnet-core-tutorials.git
 ```
 
カスタム プリセットのサンプルは、[EncodeCustomTransform](https://github.com/Azure-Samples/media-services-v3-dotnet-core-tutorials/blob/master/NETCore/EncodeCustomTransform/) フォルダーにあります。

## <a name="create-a-transform-with-a-custom-preset"></a>カスタム プリセットを使用して変換を作成する 

新しい [Transform](https://docs.microsoft.com/rest/api/media/transforms) を作成するときは、出力として生成するものを指定する必要があります。 必須のパラメーターは、下記のコードで示すように **TransformOutput** オブジェクトです。 各 **TransformOutput** には **Preset** が含まれます。 **Preset** では、目的の **TransformOutput** の生成に使用されるビデオやオーディオの処理操作の詳細な手順が記述されています。 次の **TransformOutput** では、カスタム コーデックとレイヤー出力の設定を作成します。

[Transform](https://docs.microsoft.com/rest/api/media/transforms) を作成するときは、次のコードに示すように、最初に **Get** メソッドを使って変換が既に存在するかどうかを確認する必要があります。  Media Services v3 では、エンティティが存在しない場合 (大文字と小文字の区別がない名前のチェック)、エンティティに対する **Get** メソッドは **null** を返します。

[!code-csharp[Main](../../../media-services-v3-dotnet-core-tutorials/NETCore/EncodeCustomTransform/MediaV3ConsoleApp/Program.cs#EnsureTransformExists)]

## <a name="next-steps"></a>次の手順

[ファイルのストリーミング](stream-files-tutorial-with-api.md) 
