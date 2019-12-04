---
title: Generare moduli FTI stampabili
description: In questo argomento viene descritto come utilizzare il framework di creazione di report elettronici (ER) per generare moduli stampabili (FTI) di fattura a testo libero come documenti di Microsoft Office.
author: NickSelin
manager: AnnBe
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0bb817de583c231aa55fa81b9e28d788505e0a1f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771285"
---
# <a name="generate-printable-fti-forms"></a>Generare moduli FTI stampabili

[!include[banner](../includes/banner.md)]

Il framework di creazione di report elettronici (ER) consente di generare moduli stampabili (FTI) di fattura a testo libero come documenti di Microsoft Office. In questo argomento vengono fornite le informazioni su come creare configurazioni personali nonché i dettagli dei modelli di configurazione disponibili.

## <a name="overview"></a>Panoramica

Oltre alla possibilità esistente di generare i moduli stampabili FTI utilizzando Microsoft SQL Server Reporting Services (SSRS), è ora possibile utilizzare il framework di ER. È possibile gestire i moduli FTI stampabili in Microsoft Office Excel e Word. È inoltre possibile modificare il layout, il flusso di dati e la formattazione per soddisfare i requisiti specifici senza apportare modifiche al codice.

> [!NOTE]
> Se si desidera iniziare con una panoramica delle configurazioni di ER esistenti per questo esempio di soluzione per i moduli FTI stampabili, è possibile passare direttamente alla sezione **Scaricare le configurazioni di ER di esempio per generare moduli FTI stampabili** più avanti in questo argomento.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Creare configurazioni personalizzate per i moduli FTI stampabili
Come parte della soluzione personalizzata per i moduli FTI stampabili, è necessario creare un gruppo di configurazioni di ER.

### <a name="configure-the-er-data-model"></a>Configurare il modello dati di ER
L'applicazione deve includere la configurazione del modello dati di ER che contiene un modello dati che descrive il dominio aziendale della fatturazione dei clienti. Come requisito, il nome del modello dati deve essere **CustomersInvoicing**. Per informazioni su come progettare modelli dati di ER, vedere [RE Progettare il modello dati specifico di dominio](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Configurare il mapping del modello dati di ER
L'applicazione deve includere il mapping del modello ER per il modello dati CustomersInvoicing. Il mapping del modello può essere nella configurazione del modello dati di ER o nella configurazione di mapping del modelli di ER. Tuttavia, il nome del descrittore radice del mapping del modello deve essere **FreeTextInvoice**.

Il mapping deve contenere le seguenti origini dati:

- Tipo di origine dati: **Record di tabella**

    - Questa origine dati deve essere denominata **CustInvoiceJour**.
    - È necessario fare riferimento alla tabella dell'applicazione CustInvoiceJour.
    - Viene utilizzata in fase di esecuzione per passare dall'applicazione al mapping del modello di ER l'elenco di fatture selezionate per la stampa.

- Tipo di origine dati: **Oggetto**

    - Questa origine dati deve essere denominata **PrintMgmtPrintSettingDetail**.
    - Deve fare riferimento alla classe dell'applicazione **PrintMgmtPrintSettingDetail**.
    - Viene utilizzata in fase di esecuzione per passare dall'applicazione ai dettagli di mapping del modello di ER le impostazioni di Gestione stampa per il formato ER in esecuzione.

I dettagli dell'integrazione dell'applicazioni con il framework di ER sono disponibili nella classe **ERPrintMgmtReportFormatSubscriber** (modello di integrazione della famiglia di prodotti ER) nel codice sorgente dell'applicazione.

Per ulteriori informazioni sulla progettazione di mapping di modello di ER, vedere [Definire i mapping di modello ER e selezionare le relative origini dati](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>Configurare il formato di ER
Nell'istanza dell'applicazione è necessario disporre della configurazione del formato di ER che sarà utilizzata per generare i moduli FTI. 

> [!NOTE]
> Questa configurazione di formato deve essere creata per il modello dati CustomersInvoicing e deve utilizzare il mapping del modello con il descrittore radice **FreeTextInvoice**.

Per informazioni su come configurare i formati di ER, vedere [ER Creare una configurazione formato (novembre 2016)](tasks/er-format-configuration-2016-11.md). Per informazioni su come progettare formati di ER per generare i report in formato OpenXML, vedere [ER Progettare una configurazione per la creazione di report nel formato OPENXML (novembre 2016)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>Configurare la gestione della stampa
Per generare i moduli FTI utilizzando il framework di ER, è possibile assegnare formati di ER nello stesso modo in cui si assegnano i report SSRS. Per associare il formato di ER a tutte le FTI di contabilità clienti, passare a **Contabilità clienti** \> **Impostazione** \> **Moduli** \> **Impostazione moduli** \> **Generale** \> **Gestione stampa** \> **Fattura a testo libero** \> **Originale**. Per associare il formato di ER a un cliente specifico o a una fattura, seguire questi passaggi.

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Selezionare l'FTI da associare al formato di ER e aprire la pagina **Impostazione Gestione stampa**.
3. Selezionare il livello di documento per specificare l'ambito delle fatture per l'elaborazione.
4. Selezionare il formato di ER per il livello di documento specificato.

![Impostazione Gestione stampa](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Solo i formati di ER che utilizzano il descrittore radice **FreeTextInvoice** del modello dati **CustomersInvoicing** vengono visualizzati nel campo **Ricerca formato di report** per il formato selezionato.

## <a name="generate-fti-forms"></a>Generare moduli FTI
I moduli FTI vengono generati nel framework di ER in modo analogo ai report SSRS.

Per generare i moduli FTI, è possibile selezionare le fatture in base a un intervallo o per selezione. 

![Selezione delle fatture](media/FTIbyGER-InvoiceSelection.png)

![Anteprima della fattura](media/FTIbyGER-InvoiceExcelPreview.png)

Quando si utilizzando i formati di ER per stampare i moduli FTI in questo modo, vengono utilizzate le destinazioni di file di ER predefinite. La descrizione non può essere modificata. Per altre informazioni su come configurare le destinazioni di ER per i formati di ER, vedere [Destinazioni dei report elettronici (ER)](electronic-reporting-destinations.md).

È inoltre possibile generare moduli FTI durante la registrazione di un FTI, attivando **Stampa fattura** e disattivando **Utilizza destinazione gestione stampa**.

> [!NOTE]
> Quando si utilizzando i formati di ER per stampare i moduli FTI in questo modo, vengono utilizzate le destinazioni di file di ER predefinite. È possibile cambiare la destinazione predefinita in fase di esecuzione se la destinazione è già stata configurata. Per cambiare la destinazione, è necessario disporre del seguente privilegio di sicurezza:
>
> - **Nome:** ERFormatDestinationRuntimeMaintain
> - **Etichetta:** Gestisci destinazione formato di report elettronici in fase di esecuzione

![Destinazione report elettronici](media/FTIbyGER-ERFileDestinationSetting.png)

![Destinazione del formato per la creazione di report elettronici](media/FTIbyGER-ERFileDestinationUsage.png)

Il framework di ER attualmente supporta le seguenti destinazioni per i documenti generati:

- **File scaricato** - I moduli generati vengono offerti come download che è possibile salvare utilizzando il browser.
- **Schermo** - Excel di Microsoft Office 365 viene utilizzato per visualizzare l'anteprima dei moduli FTI in formato di Excel.
- **Cartella di SharePoint** - I moduli generati vengono archiviati in base alle impostazioni del framework di gestione documenti.
- **Archivio dell'applicazione** - I moduli generati vengono archiviati come allegati dei record del registro di esecuzione in Archiviazione di Microsoft Azure.
- **Posta elettronica** - I moduli generati vengono inviati come allegati di posta elettronica.

> [!NOTE]
> Non è possibile inviare i moduli FTI generati direttamente alla stampante, poiché la stampa diretta che utilizza l'agente di registrazione della stampante di Dynamics attualmente non è supportata.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Scaricare le configurazioni di ER di esempio per generare i moduli FTI stampabili
È possibile scaricare le configurazioni di ER di esempio da utilizzare come modello per la soluzione di FTI. Le configurazioni vengono archiviate nella Raccolta di risorse condivise in Microsoft Dynamics Lifecycle Services (LCS). Le configurazioni includono:

- La configurazione **Modello di fatturazione clienti** contiene il modello dati e il mapping del modello richiesti.
- La configurazione **Report FTI clienti (GER)** contiene il formato di esempio.

> [!NOTE]
> Queste configurazioni sono state create come esempi per aiutare la chiarire i possibili scenari. Il futuro di queste configurazioni dipende dai risultati di questa valutazione dai commenti e suggerimenti che si riceveranno.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Funzionalità che sono implementate nel formato di ER di esempio
Nella configurazione del formato di ER di esempio, viene utilizzato un file di Excel come modello per generare i moduli FTI.

![Progettazione formati](media/FTIbyGER-ERFormat.png)

Attualmente, questo formato di ER di esempio supporta le seguenti funzionalità per generare i moduli FTI:

- I moduli FTI vengono generati sia per le fatture originali registrate che per le fatture originali non ancora registrate. Le fatture e le note di accredito rettificate non sono supportate.
- I moduli FTI vengono generati nella lingua della fattura. Il formato dei valori e delle date nei moduli generati è basato sulle impostazioni locali del client dell'utente.
- Le fatture generate visualizzano notifiche di indisponibilità di dati se nessuna delle righe delle fatture è stata elaborata.
- Le intestazioni di fatture generate si basano sul formato carta selezionato per il modulo FTI nella pagina **Parametri contabilità clienti**. I dettagli della società vengono visualizzati nell'intestazione del modulo della fattura generato solo se il formato carta è vuoto.
- I moduli di fatture generati mostrano le partite IVA della società e del cliente quando l'opzione appropriata è stata selezionata per il modulo FTI nella pagina **Parametri contabilità clienti**.
- Le sezioni delle righe e dei totali di fattura generate mostrano i dettagli monetari della fattura predefiniti nella valuta di registrazione della fattura.
- La sezione dei totali di fattura generata può mostrare i dettagli monetari in valuta Euro e la valuta di registrazione della fattura quando l'opzione **Stampa l'importo nella valuta che rappresenta l'euro** è abilitata nella pagina **Parametri contabilità clienti**.
- I moduli di fattura generati mostrano tutte le note di fattura di elaborazione che sono disponibili, in base alle impostazioni nella pagina **Parametri contabilità clienti**. Le note vengono incluse sia per l'intera fattura che per ogni riga di fattura.
- I moduli di fattura generati includono note per il modulo FTI del cliente e la lingua di elaborazione della fattura quando sono stati configurati nell'elenco di note modulo CoCli.
- A seconda delle impostazioni di Gestione stampa, le fatture generate includono testo personalizzato del piè di pagina quando è stato configurato per la lingua della fattura, il formato di ER e l'ambito del documento FTI.
- La sezione dei totali dei moduli di fattura generati include tutte le informazioni sugli sconti di cassa disponibili.
- La sezione dello scadenzario pagamenti dei moduli di fattura generati include tutti i dettagli dello scadenzario pagamenti disponibili.
- La sezione di markup dei moduli di fattura generati include tutte le transazioni di spese che sono disponibili.
- I moduli di fattura generati includono i dettagli IVA, in base all'impostazione **Specifica IVA** della pagina **Parametri contabilità clienti**. Questa sezione può mostrare i dettagli IVA solo nella valuta di registrazione della fattura o nella valuta di registrazione della fattura e nella valuta di contabilizzazione della società contemporaneamente.
- I moduli di fattura generati mostrano i dettagli delle notifiche di addebito diretto. Ad esempio mostrano quando il metodo di pagamento che ha l'ID di mandato di addebito diretto obbligatorio è stato selezionato per la fattura, quando l'elaborazione della fattura è stata registra nella valuta euro e quando l'ID di mandato di addebito diretto è stato definito per la fattura.
- Le fatture generate mostrano tutti i dettagli di pagamento anticipato disponibili per le fatture registrate.
- I moduli di fattura generati possono essere inviati a un cliente come allegati di posta elettronica. È consigliabile configurare la destinazione del file di ER per il formato di ER utilizzato.

### <a name="countryregion-specific-features"></a>Caratteristiche specifiche del paese 
Le seguenti funzionalità specifiche del paese/regione sono incluse nel formato di ER di esempio per mostrare in che modo possono essere gestiti i requisiti specifici nelle configurazioni di ER.

#### <a name="norway"></a>Norvegia
Il termine Registro di impresa viene inserito nell'intestazione del modulo di fattura generato quando la fattura viene elaborata per una persona giuridica che è configurata nel seguente modo:

- Viene utilizzato il contesto di paese/regione per la Norvegia.
- Il parametro **Print Foretaksregisteret** è attivo sui documenti di vendita.

#### <a name="spain"></a>Spagna
Il termine **Regime speciale per metodo di contabilità di cassa** viene inserito nell'intestazione del modulo di fattura generato quando la fattura viene elaborata per una persona giuridica che è configurata nel seguente modo:

- Viene utilizzato il contesto di paese/regione per la Spagna.
- Il Regime speciale per metodo di contabilità di cassa viene abilitato alla data di elaborazione della fattura.

Quando i dettagli dello sconto di cassa, ad esempio l'importo dello sconto di cassa e l'importo netto della riga di fattura, sono disponibili, vengono visualizzati nella sezione dei totali di fattura del modulo di fattura generato quando viene elaborato per una persona giuridica che è configurata nel seguente modo:

- Viene utilizzato il contesto di paese/regione per la Spagna.
- **Sconto di cassa applicato nella fattura** è attivato nell'opzione di fatturazione (**Parametri di contabilità generale** \> **Sezione IVA**).

#### <a name="italy"></a>Italia
Il segno di Sconto merci viene incluso nelle righe della fattura generata quando viene elaborata per una persona giuridica configurata utilizzando il contesto di paese/regione per l'italia.

#### <a name="finland"></a>Finlandia
Oltre al modulo di fattura generato, è possibile generare distinte di ordine di accredito nel seguente modo:

- Per la persona giuridica che utilizza il contesto di paese/regione per la Finlandia e che dispone di almeno un conto bancario contrassegnato come **Conto ordini di accredito** e **Codice a barre banca**. 
- Per una fattura contrassegnata come obbligatoria per l'allegato di pagamento associato **Finlandese**.

![Distinta di ordine di accredito](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> Il formato di ER di esempio è stato configurato per generare facoltativamente le distinte di ordine di accredito del foglio di lavoro separato.

> [!NOTE]
> È innanzitutto necessario installare il tipo di carattere utilizzato per generare il codice a barre nel computer locale in cui verrà visualizzato il modulo di fattura generato nel formato di Excel.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>Utilizzare il formato di ER di esempio per configurare le destinazioni di posta elettronica
Utilizzare gli elementi seguenti del formato di ER di esempio per configurare le destinazioni di posta elettronica:

- È possibile accedere all'indirizzo di posta elettronica di un contatto del cliente attraverso la seguente espressione di ER: **model.InvoiceBase.Contact.ElectronicMail**.
- È possibile accedere al testo dell'oggetto del messaggio di posta elettronica attraverso la seguente espressione di ER: **Emailing.TxtToUse.Subject**.
- È possibile accedere al testo del corpo del messaggio di posta elettronica attraverso la seguente espressione di ER: **Emailing.TxtToUse.Body**.

![Impostazioni destinazione](media/FTIbyGER-ERFileDestinationSettingEmail.png)

Il testo predefinito dell'oggetto e del corpo del messaggio di posta elettronica viene definito nel formato di ER di esempio. La lingua dipende dalle etichette del formato. Questo testo predefinito verrà utilizzato per i messaggi di posta elettronica se un modello di messaggio di posta elettronica dell'organizzazione personalizzato dispone dell'ID **ERFTITMP** predefinito.

> [!NOTE]
> L'ID del modello di messaggio di posta elettronica **ERFTITMP** è stato definito nel formato di ER di esempio. Può essere modificato in base alle esigenze in un nuovo formato di ER creato da questo formato di esempio.

Se il modello di messaggio di posta elettronica dell'organizzazione che ha l'ID **ERFTITMP** predefinito è stato aggiunto per la persona giuridica per cui si sta elaborando per la fattura, verrà utilizzato il modello per il testo dell'oggetto e del corpo del testo del messaggio di posta elettronica per generare messaggi di posta elettronica. 

![Modelli di posta elettronica a livello di organizzazione](media/FTIbyGER-EmailTemplate.png)

![Carica modello di messaggio di posta elettronica](media/FTIbyGER-EmailTemplateBody.png)

L'espressione di ER **Emailing.TxtToUse.Subject** del formato di ER di esempio viene configurata per sostituire tutte le occorrenze del segnaposto %1 con l'ID fattura in elaborazione.

L'espressione **Emailing.TxtToUse.Body** del formato di esempio viene configurata per le seguenti sostituzioni di segnaposti:

- "%1" viene sostituito con il nome del contatto del cliente.
- "%2" viene sostituito con il nome della società.
- "%3" viene sostituito con il nome del cliente.
- "%4" viene sostituito con il nome del contatto della società.
- "%5" viene sostituito con il titolo del contatto della società.
- "%6" viene sostituito con l'indirizzo email del contatto della società.

![Indirizzo di posta elettronica](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>Risorse aggiuntive
[Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md)
