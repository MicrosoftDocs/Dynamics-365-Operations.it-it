---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica per il Brasile
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il Brasile in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: fb3ec2d60875d7a0747d64b397aafaa0a3d26348
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039871"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica per il Brasile 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Il componente aggiuntivo per la fatturazione elettronica per il Brasile attualmente non supporta tutte le funzioni disponibili nell'integrazione del documento fiscale incorporata in Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il Brasile. Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e in Finance e Supply Chain Management. Inoltre, guida l'utente attraverso il processo di invio di un documento fiscale NF-e (modello di documento fiscale elettronico 55) tramite il servizio e spiega come rivedere i risultati dell'elaborazione e lo stato dei documenti fiscali.

## <a name="prerequisites"></a>Prerequisiti

Prima di completare i passaggi in questo argomento, è necessario completare i passaggi in [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Impostazioni RCS

Durante la configurazione RCS, completerai queste attività:

1. Importa la funzionalità di fatturazione elettronica per i documenti fiscali NF-e.
2. Rivedi i formati di file necessari per inviare i documenti fiscali NF-e per l'autorizzazione.
3. Rivedi i formati di file necessari per richiedere l'annullamento di un documento NF-e approvato.
4. Configura l'evento necessario per inviare i documenti fiscali NF-e per l'autorizzazione.
5. Configura l'evento necessario per richiedere l'annullamento di un documento NF-e approvato.
6. Assegna la funzionalità di fatturazione elettronica a un ambiente di componente aggiuntivo per la fatturazione elettronica.
7. Pubblica la funzionalità per la fatturazione elettronica.

> [!NOTE]
> "La funzionalità per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server del componente aggiuntivo per la fatturazione elettronica. La configurazione della funzionalità di fatturazione elettronica combina, tra le altre cose, l'uso di formati di configurazione per la creazione di report elettronici (ER) per creare file di esportazione e importazione configurabili e l'uso di azioni e flussi di azioni per consentire la creazione di regole configurabili per inviare richieste, importare le risposte e analizzare il contenuto della risposta.

## <a name="import-the-e-invoicing-feature"></a>Importare la funzionalità per la fatturazione elettronica

1. Accedere al tuo account RCS
2. Nell'area di lavoro **Funzionalità di globalizzazione** , nella sezione **Funzionalità** , seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Funzionalità di fatturazione elettronica** , seleziona **Importa** per importare un la funzionalità di fatturazione elettronica per un documento fiscale NF-e dal repository globale.

    ![Pulsante Importa](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Seleziona la funzionalità del documento fiscale NF-e, quindi seleziona **Importa**.

    ![Importazione della funzionalità NF-e](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Creare una nuova versione della funzionalità per il documento fiscale NF-e

- Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Versioni** , seleziona **Nuovo**.

![Aggiunta di una nuova versione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>Aggiornare la versione della configurazione

1. Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Configurazioni** , seleziona **Aggiungi** o **Elimina** per gestire le versioni di configurazione (configurazioni formato di file ER).

    ![Gestione delle configurazioni della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - Quando si crea una nuova versione della funzionalità per il documento fiscale NF-e, tutte le versioni di configurazione (formati di file ER) vengono ereditate dalla versione più recente.
    - Per inviare il documento fiscale NF-e per l'autorizzazione, sono necessarie le seguenti versioni di configurazione:

        - Formato di esportazione per l'invio di NFe
        - Importazione del messaggio di risposta NFe
        - Importazione del registro errori NFe

    - Per inviare l'annullamento di NF-e, è richiesta la seguente versione di configurazione:

        - Formato di esportazione per l'annullamento di NFe

2. Nell'elenco, seleziona una versione di configurazione, quindi seleziona **Modifica** o **Visualizza** per aprire la pagina **Progettazione formati** , dove puoi modificare o visualizzare la configurazione.

    ![Apertura della pagina Progettazione formati](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Utilizza la pagina **Progettazione formati** per modificare o visualizzare le configurazioni dei file in formato ER. Per ulteriori informazioni, vedi [Creare configurazioni di creazione di report elettronici (ER)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Pagina Progettazione formati](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Gestire le configurazioni della funzionalità di fatturazione elettronica

- Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Configurazioni** , seleziona **Aggiungi** o **Elimina** per gestire le configurazioni della funzionalità di fatturazione elettronica (ovvero, eventi NF-e).

![Gestione delle configurazioni della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

Quando si crea una nuova versione della funzionalità per il documento fiscale NF-e derivata da un'altra funzionalità di fatturazione elettronica, tutte le configurazioni delle funzionalità (eventi NF-e) vengono ereditate dalla versione più recente.

Per inviare documenti fiscali NF-e per l'autorizzazione è necessaria la configurazione della funzionalità **Invia**.

Per inviare l'annullamento NF-e, è richiesta la configurazione della funzionalità **Annullamento**.

#### <a name="configure-the-submit-feature-setup"></a>Configurare l'impostazione della funzionalità di invio

1. Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Configurazioni** , nella colonna **Configurazione funzionalità** , seleziona **Invia**.
2. Selezionare **Modifica**.

    ![Modificare la configurazione della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. Nella pagina **Configurazione versioni funzionalità** , seleziona la scheda **Azioni** per gestire l'elenco delle azioni.

    ![Scheda Azioni](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Rivedi le azioni necessarie per inviare un NF-e per l'autorizzazione.

    | ID azione | Nome azione                  | Descrizione azione                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Trasforma documento           | Crea il file XML NF-e per l'invio.                          |
    | 2         | Firma documento                | Applica il certificato digitale al file XML.                    |
    | 3         | Chiama servizio SEFAZ brasiliano | Invia il file XML firmato ai servizi Web per l'autorizzazione. |
    | 4         | Elabora risposta             | Ottieni la risposta del servizio Web.                                     |
    | 5         | Trasforma documento           | Analizza il contenuto del file ricevuto come risposta.     |
    | 6         | Trasforma documento           | Crea il file XML per chiedere informazioni sullo stato dell'invio.    |
    | 7         | Chiama servizio SEFAZ brasiliano | Invia il file XML che richiede lo stato di invio.          |
    | 8         | Elabora risposta             | Ottieni la risposta del servizio Web.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Configurare l'URL per i servizi Web SEFAZ 

1. Nella pagina **Configurazione versione funzionalità** , nella scheda **Azioni** , nella Scheda dettaglio **Azioni** , seleziona **Chiama servizio SEFAZ brasiliano** (ID azione **3** ).
2. Nella Scheda dettaglio **Parametri** , nel campo **Parametro indirizzo URL** , immetti l'URL del servizio Web SEFAZ per l'invio di NF-e.
3. Nella Scheda dettaglio **Azioni** , seleziona **Chiama il servizio SEFAZ brasiliano** (ID azione **7** ).
4. Nella Scheda dettaglio **Parametri** , nel campo **Parametro indirizzo URL** , immetti l'URL del servizio Web SEFAZ per l'invio di NF-e.

#### <a name="configure-the-cancellation-feature-setup"></a>Configurare l'impostazione della funzionalità di annullamento

1. Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Configurazioni** , nella colonna **Configurazione funzionalità** , seleziona **Annullamento**.
2. Selezionare **Modifica**.
3. Nella pagina **Configurazione versioni funzionalità** , seleziona la scheda **Azioni** per gestire l'elenco delle azioni.
4. Rivedi le azioni necessarie per richiedere l'annullamento di un documento NF-e approvato.

    | ID azione | Nome azione                  | Descrizione azione                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Trasforma documento           | Crea il file XML di annullamento NF-e per l'invio.            |
    | 2         | Firma documento                | Applica il certificato digitale al file XML.                   |
    | 3         | Chiama servizio SEFAZ brasiliano | Invia il file XML firmato ai servizi Web per l'annullamento. |
    | 4         | Elabora risposta             | Ottieni la risposta del servizio Web.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Configurare l'URL per i servizi Web SEFAZ

1. Nella pagina **Configurazione versione funzionalità** , nella scheda **Azioni** , nella Scheda dettaglio **Azioni** , seleziona **Chiama servizio SEFAZ brasiliano** (ID azione **3** ).
2. Nella Scheda dettaglio **Parametri** , nel campo **Parametro indirizzo URL** , immetti l'URL del servizio Web SEFAZ per l'annullamento di un documento NF-e approvato.

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>Rendere disponibile un ambiente di fatturazione elettronica e assegnare una versione Bozza

1. Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Ambienti** , seleziona **Abilita**.
2. Nel campo **Ambiente** , seleziona l'ambiente.
3. Nel campo **Valido da** , seleziona la data in cui il nuovo ambiente dovrebbe diventare effettivo.
4. Seleziona **Abilita**.

![Abilitazione di un ambiente di fatturazione elettronica](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Modificare lo stato in Completato

1. Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Versioni** , seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.
2. Selezionare **Cambia stato \> Completa**.

### <a name="change-the-status-to-publish"></a>Modificare lo stato in Pubblica

1. Nella pagina **Funzionalità di fatturazione elettronica** , nella scheda **Versioni** , seleziona la versione della funzionalità di fatturazione elettronica con stato **Completato**.
2. Seleziona **Cambia stato \> Pubblica**.

![Pubblicazione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance o Supply Chain Management

Durante la configurazione, completerai queste attività:

1. Attiva la funzionalità NF-e Federal per il Brasile.
2. Importa il modello di dati ER specifico, il mapping del modello di dati ER e i formati richiesti per i documenti fiscali NF-e.
3. Importa la configurazione ER e configura i tipi di risposta necessari per aggiornare lo stato del documento fiscale dopo la restituzione del processo di invio.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Attivare la funzionalità NF-e Federal per il Brasile

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Funzionalità** , seleziona la casella di controllo **Abilita** nella riga per il riferimento di funzionalità **BR00053**.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Importare il mapping del modello di dati ER richiesto per i documenti fiscali NF-e

1. Accedi a Finance.
2. Nell'area di lavoro **Creazione di report elettronici** , nella sezione **Provider di configurazione** , selezionare **Provider di configurazione**. Assicurati che questo provider di configurazione sia impostato su **Attivo**. Per ulteriori informazioni su come impostare un provider su **Attivo** , vedi [Creare provider di configurazioni e contrassegnarli come attivi](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Selezionare **Archivi**.
4. Seleziona **Risorsa globale \> Apri**.
5. Importa le configurazioni **Mapping documenti fiscali**.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>Importare le configurazioni ER e configurare i tipi di risposta per i documenti fiscali

1. Nell'area di lavoro **Creazione di report elettronici** , nella sezione **Provider di configurazione** , selezionare **Provider di configurazione**.
2. Selezionare **Archivi**.
3. Seleziona **Risorsa globale \> Apri**.
4. Importa **Importazione del registro errori NFe (BR)** , **Formato di importazione dei dati di risposta NF-e (BR)** e **Importazione di messaggi di risposta NF-e (BR)**.
5. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
6. Nella scheda **Documento elettronico** , seleziona **Aggiungi**.
6. Nel campo **Nome tabella** , immetti **Intestazione documento fiscale**.
7. Nel campo **Contesto documento** , seleziona **Modello di contesto fattura cliente - Contesto documento fiscale**.
8. Seleziona **Tipi di risposta**.
9. Seleziona **Nuovo** , quindi nel campo **Tipo di risposta** , seleziona **Risposta**.
10. Nel campo **Stato invio** , seleziona **In sospeso**.
11. Nel campo **Mapping modello** , seleziona **Formato di importazione dei messaggi di risposta: mapping del modello dal messaggio di risposta**.
12. Selezionare **Salva**.
13. Seleziona **Nuovo** , quindi nel campo **Tipo di risposta** , immetti **ResponseData**.
14. Nel campo **Stato invio** , seleziona **In sospeso**.
15. Nel campo **Mapping modello** , seleziona **Formato di importazione dei dati di risposta NFe - Importazione dei dati di risposta**.
16. Selezionare **Salva**.

## <a name="electronic-invoice-processing"></a>Elaborazione fattura elettronica

Durante l'elaborazione in Finance, completerai queste attività:

1. Invia un documento fiscale tramite il componente aggiuntivo per la fatturazione elettronica.
2. Visualizza i log di esecuzione dell'invio e rivedi i risultati dell'elaborazione.
3. Invia l'annullamento di un documento fiscale tramite il componente aggiuntivo per la fatturazione elettronica.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Invia i documenti fiscali NF-e per l'autorizzazione SEFAZ 

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** , il vecchio processo per l'invio di documenti fiscali NF-e per l'autorizzazione ( **Processo esportazione/importazione NF-e** ) non può più essere utilizzato. È sostituito da un nuovo processo denominato **Invia documenti elettronici**.

> [!NOTE]
> Prima di continuare, assicurati di disporre di uno o più documenti fiscali del cliente modello 55 emessi dall'istituto fiscale del cliente. La direzione per questi documenti fiscali deve essere impostata su **In uscita** e lo stato deve essere **Creato**. Per ulteriori informazioni, vedi [Emettere documenti fiscali cliente (Brasile)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Invia documenti elettronici**.
2. Per il primo invio di qualsiasi documento, imposta sempre l'opzione **Invia di nuovo i documenti** su **No**. Se devi inviare nuovamente un documento tramite il servizio, imposta questa opzione su **Sì**.
3. Nella Scheda dettaglio **Record da includere** , seleziona **Filtra** per aprire la finestra di dialogo **Richiesta** in cui è possibile creare una query per selezionare i documenti da inviare.
4. Nella scheda **Gamma** seleziona **Aggiungi**.
5. Nel campo **Tabella** , seleziona **Intestazione documento fiscale**.
6. Nel campo **Tabella derivata** , seleziona **Intestazione documento fiscale**.
6. Nel campo **Campo** seleziona **Numero**.
7. Nel campo **Criteri** , immetti il numero del documento fiscale da inviare.
8. Seleziona **OK** per chiudere la finestra di dialogo **Richiesta**.
8. Seleziona **OK** per inviare i documenti selezionati.

> [!NOTE]
> Durante il tuo primo tentativo di inviare un documento tramite il servizio, ti verrà chiesto di confermare la connessione con il componente aggiuntivo per la fatturazione elettronica. Seleziona **Fai clic qui per connetterti al servizio di invio documenti elettronici**.

### <a name="view-all-submission-logs"></a>Visualizzare tutti i registri di invio

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** , è disponibile una nuova pagina che consente di completare il processo di invio del documento. È possibile utilizzare questa pagina per visualizzare i registri di invio per tutti i documenti inviati.

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento** , seleziona **Intestazione documento fiscale** per filtrare solo i documenti fiscali.
3. Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.

![Visualizzazione dei dettagli del registro di invio](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> Per i documenti fiscali NF-e, la colonna **Codice di errore** mostra il codice di reso che è stato restituito dai servizi Web SEFAZ.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Visualizzare i registri di invio tramite la pagina del documento fiscale

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** puoi anche visualizzare i registri di invio tramite la pagina del documento fiscale.

1. Vai a **Contabilità generale \> Richieste e segnalazioni \> Documenti fiscali \> Tutti i documenti fiscali**.
2. Seleziona un documento fiscale precedentemente inviato tramite il componente aggiuntivo per la fatturazione elettronica.
3. Nel riquadro azioni, nella scheda **NF-e federale** , seleziona **Registro documenti elettronici**.

![Visualizzazione dei registri di invio dalla pagina del documento fiscale](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Inviare documenti fiscali NF-e approvati per l'annullamento SEFAZ

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** , il vecchio processo per l'annullamento dei documenti fiscali NF-e non può più essere utilizzato. Viene sostituito da un nuovo processo di annullamento incorporato nella pagina **Registro di invio documenti elettronici**.

> [!NOTE]
> Assicurati di aver eseguito l'annullamento del documento fiscale del cliente per un documento fiscale NF-e approvato. Per ulteriori informazioni, vedi [Annullare documenti fiscali cliente (Brasile)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Seleziona il documento fiscale, quindi seleziona **Funzioni \> Invia comunicazioni correlate**.
3. Immetti una descrizione per l'invio correlato, quindi seleziona **OK**.

### <a name="view-cancellation-submission-logs"></a>Visualizzare tutti i registri di annullamento

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento** , seleziona **Intestazione documento fiscale** per filtrare solo i documenti fiscali.
3. Seleziona il documento fiscale e quindi, nel riquadro azioni, seleziona **Richieste di informazioni \> Invio correlato**.

    Gli invii correlati sono invii relativi a un invio principale effettuato per primo. Ad esempio, l'invio che autorizza uno specifico NF-e è l'invio principale. L'invio che richiede l'annullamento dello stesso NF-e in SEFAZ è un invio correlato. Esiste solo perché richiede l'annullamento del processo che è stato eseguito tramite un altro invio.

    La pagina **Invii correlati** mostra tutti gli invii correlati e il loro stato di invio per un determinato documento fiscale. Nella figura seguente, la prima riga rappresenta l'invio che ha richiesto l'approvazione del documento fiscale. La seconda riga rappresenta l'invio che ha annullato il documento fiscale.

    ![Visualizzazione di tutti i registri di annullamento](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.

    ![Visualizzazione dei dettaglio del registro di invio annullamento](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Informativa sulla privacy
L'abilitazione della funzionalità e BR-00053 (NF-e Federal) potrebbe richiedere l'invio di dati limitati, che includono l'ID di registrazione fiscale dell'organizzazione. Questo verrà trasmesso ad agenzie di terze parti autorizzate dall'autorità fiscale allo scopo di inviare fatture elettroniche a questa autorità fiscale nel formato predefinito richiesto per l'integrazione con il servizio Web del governo. Un amministratore può abilitare e disabilitare la funzionalità  BR-00053 (NF-e Federal) tramite l'accesso a **Amministrazione organizzazione \> Impostazione \>Parametri del documento elettronico**. Seleziona la scheda **Funzionalità** , seleziona la riga contenente la funzionalità BR-00053, quindi effettua la selezione appropriata. I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Per ulteriori informazioni, consulta le sezioni dell'Informativa sulla privacy nella documentazione delle funzionalità specifiche del paese.


## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md)
- [Configurare il componente aggiuntivo per la fatturazione elettronica](e-invoicing-setup.md)
