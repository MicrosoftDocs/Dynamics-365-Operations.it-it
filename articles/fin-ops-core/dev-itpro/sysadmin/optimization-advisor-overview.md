---
title: Panoramica del consulente dell'ottimizzazione
description: In questo argomento viene descritto come utilizzare il consulente dell'ottimizzazione per garantire la configurazione ottimale di Finance and Operations.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 1e53dbae2d139af554b1918102937f8c3579f64a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682539"
---
# <a name="optimization-advisor-overview"></a>Panoramica consulente dell'ottimizzazione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare il consulente dell'ottimizzazione per garantire la configurazione ottimale di Finance and Operations.

## <a name="overview"></a>Panoramica

La configurazione e l'impostazione non corrette di un modulo possono influire negativamente sulla disponibilità delle funzionalità dell'applicazione, sulle prestazioni del sistema e sul funzionamento dei processi aziendali. La qualità dei dati business (ad esempio, precisione, completezza e organizzazione dei dati) influenza anche le prestazioni del sistema, le capacità decisionali di un'organizzazione, la produttività e così via.

L'area di lavoro **Consulente di ottimizzazione** è uno strumento che consente a power user, business analyst, consulenti funzionali e funzioni di supporto IT di identificare i problemi nella configurazione dei moduli e nei dati aziendali. Il consulente dell'ottimizzazione suggerisce le procedure consigliate per la configurazione del modulo e identifica i dati business che sono errati oppure obsoleti.

Il consulente dell'ottimizzazione esegue periodicamente un set di regole delle procedure consigliate. È disponibile un set di regole predefinito, tuttavia gli utenti possono anche creare regole specifiche alle personalizzazioni, alle soluzioni di fornitori software indipendenti (ISV) e ai dati aziendali. Per ulteriori informazioni sulla creazione di regole, vedere [Creare regole per il consulente dell'ottimizzazione](./create-rules-optimization-advisor.md).

Quando viene rilevata la violazione di una regola, un'opportunità di ottimizzazione viene generata e visualizzata nell'area di lavoro **Consulente di ottimizzazione**. Un utente può eseguire l'azione correttiva appropriata direttamente dall'area di lavoro **Consulente di ottimizzazione**.

Le opportunità possono essere specifiche della società o interaziendali, a seconda del tipo di impostazione e di dati che vengono convalidati. Le opportunità interaziendali possono essere visualizzate da tutte le società. Per visualizzare le opportunità per una specifica società, è necessario dapprima selezionare la società.

I criteri di sicurezza standard si applicano alle opportunità di ottimizzazione. Ad esempio, le opportunità di ottimizzazione correlate alla configurazione del modulo **Gestione magazzino** sono visibili solo agli utenti che hanno accesso alla gestione magazzino e possono modificarne la configurazione.

Quando si intraprendono azioni in relazione alle opportunità di ottimizzazione, il sistema calcola l'impatto dell'opportunità in termini di riduzione nel runtime dei processi aziendali. Purtroppo, questa funzionalità non è disponibile per tutte le opportunità di ottimizzazione.

Per ulteriori informazioni sul consulente dell'ottimizzazione, guardare il breve video [Consulente dell'ottimizzazione in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ).

## <a name="optimization-rules"></a>Regole di ottimizzazione

Per visualizzare l'elenco completo delle regole per il consulente dell'ottimizzazione e determinare la frequenza con cui le regole vengono valutate, accedere a **Amministrazione sistema** &gt; **Attività periodiche** &gt; **Gestire regola di convalida diagnostica**. Solo le regole il cui stato è **Attivo** vengono valutate. La frequenza della valutazione può essere impostata su **Giornaliera**, **Settimanale**, **Mensile** o **Non programmato**.

Per attivare la valutazione delle regole non programmate o per rivalutare regole periodiche al di fuori della programmazione predefinita, accedere a &gt; **Amministrazione sistema** **Attività periodiche** &gt; **Programma regola di convalida diagnostica**. Quindi, nella finestra di dialogo **Convalida regola di diagnostica**, selezionare la frequenza della valutazione. Tutte le regole con la frequenza specificata verranno rivalutate.

Il set di regole di ottimizzazione corrente può essere suddiviso nelle categorie esposte di seguito.

### <a name="module-configuration-and-setup"></a>Impostazione e configurazione del modulo

L'impostazione di Gestione magazzino è un processo complicato. Per semplificare il processo, sono state introdotte alcune regole per agevolare la convalida della correttezza dell'installazione. Ad esempio, una regola convalida l'impostazione di direttive di ubicazione di magazzino per le posizioni fisse di variante prodotto per gli ordini cliente e gli ordini di trasferimento.

Inoltre, alcune regole controllano se le funzionalità che sono state abilitate vengono effettivamente utilizzate. Ad esempio, una regola determina se si sta utilizzando il modulo **Pianificazione generale**. Se la regola determina che non si sta utilizzando il modulo, viene generata un'opportunità di ottimizzazione per suggerire di disattivare i processi di pianificazione.

### <a name="system-configuration"></a>Configurazione sistema

Se la funzionalità specifica che viene controllata da una chiave di configurazione non viene utilizzata, viene generata un'opportunità di ottimizzazione per suggerire di disabilitare la chiave di configurazione. Gli esempi di chiavi di configurazione includono **Peso variabile**, **Pianificazione del budget**, **Progetto** ed **Elenco di fornitori approvati**.

### <a name="business-data-consistency-and-cleanup"></a>Coerenza e pulitura dei dati aziendali

Se i dati master non sono corretti (ad esempio se non sono state definite le conversioni delle unità di misura per alcune misure o se si dispone di conversioni di unità di misura che hanno una divisione per 0 \[zero\]), viene generata un'opportunità di ottimizzazione per suggerire di correggere i dati. 

Se vi sono troppe voci di storico dei processi batch, voci obsolete, voci disponibili chiuse per articoli abilitati al magazzino e così via o se tali voci e articoli risultano troppo vecchi, vengono generate opportunità di ottimizzazione per suggerire di pulire i dati. La costante pulitura dei dati consente di migliorare le prestazioni complessive del sistema.

### <a name="best-practices"></a>Procedure consigliate

Se non si stanno eseguendo alcuni processi aziendali in base alle procedure consigliate (ad esempio, si esegue la pre-chiusura di magazzino prima che l'inventario venga chiuso o se si utilizza il batch programmato per il trasferimento batch del giornale di registrazione secondario), le opportunità di ottimizzazione notificano la procedura consigliata e chiedono che venga seguita.

## <a name="optimization-opportunities"></a>Opportunità di ottimizzazione

Per visualizzare le opportunità di ottimizzazione generate durante la valutazione delle regole di ottimizzazione, aprire l'area di lavoro **Consulente dell'ottimizzazione**.

In questa area di lavoro, è possibile visualizzare ulteriori informazioni su un'opportunità selezionando **Ulteriori informazioni**. Se si desidera fare sì che il sistema esegua un'azione e corregga l'impostazione, pulisca i dati e così via in modo che non si debba aprire personalmente le pagine corrispondenti, selezionare **Esegui azione**.

Non esiste un flusso di lavoro per le opportunità di ottimizzazione. Dopo che viene selezionato **Esegui azione** o viene utilizzato un percorso di navigazione fornito nella finestra di dialogo **Ulteriori informazioni**, l'opportunità di ottimizzazione viene eliminata dall'elenco. Se l'azione correttiva non risolve completamente un problema, l'opportunità verrà generata nuovamente alla prossima valutazione della regola.

Se un'opportunità non è applicabile al ruolo, è possibile selezionare **Nascondi nel mio elenco**. Anche se la regola dietro l'opportunità viene attivata di nuovo in un secondo momento, l'opportunità non viene visualizzata nell'elenco.

Per disattivare la valutazione di regole specifiche, selezionare l'opportunità generata dalla regola, quindi selezionare **Disattivare l'analisi**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare regole per il consulente dell'ottimizzazione](./create-rules-optimization-advisor.md)

[Consulente dell'ottimizzazione in Dynamics 365 for Finance and Operations (video)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]