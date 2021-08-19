---
title: Non è possibile filtrare gli elementi di pianificazione generale in base ai valori del gruppo di copertura correlato
description: Non è possibile filtrare gli elementi di pianificazione generale in base ai valori del gruppo di copertura correlato.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9750a73f0962179512c5e21a614a276c313ff975b7494f31589ca936886ecf6e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781395"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Non è possibile filtrare gli elementi di pianificazione generale in base ai valori del gruppo di copertura correlato

Numero KB: 4612572

## <a name="symptoms"></a>Sintomi

Vuoi filtrare gli articoli che verranno inclusi in un processo batch di pianificazione principale, in base ai valori dei record correlati dalla tabella di copertura articolo. (Ad esempio, vuoi filtrare gli elementi in base al loro valore **Fornitore** e/o **Gruppo di copertura**). La configurazione del filtro per il processo batch consente di creare un join dalla tabella **Articoli** alla tabella **Copertura dell'articolo**, quindi specificare i valori dei campi dalla tabella di copertura articoli nella query. Tuttavia, dopo aver completato questa configurazione, il sistema crea comunque ordini pianificati per l'intera copertura articolo, non solo per gli articoli che corrispondono ai valori di campo specificati dalla tabella di copertura articolo.

## <a name="resolution"></a>Risoluzione

Il filtro del processo batch può filtrare solo sugli elementi. Sebbene tu possa aggiungere un join alla tabella **Copertura dell'articolo**, le impostazioni di filtro effettuate su quella tabella non influiranno sull'output della query. In fase di esecuzione, il sistema esegue la pianificazione per tutti i gruppi di copertura e tutte le varianti di cui dispongono gli articoli filtrati. Dopo che un articolo è già stato incluso nell'esecuzione, eventuali gruppi di copertura inclusi nel filtro articolo non influiranno sull'output della pianificazione.
