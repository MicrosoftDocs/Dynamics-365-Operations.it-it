---
title: Creare un piano per un sito
description: Il pianificatore di produzione calcola i fabbisogni di capacità e materiali per la produzione di un articolo specifico.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ac906617d7c10c2c2884636d1b694bb878bb37c9946e873456da59e72f695c2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714308"
---
# <a name="create-a-plan-for-a-site"></a>Creare un piano per un sito

[!include [banner](../../includes/banner.md)]

Il pianificatore di produzione calcola i fabbisogni di capacità e materiali per la produzione di un articolo specifico. Una volta creati i suggerimenti di approvvigionamento, trova gli ordini presso il sito per il quale effettua la pianificazione e consolida gli ordini, a partire da quelli urgenti. Gli ordini più urgenti sono quelli che devono essere consolidati alla data corrente. Utilizzare la società di dati dimostrativi USMF per eseguire queste attività.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Creare un piano di capacità e materiali per un articolo
1. Fare clic su Pianificazione generale.
    * È necessario passare al dashboard predefinito.  
2. Fare clic su Esegui.
3. Espandere la sezione Record da includere.
4. Fare clic su Filtro.
5. Nell'elenco contrassegnare la riga selezionata.
6. Digitare un valore nel campo Criteri.
    * Esempio: D0001  
7. Fare clic su OK.
8. Fare clic su OK.
    * Il processo può richiedere alcuni minuti.  
9. Aggiorna la pagina.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Identificare gli ordini urgenti pianificati per l'articolo
1. Aprire il filtro dalla colonna Numero articolo.
2. Applicare un filtro sul campo "Numero articolo" con un valore pari a "D0001" tramite l'operatore di filtro "inizia con".
3. Aprire il filtro della colonna Data ordine.
4. Applicare un filtro nel campo "Data ordine", con un valore di data corrente, utilizzando l'operatore "è esattamente".

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Stabilizzare tutti gli ordini urgenti per l'articolo
1. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
2. Fare clic su Stabilizza.
3. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]