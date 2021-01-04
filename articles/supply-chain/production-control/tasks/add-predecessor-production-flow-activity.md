---
title: Aggiungere un'attività precedente a un'attività del flusso di produzione
description: In una versione del flusso di produzione, tutte le attività devono essere in sequenza.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c39cef1174439b42a072bd7fc1ac29ef31ecf864
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430880"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Aggiungere un'attività precedente a un'attività del flusso di produzione

[!include [banner](../../includes/banner.md)]

In una versione del flusso di produzione, tutte le attività devono essere in sequenza. Un'attività può avere una o più attività precedenti o successive. 

In questa procedura viene illustrato come associare un'attività precedente a un'attività. 

Per eseguire questa attività, è necessario disporre di un flusso di produzione con la versione bozza con almeno due attività che possono essere connesse. 

Per ulteriori informazioni, leggere il white paper sui flussi di produzione e le attività nel lean manufacturing.


## <a name="find-the-production-flow-and-version"></a>Trovare il flusso e la versione del flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Fare clic su Attività.

## <a name="select-an-activity-and-add-a-predecessor"></a>Selezionare un'attività e aggiungere un'attività precedente
1. Nell'elenco trovare e selezionare il record desiderato.
2. Fare clic su Aggiungi attività precedente.
3. Nel campo Attività immettere o selezionare un valore.
4. Nel campo Rapporto durata ciclo immettere un numero.
    * Il rapporto di durata ciclo predefinito di una relazione tra attività è 1. Ciò presuppone che entrambe le attività vengano eseguite allo stesso ritmo o tempo di produzione di un'unità. Se l'attività precedente viene eseguita a ritmo più alto (tempo inferiore di produzione di un'unità), il rapporto deve essere inferiore a 1, se l'attività precedente viene eseguita a ritmo più lento (tempo superiore di produzione di un'unità) il rapporto durata ciclo è maggiore di 1.  
5. Fare clic su OK.

