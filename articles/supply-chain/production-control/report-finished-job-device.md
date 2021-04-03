---
title: Dichiarazione di finito dal dispositivo scheda processo
description: In questo argomento viene descritto come configurare il sistema di modo che gli utenti di un dispositivo scheda processo possano dichiarare finiti i prodotti da un ordine di produzione all'inventario.
author: johanhoffmann
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 7eabcb23681a9b2427fa1065b045e639cc98f9d7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262143"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Dichiarazione di finito dal dispositivo scheda processo

[!include [banner](../includes/banner.md)]

I lavoratori usano la pagina **Segnala stato** nel dispositivo scheda processo per dichiarare le quantità che sono state completate per un processo di produzione. Questo argomento descrive come configurare varie opzioni che stabiliscono in che modo i lavoratori possono dichiarare come finito utilizzando questa pagina e cosa succede dopo. Di seguito sono elencate le opzioni disponibili:

- Controllare se e come le quantità dichiarate finite vengono aggiunte all'inventario.
- Controllare se e come i numeri di batch vengono generati e applicati al momento della dichiarazione come finito.
- Controllare se e come i numeri di serie vengono generati e applicati al momento della dichiarazione come finito.
- Controllare se e come dichiarare come finito su una targa.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Controllare se le quantità dichiarate finite vengono aggiunte all'inventario

Per controllare se e come aggiungere all'inventario le quantità dichiarate finite nell'ultima operazione, attenersi alla seguente procedura.

1. Andare a **Controllo produzione \> Impostazioni \> Esecuzione produzione \> Impostazioni predefinite ordini di produzione**.
1. Nella scheda **Dichiarazione di finito**, impostare il campo **Aggiorna report dichiarazione di finito in linea** su uno dei seguenti valori:

    - **No** - Nessuna quantità verrà aggiunta all'inventario quando le quantità vengono dichiarate nell'ultima operazione. Lo stato dell'ordine di produzione non cambierà mai.
    - **Stato + Quantità** - Lo stato dell'ordine di produzione cambierà in *Dichiarato finito* e la quantità verrà dichiarata finita nell'inventario.
    - **Quantità** - La quantità verrà dichiarata finita nell'inventario ma lo stato dell'ordine di produzione non cambierà mai.
    - **Stato** - Solo lo stato dell'ordine di produzione cambierà. Nessuna quantità verrà aggiunta all'inventario quando le quantità vengono dichiarate nell'ultima operazione.

> [!NOTE]
> Le quantità non sono monitorate nell'inventario se le operazioni nelle quali sono dichiarate finite non vengono definite come ultima operazione. Tuttavia, tali quantità possono essere utilizzate per visualizzare lo stato. Possono anche essere incluse in regole che controllano se i lavoratori possono iniziare l'operazione successiva prima che venga raggiunta una soglia definita di quantità dichiarate per l'operazione precedente. È possibile definire queste regole nella scheda **Convalida quantità** nella pagina **Impostazioni predefinite ordini di produzione**.

Per ulteriori informazioni su come utilizzare la pagina **Impostazioni predefinite ordini di produzione**, vedere [Parametri di produzione di Esecuzione produzione](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Dichiarare finiti articoli controllati in batch

Il dispositivo scheda processo supporta tre scenari per la dichiarazione di articoli in batch. Questi scenari si applicano sia agli articoli abilitati per processi di magazzino avanzati sia agli articoli non abilitati per processi di magazzino avanzati.

- **Numeri di batch assegnati manualmente:** i lavoratori inseriscono un numero di batch personalizzato. Questo numero di batch potrebbe provenire da una fonte esterna non nota al sistema.
- **Numeri di batch predefiniti:** i lavoratori selezionano un numero di batch in un elenco di numeri di batch che il sistema genera automaticamente prima che l'ordine di produzione venga rilasciato al dispositivo scheda processo.
- **Numeri di batch fissi:** i lavoratori non inseriscono o selezionano un numero di batch. Il sistema assegna automaticamente un numero di batch all'ordine di produzione prima che venga rilasciato.


### <a name="enable-the-feature-on-your-system"></a>Abilitare la funzionalità nel sistema

Per consentire ai dispositivi scheda processo di accettare un numero di batch durante la dichiarazione di finito, è necessario utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le seguenti funzionalità (in questo ordine):

1. Esperienza utente migliorata per la finestra di dialogo Segnala stato nel dispositivo scheda processo
1. Abilitare per immettere numeri di serie e batch durante la dichiarazione di finito dal dispositivo scheda processo (anteprima)

### <a name="configure-products-that-require-batch-number-reporting"></a>Configurare i prodotti che richiedono la segnalazione del numero di batch

Per consentire a un prodotto di supportare uno qualsiasi degli scenari disponibili controllati in batch, attenersi alla seguente procedura:

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare il prodotto da configurare.
1. Nella Scheda dettaglio **Gestione articoli**, nel campo **Gruppo numeri batch**, selezionare il gruppo di numeri di tracciamento impostato per supportare lo scenario.

> [!NOTE]
> Per impostazione predefinita, se nessun gruppo di numeri di batch è assegnato a un prodotto controllato in batch, il dispositivo scheda processo fornisce l'inserimento manuale del numero di batch durante la dichiarazione di finito.

Le seguenti sezioni descrivono come impostare gruppi di numeri di tracciamento per supportare ciascuno dei tre scenari per la dichiarazione di articoli batch.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Configurare un gruppo di numeri di tracciamento che consente ai lavoratori di assegnare manualmente un numero di batch

Per consentire numeri di batch assegnati manualmente, seguire questi passaggi per impostare un gruppo di numeri di tracciamento:

1. Andare a **Gestione articoli \> Impostazioni \> Dimensioni \> Gruppi di numeri di tracciamento**.
1. Creare o selezionare il gruppo di numeri di tracciamento da configurare.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Manuale** su **Sì**.

    ![Un gruppo di numeri di tracciamento per numeri di batch manuali](media/tracking-number-group-manual.png "Un gruppo di numeri di tracciamento per numeri di batch manuali")

1. Impostare altri valori come necessario, quindi selezionare questo gruppo di numeri di tracciamento come gruppo di numeri di batch per i prodotti rilasciati per i quali si desidera utilizzare questo scenario.

Quando si utilizza questo scenario, il campo **Numero batch** nella pagina **Segnala stato** nel dispositivo scheda processo è una casella di testo in cui i lavoratori possono immettere qualsiasi valore.

![Pagina Segnala stato con un campo per i numeri di batch manuali](media/job-card-device-batch-manual.png "Pagina Segnala stato con un campo per i numeri di batch manuali")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Configurare un gruppo di numeri di tracciamento che fornisce un elenco di numeri di batch predefiniti

Per fornire un elenco di numeri di batch predefiniti, seguire questi passaggi per configurare un gruppo di numeri di tracciamento.

1. Andare a **Gestione articoli \> Impostazioni > Dimensioni \> Gruppi di numeri di tracciamento**.
1. Creare o selezionare il gruppo di numeri di tracciamento da configurare.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Solo per operazioni di magazzino** su **Sì**.
1. Utilizzare il campo **Per qtà** per dividere i numeri di batch per quantità, in base al valore inserito. Ad esempio, si ha un ordine di produzione per dieci pezzi e il campo **Per qtà** è impostato su *2*. In questo caso, cinque numeri di batch verranno assegnati all'ordine di produzione quando questo viene creato.

    ![Un gruppo di numeri di tracciamento per numeri di batch predefiniti](media/tracking-number-group-predefined.png "Un gruppo di numeri di tracciamento per numeri di batch predefiniti")

1. Impostare altri valori come necessario, quindi selezionare questo gruppo di numeri di tracciamento come gruppo di numeri di batch per i prodotti rilasciati per i quali si desidera utilizzare questo scenario.

Quando si utilizza questo scenario, il campo **Numero batch** nella pagina **Segnala stato** nel dispositivo scheda processo è un elenco a discesa in cui i lavoratori possono selezionare un valore predefinito.

![Pagina Segnala stato con un elenco di numeri di batch predefiniti](media/job-card-device-batch-predefined.png "Pagina Segnala stato con un elenco di numeri di batch predefiniti")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Configurare un gruppo di numeri di tracciamento che assegna automaticamente numeri di batch

Se i numeri di batch devono essere assegnati automaticamente, senza input del lavoratore, seguire questi passaggi per configurare un gruppo di numeri di tracciamento.

1. Andare a **Gestione articoli \> Impostazioni \> Dimensioni \> Gruppi di numeri di tracciamento**.
1. Creare o selezionare il gruppo di numeri di tracciamento da configurare.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Solo per operazioni di magazzino** su **No**.
1. Impostare l'opzione **Manuale** su **No**.

    ![Un gruppo di numeri di tracciamento per numeri di batch fissi](media/tracking-number-group-fixed.png "Un gruppo di numeri di tracciamento per numeri di batch fissi")

1. Impostare altri valori come necessario, quindi selezionare questo gruppo di numeri di tracciamento come gruppo di numeri di batch per i prodotti rilasciati per i quali si desidera utilizzare questo scenario.

Quando si utilizza questo scenario, il campo **Numero batch** nella pagina **Segnala stato** nel dispositivo scheda processo mostra un valore che i lavoratori non possono modificare.

![Pagina Segnala stato con un numero di batch fisso](media/job-card-device-batch-fixed.png "Pagina Segnala stato con un numero di batch fisso")

## <a name="report-serial-controlled-items-as-finished"></a>Dichiarare finiti articoli controllati in serie

Il dispositivo scheda processo supporta tre scenari per la dichiarazione di articoli controllati in serie. Questi scenari si applicano sia agli articoli abilitati per processi di magazzino avanzati sia agli articoli non abilitati per processi di magazzino avanzati.

- **Numeri di serie assegnati manualmente:** i lavoratori inseriscono un numero di serie personalizzato. Questo numero di serie potrebbe provenire da una fonte esterna non nota al sistema.
- **Numeri di serie predefiniti:** i lavoratori selezionano un numero di serie in un elenco di numeri di serie che il sistema genera automaticamente prima che l'ordine di produzione venga rilasciato al dispositivo scheda processo.
- **Numeri di serie fissi:** i lavoratori non inseriscono o selezionano un numero di serie. Il sistema assegna automaticamente un numero di serie all'ordine di produzione prima che venga rilasciato.

### <a name="enable-the-feature-on-your-system"></a>Abilitare la funzionalità nel sistema

Per consentire ai dispositivi scheda processo di accettare un numero di serie durante la dichiarazione di finito, è necessario utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le seguenti funzionalità (in questo ordine):

1. Esperienza utente migliorata per la finestra di dialogo Segnala stato nel dispositivo scheda processo
1. Abilitare per immettere numeri di serie e batch durante la dichiarazione di finito dal dispositivo scheda processo (anteprima)

### <a name="configure-products-that-require-serial-number-reporting"></a>Configurare i prodotti che richiedono la segnalazione del numero di serie

Per consentire a un prodotto di supportare uno qualsiasi degli scenari disponibili controllati in serie, attenersi alla seguente procedura:

Per abilitare ogni scenario, attenersi alla procedura seguente.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare il prodotto da configurare.
1. Nella Scheda dettaglio **Gestione articoli**, nel campo **Gruppo numeri di serie**, selezionare il gruppo di numeri di tracciamento impostato per supportare lo scenario.

> [!NOTE]
> Per impostazione predefinita, se nessun gruppo di numeri di serie è assegnato a un prodotto controllato in serie, il dispositivo scheda processo fornisce l'inserimento manuale del numero di serie durante la dichiarazione di finito.

Le seguenti sezioni descrivono come impostare gruppi di numeri di tracciamento per supportare ciascuno dei tre scenari per la dichiarazione di articoli controllati in serie.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-serial-number"></a>Configurare un gruppo di numeri di tracciamento che consente ai lavoratori di assegnare manualmente un numero di serie

Per consentire numeri di serie assegnati manualmente, seguire questi passaggi per impostare un gruppo di numeri di tracciamento:

1. Andare a **Gestione articoli \> Impostazioni \> Dimensioni \> Gruppi di numeri di tracciamento**.
1. Creare o selezionare il gruppo di numeri di tracciamento da configurare.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Manuale** su **Sì**.

    ![Pagina dei gruppi di numeri di tracciamento, numeri di serie](media/tracking-number-group-manual-serial.png "Pagina dei gruppi di numeri di tracciamento, numeri di serie")

1. Impostare altri valori come necessario, quindi selezionare questo gruppo di numeri di tracciamento come gruppo di numeri di serie per i prodotti rilasciati per i quali si desidera utilizzare questo scenario.

Quando si utilizza questo scenario, il campo **Numero di serie** nella pagina **Segnala stato** nel dispositivo scheda processo è una casella di testo in cui i lavoratori possono immettere qualsiasi valore per il numero di serie. Inserendo un valore, questo viene aggiunto all'elenco dei numeri di serie. In questo elenco, i lavoratori possono effettuare le seguenti operazioni:

- Per contrassegnare un numero di serie come scartato, selezionare il pulsante **Scarti** per la riga appropriata. Al lavoratore verrà richiesto di fornire una **Causa dell'errore**.
- Per eliminare un numero di serie, selezionare il pulsante **Elimina** per la riga appropriata.

![Pagina Segnala stato con un campo per i numeri di serie manuali](media/job-card-device-serial-manual.png "Pagina Segnala stato con un campo per i numeri di serie manuali")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-serial-numbers"></a>Configurare un gruppo di numeri di tracciamento che fornisce un elenco di numeri di serie predefiniti

Per fornire un elenco di numeri di serie predefiniti, seguire questi passaggi per configurare un gruppo di numeri di tracciamento.

1. Andare a **Gestione articoli \> Impostazioni \> Dimensioni \> Gruppi di numeri di tracciamento**.
1. Creare o selezionare il gruppo di numeri di tracciamento da configurare.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Solo per operazioni di magazzino** su **Sì**.
1. Utilizzare il campo **Per qtà** per dividere i numeri di serie per quantità di uno.

    ![Un gruppo di numeri di tracciamento per numeri di serie predefiniti](media/tracking-number-group-predefined-sn.png "Un gruppo di numeri di tracciamento per numeri di serie predefiniti")

1. Impostare altri valori come necessario, quindi selezionare questo gruppo di numeri di tracciamento come gruppo di numeri di serie per i prodotti rilasciati per i quali si desidera utilizzare questo scenario.

Quando si utilizza questo scenario, il campo **Numero di serie** nella pagina **Segnala stato** nel dispositivo scheda processo è un elenco a discesa in cui i lavoratori possono selezionare un valore predefinito.

![Pagina Segnala stato con un elenco di numeri di serie predefiniti](media/job-card-device-serial-predefined.png "Pagina Segnala stato con un elenco di numeri di serie predefiniti")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-serial-numbers"></a>Configurare un gruppo di numeri di tracciamento che assegna automaticamente numeri di serie

Se un numero di serie deve essere assegnati automaticamente, senza input del lavoratore, seguire questi passaggi per configurare un gruppo di numeri di tracciamento.

1. Andare a **Gestione articoli \> Impostazioni \> Dimensioni \> Gruppi di numeri di tracciamento**.
1. Creare o selezionare il gruppo di numeri di tracciamento da configurare.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Solo per operazioni di magazzino** su **No**.
1. Impostare l'opzione **Manuale** su **No**.

    ![Un gruppo di numeri di tracciamento per numeri di serie fissi](media/tracking-number-group-fixed-sn.png "Un gruppo di numeri di tracciamento per numeri di serie fissi")

1. Impostare altri valori come necessario, quindi selezionare questo gruppo di numeri di tracciamento come gruppo di numeri di serie per i prodotti rilasciati per i quali si desidera utilizzare questo scenario.

Quando si utilizza questo scenario, il campo **Numero di serie** nella pagina **Segnala stato** nel dispositivo scheda processo mostra un valore che i lavoratori non possono modificare. Questo scenario è rilevante solo quando viene creato un ordine di produzione per una quantità di un pezzo di un articolo controllato in serie.

![Pagina Segnala stato con un numero di serie fisso](media/job-card-device-serial-fixed.png "Pagina Segnala stato con un numero di serie fisso")

## <a name="report-as-finished-to-a-license-plate"></a>Dichiarazione di finito per una targa

I processi di magazzino avanzati possono utilizzare la dimensione della targa per tenere traccia dell'inventario nelle posizioni di magazzino che sono state impostate per questo scopo. In questo caso, il numero di targa viene richiesto quando un lavoratore dichiara finite le quantità.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Abilitare la dichiarazione di una targa e stampa di etichette

Per utilizzare le funzionalità descritte in questa sezione, è necessario utilizzare la pagina [Gestione funzionalità ](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le seguenti funzionalità (in questo ordine):

1. Targa per la dichiarazione di finito aggiunta al dispositivo scheda processo
1. Abilitare la generazione automatica del numero di identificazione durante la dichiarazione di finito nel dispositivo scheda processo
1. Stampa etichetta dal dispositivo scheda processo

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Configurare la dichiarazione di finito per una targa

Per controllare se i lavoratori devono riutilizzare una targa esistente o generare una nuova targa quando dichiarano finite le quantità, attenersi alla seguente procedura.

1. Passare a **Controllo produzione \> Impostazioni \> Esecuzione produzione \> Configura scheda processo per dispositivi**.
2. Impostare le seguenti opzioni per ciascun dispositivo:

    - **Genera targa**: impostare questa opzione su **Sì** per generare una nuova targa per ogni dichiarazione di finito. Impostarla su **No** se una targa esistente deve essere utilizzata per ogni dichiarazione di finito.
    - **Stampa etichetta**: impostare questa opzione su **Sì** se il lavoratore deve stampare l'etichetta di una targa per ogni dichiarazione di finito. Impostarla su **No** se l'etichetta non è richiesta. 

![Pagina Configura scheda processo per dispositivi](media/config-job-card-raf.png "Pagina Configura scheda processo per dispositivi")

> [!NOTE]
> Per configurare l'etichetta, andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout distribuzione documenti**. Per ulteriori informazioni, vedere [Abilitare la stampa di etichette targa](../warehousing/tasks/license-plate-label-printing.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]