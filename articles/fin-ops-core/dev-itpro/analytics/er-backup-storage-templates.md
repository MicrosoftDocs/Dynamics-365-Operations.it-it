---
title: Archiviazione di backup di modelli ER
description: In questo argomento viene descritto come utilizzare l'archiviazione di backup ER per il recupero di modelli.
author: NickSelin
manager: AnnBe
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d1bf2f13833b4441812b1c5326f897415c752091
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565627"
---
# <a name="backup-storage-of-er-templates"></a>Archiviazione di backup di modelli ER

[!include [banner](../includes/banner.md)]

La [Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md) consente agli utenti aziendali di configurare formati per documenti in uscita in base ai requisiti legali dei vari paesi. I formati ER configurati possono utilizzare modelli predefiniti per generare documenti in uscita in vari formati, ad esempio cartelle di lavoro Microsoft Excel, documenti Microsoft Word o documenti PDF. I modelli vengono riempiti con i dati necessari al flusso di dati configurato per documenti generati.

Ogni formato configurato può essere pubblicato come parte di una soluzione ER. Ogni soluzione ER può essere esportata da un'istanza di Finance and Operations e importata in un'altra istanza.

Il framework ER utilizza la [configurazione della gestione dei documenti](../../fin-ops/organization-administration/configure-document-management.md) per gestire i modelli necessari per l'istanza corrente di Finance and Operations. A seconda delle impostazioni del framework ER, l'archiviazione Blob di Microsoft Azure o una cartella di Microsoft SharePoint può essere selezionata come percorso fisico di archiviazione principale per i modelli. Per ulteriori informazioni, vedere [Configurare il framework di report elettronici](electronic-reporting-er-configure-parameters.md). La tabella DocuValue contiene un singolo record per ogni modello. In ogni record, il campo **AccessInformation** memorizza il percorso di un file di modello che si trova nel percorso di archiviazione configurato.

Quando si gestiscono le istanze di Finance and Operations, è possibile che si decida di migrare l'istanza corrente a un'altra posizione. Ad esempio, si potrebbe migrare l'istanza di produzione a un nuovo ambiente sandbox. Se il framework ER è stato configurato per archiviare modelli nell'archiviazione Blob, la tabella DocuValue nel nuovo ambiente sandbox fa riferimento all'istanza dell'archiviazione Blob nell'ambiente di produzione. Tuttavia, non è possibile accedere a questa istanza dall'ambiente sandbox, in quanto il processo di migrazione non supporta la migrazione di elementi nell'archiviazione Blob. Di conseguenza, se si tenta di eseguire un formato ER che utilizza un modello per generare documenti aziendali, si verifica un'eccezione e si riceve una notifica relativa al modello mancante. Vengono inoltre fornite informazioni sull'utilizzo dello strumento di pulitura ER per eliminare e quindi reimportare la configurazione di formato ER che contiene il modello. Poiché è possibile che vi siano varie configurazioni di formato ER, questo processo può richiedere molto tempo.

La funzionalità di archiviazione di backup di modelli ER consente di rendere i modelli sempre disponibili per generare documenti aziendali.

> [!NOTE]
> Questa funzionalità può essere utilizzata solo quando l'archiviazione Blob è stata selezionata come percorso di archiviazione fisico per i modelli ER.

## <a name="automated-recovery-and-notification"></a>Ripristino e notifica automatizzati

Per questa funzionalità, ogni modello di una nuova configurazione di formato ER nell'ambiente corrente viene salvato automaticamente nel percorso di archiviazione di backup per i modelli (tabella di database ERDocuDatabaseStorage) quando si verificano i seguenti eventi:

- Si importa una nuova configurazione di formato ER che contiene un modello.
- Si completa la versione bozza di una configurazione di formato ER che contiene un modello.

Le copie di backup dei modelli vengono migrate a una nuova istanza di Finance and Operations come parte del database dell'applicazione.

Se un modello di un formato di ER è necessario per la generazione di documenti in uscita, ad esempio per elaborare i pagamenti fornitori inclusa la generazione di report di avvisi di pagamento e di controllo, ma il modello richiesto non è presente nel percorso di archiviazione principale, si verifica l'evento seguente:

- Se il modello è disponibile nel percorso di archiviazione di backup, viene automaticamente estratto da tale percorso, ripristinato nel percorso di archiviazione principale e utilizzato per l'esecuzione corrente.
- A ogni utente assegnato al ruolo **Sviluppatore per la creazione di report elettronici** o **Amministratore di sistema** viene inviata una notifica relativa al modello mancante mediante il Centro azioni. Il messaggio visualizzato dipende dal valore del parametro **Esegui automaticamente procedura di ripristino di modelli danneggiati in batch**:

    - Se questo parametro è impostato su **Disattivato**, il messaggio consiglia di avviare il processo batch per correggere automaticamente problemi simili per altri modelli di configurazione di formato ER. Il messaggio include un collegamento che può essere utilizzato per avviare il processo batch.
    - Se questo parametro è impostato su **Attivato**, il messaggio informa che è stato rilevato un problema di modello mancante e che un nuovo processo batch, **Ripristina modelli danneggiati da backup del database interno**, è stato programmato automaticamente. Questo processo batch correggerà automaticamente problemi simili per altri modelli.

Per configurare il parametro **Esegui automaticamente procedura di ripristino di modelli danneggiati in batch**, completare i passaggi seguenti:

1. In Finance and Operations aprire la pagina **Amministrazione organizzazione \> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, impostare il valore necessario per il parametro **Esegui automaticamente procedura di ripristino di modelli danneggiati in batch**.

> [!NOTE]
> Questo parametro è definito come specifico dell'utente dell'applicazione e della società connessa.

![Pagina delle configurazioni ER](./media/GER-BackupTemplates-1.png)

Nella figura seguente è illustrato un esempio del messaggio visualizzato quando il parametro **Esegui automaticamente procedura di ripristino di modelli danneggiati in batch** è impostato su **Attivato**.

![Pagina Giornale di registrazione pagamenti fornitore](./media/GER-BackupTemplates-2.png)

Nella figura seguente è illustrato il processo batch **Ripristina modelli danneggiati da backup del database interno** nella pagina **Processo batch**.

![Pagina Processo batch](./media/GER-BackupTemplates-3.png)

Il registro di esecuzione del processo batch **Ripristina modelli danneggiati da backup del database interno** completato include informazioni sui modelli che sono stati ripristinati dal percorso di archiviazione di backup al percorso di archiviazione principale.

![Pagina Storico processi batch](./media/GER-BackupTemplates-4.png)

Per impostazione predefinita, il processo di creazione automatica di copie di backup dei modelli che si trovano nelle configurazioni di formato ER è attivato. Per interrompere la creazione di copie di backup dei modelli, impostare l'opzione **Interrompi creazione di copie di backup del modello** su **Sì** nella scheda **Allegati** della pagina **Parametri per la creazione di report elettronici**. È possibile aprire questa pagina dall'area di lavoro **Creazione di report elettronici**.

Se si imposta **Interrompi creazione di copie di backup del modello** su **Sì** e non si desidera mantenere le copie di backup dei modelli create in precedenza, selezionare **Pulisci archiviazione di backup** nella pagina **Parametri per la creazione di report elettronici**.

Se l'ambiente è stato aggiornato a Finance and Operations versione 10.0.5 (ottobre 2019) e si desidera eseguire la migrazione a un nuovo ambiente che include configurazioni di formato ER eseguibili, selezionare **Completa archiviazione di backup** nella pagina **Parametri per la creazione di report elettronici** prima di eseguire la migrazione. Questo pulsante avvia il processo di creazione di copie di backup di tutti i modelli disponibili, di modo che possano essere archiviati nel percorso di archiviazione di backup ER per modelli.

![Pagina Parametri per la creazione di report elettronici](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Ripristino manuale

Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Ripristina modelli danneggiati** per avviare manualmente il processo di ripristino dei modelli ER dal percorso di archiviazione di backup al percorso di archiviazione principale. Prima di iniziare questo processo, nella pagina **Ripristina modelli danneggiati** è possibile specificare se l'operazione verrà eseguita in modo interattivo o se il processo batch verrà pianificato a tal fine.

## <a name="supported-deployments"></a>Distribuzioni supportate

In Finance and Operations versione 10.0.5 la funzionalità di archiviazione di backup di modelli ER è disponibile solo nelle distribuzioni cloud.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md)

[Configurare il framework di report elettronici](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]