---
title: Ottimizzare i processi batch programmati BYOD
description: Questo articolo spiega come ottimizzare le prestazioni quando si utilizza la funzionalità Bring Your Own Device (BYOD) con Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: 4df60a82e016ec8f3ba6ba0d70c261824961d221
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848315"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Ottimizzare i processi batch programmati BYOD


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo spiega come ottimizzare le prestazioni quando si utilizza la funzionalità Bring Your Own Device (BYOD). Per ulteriori informazioni su BYOD, vedere [Portare il proprio database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

## <a name="performance-considerations-for-data-export"></a>Considerazioni sulle prestazioni per l'esportazione dei dati

Dopo che le entità sono state pubblicate nel database di destinazione, è possibile utilizzare la funzione Esporta nell'area di lavoro **Gestione dei dati** per spostare i dati. La funzione Esporta consente di definire un processo di spostamento dati che contiene una o più entità. Per ulteriori informazioni sull'esportazione dei dati, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

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

Per eseguire un push incrementale, è necessario attivare il rilevamento delle modifiche per ogni entità nella pagina **Entità**. Per ulteriori informazioni, vedere [Abilitare il rilevamento delle modifiche per le entità](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

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

**Soluzione:** le tabelle di rilevamento delle modifiche SQL potrebbero non essere nello stato previsto. In casi di questo tipo, consigliamo di disattivare il rilevamento delle modifiche per l'entità e quindi di riattivarlo. Per ulteriori informazioni, vedere [Abilitare il rilevamento delle modifiche per le entità](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="staging-tables-arent-clearing"></a>Le tabelle di gestione temporanea non vengono cancellate

**Problema:** Quando si utilizza la gestione temporanea per il progetto, le tabelle di gestione temporanea non vengono cancellate correttamente. I dati nelle tabelle continuano quindi a crescere, causando problemi di prestazioni.

**Soluzione:** Sette giorni di storico sono conservati nelle tabelle di gestione temporanea. I dati storici più vecchi di sette giorni vengono automaticamente cancellati dalle tabelle di gestione temporanea dal processo batch **Importa/Esporta pulizia gestione temporanea**. Se questo processo si blocca, le tabelle non verranno cancellate correttamente. Il riavvio di questo processo batch consentirà al processo di cancellare automaticamente le tabelle di gestione temporanea.

## <a name="see-also"></a>Vedere anche

[Panoramica della gestione dati](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Portare il proprio database (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Panoramica processi di importazione ed esportazione dati](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[Abilitare il rilevamento delle modifiche per le entità](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
