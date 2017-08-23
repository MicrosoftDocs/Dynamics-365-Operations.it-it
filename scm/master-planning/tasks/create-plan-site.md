--- 
title: Creare un piano per un sito
description: "Il pianificatore di produzione calcola i fabbisogni di capacità e materiali per la produzione di un articolo specifico."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d89d34d4d429faf87c70943961f7141a6258d482
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-plan-for-a-site"></a>Creare un piano per un sito

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


