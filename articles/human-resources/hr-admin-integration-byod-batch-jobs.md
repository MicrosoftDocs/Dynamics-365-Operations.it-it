---
title: Ottimizzare i processi batch programmati BYOD
description: Questo argomento spiega come ottimizzare le prestazioni quando si utilizza la funzionalità Bring Your Own Device (BYOD) con Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: d08762ff40b4da8264bd5bc4a1c16fd2afc4d610
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712605"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Ottimizzare i processi batch programmati BYOD

Questo argomento spiega come ottimizzare le prestazioni quando si utilizza la funzionalità Bring Your Own Device (BYOD). Per ulteriori informazioni su BYOD, vedere [Portare il proprio database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json).

## <a name="performance-considerations-for-data-export"></a>Considerazioni sulle prestazioni per l'esportazione dei dati

Dopo che le entità sono state pubblicate nel database di destinazione, è possibile utilizzare la funzione Esporta nell'area di lavoro **Gestione dei dati** per spostare i dati. La funzione Esporta consente di definire un processo di spostamento dati che contiene una o più entità. Per ulteriori informazioni sull'esportazione dei dati, vedere [Panoramica dei processi di importazione ed esportazione dei dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json).

Usare la pagina **Esporta** per esportare i dati in diversi formati di dati di destinazione, come un file con valori separati da virgole (CSV). Questa pagina supporta anche i database SQL come altra destinazione.

È possibile creare un progetto di dati con più entità e utilizzare un processo batch per programmare l'esecuzione di tale progetto di dati. Se si seleziona l'opzione **Esporta in batch** è possibile programmare l'esecuzione periodica del processo di esportazione dei dati.

Per preservare l'affidabilità complessiva dell'esportazione BYOD, è necessario fare attenzione quando si aggiungono più entità a un progetto di esportazione. Quando si determina il numero di entità da aggiungere allo stesso progetto, considerare i seguenti parametri:

- La complessità delle entità
- Il volume di dati previsto per entità
- Il tempo complessivo necessario per completare l'esportazione a livello di processo

Per le migliori prestazioni, evitare di aggiungere centinaia di entità a un singolo progetto. Ti consigliamo di creare più lavori, ognuno dei quali contiene meno entità.

## <a name="scheduling-byod-batch-jobs"></a>Programmare i processi batch BYOD

Per aiutare a ridurre l'impatto sugli utenti di Microsoft Dynamics 365 Human Resources, eseguire processi batch BYOD di notte o fuori orario di lavoro. Assicurarsi di controllare il fuso orario per i processi batch ricorrenti. Alcuni processi batch potrebbero utilizzare Pacific Standard Time (PST).

Per evitare problemi di prestazioni, considerare i seguenti fattori quando si configura la frequenza di pianificazione per i processi batch BYOD:

- Il tempo necessario per completare ogni processo batch
- La necessità aziendale per i dati in BYOD

Impostare la frequenza per ogni lavoro batch su un valore che garantisca che il processo possa essere completato molto prima della successiva fase di esecuzione programmata. Evitare di eseguire più processi in parallelo, perché questo approccio può influire negativamente sulle prestazioni di Human Resources.

Per le migliori prestazioni, usare sempre l'opzione **Esporta in batch** nella pagina **Esporta** per programmare i processi batch BYOD. Evitare di programmare esportazioni ricorrenti in **Gestione \> Gestisci processi di dati ricorrenti**.

## <a name="incremental-export"></a>Esportazione incrementale

Quando si aggiunge un'entità per l'esportazione dei dati, è possibile eseguire un push incrementale (esportazione) o un push completo. Un push completo elimina tutti i record esistenti da un'entità nel database BYOD. Quindi inserisce il set corrente di record dall'entità Human Resources.

Per eseguire un push incrementale, è necessario attivare il rilevamento delle modifiche per ogni entità nella pagina **Entità**. Per ulteriori informazioni, vedere [Abilitare il rilevamento delle modifiche per le entità](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

Se si seleziona un push incrementale, il primo push è sempre un push completo. SQL tiene traccia delle modifiche da questo primo push completo. Quando viene inserito un nuovo record o quando un record viene aggiornato o eliminato, la modifica si riflette nell'entità di destinazione.

## <a name="time-outs"></a>Timeout

Di seguito sono riportati i timeout predefiniti per le esportazioni BYOD:

- Dieci minuti per le operazioni di troncamento
- Un'ora per le operazioni di inserimento in blocco

Quando i volumi sono alti, queste impostazioni di timeout potrebbero non essere sufficienti. Per aggiornarle, andare a **Gestione dei dati \> Parametri del framework \> Portare il proprio database**. Questi timeout sono specifici dell'azienda e devono essere impostati separatamente per ciascuna società.

## <a name="known-limitations"></a>Limitazioni note

La funzionalità BYOD prevede le limitazioni seguenti:

- Non devono essere presenti blocchi attivi sul database durante la sincronizzazione. I blocchi attivi possono causare scritture lente o addirittura la mancata esportazione dei dati nel database SQL di Azure.
- Non è possibile esportare entità composite nel database. Attualmente, le entità composite non sono supportate. È necessario esportare singole entità che compongono l'entità composta. Tuttavia, è possibile esportare entrambe le entità nello stesso progetto di dati.
- Le entità che non dispongono di chiavi univoche non possono essere esportate utilizzando il push incrementale. Questa limitazione si manifesta soprattutto quando si prova a esportare in modo incrementale i record da poche entità già pronte. Poiché queste entità sono state progettate per consentire l'importazione di dati, non dispongono di una chiave univoca.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="incremental-push-doesnt-work-correctly"></a>Il push incrementale non funziona correttamente

**Problema:** quando si verifica un push completo per un'entità, viene visualizzato un ampio set di record in BYOD quando si utilizza un'istruzione **select**. Tuttavia, quando si esegue un push incrementale, vengono visualizzati solo pochi record in BYOD. Sembra che il push incrementale abbia eliminato tutti i record e aggiunto solo i record modificati in BYOD.

**Soluzione:** le tabelle di rilevamento delle modifiche SQL potrebbero non essere nello stato previsto. In casi di questo tipo, consigliamo di disattivare il rilevamento delle modifiche per l'entità e quindi di riattivarlo. Per ulteriori informazioni, vedere [Abilitare il rilevamento delle modifiche per le entità](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

## <a name="see-also"></a>Vedere anche

[Panoramica della gestione dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages?toc=/dynamics365/human-resources/toc.json)<br>
[Portare il proprio database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json)<br>
[Panoramica processi di importazione ed esportazione dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json)<br>
[Abilitare il rilevamento delle modifiche per le entità](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json)