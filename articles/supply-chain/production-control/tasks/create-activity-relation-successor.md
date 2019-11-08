---
title: 'Creare relazione attività: attività successiva'
description: Il flusso di attività in un flusso di produzione snella viene documentato tramite relazioni tra le attività.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07ebb7d2158964a5d8862df998fe470032a0d354
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550415"
---
# <a name="create-activity-relation---successor"></a>Creare relazione attività: attività successiva

[!include [task guide banner](../../includes/task-guide-banner.md)]

Il flusso di attività in un flusso di produzione snella viene documentato tramite relazioni tra le attività. Questa registrazione mostra come creare una relazione tra attività.

Prerequisiti:

- Un flusso di produzione e una versione in modalità bozza. 

- Due attività susseguenti nel flusso di produzione vengono create ma non correlate.


## <a name="find-the-production-flow-version"></a>Trovare la versione del flusso di produzione 
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nell'elenco contrassegnare la riga selezionata.
5. Selezionare una versione bozza nell'elenco.
    * Le relazioni di attività possono essere aggiunte alle versioni bozza o attive di un flusso di produzione.  

## <a name="open-the-activity-overview"></a>Aprire la panoramica attività
1. Fare clic su Attività.
    * Si noti che il modulo mostra tutte le attività del flusso di produzione allocate alla versione dei flussi di produzione in uso.  

## <a name="add-a-successor"></a>Aggiungere un'attività successiva
1. Fare clic su Aggiungi attività successiva.
2. Nel campo Attività fare clic sul pulsante a discesa per aprire la ricerca.
3. Trovare e selezionare il record desiderato nell'elenco.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Selezionare la casella di controllo Vincolo.
6. Nel campo Valore vincolo immettere un numero.
    * La durata del vincolo è il tempo da programmare tra la fine programmata dell'attività precedente (data e ora di scadenza) e la data di inizio programmata dell'attività successiva.  
7. Digitare un valore nel campo Unità.
8. Nel campo Rapporto durata ciclo immettere un numero.
    * Se entrambe le attività vengono eseguite nello stesso tempo di produzione di un'unità, il rapporto durata ciclo deve essere 1. Se l'attività precedente viene eseguita a velocità doppia della successiva, il rapporto deve essere 2.   Il rapporto di durata ciclo viene utilizzato per calcolare le durate ciclo individuali delle attività del flusso di produzione.  
9. Fare clic su OK.
10. Chiudere la pagina.
11. Fare clic sulla scheda GridPanel.
12. Chiudere la pagina.
13. Aggiorna la pagina.

