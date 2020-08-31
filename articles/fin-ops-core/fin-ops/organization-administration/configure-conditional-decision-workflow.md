---
title: Configurare le decisioni condizionali in un flusso di lavoro
description: Per configurare le proprietà di una decisione condizionale, attenersi alla procedura indicata di seguito.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a953d4e781db42834f0bc8daf80040c39ea5b5c
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698122"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>Configurare le decisioni condizionali in un flusso di lavoro

[!include [banner](../includes/banner.md)]

Per configurare le proprietà di una decisione condizionale, attenersi alla procedura indicata di seguito.

Una decisione condizionale rappresenta un punto nel quale un flusso di lavoro si divide in due rami. Per configurare una decisione condizionale, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sulla decisione e scegliere **Proprietà** per aprire il modulo **Proprietà**.

## <a name="name-a-decision"></a>Assegnare un nome a una decisione

Per immettere un nome per una decisione condizionale, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Nome** immettere un nome univoco per la decisione condizionale.

## <a name="set-conditions"></a> Impostare condizioni

Il sistema determina quale ramo utilizzare valutando il documento inviato per determinare se soddisfa le condizioni specifiche.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Fare clic su **Aggiungi condizione**.
3. Immettere una condizione.
4. Immettere altre condizioni, se necessario.
5. Per verificare la correttezza della configurazione delle condizioni immesse, eseguire i passaggi seguenti:

    1. Fare clic su **Test** per aprire il modulo **Test condizione flusso di lavoro**.
    2. Selezionare un record nell'area **Convalida condizione** del modulo.
    3. Fare clic su **Test**. Il sistema valuta il record per determinare se soddisfa le condizioni definite.
    4. Fare clic su **OK** o **Annulla** per tornare al modulo **Proprietà**.
