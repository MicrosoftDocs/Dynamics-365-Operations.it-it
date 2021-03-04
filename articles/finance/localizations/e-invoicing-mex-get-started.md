---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica per il Messico
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il Messico in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6d15a79a359b3c708b2b33893d700377a57c3eb7
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512236"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica per il Messico

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Il componente aggiuntivo per la fatturazione elettronica per il Messico potrebbe attualmente non supportare tutte le funzioni disponibili nel documento Comprobante Fiscal Digital por Internet (CFDI) e nella relativa integrazione incorporata in Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il Messico. Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e Finance. Inoltre, guida l'utente attraverso i passaggi da seguire in Finance per inviare fatture CFDI tramite il servizio e spiega come esaminare i risultati dell'elaborazione e lo stato delle fatture CFDI.

## <a name="prerequisites"></a>Prerequisiti

Prima di completare i passaggi in questo argomento, è necessario completare i passaggi in [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Impostazioni RCS

Durante la configurazione RCS, completerai queste attività:

1. Importa la funzionalità per la fatturazione elettronica per l'elaborazione delle fatture CFDI.
2. Rivedi le configurazioni di formato necessarie per generare, inviare e ricevere risposte sulle fatture CFDI e per inviare e ricevere risposte sull'annullamento.
3. Configura gli eventi che supportano gli scenari di invio delle fatture CFDI.
4. Pubblica la funzionalità per la fatturazione elettronica per le fatture CFDI.

> [!NOTE]
> "La funzionalità per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server del componente aggiuntivo per la fatturazione elettronica. In questo caso, le fatture CFDI (MX) rappresentano la funzionalità per la fatturazione elettronica che configurerai.

## <a name="import-the-e-invoicing-feature"></a>Importare la funzionalità per la fatturazione elettronica

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Funzionalità di fatturazione elettronica**, seleziona **Importa** per importare la funzionalità **Fatture CFDI (MX)** dal repository globale.

    > [!NOTE]
    > Se non vedi la funzionalità nell'elenco, seleziona **Sincronizza** e quindi ripeti il passaggio 3.

![Importazione della funzionalità per le fatture CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

Quando importi la funzionalità **Fatture CFDI (MX)** dal repository globale, vengono importate anche tutte le impostazioni delle funzionalità, comprese le configurazioni e le azioni.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>Creare una nuova versione della funzionalità Fatture CFDI (MX)

È possibile creare una nuova versione se, ad esempio, gli URL devono essere aggiornati. Per ulteriori informazioni, vedi [Fatturazione elettronica CFDI](tasks/mx-00010-e-invoicing-cfdi.md).

- Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona **Nuovo**.

![Aggiunta di una nuova versione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>Aggiornare la versione della configurazione

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi** o **Elimina** per gestire le versioni di configurazione (configurazioni formato di file ER).

    ![Gestione delle configurazioni della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    Quando crei una nuova versione, tutte le configurazioni vengono ereditate dall'ultima versione pubblicata. Per elaborare le fatture CFDI, sono necessarie le seguenti configurazioni:

    - Fattura CFDI (BusinessDocumentService)
    - Importazione del messaggio di risposta CFDI
    - Importazione del registro errori CFDI
    - Richiesta di annullamento CFDI (MX) (BusinessDocumentService)
    - Fattura CFDI (BusinessDocumentService)

2. Nell'elenco, seleziona una versione di configurazione, quindi seleziona **Modifica** o **Visualizza** per aprire la pagina **Progettazione formati**, dove puoi modificare o visualizzare la configurazione.

    ![Apertura della pagina Progettazione formati](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Utilizza la pagina **Progettazione formati** per modificare e visualizzare le configurazioni dei file in formato ER. Per ulteriori informazioni, vedi [Creare configurazioni di creazione di report elettronici (ER)](../../dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Pagina Progettazione formati](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Gestire le configurazioni della funzionalità di fatturazione elettronica

- Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi**, **Elimina** o **Modifica** per gestire le configurazioni della funzionalità di fatturazione elettronica.

![Gestione delle configurazioni della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

Per inviare fatture CFDI per l'autorizzazione (generare il file XML, inviare il file XML ed elaborare la risposta), è richiesta la configurazione della funzionalità **Fattura di vendita**.

Per inviare l'annullamento della fattura CFDI, sono obbligatorie le configurazioni delle funzionalità **Annullamento** e **Annulla**.

### <a name="configure-the-sales-invoice-feature-setup"></a>Configurare l'impostazione della funzionalità Fattura di vendita

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, nella colonna **Configurazione funzionalità**, seleziona **Fattura di vendita**.
2. Seleziona **Modifica** per configurare le azioni, le regole di applicabilità e le variabili.

    ![Modifica della configurazione della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. Nella pagina **Configurazione versioni funzionalità**, seleziona la scheda **Azioni** per gestire l'elenco delle azioni. Le azioni definiscono un elenco di operazioni che devono essere eseguite in ordine sequenziale per completare l'intera esecuzione dell'evento.

    ![Scheda Azioni](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | ID azione | Azione                   | Nome azione                                  | Descrizione azione                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Trasforma documento       | Generare la fattura elettronica CFDI senza firma digitale | Genera la fattura elettronica CFDI.                                |
    | 2         | Firma documento            | Firma digitale                                 | Firma digitalmente la fattura elettronica per l'invio.                |
    | 3         | Chiama servizio PAC messicano | Inviare la fattura elettronica CFDI                        | Il client Windows Communication Foundation (WCF) invia la fattura elettronica CFDI. |
    | 4         | Elabora risposta         | Analizzare la risposta del servizio Web                 | Analizza la risposta del servizio Web e restituisci il registro degli errori. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>Configurare l'URL per i servizi Web PAC messicano 

1. Nella pagina **Configurazione versione funzionalità**, nella scheda **Azioni**, nella Scheda dettaglio **Azioni**, seleziona **Chiama servizio PAC messicano**.
2. Nella Scheda dettaglio **Parametri**, nel campo **Indirizzo URL**, immetti l'URL del servizio Web per l'invio della fattura CFDI.

> [!NOTE]
> Utilizza gli stessi passaggi per aggiornare l'URL per l'azione **Chiama servizio PAC messicano** per le configurazioni delle funzionalità **Annulla** e **Richiesta di annullamento**.

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>Assegnare la versione Bozza a un ambiente di fatturazione elettronica

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Ambienti**, seleziona **Abilita**.
2. Nel campo **Ambiente**, seleziona l'ambiente.
3. Nel campo **Valido da**, seleziona la data in cui il nuovo ambiente dovrebbe diventare effettivo.
3. Seleziona **Abilita**.

![Abilitazione di un ambiente di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>Modificare lo stato della versione in Completato

1. Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.
2. Selezionare **Cambia stato \> Completa**.

## <a name="change-the-version-status-to-published"></a>Modificare lo stato della versione in Pubblicato

- Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona **Cambia stato \> Pubblica**.

## <a name="publish-the-e-invoicing-feature"></a>Pubblicare la funzionalità per la fatturazione elettronica

1. Nella pagina **Funzionalità di fatturazione elettronica**, seleziona la scheda **Versioni** per gestire lo stato della funzionalità **Fatture CFDI (MX)**.
2. Seleziona **Cambia stato** per modificare lo stato della funzionalità.

![Modifica dello stato della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a>Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance

Per configurare il componente aggiuntivo per la fatturazione elettronica in Finance, completerai queste attività:

1. Importa il modello di dati ER, il mapping del modello di dati ER e i formati richiesti per le fatture CFDI.
2. Configura i tipi di risposta per l'aggiornamento delle fatture CFDI. Questi tipi di risposta vengono utilizzati per la risposta dal server PAC (provider di certificazione autorizzato).

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importare il modello di dati ER, il mapping del modello di dati ER e le configurazioni del contesto per le fatture CFDI

1. Accedi a Finance.
2. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**. Assicurati che questo provider di configurazione sia impostato su **Attivo**. Per ulteriori informazioni su come impostare un provider su **Attivo**, vedi [Creare provider di configurazioni e contrassegnarli come attivi](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Selezionare **Archivi**.
4. Seleziona **Risorsa globale \> Apri**.
5. Importa **Modello di fattura**, **Mapping modello di fattura**, **Formato fattura CFDI (MX)**, **Formato di richiesta annullamento fattura CFDI (MX)** e **Formato di annullamento della fattura CFDI (MX)**.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Attivare la funzionalità per l'elaborazione delle fatture CFDI

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Funzionalità**, seleziona la casella di controllo **Abilita** nelle righe per i riferimenti alle funzionalità **MX-00010** e **MX-00016**.

![Attivazione delle funzionalità per l'elaborazione delle fatture CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>Importare le configurazioni ER e configurare i tipi di risposta per l'aggiornamento delle fatture CFDI

#### <a name="import-er-configurations"></a>Importare configurazioni ER

1. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**.
3. Selezionare **Archivi**.
4. Seleziona **Risorsa globale \> Apri**.
5. Importa **Modello di messaggio di risposta**, **Importazione registro errori CFDI (MX)** e **Importazione messaggi di risposta CFDI (MX)**.

#### <a name="set-up-the-response-types"></a>Configurare i tipi di risposta

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Documento elettronico**, seleziona **Aggiungi**.
3. Immetti il giornale di registrazione fatture cliente e quindi nel campo **Nome tabella** seleziona la fattura del progetto.
4. Per ogni tabella, definisci un contesto di documento correlato:

    - Per **Giornale di registrazione fatture cliente**, immetti **Contesto della fattura cliente**.
    - Per **Fattura di progetto**, immetti **Contesto della fattura di progetto**.

4. Seleziona **Tipi di risposta** per configurare i tipi di risposta che possono essere restituiti dal componente aggiuntivo per la fatturazione elettronica e inclusi in un giornale di registrazione fatture cliente o in una fattura di progetto.
5. Seleziona **Nuovo**, quindi nel campo **Tipo di risposta**, seleziona **Risposta**.
6. Nel campo **Stato invio**, seleziona **In sospeso**.
7. Nel campo **Mapping modello**, seleziona **Formato di importazione dei messaggi di risposta: mapping del modello dal messaggio di risposta**.
8. Selezionare **Salva**.
9. Seleziona **Nuovo**, quindi nel campo **Tipo di risposta**, seleziona **ResponseData**.
10. Nel campo **Stato invio**, seleziona **In sospeso**.
11. Nel campo **Mapping modello**, seleziona **Formato di importazione dei dati di risposta CFDI (dettagli) - Importazione dei dati di risposta**.
12. Selezionare **Salva**.

## <a name="process-electronic-invoices-in-finance"></a>Elaborazione di fatture elettroniche in Finance 

Durante l'elaborazione delle fatture CFDI in Finance tramite il componente aggiuntivo per la fatturazione elettronica, è possibile eseguire le seguenti attività:

- Inviare le fatture CFDI.
- Visualizzare i log di esecuzione dell'invio.
- Inviare l'annullamento di una fattura CFDI.

### <a name="submit-cfdi-invoices"></a>Inviare le fatture CFDI

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**, il processo **Esporta/Importa fattura elettronica** (**Contabilità clienti \>Fatture \> Fatture elettroniche**) per l'invio di fatture CFDI non possono più essere utilizzati. È sostituito da un nuovo processo denominato **Invia documenti elettronici**.

> [!NOTE]
> Prima di utilizzare il nuovo processo **Invia documenti elettronici**, verifica che la configurazione obbligatoria per le fatture elettroniche messicane sia stata completata. Per altre informazioni, vedi [Versione layout CFDI 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Invia documenti elettronici**.
2. Per il primo invio di qualsiasi documento, imposta sempre l'opzione **Invia di nuovo i documenti** su **No**. Se devi inviare nuovamente un documento tramite il servizio, imposta questa opzione su **Sì**.
3. Nella Scheda dettaglio **Record da includere**, seleziona **Filtra** per aprire la finestra di dialogo **Richiesta** in cui è possibile creare una query per selezionare i documenti da inviare.

![Invio di un documento CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> Durante il tuo primo tentativo di inviare un documento tramite il servizio, ti verrà chiesto di confermare la connessione con il componente aggiuntivo per la fatturazione elettronica. Seleziona **Fai clic qui per connetterti al servizio di invio documenti elettronici**.

### <a name="view-submission-logs"></a>Visualizzare i registri di invio

È possibile visualizzare i registri di invio per tutti i documenti inviati o per un solo documento inviato.

#### <a name="view-all-submission-logs"></a>Visualizzare tutti i registri di invio

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**, è disponibile una nuova pagina che consente di completare il processo di invio del documento. È possibile utilizzare questa pagina per visualizzare i registri di invio per tutti i documenti inviati.

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento**, seleziona **Giornale di registrazione fatture cliente** per filtrare i documenti elettronici obbligatori.

    ![Selezione di un tipo di documento per visualizzare i registri di invio](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.

    ![Visualizzazione dei dettagli del registro di invio](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

Le informazioni nei registri di invio sono suddivise in tre Schede dettaglio:

- **Azioni di elaborazione**: questa Scheda dettaglio mostra il registro di esecuzione delle azioni configurate nella versione della funzionalità configurata in RCS. La colonna **Stato** mostra se l'azione è stata eseguita correttamente.
- **File di azione**: questa Scheda dettaglio mostra i file intermedi che sono stati generati durante l'esecuzione delle azioni. Puoi selezionare **Visualizza** per scaricare e visualizzare il file.
- **Registro azioni di elaborazione**: questa scheda dettaglio mostra i risultati della comunicazione tra il componente aggiuntivo per la fatturazione elettronica e il servizio Web di destinazione. Mostra anche ciò che è stato restituito dall'elaborazione del servizio Web. La colonna **Codice di errore** mostra il codice di reso che è stato restituito dal servizio Web di autorizzazione.

Quando la fattura CFDI inviata viene autorizzata, il suo stato viene aggiornato su **Approvata**.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Visualizzare i registri di invio dalle fatture CFDI

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile** puoi anche visualizzare i registri di invio dalle fatture CFDI.

1. Passa a **Contabilità clienti \> Richieste di informazioni e report \> CFDI (fatture elettroniche)**.
2. Seleziona una fattura CFDI inviata dopo l'attivazione della funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**.
3. Nel riquadro azioni, nella scheda **Cronologia**, seleziona **Registro documenti elettronici**.

![Visualizzazione dei registri di invio dalle fatture CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> Per le fatture CFDI presentate prima dell'attivazione della funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**, è disponibile il pulsante **Cronologia**. Il pulsante **Cronologia** non è disponibile per le fatture CFDI inviate dopo l'attivazione della funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**.

### <a name="submit-cancellation-of-cfdi-invoices"></a>Inviare l'annullamento delle fatture CFDI

Dopo aver attivato la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**, il vecchio processo per l'annullamento delle fatture CFDI non può più essere utilizzato. Viene sostituito da un nuovo processo di annullamento incorporato nella pagina **Registro di invio documenti elettronici**.

1. Passa a **Contabilità clienti \> Richieste di informazioni e report \> CFDI (fatture elettroniche)**.
2. Se la fattura CFDI ha uno stato **Approvato**, seleziona **Funzioni \> Annulla CFDI**.
3. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
4. Seleziona la fattura CFDI, quindi seleziona **Funzioni \> Invia comunicazioni correlate**.
5. Immetti una descrizione per l'invio correlato, quindi seleziona **OK**.

#### <a name="view-cancellation-submission-logs"></a>Visualizzare tutti i registri di annullamento

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento**, seleziona **Giornale di registrazione fatture cliente** per filtrare solo i documenti del giornale di registrazione delle fatture cliente.
3. Seleziona la fattura CFDI e quindi, nel riquadro azioni, seleziona **Richieste di informazioni \> Invio correlato**.

    La pagina **Invii correlati** mostra tutti gli invii correlati e il loro stato di invio per una determinata fattura CFDI. Nella figura seguente, la prima riga rappresenta l'invio che ha richiesto l'approvazione della fattura CFDI. La seconda riga rappresenta l'invio che ha annullato la fattura CFDI.

    ![Visualizzazione di tutti i registri di annullamento](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.

    ![Visualizzazione dei dettaglio del registro di invio annullamento](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Informativa sulla privacy
L'abilitazione delle funzionalità MX-00010 e MX-00016 (Fattura CFDI e Annullamento CFDI) potrebbe richiedere l'invio di dati limitati, che includono l'ID di registrazione fiscale dell'organizzazione. Questo verrà trasmesso ad agenzie di terze parti autorizzate dall'autorità fiscale allo scopo di inviare fatture elettroniche a questa autorità fiscale nel formato predefinito richiesto per l'integrazione con il servizio Web del governo. Un amministratore può abilitare e disabilitare le funzionalità MX-00010 e MX-00016 (Fattura CFDI e Annullamento CFDI) tramite l'accesso a **Amministrazione organizzazione \> Impostazione \>Parametri del documento elettronico**. Seleziona la scheda **Funzionalità**, seleziona le righe contenenti le funzionalità MX-00010 e MX-00016, quindi effettua la selezione appropriata. I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Consulta le sezioni dell'Informativa sulla privacy nella documentazione delle funzionalità specifiche del paese.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md)
- [Configurare il componente aggiuntivo per la fatturazione elettronica](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]