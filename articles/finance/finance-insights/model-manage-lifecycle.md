---
title: Ciclo di vita della gestione dei modelli
description: Questo argomento descrive modi per gestire i modelli di Machine Learning dell'organizzazione per ottimizzare le previsioni che generano.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: a7b57bc0322e0f9a78dddfb924e379ac05ffca32
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722096"
---
# <a name="model-management-lifecycle"></a>Ciclo di vita della gestione dei modelli

[!include [banner](../includes/banner.md)]

Questo argomento descrive modi per gestire i modelli di Machine Learning dell'organizzazione per ottimizzare le previsioni che generano.

Consigliamo di eseguire il training del modello di intelligenza artificiale in un ambiente sandbox e di utilizzare soluzioni gestite per distribuirlo in un ambiente di produzione. Questo approccio consente di garantire che vengano attuati i controlli corretti per la gestione del ciclo di vita del modello.

Poiché il modello di intelligenza artificiale si basa sulla fattura disponibile e sui dati cliente, è importante che l'ambiente sandbox disponga di una copia recente dei dati di produzione. È possibile iniziare a eseguire il training del modello eseguendo i passaggi in [Utilizza le previsioni di pagamento dei clienti](use-customer-payment-predictions.md). Dopo aver rieseguito il training del modello, valutare i risultati come descritto in [Valutare il modello iniziale di previsione del pagamento del cliente](evaluate-payment-prediction.md). Utilizzare le informazioni in [Migliora il modello di previsione](improve-model.md) per sperimentare combinazioni di funzionalità e filtri che possono migliorare il modello.

Quando si è soddisfatti dei risultati del training, eseguire i passaggi in [Distribuire il modello di intelligenza artificiale](/ai-builder/distribute-model) per trasferire il modello nell'ambiente di produzione.
