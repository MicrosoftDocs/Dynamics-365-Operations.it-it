---
title: Programmare la pulizia dei dati dello storico vendite
description: In questo argomento viene descritto come migliorare le prestazioni del sistema pianificando l'attività periodica di pulizia della cronologia degli aggiornamenti delle vendite in modo che venga eseguita a intervalli regolari.
author: myvakalo
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6c6c1e08d45f2a7d1e1267010b286111bad01a6c
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570368"
---
# <a name="schedule-sales-history-data-cleanup"></a>Programmare la pulizia dei dati dello storico vendite

[!include [banner](../includes/banner.md)]

Come parte della sua operazione standard, Microsoft Dynamics 365 Supply Chain Management genera e archivia i dati di aggiornamento della cronologia delle vendite su base continuativa. Nel tempo, nel tuo sistema potrebbe accumularsi una grande quantità di dati storici sulle vendite obsoleti. Questi dati accumulati possono causare problemi di prestazioni e funzionali quando vengono registrati documenti correlati agli ordini cliente. Questi documenti includono conferme dell'ordine cliente, documenti di trasporto di vendita, distinte di prelievo vendite e fatture. Pertanto, è necessario impostare e programmare l'attività periodica *Pulizia della cronologia degli aggiornamenti delle vendite* da eseguire a intervalli regolari. Questa attività rimuoverà tutti i dati di aggiornamento della cronologia delle vendite che non sono più necessari.

Se usi l'attività periodica *Pulizia della cronologia degli aggiornamenti delle vendite* ti consigliamo di abilitare la funzionalità *Miglioramenti delle prestazioni di pulizia della cronologia delle vendite* in modo da eseguire l'attività in modo più efficace. Tuttavia, puoi anche eseguire l'attività senza abilitare questa funzione.

## <a name="turn-on-the-sales-history-cleanup-features"></a>Attivare le funzioni di pulizia della cronologia delle vendite

Per impostare e utilizzare l'attività periodica *Pulizia della cronologia degli aggiornamenti delle vendite* insieme a tutte le funzionalità descritte in questo argomento, è necessario abilitare e funzionalità *Miglioramenti delle prestazioni di pulizia della cronologia delle vendite* e *Pulisci storico aggiornamento vendite in base alla validità* in Gestione funzionalità, come descritto nelle seguenti sottosezioni.

### <a name="sales-history-cleanup-performance-improvements"></a>Miglioramenti delle prestazioni di pulizia della cronologia delle vendite

Il processo batch periodico di **pulizia della cronologia delle vendite** può richiedere molto tempo se eseguito raramente in ambienti con un volume elevato di aggiornamenti delle vendite. In queste situazioni, la funzionalità *Miglioramenti delle prestazioni di pulizia della cronologia delle vendite* può aiutare a ridurre la durata dell'esecuzione e migliorare l'affidabilità.

La funzione migliora il lavoro di pulizia esistente nei seguenti modi:

- Suddivide la pulizia in batch (è possibile modificare la dimensione del batch tramite personalizzazioni).
- Funzionerà per un massimo di 2 ore (è possibile modificare la durata tramite personalizzazioni).
- Ove possibile, le funzionalità del database verranno sfruttate per ridurre al minimo il blocco ed evitare di unire tabelle transazionali durante la pulizia.

Dopo aver abilitato la funzionalità, il lavoro in batch **pulizia della cronologia degli aggiornamenti delle vendite** (**Vendite e marketing \> Attività periodo \> Pulizia \> Pulizia della cronologia degli aggiornamenti delle vendite**) verrà eseguito come prima, ma con prestazioni migliori per un massimo di 2 ore. Ciò significa che potrebbe essere necessario eseguirlo più volte per ripulire tutti i dati per un intervallo di tempo di conservazione specifico.

Prima di utilizzare la funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Vendite e marketing*
- **Nome funzionalità:** *Miglioramenti delle prestazioni di pulizia della cronologia delle vendite*

### <a name="clean-up-sales-update-history-based-on-age"></a>Pulisci storico aggiornamento vendite in base alla validità

La funzionalità *Pulisci storico aggiornamento vendite in base alla validità* ti consente di specificare l'età massima dei record da conservare durante l'esecuzione dell'attività periodica *Pulizia dello storico aggiornamenti delle vendite*. I record più vecchi verranno eliminati. La funzionalità è utile quando si imposta l'attività per l'esecuzione periodica perché l'età viene sempre calcolata rispetto alla data di esecuzione dell'attività. Se non usi questa funzionalità, puoi solo impostare una data specifica per i record più vecchi da conservare.

Prima di utilizzare la funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Vendite e marketing*
- **Nome funzionalità:** *Pulisci storico aggiornamento vendite in base alla validità*

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Impostare e pianificare l'attività periodica di pulizia della cronologia delle vendite

Per impostare e pianificare l'attività periodica *pulizia della cronologia delle vendite* segui questi passaggi.

1. Analizza le tue esigenze aziendali per determinare quanti giorni di dati storici di registrazione degli ordini cliente devi conservare. In genere è consigliabile eseguire l'attività di pulizia ogni tre mesi e al massimo ogni sei mesi.
1. Vai a **Vendite e marketing \> Attività periodo \> Pulisci \> Pulizia della cronologia degli aggiornamenti delle vendite**.
1. Nella finestra di dialogo **Pulisci storico aggiornamento vendite**, nella scheda dettaglio **Parametri**, impostare i seguenti campi:

    - **Pulizia** – Seleziona uno dei seguenti valori per specificare il tipo di record da ripulire:

        - **Eseguito** – Elimina solo i record che sono stati completamente elaborati. Poiché è improbabile che tu possa utilizzare ulteriormente questi record, questa opzione è la più sicura.
        - **Eseguito ed errato** – Elimina sia i record completamente elaborati che i record in cui si è verificato un errore. Questa opzione è la più comunemente usata. Potresti voler ispezionare e persino correggere i record errati invece di farli ripulire automaticamente. Tuttavia, molte aziende scelgono di ripulire anche questi record dopo circa un mese, perché probabilmente non sono più rilevanti a quel punto.
        - **Tutti** – Elimina i record eseguiti, errati e in attesa. I record in attesa sono validi ma non sono stati ancora completamente elaborati. Nella maggior parte dei casi, probabilmente non vuoi che vengano eliminati automaticamente. Tuttavia, in alcune situazioni, potresti scegliere di eliminarli automaticamente dopo che è trascorso un determinato periodo di tempo.

    - **Mantieni i record in base all'età** – Specifica se vuoi ripulire i record in base alla loro età nel giorno in cui viene eseguita l'attività o eliminare i record creati prima di una data fissa. Se stai pianificando la pulizia come attività ricorrente, dovresti impostare questa opzione su *sì*, perché l'età viene sempre calcolata rispetto alla data di esecuzione dell'attività.

        - Imposta questa opzione su *sì* per abilitare il campo **Età massima**. Utilizza questo campo per specificare l'età massima dei record da conservare ogni volta che l'attività viene eseguita. Il campo **Creato fino a** viene ignorato.
        - Imposta questa opzione su *No* per abilitare il campo **Creato fino a**. Utilizza questo campo per specificare la data di creazione più vecchia dei record da conservare quando l'attività viene eseguita. Il campo **Età massima** viene ignorato.

    - **Creato fino a** – Questa impostazione si applica solo quando l'opzione **Conserva i record in base all'età** è impostata su *No*. Specifica la data di creazione più vecchia dei record da conservare quando l'attività viene eseguita. I record creati prima di questa data verranno eliminati.
    - **Età massima** – Questa impostazione si applica solo quando l'opzione **Conserva i record in base all'età** è impostata su *Sì*. Specifica l'età massima in giorni dei record da conservare ogni volta che l'attività viene eseguita. I record più vecchi verranno eliminati.

1. Nella scheda dettaglio **Esegui in background**, specifica come, quando e con quale frequenza viene eseguita l'attività. Utilizza queste impostazioni per implementare la pianificazione determinata nel passaggio 1. I campi funzionano esattamente come funzionano per altri tipi di [processi batch](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Selezionare **OK** per applicare le impostazioni e chiudere la finestra di dialogo.
