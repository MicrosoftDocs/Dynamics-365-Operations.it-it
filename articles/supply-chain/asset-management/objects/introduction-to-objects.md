---
title: Introduzione ai cespiti
description: Questo argomento fornisce una panoramica sui cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetTimeline, EntAssetObjectTableLookup, EntAssetObjectTableParent, EntAssetObjectOverview, EntAssetObjectImage, EntAssetObjectTable, EntAssetLifecycleStateLog, EntAssetObjectWorkOrderActive, EntAssetObjectAttribute
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f629ebdf7423ca75fe215b0a3223478685fe95c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018573"
---
# <a name="introduction-to-assets"></a>Introduzione ai cespiti

[!include [banner](../../includes/banner.md)]

 

Questo argomento fornisce una panoramica sui cespiti in Gestione cespiti. Un *cespite* è qualsiasi tipo di attrezzatura, ad esempio una macchina o una sua parte, che richiede la manutenzione, assistenza o riparazione.

Un cespite viene aggiornato automaticamente con informazioni correlate. Ad esempio, queste informazioni correlate potrebbero riguardare ordini di lavoro nuovi o aggiornati. È possibile creare i cespiti utilizzando la voce di menu **Tutti i cespiti** oppure la voce di menu **Cespiti in sospeso**. In questo argomento viene descritto come creare i cespiti utilizzando la voce di menu **Tutti i cespiti**. Per informazioni sulla creazione dei cespiti utilizzando la voce di menu **Cespiti in sospeso**, vedere [Creare cespiti in base agli ordini fornitore](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Tutti i cespiti

Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti**. La pagina elenco **Tutti i cespiti** mostra tutti i cespiti e alcune delle informazioni correlate. Per visualizzare solo i cespiti attivi, selezionare **Cespiti attivi**. Per visualizzare solo i cespiti installati nelle unità funzionali a cui si è correlati come addetti alla manutenzione, selezionare **Cespiti attivi personali**. Questa relazione viene impostata nella pagina **Lavoratori**. Per ulteriori informazioni, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).

Nella visualizzazione griglia **Tutti i cespiti**, selezionare un collegamento nella colonna **Cespite** per visualizzare i dettagli relativi al record selezionato. Per modificare il record, selezionare il pulsante **Modifica**. La visualizzazione dettagli mostra informazioni dettagliate correlate al cespite. Un riquadro **Informazioni correlate** a destra contiene informazioni aggiuntive correlate cespite. Espandere il riquadro per visualizzare le informazioni correlate per il cespite selezionato.

I pulsanti del riquadro azioni sono organizzati in schede. Nella tabella seguente vengono brevemente descritte i pulsanti correlati a Gestione cespiti.

| Nome del pulsante          | Descrizione                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifica                 | Modifica il cespite selezionato.                                                                                                                                         |
| Nuove                  | Crea un nuovo cespite                                                                                                                                                |
| Eliminazione               | Elimina il cespite selezionato.                                                                                                                                       |
| Sposta cespite           | Sposta i cespiti in un'altra struttura di cespite, o in un altro ubicazione nella stessa struttura del cespite.                                                                                         |
| Sostituisci cespite        | Sostituisce un cespite figlio in una gerarchia di cespiti con un altro cespite.                                                                                                  |
| Installa cespite        | Installa un cespite in una unità funzionale.                                                                                                                          |
| Copia cespite           | Copia una gerarchia di cespiti in un altro cespite.                                                                                                                          |
| Richieste             | Apre la pagina elenco **Richieste attive**, in cui è possibile visualizzare le richieste di intervento di manutenzione create per il cespite selezionato.                                                                         |
| Storico eventi        | Consente di visualizzare una panoramica delle diverse registrazioni effettuate nel cespite.                                                                                                         |
| DBA cespiti            | Consente di visualizzare un elenco di tutti gli articoli (pezzi di ricambio e altri articoli) utilizzati in un cespite.                                                                                  |
| Ordini di lavoro          | Consente  aprire la pagina elenco **Ordini di lavoro attivi**, in cui è possibile visualizzare gli ordini di lavoro per il cespite.                                                                                        |
| Elenco di controllo            | Visualizza una panoramica degli elenchi di controllo di manutenzione e delle misurazioni registrate per il cespite.                                                                                                 |
| Tempi di fermo per la manutenzione | Crea o visualizza le registrazioni dei tempi di fermo per la manutenzione del cespite.                                                                                                       |
| Transazioni progetto | Consente di visualizzare tutte le transazioni registrate correlate agli ordini di lavoro creati per il cespite.                                                                                       |
| Misure dei cespiti       | Consente di creare o visualizzare le misurazioni relative al cespite.                                                                                                               |
| Programma di manutenzione | Consente  aprire la pagina elenco **Apri programma di manutenzione**, in cui è possibile visualizzare piani di manutenzione, richieste di intervento di manutenzione e cicli di manutenzione associati al cespite e con stato **Creato**. |
| Aggiorna stato del cespite   | Aggiorna lo stato del ciclo di vita del cespite. È possibile selezionare più cespiti nella pagina elenco **Tutti i cespiti** e quindi aggiornare lo stato del ciclo di vita per tutti contemporaneamente.              |
| Registro dello stato del ciclo di vita  | Apre un registro contenente gli stati del ciclo di vita del cespite selezionato.                                                                                                                 |
| Documenti cespiti      | Visualizza un elenco di documenti collegati a un cespite. Tali documenti vengono impostati in **Gestione cespiti** \> **Impostazione** \> **Documenti cespiti**.                 |
| Attributi           | Consente di creare o visualizzare gli attributi del cespite.                                                                                                                             |
| Immagine                | Selezionare un'immagine per il cespite.                                                                                                                                   |
| Cespiti padre        | Consente di visualizzare lo storico dei cespiti padre per il cespite selezionato.                                                                                                                |
| Unità funzionali | Consente di visualizzare lo storico delle unità funzionali per il cespite selezionato.                                                                                                          |
| Valutazione delle condizioni | Registra le misurazioni di valutazione delle condizioni del cespite.                                                                                                         |
| Errori               | Consente  aprire la pagina elenco **Problemi cespiti**, in cui è possibile visualizzare i problemi registrati nel cespite.                                                                                             |
| Controllo costi         | Confronta i costi in budget e i costi effettivi nel cespite.                                                                                                              |
| Controllo ore         | Confronta le ore previste e le ore effettive relative al cespite.                                                                                                              |
| KPI del cespite           | Consente di calcolare e visualizzare indicatori di prestazioni chiave (KPI) per il cespite.                                                                                              |
| Tipi di lavoro            | Consente di visualizzare una panoramica dei tipi di processo predefiniti correnti per il cespite.                                                                                                            |
| Tipi di criticità    | Visualizza o aggiorna i tipi di criticità del cespite.                                                                                                                              |
| Parti di ricambio          | Consente di visualizzare un elenco di pezzi di ricambio approvati e alternativi che possono essere usati per il cespite.                                                                               |
| Consumo cespite    | Consente di stampare un report contenente le registrazioni del consumo relativo al cespite.                                                                                                |
| Errore del cespite          | Consente di stampare un report contenente le registrazioni dei problemi del cespite.                                                                                                      |
