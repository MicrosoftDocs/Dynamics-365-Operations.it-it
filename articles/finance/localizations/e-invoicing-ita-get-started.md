---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica per l'Italia
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per l'Italia in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 08d41244d3ec785127db8f69e37dd522a463c388
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988542"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica per l'Italia

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Il componente aggiuntivo per la fatturazione elettronica per l'Italia potrebbe attualmente non supportare tutte le funzioni disponibili per le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management. 

Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il l'Italia. Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e Finance. Inoltre, guida l'utente attraverso il processo di invio delle fatture elettroniche generate nel formato **FatturaPA** specifico per l'Italia tramite il servizio e spiega come rivedere i risultati dell'elaborazione.

## <a name="prerequisites"></a>Prerequisiti

Prima di completare i passaggi in questo argomento, è necessario completare i passaggi in [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Impostazioni RCS

Durante la configurazione RCS, completerai queste attività:

1. Importa la funzionalità di fatturazione elettronica per l'esportazione delle fatture elettroniche dei clienti nel formato **FatturaPA**.
2. Esamina le configurazioni di formato necessarie per generare, inviare e ricevere risposte sulle fatture elettroniche.
3. Configura gli eventi che supportano gli scenari di invio delle fatture elettroniche.
4. Pubblica la funzionalità per la fatturazione elettronica.

> [!NOTE]
> "La funzionalità per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server del componente aggiuntivo per la fatturazione elettronica. In questo caso, l'esportazione delle fatture elettroniche dei clienti rappresenta la funzionalità di fatturazione elettronica che configurerai.

## <a name="import-the-e-invoicing-feature"></a>Importare la funzionalità per la fatturazione elettronica

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Funzionalità di fatturazione elettronica**, seleziona **Importa** per importare la funzionalità di fatturazione elettronica dal repository globale.

    > [!NOTE]
    > Se non vedi l'elenco delle funzionalità disponibili, seleziona **Sincronizza**. 

4. Seleziona la funzionalità **Esportazione fatture elettroniche (IT)**, quindi seleziona **Importa**.

![Importazione della funzionalità di esportazione delle fatture elettroniche (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

Quando importi la funzionalità **Esportazione fatture elettroniche (IT)** dal repository globale, vengono importate anche tutte le impostazioni descritte nelle sezioni successive.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Creare una nuova versione della funzionalità di esportazioni delle fatture elettroniche (IT)

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona **Nuovo**. 

    ![Aggiunta di una nuova versione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    Successivamente, configurerai i formati di creazione di reporting elettronici (ER) associati alla funzionalità di fatturazione elettronica.

2. Nella scheda **Configurazioni**, seleziona **Aggiungi** per gestire le versioni di configurazione.

    ![Gestione delle versioni di configurazione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    In questo passaggio, stai aggiungendo e configurando i formati ER di diversi file utilizzati per esportare le fatture elettroniche italiane. Per le fatture elettroniche FatturaPA italiane, utilizza le seguenti configurazioni standard o le configurazioni personalizzate effettive utilizzate per la fatturazione elettronica:

    - Fattura di vendita (IT)
    - Fattura di progetto (IT)

    Quando crei una funzionalità di fatturazione elettronica derivata da un'altra funzionalità di fatturazione elettronica, tutti i formati ER vengono ereditati dalla funzionalità originale.

3. Seleziona una configurazione di file in formato ER specifica.
4. Seleziona **Modifica** o **Visualizza** per aprire la pagina **Progettazione formati**.

    ![Apertura della pagina Progettazione formati](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Utilizza la pagina **Progettazione formati** per modificare e visualizzare le configurazioni dei file in formato ER.

    ![Pagina Progettazione formati](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Gestire le configurazioni della funzionalità di fatturazione elettronica

- Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi**, **Elimina** o **Modifica** per gestire le configurazioni della funzionalità di fatturazione elettronica.

![Gestione delle configurazioni della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

In questo passaggio si configurano gli eventi applicabili alle fatture elettroniche, inclusa la generazione dei file di output XML in formato **FatturaPA** e firma digitale (se richiesta).

### <a name="configure-the-sales-invoice-feature-setup"></a>Configurare l'impostazione della funzionalità Fattura di vendita

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, nella colonna **Configurazione funzionalità**, seleziona **Fattura di vendita**.
2. Selezionare **Modifica**.
3. Nella pagina **Configurazione versioni funzionalità**, seleziona la scheda **Azioni** per gestire l'elenco delle azioni. Le azioni definiscono un elenco di operazioni che devono essere eseguite in ordine sequenziale per completare l'intera esecuzione dell'evento.

    ![Scheda Azioni](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | ID azione | Nome azione        | Descrizione azione                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Trasforma documento | Crea il file XML della fattura elettronica in formato **FatturaPA**. |
    | 2         | Firma documento      | Applica una firma digitale al file XML.             |

4. Seleziona la scheda **Regole di applicabilità** per visualizzare e gestire le regole di applicabilità. Le regole di applicabilità definiscono il contesto in cui verrà eseguita l'azione.

    ![Scheda Regole di applicabilità](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. Seleziona la scheda **Variabili** per visualizzare e gestire le variabili.

    ![Scheda Variabili](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. Definisci le variabili pubbliche necessarie per eseguire le azioni.

### <a name="configure-the-project-invoice-feature-setup"></a>Configurare l'impostazione della funzionalità Fattura di progetto 

I passaggi e le impostazioni necessari per configurare la funzionalità **Fattura di progetto** sono molto simili ai passaggi e alle impostazioni per configurare la funzionalità **Fattura di vendita**. Quando si lavora con le fatture di progetto, vedi le procedure per le fatture di vendita.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Assegnare la funzionalità di fatturazione elettronica all'ambiente

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Ambienti**, seleziona **Abilita**.
2. Nel campo **Ambiente**, seleziona l'ambiente.
3. Nel campo **Valido da**, seleziona la data in cui il nuovo ambiente dovrebbe diventare effettivo.
4. Seleziona **Abilita**. 

![Abilitazione dell'ambiente di fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Pubblicare la funzionalità per la fatturazione elettronica

È possibile pubblicare la funzione di fatturazione elettronica modificando lo stato della versione in **Completato** o **Pubblicato**.

### <a name="change-the-version-status-to-completed"></a>Modificare lo stato della versione in Completato

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.
2. Selezionare **Cambia stato \> Completa**. 

### <a name="change-the-version-status-to-published"></a>Modificare lo stato della versione in Pubblicato 

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Completato**.
2. Seleziona **Cambia stato \> Pubblica**.

![Modifica dello stato della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a>Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance

Durante la configurazione di Finance, completerai queste attività:

1. Importa il modello di dati ER, il mapping del modello di dati ER e le configurazioni del contesto per le fatture elettroniche FatturaPA.
2. Configura il certificato necessario per la firma digitale delle fatture elettroniche italiane.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Importa il modello di dati ER, il mapping del modello di dati e i formati

1. Nell'area di lavoro **Creazione di report elettronici**, verificare che il provider di configurazione **Servizio documenti aziendali** sia impostato su **Attivo**.
2. Selezionare **Archivi**.
3. Seleziona **Risorsa globale \> Apri**.
4. Importa **Modello di fattura**, **Mapping modello di fattura** e **Modello di contesto della fattura cliente**.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Attivare la funzionalità per esportare le fatture elettroniche dei clienti per l'Italia

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Funzionalità**, seleziona la casella di controllo **Abilitata** nella riga per il riferimento di funzionalità **IT00036**.

![Attivazione della funzionalità FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Configurare documenti elettronici

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Documento elettronico**, seleziona **Aggiungi** e inserisci le tabelle necessarie per generare le fatture elettroniche italiane:

    - **Nome tabella:** giornale di registrazione fatture cliente
    - **Nome tabella:** fattura di progetto

3. Per ogni tabella, definisci un contesto di documento correlato:

    - Per **Giornale di registrazione fatture cliente**, seleziona **Contesto della fattura cliente**.
    - Per **Fattura di progetto**, seleziona **Contesto della fattura di progetto**.

![Configurazione dei tipi di risposta](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Elaborazione fattura elettronica

Durante l'elaborazione in Finance, completerai queste attività:

1. Generare fatture elettroniche italiane tramite il componente aggiuntivo per la fatturazione elettronica
2. Visualizzare i log di esecuzione e rivedere i risultati dell'elaborazione

### <a name="generate-electronic-invoices"></a>Generare fatture elettroniche

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** e la funzionalità **IT00036**, il vecchio processo di Finance per la generazione di fatture elettroniche italiane non può più essere utilizzato. È sostituito da un nuovo processo denominato **Invia documenti elettronici**.

È possibile inviare i documenti manualmente, in base alla richiesta di documenti di fatturazione elettronica.

> [!NOTE]
> Prima di continuare, verifica che la configurazione obbligatoria per le fatture elettroniche italiane sia stata completata. Per ulteriori informazioni, vedi [Fatture elettroniche dei clienti](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices). Tieni presente che alcuni dei passaggi di configurazione descritti in tale argomento potrebbero non essere disponibili a causa dell'attivazione del componente aggiuntivo per la fatturazione elettronica.

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Invia documenti elettronici**.
2. Per il primo invio di qualsiasi documento, imposta l'opzione **Invia di nuovo i documenti** su **No**. Se devi inviare nuovamente un documento tramite il servizio, imposta questa opzione su **Sì**.
3. Nella Scheda dettaglio **Record da includere**, seleziona **Filtra** per aprire la finestra di dialogo **Richiesta** in cui è possibile creare una query per selezionare i documenti da inviare.

![Finestra di dialogo Invia documenti elettronici](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Query filtri

1. Nella finestra di dialogo **Richiesta**, configura le condizioni di filtro sia per le fatture di vendita che per le fatture di progetto oppure lascia vuote le condizioni per includere tutte le fatture non inviate.

    ![Configurazione dei criteri del filtro di invio](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Seleziona **OK** per chiudere la finestra di dialogo **Richiesta**.
3. Seleziona **OK** per inviare i documenti selezionati.

> ![NOTE] Durante il tuo primo tentativo di inviare un documento tramite il servizio, ti verrà chiesto di confermare la connessione con il componente aggiuntivo per la fatturazione elettronica. Seleziona **Fai clic qui per connetterti al servizio di invio documenti elettronici**.

#### <a name="view-submission-logs"></a>Visualizzare i registri di invio

È possibile visualizzare i registri di invio per tutti i documenti inviati.

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento**, seleziona **Giornale di registrazione fatture cliente** o **Fattura di progetto** per filtrare i documenti elettronici obbligatori.

    ![Selezione di un tipo di documento per visualizzare i registri di invio](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    Il valore mostrato nella colonna **Stato invio** rappresenta lo stato del processo di invio. Indica se il processo è stato eseguito come configurato e se è necessaria un'azione aggiuntiva.

3. Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.

    ![Visualizzazione dei dettagli del registro di invio](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. Nella Scheda dettaglio **Azioni di elaborazione** puoi visualizzare il registro di esecuzione delle azioni configurate nella versione della funzionalità configurata in RCS. La colonna **Stato** mostra se l'azione è stata eseguita correttamente.
5. Nella Scheda dettaglio **File di azione** puoi visualizzare i file intermedi che sono stati generati durante l'esecuzione delle azioni. Puoi selezionare **Visualizza** per scaricare il file XML di output in formato **FatturaPA** e visualizzarne il contenuto.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md)
- [Configurare il componente aggiuntivo per la fatturazione elettronica](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]