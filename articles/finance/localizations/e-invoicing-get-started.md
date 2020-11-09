---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
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
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039848"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica. Innanzitutto, ti guida attraverso i passaggi di configurazione in Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Services (RCS) e Dynamics 365 Finance. Successivamente, descrive il processo per l'invio di documenti tramite il servizio utilizzando Dynamics 365 Finance o Dynamics 365 Supply Chain Management. Imparerai anche come interpretare i registri di invio.

## <a name="availability"></a>Disponibilità

Il componente aggiuntivo per la fatturazione elettronica è inizialmente disponibile per diversi paesi/aree geografiche. Il componente aggiuntivo supporta la creazione di fatture elettroniche e l'invio dei seguenti documenti commerciali:

| Paese/area geografica  | Documento aziendale                          |
|-----------------|--------------------------------------------|
| Austria         | Fatture di vendita e di progetto                 |
| Belgio         | Fatture di vendita e di progetto                 |
| Brasile          | Modelli di documento fiscale elettronico 55 (NF-e) |
| Danimarca         | Fatture di vendita e di progetto                 |
| Estonia         | Fatture di vendita e di progetto                 |
| Finlandia         | Fatture di vendita e di progetto                 |
| Francia          | Fatture di vendita e di progetto                 |
| Germania         | Fatture di vendita e di progetto                 |
| Italia           | Fatture di vendita e di progetto                 |
| Messico          | Fattura CFDI                               |
| Paesi Bassi     | Fatture di vendita e di progetto                 |
| Norvegia          | Fatture di vendita e di progetto                 |
| Spagna           | Fatture di vendita e di progetto                 |
| Europa          | Fatture di vendita e di progetto PEPPOL          |
    
## <a name="licensing"></a>Licenze

È possibile utilizzare il componente aggiuntivo per la fatturazione elettronica con la licenza corrente. Non sono necessarie licenze aggiuntive per utilizzare il servizio.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare i passaggi in questo argomento, è necessario soddisfare i seguenti prerequisiti:

- Accesso al tuo account LCS.
- Un progetto di distribuzione LCS che include Finance o Supply Chain Management versione 10.0.13 o successiva.
- Accesso al tuo account RCS.
- Attiva la funzionalità di globalizzazione per il tuo account RCS tramite il modulo **Gestione funzionalità**. Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md)
- Crea una risorsa Key Vault e un account di archiviazione in Azure. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="overview"></a>Panoramica

La figura seguente mostra i cinque passaggi principali che verranno completati in questo argomento.

![Panoramica dei cinque passaggi in questo argomento](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Configurazione delle risorse di Azure:** configura l'archiviazione di Azure e il caricamento di certificati digitali in Azure Key Vault.
2. **Configurazione LCS:** installa il componente aggiuntivo per i microservizi.
3. **Configurazione RCS:** configurare l'ambiente, l'accesso utente e le funzioni di fatturazione elettronica.
4. **Configurazione client:** configura la connessione tra il client e il componente aggiuntivo per la fatturazione elettronica e disattiva le vecchie funzionalità per l'invio e la ricezione di risposte per i documenti elettronici.
5. **Invia fatture:** invia documenti elettronici tramite il componente aggiuntivo per la fatturazione elettronica e ricevi risposte.

> [!NOTE]
> Alcuni passaggi di configurazione in questo argomento sono comuni e indipendenti dal paese/area geografica. I passaggi e le procedure di configurazione specifici del paese/area geografica sono descritti negli argomenti specifici del paese/area geografica.

## <a name="lcs-setup"></a>Impostazioni LCS

1. Accedi al tuo account LCS.
2. Seleziona il riquadro **Gestione funzionalità di anteprima** e nel gruppo di campi **Funzionalità di anteprima pubblica** , seleziona **BusinessDocumentSubmission**.
3. Seleziona il campo **Funzionalità di anteprima abilitata**.
4. Seleziona il progetto di distribuzione LCS. Prima di poter selezionare il progetto, è necessario che sia attivo e funzionante.
5. Nella Scheda dettaglio **Componenti aggiuntivi per l'ambiente** , seleziona **Installa un nuovo componente aggiuntivo**.
6. Seleziona **Invio documenti aziendali**.
7. Nella finestra di dialogo **Configura componente aggiuntivo** , nel campo **ID applicazione AAD** , inserisci **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Questo valore è un valore fisso.
8. Nel campo **ID tenant AAD** immetti l'ID del tuo account di sottoscrizione di Azure.

    ![Finestra di dialogo Configura componente aggiuntivo in LCS](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Seleziona la casella di controllo per accettare i termini e le condizioni.
10. Selezionare **Installa**.

## <a name="rcs-setup"></a>Impostazioni RCS

Durante la configurazione RCS, completerai queste attività:

1. Configura il Key Vault in RCS.
2. Configura l'integrazione RCS con il server del componente aggiuntivo per la fatturazione elettronica.
3. Crea un ambiente del componente aggiuntivo per la fatturazione elettronica per la tua organizzazione.

### <a name="set-up-the-key-vault-in-rcs"></a>Configurare il Key Vault in RCS

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione** , nella sezione **Ambienti** , seleziona il riquadro **Fatturazione elettronica**.
3. Seleziona **Ambienti di servizio**.

    ![Selezione di Ambienti di servizio](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> L'opzione **Applicazioni connesse** consente l'accesso per la configurazione automatica del componente aggiuntivo per la fatturazione Elettronica in Finance o Supply Management tramite RCS. Tuttavia, attualmente, questa funzione è ancora in fase di sviluppo.

4. Nel riquadro azioni, seleziona **Parametri Key Vault**.

    ![Selezione del parametro Key Vault](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. Nel riquadro azioni seleziona **Nuovo** per aggiungere un Key Vault.
6. Nel campo **URI Key Vault** , inserisci il valore dell'attributo **Nome DNS** della risorsa Key Vault configurata in Azure. Per informazioni su dove trovare il valore **Nome DNS** , vedi [Creare un account di archiviazione di Azure e il Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

    ![Campo URI di Key Vault](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. Nella Scheda dettaglio **Certificati** , seleziona **Aggiungi** per immettere tutti i nomi dei certificati digitali e i segreti del Key Vault necessari per stabilire connessioni attendibili. Nella colonna **Tipo** è possibile specificare se si tratta di un certificato o di un segreto. Entrambi i set di valori vengono configurati nella risorsa Key Vault in Azure.

    ![Aggiunta di certificati](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Se la fattura specifica per paese/area geografica richiede una catena di certificati per applicare una firma digitale, seleziona **Catena di certificati** nel riquadro azioni, quindi immetti la sequenza di certificati o segreti del Key Vault che compongono la catena.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Configurare l'integrazione RCS con il server del componente aggiuntivo per la fatturazione elettronica

1. Nell'area di lavoro **Funzionalità di globalizzazione** , nella sezione **Impostazioni correlate** , seleziona il collegamento **Parametri per la creazione di report elettronici**.
2. Seleziona **Fare clic qui per connettersi a Regulatory Configuration Service**. Se non desideri connetterti a LCS, seleziona **Annulla**.
3. Nella scheda **Servizi di fatturazione elettronica** , nel campo **URI endpoint servizio** , immetti il valore in base alle aree geografiche disponibili: `https://businessdocumentsubmission.us.operations365.dynamics.com/` o `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. Nel campo **ID applicazione** , verifica che venga visualizzato l'ID **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Questo valore è un valore fisso.
5. Nel campo **ID ambiente LCS** immetti l'ID del tuo account di sottoscrizione LCS.

![Inserimento dei parametri del componente aggiuntivo per la fatturazione elettronica](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Aggiungere un ambiente del componente aggiuntivo per la fatturazione elettronica

È possibile creare ambienti diversi per il componente aggiuntivo per la fatturazione elettronica, come ambienti di sviluppo, test o produzione.

1. Nell'area di lavoro **Funzionalità di globalizzazione** , nella sezione **Ambienti** , seleziona il riquadro **Fatturazione elettronica**.
2. Seleziona **Nuovo** per creare un ambiente.
3. Nel campo **Account token SAS di archiviazione** , inserisci il nome del segreto del Key Vault configurato nel Key Vault in RCS.

    ![Campo Account token SAS di archiviazione](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. Nella Scheda dettaglio **Utenti** , seleziona **Nuovo** per concedere l'accesso agli utenti per questo ambiente.

    ![Aggiunta di utenti del servizio](media/e-invoicing-services-get-started-enter-service-users.png)

5. Nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente sul server del componente aggiuntivo per la fatturazione elettronica.

    ![Pulsante Pubblica](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>Configurazione della funzionalità di fatturazione elettronica

"La funzionalità per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server del componente aggiuntivo per la fatturazione elettronica. La configurazione della funzionalità di fatturazione elettronica combina, tra le altre cose, l'uso di formati di configurazione per la creazione di report elettronici (ER) per creare file di esportazione e importazione configurabili e l'uso di azioni e flussi di azioni per consentire la creazione di regole configurabili per inviare richieste, importare le risposte e analizzare il contenuto della risposta.

A causa delle variazioni nei formati delle fatture e nei flussi di azioni, la configurazione della funzionalità di fatturazione elettronica dipende dal paese/area geografica.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance o Supply Chain Management 

Durante questa configurazione, si completeranno le seguenti attività:

1. Aprire la funzionalità distribuita in anteprima
2. Attiva la funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica per abilitare l'integrazione con Finance.
3. Configura l'URL dell'endpoint del componente aggiuntivo per la fatturazione elettronica.
4. Importa le configurazioni ER correlate alla funzione di fatturazione elettronica specifica del paese/area geografica.
5. Attiva la funzionalità di fatturazione elettronica specifica del paese/area geografica applicabile.
6. Importa le configurazioni ER e configura i tipi di risposta necessari per aggiornare il documento di fattura specifico del paese/area geografica come risultato del processo di invio.

### <a name="open-flighted-feature"></a>Aprire la funzionalità distribuita in anteprima
La funzione di integrazione della fattura elettronica è abilitata tramite distribuzione di versioni di anteprima. La distribuzione di versioni di anteprima è un concetto che consente di attivare o disattivare una funzione per impostazione predefinita. I passaggi seguenti abilitano una distribuzione in anteprima in un ambiente non di produzione. 

1. Eseguire il seguente comando SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)
    
2. Dopo aver apportato la modifica di cui sopra, esegui un IISReset su tutti gli AOS

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Attivare la funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica

1. Accedi a Finance o Supply Chain Management.
2. Nell'area di lavoro **Gestione funzionalità** , cerca la nuova funzionalità, **Integrazione del componente aggiuntivo per la fatturazione elettronica configurabile**. Se la funzionalità non è ancora visualizzata nella pagina Gestione funzionalità, esegui la funzione **Controlla aggiornamenti**
3. Seleziona la funzionalità, quindi seleziona **Abilita ora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurare l'URL dell'endpoint di servizio

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Servizio di invio** , nel campo **URL endpoint servizio** , immetti `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. Nel campo **Ambiente** , immetti il nome dell'ambiente del componente aggiuntivo per la fatturazione elettronica creato durante la configurazione RCS.

![Immissione dei parametri di servizio](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Importare le configurazioni ER

Per consentire la raccolta e l'invio dei dati aziendali al componente aggiuntivo per la fatturazione elettronica, è necessario importare il modello di dati ER e la configurazione del modello di dati ER correlati alla funzione di fatturazione elettronica specifica del paese/area geografica che si desidera utilizzare.

1. Nell'area di lavoro **Creazione di report elettronici** , nella sezione **Provider di configurazione** , selezionare **Provider di configurazione**. Assicurati che questo provider di configurazione sia impostato su **Attivo**. Per ulteriori informazioni su come impostare un provider su **Attivo** , vedi [Creare provider di configurazioni e contrassegnarli come attivi](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Selezionare **Archivi**.
4. Seleziona **Risorsa globale** e quindi seleziona **Apri**.
5. Nella finestra di dialogo **Connettiti a Lifecycle Services** , seleziona **Fare clic qui per connettersi a Lifecycle Service**.
6. A seconda del paese o dell'area geografica in cui vuoi utilizzare la funzione di fatturazione elettronica, è necessario importare il modello di dati applicabile, il mapping del modello di dati e i formati. Per informazioni sulle configurazioni ER da importare, vedi l'argomento "Introduzione al componente aggiuntivo per la fatturazione elettronica" specifico per il paese/area geografica.
7. Importa il **Modello di contesto della fattura cliente**. Questo modello contiene parametri aggiuntivi che descrivono, tra le altre cose, l'ambiente in Finance utilizzato per il componente aggiuntivo per la fatturazione elettronica durante l'invio dei dati aziendali.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Attivare le funzionalità di fatturazione elettronica specifiche del paese/area geografica

Per attivare le funzionalità di fatturazione elettronica specifiche per paese/area geografica in modo che funzionino con il componente aggiuntivo per la fatturazione elettronica, è necessario attivare la funzione in ciascuna persona giuridica in cui si desidera utilizzarla. Successivamente, la vecchia integrazione della fatturazione elettronica non può più essere utilizzata e viene attivata l'integrazione con il nuovo componente aggiuntivo per la fatturazione elettronica.

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Funzionalità** , nella riga della funzionalità correlata alla funzionalità di fatturazione elettronica specifica per paese/area geografica, seleziona la casella di controllo nella colonna **Abilitato**. Per informazioni sul quale funzionalità attivare, vedi l'argomento "Introduzione al componente aggiuntivo per la fatturazione elettronica" specifico per il paese/area geografica.

![Attivazione della funzionalità di fatturazione elettronica](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Se disponi di più persone giuridiche configurate per diversi paesi o aree geografiche, è possibile attivare la funzionalità di fatturazione elettronica specifica per paese/area geografica per ciascuna persona giuridica.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Importare le configurazioni ER e configurare i tipi di risposta per aggiornare il documento di fattura specifico per paese/area geografica

Se il documento di fattura inviato richiede un aggiornamento dopo la risposta dell'invio ai servizi di autorizzazione governativa, è necessario importare un modello di dati ER e configurazioni speciali per consentire l'aggiornamento dello stato del documento di fattura o di qualsiasi altro campo aggiuntivo.

1. Nell'area di lavoro **Creazione di report elettronici** , nella sezione **Provider di configurazione** , selezionare **Provider di configurazione**.
2. Selezionare **Archivi**.
3. Seleziona **Risorsa globale** e quindi seleziona **Apri**.
4. Importa i valori di **Modello di messaggio di risposta** , **Formato di importazione dei messaggi di risposta** , **Mapping del modello del messaggio di risposta alla destinazione** e **Formato di importazione del contenuto del file**.
5. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
6. Nella scheda **Documento elettronico** , seleziona **Aggiungi** per immettere il nome della tabella correlata al documento di fattura specifico del paese/area geografica. Per informazioni sul quali nomi di tabella selezionare, vedi l'argomento "Introduzione al componente aggiuntivo per la fatturazione elettronica" specifico per il paese/area geografica.
7. Seleziona **Tipi di risposta** per configurare i tipi di risposta. Per informazioni sul quali nomi di tabella selezionare, vedi l'argomento "Introduzione al componente aggiuntivo per la fatturazione elettronica" specifico per il paese/area geografica.

![Configurazione dei tipi di risposta](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>Nomi delle funzionalità di fatturazione elettronica per paese/area geografica 
La tabella seguente descrive altre funzionalità di fatturazione elettronica disponibili per il download dal repository globale per la creazione di report elettronici per generare fatture elettroniche.
In RCS, è possibile scaricare le funzionalità di fatturazione elettronica elencate in questa tabella, le configurazioni ER e le impostazioni delle funzionalità di fatturazione elettronica disponibili.
In Finance, è possibile abilitare i riferimenti alle funzionalità correlate nella pagina **Parametri del documento elettronico** per emettere fatture elettroniche per questi paesi/aree geografiche. Per altre informazioni, vedi la sezione, [Attivare le funzionalità di fatturazione elettronica specifiche per paese/area geografica](#region-specific) all'inizio di questo argomento.

| Nome funzionalità                      | descrizione                                 | Configurazioni ER                                                                                                  | Impostazioni                                                                                                                                                         | Paese  | Riferimento funzionalità      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Fatture elettroniche austriache (AT) | Fatture di vendita e di progetto per l'Austria      | - Fattura vendita OIOUBL <br>- Fattura progetto OIOUBL <br>- Nota di accredito vendite OIOUBL <br>- Nota di accredito progetto OIOUBL | - Generazione fattura di vendita (AT) <br>- Generazione fattura di progetto (AT) <br>- Generazione nota di credito di vendita (AT) <br>- Generazione nota di credito di progetto (AT)         | Austria         | EUR-00023              |
| Fattura elettronica belga (BE)   | Fatture di vendita e di progetto per il Belgio      | - Fattura di vendita UBL BE <br>- Fattura di progetto UBL BE <br>- Nota di accredito di progetto UBL BE <br>- Nota di accredito vendita UBL BE | - Generazione fattura di vendita (BE)<br>- Generazione fattura di progetto (BE) <br>- Generazione nota di credito di vendita (BE) <br>- Generazione nota di credito di progetto (BE)         | Belgio         | EUR-00023              |
| Fattura elettronica danese (DK)    | Fatture di vendita e di progetto per la Danimarca      | - Fattura vendita OIOUBL <br>- Fattura progetto OIOUBL <br>- Nota di accredito vendite OIOUBL <br>- Nota di accredito progetto OIOUBL | - Generazione fattura di vendita (DK) <br>- Generazione fattura di progetto (DK) <br>- Generazione nota di credito di vendita (DK)<br>- Generazione nota di credito di progetto (DK)         | Danimarca         | EUR-00023<br> DK-00001 |
| Fattura elettronica olandese (NL)     | Fatture di vendita e di progetto per i Paesi Bassi  | - Fattura di vendita UBL NL <br>- Fattura di progetto UBL NL <br>- Nota di accredito vendita UBL NL <br>- Nota di accredito di progetto UBL NL | - Generazione fattura di vendita (NL) <br> - Generazione fattura di progetto (NL) <br> - Generazione nota di credito di vendita (NL) <br>- Generazione nota di credito di progetto (NL)          | Paesi Bassi | EUR-00023              |
| Fattura elettronica estone (EE)  | Fatture di vendita e di progetto per l'Estonia      | - Fattura di vendita (EE) <br> - Fattura di progetto (EE)                                                                     | - Generazione fattura di vendita (EE) <br>- Generazione fattura di progetto (EE)                                                                                           | Estonia         | EUR-00023              |
| Fattura elettronica finlandese (FI)   | Fatture di vendita e di progetto per la Finlandia      | - Fattura di vendita (FI) <br>- Generazione fattura di progetto (FI)                                                          | - Generazione fattura di vendita (FI) <br>- Generazione fattura di progetto (FI)                                                                                           | Finlandia         | EUR-00023              |
| Fattura elettronica francese (FR)    | Fatture di vendita e di progetto per la Francia    | - Fattura di vendita UBL FR <br> - Fattura di progetto UBL FR <br> - Nota di accredito vendita UBL FR <br>- Nota di accredito di progetto UBL FR | - Generazione fattura di vendita (FR) <br> - Generazione fattura di progetto (FR) <br>- Generazione nota di credito di vendita (FR) <br>- Generazione nota di credito di progetto (FR)         | Francia          | EUR-00023              |
| Fattura elettronica tedesca (DE)    | Fatture di vendita e di progetto per la Germania      |- Fattura di vendita (DE) <br> - Fattura di progetto <DE>                                                                     | - Generazione fattura di vendita (DE) <br>- Generazione fattura di progetto (DE)                                                                                           | Germania         | EUR-00023              |
| Fattura elettronica norvegese (NO) | Fatture di vendita e di progetto per la Norvegia       | - Fattura vendita OIOUBL <br>- Fattura progetto OIOUBL <br>- Nota di accredito vendite OIOUBL <br>- Nota di accredito progetto OIOUBL | - Generazione fattura di vendita (NO) <br>- Generazione fattura di progetto (NO) <br>- Generazione nota di credito di vendita (NO) <br>- Generazione nota di credito di progetto (NO)          | Norvegia          | EUR-00023<br> NO-00010 |
| Fattura elettronica spagnola (ES)   | Fatture di vendita e di progetto per la Spagna        | - Fattura di vendita (ES) <br>- Fattura di progetto (ES)                                                                     | - Generazione fattura di vendita (ES) <br>- Generazione fattura di progetto (ES)                                                                                           | Spagna           | EUR-00023 <br>ES-00025 |
| Fattura elettronica italiana (IT)   | Fatture di vendita e di progetto per l'Italia        | - (Anteprima) Fattura di vendita (IT) <br> - Fattura di progetto (IT)                                                           | - Fattura di vendita <br> - Fattura di progetto                                                                                                                           | Italia           | EUR-00023 <br>IT-00036 |
| Fattura elettroniche PEPPOL         | Generazione fatture di vendita e di progetto PEPPOL | - Fattura di vendita PEPPOL <br>- Fattura progetto PEPPOL <br>- Nota di credito vendita PEPPOL <br> - Nota di credito progetto PEPPOL | - Generazione fattura di vendita PEPPOL <br>- Generazione fattura di progetto PEPPOL <br>- Generazione nota di credito di vendita PEPPOL <br>- Generazione nota di credito di progetto PEPPOL |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Elaborazione di fatture elettroniche in Finance and Supply Chain Management

Durante l'elaborazione, completerai queste attività:

1. Invia un documento aziendale (fattura) tramite il componente aggiuntivo per la fatturazione elettronica.
2. Visualizzare i log di esecuzione dell'invio.

### <a name="submit-business-documents"></a>Inviare documenti aziendali

Durante il normale processo di invio, la comunicazione tra il client e il componente aggiuntivo per la fatturazione elettronica è bidirezionale. Lo scopo è svolgere due compiti principali durante la presentazione di documenti elettronici:

1. Invia tutti i documenti elettronici che sono in attesa di essere inviati da Finance e che hanno lo stato corretto per l'invio e soddisfano i criteri di selezione.
2. Importa, in Finance, la risposta che il componente aggiuntivo per la fatturazione elettronica restituisce per i documenti elettronici precedentemente inviati. Dopo l'importazione, le risposte vengono analizzate e lo stato dei documenti aziendali viene aggiornato di conseguenza.

È possibile inviare documenti aziendali manualmente o in base ai requisiti di pianificazione.

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Invia documenti elettronici**.
2. Per il primo invio di qualsiasi documento, imposta sempre l'opzione **Invia di nuovo i documenti** su **No**. Se devi inviare nuovamente un documento tramite il servizio, imposta questa opzione su **Sì**.
3. Nella Scheda dettaglio **Record da includere** , seleziona **Filtra** per aprire la finestra di dialogo **Richiesta** in cui è possibile creare una query per selezionare i documenti da inviare.

![Finestra di dialogo Invia documenti elettronici](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Query filtri

1. Nella finestra di dialogo **Richiesta** , nella scheda **Intervallo** , immetti i criteri di filtro utilizzando i campi **Tabella** , **Tabella derivata** , **Campo** e **Criteri**.
2. Seleziona **Aggiungi** per aggiungere tutti i criteri aggiuntivi necessari per selezionare i documenti aziendali.

    ![Configurazione dei criteri del filtro di invio](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Seleziona **OK** per chiudere la finestra di dialogo **Richiesta**.
4. Seleziona **OK** per inviare i documenti aziendali selezionati al componente aggiuntivo per la fatturazione elettronica.

    > [!NOTE]
    > Durante il tuo primo tentativo di inviare un documento tramite il servizio, ti verrà chiesto di confermare la connessione con il componente aggiuntivo per la fatturazione elettronica. Seleziona **Fai clic qui per connetterti al servizio di invio documenti elettronici**.
    >
    > ![Connettersi alla finestra di messaggio del servizio di invio documenti elettronici](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Se la connessione ha esito positivo, riceverai un messaggio di conferma.
    >
    > ![Conferma della connessione al componente aggiuntivo per la fatturazione elettronica](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Chiudi la finestra di dialogo.

> [!NOTE]
> Dopo ogni invio, il Centro azioni mostra il numero di documenti inviati.
>
> ![Messaggi del Centro azioni](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Invio per batch

Invece di inviare manualmente i documenti, puoi automatizzare il processo di invio ed eseguirlo in background, in base a una frequenza configurata di esecuzione in batch.

1. Nella finestra di dialogo **Invia documenti elettronici** , nella Scheda dettaglio **Esegui in background** , imposta l'opzione **Elaborazione in batch** su **Sì**.
2. Nella scheda **Ricorrenza** , configura la frequenza di elaborazione in batch.

![Configurazione dell'invio in batch](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Visualizzare tutti i registri di invio

1. Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento** , seleziona il tipo di documento in base al quale filtrare.

    ![Selezione del tipo di documento per cui visualizzare i registri di invio](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > Il valore mostrato nella colonna **Stato invio** rappresenta lo stato correlato al completamento del processo di invio stesso. Indica se il flusso di azioni configurato in RCS è stato eseguito fino alla fine, indipendentemente dal fatto che il documento elettronico sia stato approvato o rifiutato. Il valore nella colonna **Stato invio** non rappresenta lo stato del documento inviato. È possibile visualizzare lo stato del documento inviato (ovvero, se il documento è stato approvato o rifiutato) nella Scheda dettaglio **Registro azioni di elaborazione** nei dettagli del registro di invio, come descritto di seguito.

3. Nel riquadro azioni seleziona **Richieste \> Dettagli invio**.
4. Visualizza i dettagli del registro di invio.

    ![Dettagli del registro di invio](media/e-invoicing-services-get-started-view-submission-log-form.png)

I risultati visualizzati nel registro di invio dipendono da come è stata configurata la funzione di fatturazione elettronica in RCS. Tuttavia, indipendentemente dalla configurazione, il registro di invio ha sempre tre Schede dettaglio:

- **Azioni di elaborazione** : questa Scheda dettaglio mostra il registro di esecuzione delle azioni configurate nella versione della funzionalità configurata in RCS. La colonna **Stato** mostra se l'azione è stata eseguita correttamente.
- **File di azione** : questa Scheda dettaglio mostra i file intermedi che sono stati generati durante l'esecuzione delle azioni. Puoi selezionare **Visualizza** per scaricare il file e visualizzarne il contenuto.
- **Registro azioni di elaborazione** : questa scheda dettaglio mostra i risultati della comunicazione tra il componente aggiuntivo per la fatturazione elettronica e il servizio Web di destinazione. Mostra anche ciò che è stato restituito dall'elaborazione del servizio Web.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica per il Brasile](e-invoicing-bra-get-started.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica per il Messico](e-invoicing-mex-get-started.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica per l'Italia](e-invoicing-ita-get-started.md)
- [Configurare il componente aggiuntivo per la fatturazione elettronica](e-invoicing-setup.md)
