---
title: Panoramica di Gestione documenti aziendali
description: In questo argomento vengono fornite informazioni sull'utilizzo della funzionalità Gestione documenti aziendali del framework ER.
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 05dee1efc4e817795824e3fa1c41093d48a97d78
ms.sourcegitcommit: 219a73371638a9a4c6076d4c88b95fb2ebe95b00
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "2652619"
---
# <a name="business-document-management-overview"></a>Panoramica di Gestione documenti aziendali

Gli utenti aziendali utilizzano il [framework ER](general-electronic-reporting.md) per configurare i formati per documenti in uscita in base ai requisiti legali dei vari paesi. Gli utenti possono inoltre definire il flusso di dati per specificare i dati dell'applicazione da inserire nei documenti generati. Il framework ER genera documenti in uscita nei formati di Microsoft Office (cartelle di lavoro di Excel o documenti di Word) utilizzando modelli predefiniti. Nei modelli vengono inseriti i dati necessari in base al flusso di dati configurato durante la generazione dei documenti richiesti. Ogni formato configurato può essere pubblicato come parte di una soluzione ER per generare specifici documenti in uscita. Ciò è rappresentato da una configurazione di formato ER che può contenere modelli utilizzabili per generare differenti documenti in uscita. Gli utenti aziendali possono utilizzare questo framework per gestire i documenti aziendali necessari.

La funzionalità **Gestione documenti aziendali** si basa sul framework ER e consente agli utenti aziendali di modificare i modelli di documenti aziendali tramite il servizio Microsoft Office 365 o l'applicazione desktop Microsoft Office appropriata. Le modifiche ai documenti possono includere le modifiche alle strutture di documenti aziendali e l'aggiunta di segnaposto per dati aggiuntivi senza alterazione del codice sorgente e nuove distribuzioni. Non è richiesta alcuna conoscenza del framework ER per aggiornare i modelli di documenti aziendali.

> [!NOTE]
> Da notare che Gestione documenti aziendali consente di modificare i modelli utilizzati per generare documenti aziendali quali ordini, fatture e così via. Anche se un modello è stato modificato e una nuova versione dello stesso è stata pubblicata, questa versione viene utilizzata per generare i documenti aziendali richiesti. La funzionalità Gestione documenti aziendali non può essere utilizzata per modificare documenti aziendali già generati.

## <a name="supported-deployments"></a>Distribuzioni supportate

Attualmente, Gestione documenti aziendali è disponibile solo per le distribuzioni cloud. Se questa funzionalità è fondamentale per la distribuzione locale, fornire dei commenti al proposito sul sito [Ideas](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Applicazioni Microsoft Office supportate

Per modificare i modelli in formati di Excel o Word con Gestione documenti aziendali utilizzando le applicazioni desktop Microsoft Office, è necessario disporre di Microsoft Office 2010 o versione successiva installata. Queste versioni sono supportate nella distribuzione cloud e in quella locale.

## <a name="business-document-availability"></a>Disponibilità dei documenti aziendali

I seguenti report, con modelli basati su Excel, saranno disponibili con la versione dell'anteprima pubblica:

**Contabilità clienti** (agosto 2019)

- Fattura anticipo di vendita
- Documento di trasporto ordine cliente

**Contabilità fornitori** (agosto 2019)

- Fattura anticipo di acquisto
- Ordine fornitore
- Documento di trasporto ordine fornitore

Altri report saranno presto disponibili. Notifiche speciali sui report aggiuntivi saranno inviate separatamente. 

Un elenco completo di tutti i report pianificati per la versione di ottobre 2019 sono disponibili in [Report dei documenti aziendali configurabili in Word e Excel](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

# <a name="example-enable-configure-and-use-business-document-management"></a>Esempio: attivare, configurare e utilizzare Gestione documenti aziendali

Per ulteriori informazioni su questa funzionalità, completare l'esempio in questo argomento.

## <a name="configure-er-parameters"></a>Configurare i parametri ER

Poiché la funzionalità Gestione documenti aziendali si basa sul framework ER, è necessario configurare i parametri ER per iniziare a utilizzarla. A questo scopo, è necessario impostare i parametri ER come descritto in [Configurare il framework ER](electronic-reporting-er-configure-parameters.md). È inoltre necessario aggiungere un nuovo provider di configurazione come descritto in [Creare fornitori di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Area di lavoro ER](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importare soluzioni ER

È necessario importare configurazioni ER contenenti modelli di documenti aziendali nell'istanza corrente. Scaricare e archiviare localmente i seguenti file per completare questa procedura.

**Esempio di soluzione di fatturazione di clienti ER**

| **File**                                  | **Contenuto**                                |
|-------------------------------------------|--------------------------------------------|
| Customer invoicing model.version.2.xml    | [Configurazione del modello di dati ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Customer FTI report (GER).version.2.3.xml | [Configurazioni del formato ER per fatture a testo libero](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Esempio di soluzione ER per pagamento con assegni**

| **File**                                  | **Contenuto**                                |
|-------------------------------------------|--------------------------------------------|
| Model for cheques.version.10.xml          | [Configurazione del modello di dati ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Cheques printing format.version.10.9.xml  | [Configurazione del formato ER per pagamento con assegni](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Esempio di soluzione ER per il commercio estero**

| **File**                                  | **Contenuto**                                |
|-------------------------------------------|--------------------------------------------|
| Intrastat model.version.1.xml             | [Configurazione del modello di dati ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Intrastat report.version.1.9.xml          | [Configurazione del formato ER per report di controllo Intrastat](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Per importare ogni file attenersi alla seguente procedura. Importare la configurazione del *modello di dati* ER di ogni soluzione ER nelle tabelle precedenti prima di importare la configurazione del *formato* ER corrispondente.

1. Aprire la pagina **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Selezionare **Scambia** nella parte superiore della pagina.
3. Selezionare **Carica da file XML**.
4. Selezionare **Esplora** per caricare il file XML richiesto.
5. Selezionare **OK** per confermare l'importazione della configurazione.

![Pagina delle configurazioni ER](./media/BDM-Overview-ERSolutions.png)

Per ulteriori informazioni sull'importazione delle configurazioni ER, vedere [Gestire il ciclo di vita della configurazione ER](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Abilitare Gestione documenti aziendali

Per avviare Gestione documenti aziendali, è necessario aprire l'area di lavoro **Gestione funzionalità** e abilitare la funzionalità **Gestione documenti aziendali**.

Utilizzare la procedura seguente per abilitare la funzionalità Gestione documenti aziendali per tutte le persone giuridiche.

1. Aprire l'area di lavoro **Gestione funzionalità**.
2. Nella scheda **Nuovo**, selezionare la funzionalità **Gestione documenti aziendali** nell'elenco.
3. Selezionare **Abilita ora** per attivare la funzionalità selezionata.
4. Aggiorna la pagina per accedere alla nuova funzionalità.

![Area di lavoro Gestione funzionalità](./media/BDM-Overview-FMEnabling.png)

Per ulteriori informazioni sull'attivazione di nuove funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

## <a name="configure-parameters"></a>Configurare i parametri

Utilizzare le informazioni nelle sezioni seguenti per impostare i parametri di base per Gestione documenti aziendali.

### <a name="prerequisites-for-parameter-setup"></a>Prerequisiti per l'impostazione dei parametri
Prima di impostare Gestione documenti aziendali, è necessario impostare il tipo di documento necessario nel framework Gestione documenti. Questo tipo di documento viene utilizzato per specificare una memorizzazione temporanea dei documenti in formati di Office (Excel e Word e) utilizzati come modelli per report ER. Il modello di memorizzazione temporanea può essere modificato utilizzando le applicazioni desktop di Office.

Per questo tipo di documento, i seguenti valori di attributi devono essere selezionati.

| **Nome attributo**  | **Valore attributo**   |
|---------------------|-----------------------|
| Classe               | Allega file           |
| Raggruppa               | File                  |
| Ubicazione            | SharePoint            |

Per informazioni su come impostare i parametri di gestione dei documenti e i tipi di documento necessari, vedere [Configurare la gestione dei documenti](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management).

![Impostare il tipo di documento in Gestione documenti](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a>Impostare i parametri

I parametri di base di Gestione documenti aziendali possono essere impostati nella pagina **Parametri di documenti aziendali**. Solo determinati utenti possono accedere alla pagina, ovvero:

- Utenti assegnati al ruolo **Amministratore di sistema**.
- Utenti assegnati a qualsiasi ruolo configurato per eseguire l'operazione, **Gestire i parametri di Gestione documenti aziendali** (nome AOT **ERBDMaintainParameters**).

Utilizzare la seguente procedura per impostare i parametri di base per tutte le persone giuridiche.

1. Accedere come utente con accesso alla pagina **Parametri di documenti aziendali**.
2. Accedere a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Gestione documenti aziendali** \> **Parametri di documenti aziendali**.
3.  Nella pagina **Parametri di documenti aziendali**, nella scheda **Allegati**, nel campo **Tipo di documento SharePoint**, definire il tipo di documento che deve essere utilizzato per archiviare temporaneamente i modelli in formati di Office quando vengono modificati utilizzando applicazioni desktop di Office. 

> [!NOTE]
> Solo i tipi di documento configurati utilizzando un percorso SharePoint sono disponibili per questo parametro.

![Impostazione dei parametri di Gestione documenti aziendali](./media/BDM-Overview-BDMSetting.png)

Il tipo di documento selezionato è specifico alla società e verrà utilizzato quando l'utente utilizza Gestione documenti aziendali nella società per la quale il tipo di documento selezionato è configurato. Quando l'utente utilizza Gestione documenti aziendali in un'altra società, lo stesso tipo di documento selezionato sarà utilizzato se un tipo non è stato configurato per tale società. Dopo che un tipo di documento è stato configurato, verrà utilizzato al posto di quello selezionato nel campo **Tipo di documento SharePoint**.

## <a name="configure-access-permissions"></a>Configurare le autorizzazioni di accesso

Per impostazione predefinita, quando l'accesso alle autorizzazioni di Gestione documenti aziendali non è abilitato, ogni utente con accesso all'area di lavoro della gestione di documenti aziendali vedrà tutti i modelli della soluzione ER disponibili. Nell'area di lavoro di Gestione documenti aziendali sono visualizzati solo i modelli inclusi nelle configurazioni di formato ER e contrassegnati con un tag **Tipo di documento aziendale**.

![Pagina delle configurazioni ER](./media/BDM-Overview-ERFormatTags.png)

L'elenco dei modelli disponibili nell'area di lavoro di Gestione documenti aziendali può essere limitato configurando le autorizzazioni di accesso. Ciò può essere importante quando si utilizzano modelli differenti per generare documenti aziendali per diversi domini aziendali (aree funzionali) e si desidera consentire a specifici utenti l'accesso a vari modelli per la modifica nell'area di lavoro Gestione documenti aziendali.

Le autorizzazioni di accesso di Gestione documenti aziendali possono essere impostate in **Configurazione delle autorizzazioni di accesso**. Solo i seguenti utenti possono accedere alla pagina:

- Utenti assegnati al ruolo **Amministratore di sistema**.
- Utenti assegnati a qualsiasi altro ruolo configurato per eseguire l'operazione, **Configurare le autorizzazioni per accedere a modelli di documenti aziendali e modificarli** (nome AOT **ERBDTemplatesSecurity**).

Utilizzare la procedura seguente per impostare le autorizzazioni di Gestione documenti aziendali per tutte le persone giuridiche.

1. Accedere come utente con accesso alla pagina **Configurazione delle autorizzazioni di accesso**.
2. Accedere a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Gestione documenti aziendali** \> **Gestisci autorizzazioni di accesso**.

Prestare attenzione alla notifica che informa che l'utilizzo delle autorizzazioni di accesso per Gestione documenti aziendali non è attualmente abilitata.

![Configurazione della pagina delle autorizzazioni di accesso di Gestione documenti aziendali](./media/BDM-Overview-TemplatesAccess1.png)

Con questa impostazione, ogni utente assegnato a un qualsiasi ruolo di sicurezza configurato per eseguire l'operazione **Modelli per la gestione di documenti aziendali** (nome AOT **ERBDManageTemplates**) e in grado di aprire l'area di lavoro di Gestione documenti aziendali e può modificare qualsiasi modello disponibile.

Nella figura seguente viene illustrato ciò che è disponibile nell'area di lavoro di Gestione documenti aziendali per gli utenti assegnati al ruolo **Impiegato contabilità clienti**. Con l'impostazione corrente delle autorizzazioni di accesso, l'utente può modificare i modelli di documenti aziendale da diverse aree funzionali tra cui fatturazione, dichiarazioni normative e pagamenti.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-TemplatesForAlice1.png)

3. Nella pagina **Configurazione delle autorizzazioni di accesso**, selezionare **Impostazione delle autorizzazioni di accesso**.
4. Nella finestra di dialogo **Impostazioni di autorizzazioni di accesso per modificare i modelli**, attivare l'opzione **Applica autorizzazioni di accesso configurate**.
5. Selezionare **OK** per confermare che le autorizzazioni di accesso di Gestione documenti aziendali sono state abilitate.

![Configurazione della pagina delle autorizzazioni di accesso di Gestione documenti aziendali](./media/BDM-Overview-TemplatesAccess2.png)

6. Selezionare **Aggiungi** per immettere un nuovo ruolo per il quale configurare autorizzazioni di accesso ai modelli di Gestione documenti aziendali.
7. Nella finestra di dialogo **Ruoli di sicurezza**, selezionare il ruolo **Impiegato contabilità clienti** e **OK** per confermare la selezione del ruolo.
8. Nella scheda **Autorizzazioni di accesso per tag di configurazioni**, selezionare **Nuovo**.
9. Nel campo **Tipo di tag**, selezionare **Area funzionale** e nel campo **ID**, selezionare **Fatturazione**.
10. Selezionare **Salva** per memorizzare le autorizzazioni di accesso configurati per il ruolo selezionato.

  L'impostazione corrente significa che per qualsiasi utente a cui è assegnato il ruolo **Impiegato contabilità clienti** e che esegue l'operazione **Modelli di Gestione documenti aziendali** (nome AOT **ERBDManageTemplates**), i modelli di configurazione in formato ER il cui valore del tag **Area funzionale** è **Fatturazione** saranno disponibili per la modifica dell'area di lavoro di Gestione documenti aziendali.

11. Passare al riquadro **Informazioni correlate** dal lato destro della pagina corrente. Nel riquadro **Informazioni correlate** viene illustrato come le autorizzazioni di accesso configurate verranno applicate, inclusi i modelli di configurazione ER che saranno disponibili per gli utenti assegnati al ruolo **Impiegato contabilità clienti**.

![Configurazione della pagina delle autorizzazioni di accesso di Gestione documenti aziendali](./media/BDM-Overview-TemplatesAccess3.png)

12. Nella scheda **Autorizzazioni di accesso per configurazioni**, selezionare l'opzione **Aggiungi**.
13. Nella finestra di dialogo **Seleziona configurazione**, contrassegnare la configurazione in formato ER **Report Intrastat**.
14. Selezionare **OK** per confermare la voce delle configurazioni selezionate e quindi selezionare **Salva** per memorizzare le autorizzazioni di accesso configurate per il ruolo selezionato.

L'impostazione corrente significa che per qualsiasi utente a cui è assegnato il ruolo **Impiegato contabilità clienti** e che esegue l'operazione **Modelli di Gestione documenti aziendali** (nome AOT **ERBDManageTemplates**), i modelli seguenti potranno essere modificati nell'area di lavoro di Gestione documenti aziendali.

- Modelli con il valore **Fatturazione** per il tag **Area funzionale**.
- Modelli delle configurazioni in formato ER elencati nella scheda **Autorizzazioni di accesso per configurazioni** (modelli della configurazione in formato **Report Intrastat** del dominio **Relazione finanziaria** in questo esempio).

![Configurazione della pagina delle autorizzazioni di accesso di Gestione documenti aziendali](./media/BDM-Overview-TemplatesAccess4.png)

Nella figura seguente viene illustrato ciò che l'area di lavoro di Gestione documenti aziendali fornisce agli utenti assegnati al ruolo **Impiegato contabilità clienti**. Con l'impostazione delle autorizzazioni di accesso di Gestione documenti aziendali, l'utente può modificare i modelli di documenti aziendali dal dominio **Fatturazione** e dalla configurazione in formato ER **Report Intrastat**. I modelli dal dominio **Pagamenti** non sono accessibili per il ruolo **Impiegato contabilità clienti**.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Le regole **Autorizzazioni di accesso per configurazioni** vengono archiviate utilizzando l'ID di identificazione univoco di una configurazione in formato ER. Ciò significa che tali regole non verranno eliminate quando una configurazione ER che fa riferimento alle stesse viene eliminata. Quando si reimportano le configurazioni eliminate in questa istanza, tali regole vi faranno ancora riferimento. Non è necessario impostare di nuovo le regole dopo che le configurazioni eliminate vengono reimportate.

## <a name="use-business-document-management-to-edit-templates"></a>Utilizzare Gestione documenti aziendali per modificare i modelli

Gli utenti aziendali possono accedere ai modelli di documenti aziendali per la modifica nell'area di lavoro di Gestione documenti aziendali. Solo gli utenti seguenti possono accedere all'area di lavoro di Gestione documenti aziendali:

- Utenti assegnati al ruolo **Amministratore di sistema**.
- Utenti assegnati a qualsiasi ruolo configurato per eseguire l'operazione, **Gestire i modelli di documenti aziendali** (nome AOT **ERBDManageTemplates**).

Utilizzare la seguente procedura per modificare modelli di fattura a testo libero nell'area di lavoro di Gestione documenti aziendali. Prima di completare la procedura, è necessario aver completato tutte le procedure precedenti in questo argomento.

1. Accedere come utente con accesso all'area di lavoro di Gestione documenti aziendali.
2. Aprire l'area di lavoro di Gestione documenti aziendali

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingTemplate1.png)

La scheda **Modello** presenta il contenuto del modello selezionato. Selezionare la scheda **Dettagli** per esaminare i dettagli del modello selezionato nonché quelli di una configurazione in cui tale modello si trova. Da notare che lo stato di tutti i modelli è **Pubblicato** e che questi non presentano dettagli nella colonna **Revisione**. Ciò significa che tali modelli non vengono attualmente modificati.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Iniziare la modifica di modelli di proprietà del provider di configurazione

1. Nell'area di lavoro di Gestione documenti aziendali, selezionare il modello **Cheques printing format** nell'elenco.
2. Selezionare la scheda **Dettagli**.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingTemplate2.png)

L'opzione **Modifica modello** è disponibile per il modello selezionato. Questa opzione è sempre disponibile per un modello in una configurazione in formato ER di proprietà del provider di configurazione ER attivo (**Litware, Inc.** in questo esempio). Se l'opzione **Modifica modello** è selezionata, il modello esistente nella versione bozza della configurazione in formato ER sottostante sarà disponibile per la modifica.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Iniziare la modifica di modelli di proprietà di altri provider

1. Nell'area di lavoro di Gestione documenti aziendali, selezionare il modello **Customer FTI report (GER)** nell'elenco.
2. Selezionare la scheda **Dettagli**.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingTemplate3.png)

L'opzione **Nuovo documento** è disponibile per il modello selezionato. Questa opzione è sempre disponibile per un modello in una configurazione in formato ER fornito da un altro provider (**Microsoft** in questo esempio). Quando **Nuovo documento** è selezionato, un nuovo modello sarà disponibile per la modifica. Il modello modificato verrà archiviato in una nuova configurazione in formato ER generato automaticamente.

### <a name="start-editing-a-template"></a>Iniziare a modificare un modello

1. Nel modello selezionato, selezionare **Nuovo documento**.
2. Nel campo **Titolo**, modificare il titolo del modello modificabile se necessario. Il testo verrà utilizzato per assegnare un nome alla configurazione in formato ER creata automaticamente. Da notare che la versione bozza di questa configurazione (**Copia di Customer FTI report (GER)**) che conterrà il modello modificata verrà automaticamente contrassegnata per eseguire questo formato ER per l'utente corrente. Contemporaneamente, il modello originale della configurazione in formato ER di base sara utilizzato per eseguire questo formato ER per qualsiasi altro utente.
3. Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.
4. Nel campo **Commento**, modificare il commento per la revisione del modello modificabile creata automaticamente.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingTemplate4.png)

5. Selezionare **OK** per confermare l'avvio del processo di modifica.

Viene visualizzata la pagina **Editor di modelli BDM**. Il modello selezionato sarà disponibile per la modifica online mediante Office 365.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a>Modificare un modello in Office 365

Modificare il modello utilizzando la funzionalità di Office 365. Ad esempio, in Office Online, modificare il carattere dei prompt dei campi nell'intestazione del modello da **Normale** a **Grassetto**. Queste modifiche vengono salvate automaticamente per il modello modificabile che si trova nell'archiviazone del modello principale (per impostazione predefinita, l'archiviazione BLOB di Azure) configurata per il framework ER.

![Pagina dell'editor di modelli di Gestione documenti aziendali](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a>Modificare un modello nell'applicazione desktop di Office

1. Selezionare **Apri nell'app desktop** per modificare il modello utilizzando la funzionalità dell'applicazione desktop di Office (Excel in questo esempio). Il modello modificabile viene copiato dall'archiviazione permanente a quella temporanea configurata nei parametri di Gestione documenti aziendali come cartella SharePoint.
2. Confermare che si desidera aprire il modello dall'archiviazione di file temporanea nell'applicazione Excel desktop di Office.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingLayout3.png)

3. Modificare il modello. Ad esempio, modificare il carattere dei prompt dei campi nell'intestazione del modello modificando il colore da **Nero** a **Blu**.

![Pagina dell'editor di modelli di Gestione documenti aziendali](./media/BDM-Overview-EditingLayout4.png)

4. Selezionare **Salva** nell'applicazione desktop Excel per salvare le modifiche al modello nell'archiviazione temporanea.

![Pagina dell'editor di modelli di Gestione documenti aziendali](./media/BDM-Overview-EditingLayout5.png)

5. Chiudere l'applicazione desktop Excel.
6. Selezionare **Sincronizza copia archiviata** per sincronizzare l'archiviazione temporanea del modello nell'archiviazione permanente.

> [!NOTE]
> La copia del modello modificabile nell'archiviazione di file temporanea viene mantenuta solo per la sessione corrente della modifica del modello. Quando si termina tale sessione chiudendo la pagina **Editor di modelli BDM**, tale copia verrà eliminata. Se si è modificato il modello nell'archiviazione di file temporanea e l'opzione **Sincronizza copia archiviata** non è stata selezionata, quando si tenta di chiudere la pagina **Editor di modelli BDM**, un messaggio chiederà se si desidera memorizzare le modifiche apportate. Selezionare **Sì** se si desidera salvare le modifiche al modello nel percorso di file permanente.

### <a name="validate-a-template"></a>Convalidare un modello

1. Nella pagina **Editor di modelli BDM**, selezionare **Verifica documento** per convalidare il modello modificato rispetto alla configurazione di formato ER sottostante. Seguire gli eventuali suggerimenti per allineare il modello alla struttura del formato dalla configurazione in formato ER di base.
2. Selezionare **Mostra formato** per visualizzare la struttura corrente del formato dalla configurazione in formato ER di base che deve essere allineata al modello modificabile. 
3. Selezionare **Nascondi formato** per chiudere il riquadro.

![Pagina dell'editor di modelli BDM](./media/BDM-Overview-EditingTemplate6.png)

4. Chiudere la pagina **Editor di modelli BDM**.

Il modello aggiornato è visualizzato nella scheda **Modello**. Si noti che lo stato del modello modificato è ora **Bozza** e la revisione corrente non è più vuota. Ciò significa che il processo di modifica di tale modello è stato avviato.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Test del modello modificato 

1. Nell'applicazione, selezionare la società **USMF**.
2. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
3. Selezionare la fattura **FTI-00000002** e quindi selezionare **Gestione stampa**.
4. Selezionare il livello **Modulo - Contabilità clienti** \> **Documenti** \> **Fattura a testo libero** \> **Documento originale** per specificare l'ambito delle fatture per l'elaborazione.
5. Nel campo **Formato report**, selezionare il formato ER **Customer FTI report (GER) Copy** per il livello di documento specificato.

![Pagina Impostazione Gestione stampa](./media/BDM-Overview-TestRun1.png)

6. Premere **ESC** per chiudere la pagina corrente.
7. Selezionare **Stampa** quindi fare clic su **Selezionato**.
8. Scaricare il documento e aprirlo utilizzando l'applicazione desktop Excel.

![Pagina delle fatture a testo libero](./media/BDM-Overview-TestRun2.png)

Il modello modificato viene utilizzato per generare il report delle fatture a testo libero per l'articolo selezionato. Per analizzare il modo in cui questo report viene modificato in seguito ai cambiamenti al modello, è possibile eseguire questo report in una sessione dell'applicazione subito dopo aver modificato il modello in un'altra sessione dell'applicazione.

### <a name="create-an-alternative-template-revision"></a>Creare una revisione alternativa del modello

1. Aprire la pagina **Editor di modelli BDM** e selezionare il modello **Customer FTI report (GER) Copy**.
2. Nella scheda **Revisioni**, selezionare **Nuovo**.
3. Se necessario, nel campo **Nome**, modificare il nome della seconda revisione e basarlo sulla prima revisione correntemente attiva.
4. Se necessario nel campo **Commento**, modificare il commento per la revisione del modello modificabile creata automaticamente.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-AddRevision.png)

Una nuova revisione del modello è stata memorizzata nell'archiviazione del modello permanente. A questo punto è possibile continuare a modificare il modello della seconda revisione attualmente selezionata come attiva.

5. Selezionare la prima revisione e quindi **Imposta come attivo**. È possibile selezionare un'altra revisione come attiva se in qualsiasi momento si desidera tornare a quella revisione del modello.
6. Selezionare la seconda revisione e quindi **Elimina**.
7. Selezionare **OK** per confermare che si desidera eliminare la revisione selezionata. È possibile eliminare una qualsiasi delle revisioni non attive quando non sono più necessarie.

### <a name="delete-a-modified-template"></a>Eliminare un modello modificato

1. Nella pagina **Editor di modelli BDM**, selezionare la scheda **Modello**.
2. Selezionare **Elimina**.
3. Se si seleziona **OK** per confermare l'eliminazione, il formato ER **Customer FTI report (GER) Copy** con il modello modificato verrà eliminato. Selezionare **Annulla** per esplorare altre opzioni.

### <a name="revoke-changes-of-template"></a>Revocare le modifiche del modello

Quando si modifica il modello da un formato ER di proprietà del provider corrente attivo, è disponibile un'opzione per revocare le modifiche apportate al modello.

![Pagina dell'area di lavoro di Gestione documenti aziendali](./media/BDM-Overview-RevokeChanges.png)

1. Nella pagina **Editor di modelli BDM**, selezionare la scheda **Modello**.
2. Selezionare **Annulla**.
3. Se si seleziona **OK** per revocare le modifiche al modello, il modello modificato verrà sostituito dal modello originale e tutte le modifiche verranno rimosse. Quando si revocano le modifiche al modello, sarà possibile eliminare il modello. Selezionare **Annulla** per esplorare altre opzioni.

### <a name="publish-a-modified-template"></a>Pubblicare un modello modificato
1. Nella pagina **Editor di modelli BDM**, nella scheda **Modello**, selezionare **Pubblica**.
2. Se si seleziona **OK** per confermare la pubblicazione, la versione bozza del formato **Customer FTI report (GER) Copy** derivato contenente il modello modificato verrà contrassegnata come completata. Il modello modificato diventa disponibile per altri utenti. Le versioni completate di questo formato ER manterranno solo l'ultima revisione attiva del modello. Le altre revisioni verranno eliminate. Selezionare **Annulla** per esplorare altre opzioni.

## <a name="frequently-asked-questions"></a>Domande frequenti

#### <a name="i-selected-new-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a>Ho selezionato **Nuovo documento**, ma anziché la pagina **Editor di modelli BDM** in Finance and Operations viene visualizzata la pagina Web Office 365.
Si tratta di un problema noto con il reindirizzamento di Office 365. Questo problema si verifica quando si accede a Office 365 per la prima volta. Per risolverlo, selezionare il pulsante **Indietro** del browser per tornare alla pagina precedente.

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a>So come modificare un modello utilizzando Office 365 nella prima sessione dell'applicazione e come utilizzare il modello nella seconda sessione dell'applicazione modificando il modello per determinare come le modifiche alterano il documento aziendale generato. Posso farlo utilizzando l'applicazione desktop di Office?
Sì, è possibile. Nella prima sessione dell'applicazione, selezionare **Apri nell'app desktop**. Il modello verrà memorizzato nell'archiviazione di file temporanea e aperto nell'applicazione desktop di Office. Successivamente, completare la procedura per visualizzare l'anteprima delle modifiche nel documento aziendale generato:

1. Apportare le modifiche nel modello utilizzando l'applicazione desktop di Office.
2. Selezionare **Salva** nell'applicazione desktop di Office.
3. Nella pagina **Editor di modelli BDM** della prima sessione dell'applicazione, selezionare **Sincronizza copia archiviata**.
4. Eseguire questo formato ER di modello nella seconda sessione dell'applicazione.

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a>Viene visualizzato il messaggio di errore "Il valore non può essere null. Nome parametro: externalId quando seleziono **Apri nell'app desktop**. Come posso risolvere questo problema? 
Molto probabilmente è stato eseguito l'accesso all'istanza corrente dell'app del dominio Azure AD che differisce dal dominio Azure AD utilizzato per distribuire questa istanza. Poiché il servizio SharePoint, utilizzato per archiviare i modelli e renderli disponibili per la modifica utilizzando le applicazioni desktop di Office, appartiene allo stesso dominio, non disponiamo delle autorizzazioni per accedere al servizio SharePoint. Per risolvere questo problema, accedere all'istanza corrente utilizzando le credenziali di un utente con il dominio Azure AD corretto.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei report elettronici](general-electronic-reporting.md)

[Progettare una configurazione per la creazione di report nel formato OPENXML](tasks/er-design-reports-openxml-2016-11.md)

[Progettare le configurazioni di ER per generare report in formato di Word](tasks/er-design-configuration-word-2016-11.md)

[Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)

[Configurare la creazione di report elettronici per eseguire il pull dei dati in Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
