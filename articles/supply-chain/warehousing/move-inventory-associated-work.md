---
title: Movimento di magazzino con lavoro associato nella gestione magazzino
description: Utilizzo il movimento dell'inventario, è possibile decidere quali lavoratori del magazzino sono autorizzati a spostare le scorte prenotate.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6477a91b3c65e8be5ab527eaff12c92ae7918b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808752"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Movimento di magazzino con lavoro associato nella gestione magazzino

[!include [banner](../includes/banner.md)]

Utilizzo il movimento dell'inventario, è possibile decidere quali lavoratori del magazzino sono autorizzati a spostare le scorte prenotate. In questo modo si ottiene una flessibilità nei magazzini regolamentati in cui è possibile scegliere di non consentire a un lavoratore di selezionare una nuova ubicazione di prelievo per il lavoro del prelievo che è già creato. Consente inoltre a un responsabile del magazzino di verificare quali competenze dovrebbero avere alcuni lavoratori con meno esperienza.

La flessibilità di gestire le operazioni giornaliere dei lavoratori di magazzino può essere utile in scenari come i seguenti:

## <a name="scenario-1"></a>Scenario 1

Una società ha un'area di ricevimenti relativamente piccola, congestionata con pallet e scatole in attesa di stoccaggio. Una spedizione consistente è programmata per il giorno corrente, pertanto l'addetto al ricevimento decide di sistemare l'area di ricevimento spostando alcuni dei pallet in un'area di gestione temporanea.

## <a name="scenario-2"></a>Scenario 2

Un lavoratore di magazzino esperto nota che in un magazzino vi è l'opportunità di consolidare gli articoli in un'ubicazione invece di doverli ripartire in tre ubicazioni vicine con poca quantità ciascuno. Il lavoratore desidera consolidare la quantità spostando gli articoli da ciascuna di queste ubicazioni nella stessa ubicazione con la stessa targa.

## <a name="scenario-3"></a>Scenario 3

Un pallet è in attesa della spedizione in'ubicazione di gestione temporanea, ad esempio STAGE01, vicina a BAYDOOR01. Tuttavia, a causa di una modifica dei piani il camion dovrebbe arrivare presso l'ubicazione BAYDOOR04. L'addetto alle spedizioni è consapevole di questo e deve fare in modo che il camion non debba attendere per essere caricato da STAGE01. L'addetto alle spedizioni decide di spostare gli articoli della spedizione da STAGE01 a STAGE04, ovvero più vicina alla nuova destinazione.

### <a name="current-limitations"></a>Limitazioni correnti

Le prenotazioni di lavoro che è possibile spostare sono limitate alle attività relative a Ordine cliente, Invio ordine di trasferimento, Ricezione ordine di trasferimento, Ordine fornitore e Rifornimento.

Lo spostamento di articoli è limitato per impedire la divisione delle righe di lavoro. Ciò significa che se si dispone di una riga di lavoro per 100 pezzi dell'articoloo A dall'ubicazione Loc1, non sarà possibile spostare solo 30 pezzi dell'articoloo A da quella a un'altra ubicazione. Questo comporterebbe una divisione della riga esistente di lavoro a 30 e 70, poiché le ubicazioni sono ora differenti.

Per gli scenari di gestione temporanea, in cui la targa da cui si spostano le merci o la targa in cui vengono spostate vengono impostate come Targa destinazione per un ordine di lavoro, solo lo spostamento dell'intera targa è consentito, in modo da non dover smembrare la targa di destinazione.

Attualmente è supportato solo lo spostamento ad hoc. Questo significa che non sarà possibile spostare le scorte prenotate mediante lo spostamento per voci di menu del dispositivo mobile del modello.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Configurare l'autorizzazione per spostare le scorte prenotate per singoli lavoratori

Per il lavoratore a cui dovrà essere consentito di spostare le scorte prenotate, selezionare la casella di controllo **Consenti movimento di magazzino e lavoro associato** in **Gestione magazzino \> Impostazioni \> Lavoratore**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
