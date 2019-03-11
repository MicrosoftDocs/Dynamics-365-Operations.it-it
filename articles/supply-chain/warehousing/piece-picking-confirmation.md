---
title: Conferma di prelievo pezzi
description: In questo argomento viene descritto come impostare e applicare la conferma di prelievo dei pezzi da un dispositivo mobile.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b85414dd1385dc3d8c97632eaaeb252759590ff
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "349632"
---
# <a name="piece-picking-confirmation"></a>Conferma di prelievo pezzi

[!include [banner](../includes/banner.md)]

Il prelievo dei pezzi consente di confermare ogni pezzo di magazzino tramite lavoro di prelievo o conteggio su un dispositivo mobile. Per i prelievi, è possibile confermare la quantità di lavoro da elaborare fino a quella specificata sul lavoro da prelevare. Per il lavoro di conteggio, è possibile analizzare le scorte in fase di conteggio e registrare l'importo totale.

Quando si abilita il prelievo dei pezzi, la conferma del prodotto viene selezionata automaticamente. Per i prelievi di tipo lavoro, il numero massimo di pezzi è abilitato. Consente di impostare un valore massimo per il numero di pezzi che devono essere confermati durante il processo di lavoro. La quantità massima è basata sull'unità di lavoro corrente in corso di elaborazione. Il tipo di lavoro conteggio non consente un valore massimo.

È inoltre possibile utilizzare la quantità e l'unità di misura (UOM) associata a un codice a barre letto tramite scanner. Questo funzionerà per il ricevimento sui flussi in entrata incluso il ricevimento di numero di identificazione, articolo ordine fornitore, articolo ordine di trasferimento e articolo di carico. Funziona anche con il prelievo dei pezzi in cui scansione del codice a barre aggiunge la quantità al numero totale di pezzi confermati che eseguono la conversione tra l'unità di misura sul codice a barre e l'unità di lavoro. Se durante il conteggio dell'unità di misura sul codice a barre, viene confermato che la quantità è consentita per il conteggio per il gruppo di sequenze, la quantità verrà aggiunto al conto totale.

## <a name="where-it-applies"></a>Dove si applica

Il prelievo di pezzi funziona per tutto il lavoro di conteggio per il prelievo iniziale per qualsiasi tipo di lavoro. Il prelievo dei pezzi non è applicabile se l'articoloo è controllato dai numeri di serie o se si tratta di prelievo kanban o di produzione da un'ubicazione di della targa e l'articoloo è impostato sulla gestione temporanea.

## <a name="set-up-piece-picking"></a>Impostare il prelievo di pezzi

1.  Su una voce di menu del dispositivo mobile, aprire il modulo di impostazione per la conferma di lavoro: Gestione magazzino > **Gestione magazzino** > **Impostazione** > **Dispositivo mobile** > **Voci di menu del dispositivo mobile**. 
2. Dalle voci di menu del dispositivo mobile, aprire la configurazione della conferma del lavoro.

Le opzioni seguenti diventano disponibili per la selezione quando il tipo di lavoro è prelievo o conteggio.


|           Opzione           |                                                                            descrizione                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Conferma di prelievo pezzi | Disponibile per i tipi di lavoro prelievo e conteggio. La conferma del prodotto viene selezionata automaticamente. Consente di confermare ogni pezzo di magazzino dal dispositivo mobile. |
|  Numero massimo di pezzi  |                   Disponibile per il lavoro di prelievo se la conferma di prelievo del pezzo è abilitata. Consente di impostare un limite al numero di pezzi che è necessario confermare.                   |

