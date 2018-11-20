---
title: Esempio di integrazione di stampante fiscale per l'Italia
description: In questo argomento viene fornita una panoramica di esempio di integrazione fiscale per l'Italia.
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Italy
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: ff6ccd5fd1a0772aedba16dcc720dcfbd0c8bcab
ms.contentlocale: it-it
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Esempio di integrazione di stampante fiscale per l'Italia

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

L'integrazione fiscale per l'Italia include esempi dell'integrazione con la stampante fiscale EPSON FP-90III. Questo è stato sviluppato in base al framework di integrazione fiscale. Per informazioni dettagliate sulla funzionalità di integrazione fiscale, vedere [Integrazione fiscale per il canale di vendita al dettaglio](fiscal-integration-for-retail-channel.md).

In questo esempio sono incluse le seguenti funzionalità:
- Integrazione con la stampante fiscale Epson FP-90III tramite la soluzione modalità web-service - ePOS-Print.
- Registrazione dei seguenti eventi nel POS:
    - Stampa ricevuta per vendita:
      - Stampa ricevuta per reso vendita.
      - Stampa report X.
      - Stampa report Z.

Le ricevute per le operazioni di vendita e reso di vendita supportano anche i seguenti scenari:  
- Stampa di sconti.
- Esclusione di gift card dalla ricevuta.
- Ricevute per ordine cliente.

## <a name="design"></a>Progetto

L'integrazione per la stampnte fiscale Epson FP-90III è implementata in due estensioni:
- Estensione CRT - genera documenti XML in formato specifico per la stampante (Runtime.Extensions.DocumentProvider.EpsonFP90IIISample).
- Estensione stazione hardware - invia i documenti generati dall'estensione CRT alla stampante fiscale (tramite il protocollo HTTP) e gestisce la risposta da HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample.

![testo alternativo](media/emea-ita-fpi-solution.png "Schema soluzione")

## <a name="set-up-retail-for-italy"></a>Impostazione vendita al dettaglio per l'Italia

### <a name="enabling-extensions"></a>Abilitazione delle estensioni

##### <a name="crt-extension-components"></a>Componenti dell'estensione CRT

I componenti dell'estensione CRT sono inclusi in Retail SDK. Per completare le seguenti procedure, aprire la soluzione CRT, CommerceRuntimeSamples.sln, in RetailSdk\SampleExtensions\CommerceRuntime.

1. Individuare il progetto Runtime.Extensions.DocumentProvider.EpsonFP90IIISample e compilarlo.
1. Nella cartella Extensions.DocumentProvider.EpsonFP90IIISample\bin\Debug, trovare il file assembly Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll.
1. Copiare il file assembly alla cartella dell'estensione CRT:
    - Server Retail: copiare l'assembly nella cartella \bin\ext nella posizione del sito del Server Retail Microsoft Internet Information Services (IIS).
    - CRT locale su POS moderno: copiare assembly nella cartella \ext nella posizione boker client CRT locale.
1. Individuare il file di configurazione di estensioni per il CRT:
    - Server Retail: Il file si chiama commerceruntime.ext.config e si trova nella cartella bin\ext nella posizione del sito del Server Retail IIS.
    - CRT locale sul POS moderno: Il file si chiama CommerceRuntime.MPOSOffline.Ext.config e si trova nella posizione del broker client CRT locale.
1. Registrare la modifica CRT nel file di configurazione di estensioni. Aggiungere source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" 
1. Riavviare il servizio vendita al dettaglio:
    - Server Retail: riavviare il sito del servizio di vendita al dettaglio da Gestione IIS.
    - Broker client: terminare il processo dllhost.exe in Gestione attività quindi riavviare il POS moderno.

##### <a name="hardware-station-extension-components"></a>Componenti dell'estensione stazione hardware
I componenti dell'estensione stazione hardware sono inclusi in Retail SDK. Per completare le seguenti procedure, aprire la soluzione Stazione hardware, HardwareStationSamples.sln, under RetailSdk\SampleExtensions\HardwareStation.

1. Individuare il progetto HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample e compilarlo.
1. Nella cartella Extensions.EpsonFP90IIIFiscalDeviceSample \bin\Debug, trovare il file assembly Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll.
1. Copiare i file in un computer stazione hardware distribuito:
    - Stazione hardware remota: copiare i file nella cartella bin nella posizione del sito stazione hardware Microsoft Internet Information Services (IIS).
    - Stazione hardware locale: Copiare i file nella posizione del broker client POS moderno.
1. Individuare il file di configurazione per le estensioni della stazione hardware. Il file si chiama HardwareStation.Extension.config:
    - Stazione hardware remota: Il file è situato sotto all'ubicazione della stazione hardware IIS.
    - Stazione hardware locale: il file si trova nella posizione del broker client POS moderno.
    
1. Aggiungere la sezione seguente alla sezione di composizione del file di configurazione. 
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample" />
1. Riavviare il servizio della stazione hardware:
    - Stazione hardware remota: Riavviare il sito della stazione hardware da Gestione IIS.
    - Stazione hardware locale: terminare il processo dllhost.exe in Gestione attività quindi riavviare il POS moderno.

### <a name="set-up-the-registration-process"></a>Impostare il processo di registrazione
Per abilitare il processo di registrazione, impostare la sede centrale utilizzando i seguenti passaggi:
1. Aprire Vendita al dettaglio\Impostazione canale\Integrazione fiscale\Connettori fiscali. Importare la configurazione da RetailSdk\SampleExtensions\CommerceRuntime\Entension.DocumentProvider.EpsonFP90IIISample\Configuration\DocumentProviderEpsonFP90IIISample.xml.

![testo alternativo](media/emea-ita-fpi-fiscalconnector.png "Connettore fiscale")

2. Aprire Vendita al dettaglio\Impostazione canale\Integrazione fiscale\Fornitori di documenti fiscali. Importare la configurazione da RetailSdk\SampleExtensions\HardwareStation\Entension.EpsonFP90IIIFiscalDeviceSample\Configuration\ConnectorEpsonFP90IIISample.xml.

![testo alternativo](media/emea-ita-fpi-documentprovider.png "Fornitore di doumenti")

3. Aprire Vendita al dettaglio\Impostazione canale\Integrazione fiscale\Profili tecnici del connettore. Creare un nuovo profilo e selezionare il connettore caricato nel passaggio precedente. Aggiornare le impostazioni di connessione se necessario.

![testo alternativo](media/emea-ita-fpi-technicalprofile.png "Profilo tecnico")

4. Aprire Vendita al dettaglio\Impostazione canale\Integrazione fiscale\Profili funzionali del connettore. Creare un nuovo profilo e selezionare il connettore caricato e il fornitore di documenti dal passaggio precedente. Aggiornare le impostazioni di mapping dei dati se necessario

![testo alternativo](media/emea-ita-fpi-fiscalfunctionalityprofile.png "Profilo funzionale del connettore")

5. Aprire Vendita al dettaglio\Impostazione canale\Integrazione fiscale\Gruppo funzionale di connettori. Creare un nuovo gruppo e selezionare il profilo funzionale del connettore dal passaggio precedente.

![testo alternativo](media/emea-ita-fpi-connectorgroup.png "Gruppo di connettori")

6. Aprire Vendita al dettaglio\Impostazione canale\Integrazione fiscale\Processo di registrazione. Creare un nuovo processo. Selezionare il gruppo funzionale di connettori dal passaggio precedente.

![testo alternativo](media/emea-ita-fpi-registrationprocess.png "Processo di registrazione")

7. Aprire il profilo Funzionalità collegato al punto vendita in cui il processo di registrazione deve essere attivato. Espandere la scheda dettaglio **Processo di registrazione fiscale**. Selezionare il processo di registrazione creato nel passaggio precedente.

![testo alternativo](media/emea-ita-fpi-functionalityprofile.png "Profilo funzionalità POS")

8. Apre il profilo hardware collegato alla stazione hardware a cui la stampante fiscale sarà collegata. Espandere la scheda dettaglio **Periferiche fiscali**. Selezionare il profilo tecnico del connettore.

![testo alternativo](media/emea-ita-fpi-hardwareprofile.png "Profilo hardware")

9. Aprire la programmazione di distribuzione e selezionare il processo **1070** per trasferire i dati nel database canale.

![testo alternativo](media/emea-ita-fpi-distributionjobs.png "Programmazione di distribuzione")

## <a name="commerce-runtime-extension-design"></a>Progettazione dell'estensione di Commerce Runtime

Lo scopo dell'estensione (Fornitore di documenti) è di generare documenti specifici per la stampante e di gestire le risposte dalla stampante fiscale. 

### <a name="request-handler"></a>Gestore richieste
    
Il gestore richieste DocumentProviderEpsonFP90III è il punto di ingresso per la richiesta di generare documenti dalla stampante fiscale.

Il gestore viene ereditato dall'interfaccia INamedRequestHandler. Metodo HandlerName è responsabile della restituzione del nome del gestore. Deve corrispondere al nome del fornitore di documenti del connettore specificato in sede centrale.

Il connettore supporta le seguenti richieste:
- GetFiscalDocumentDocumentProviderRequest- contiene informazioni su quale documento dovrà essere generato. Restituisce un documento specifico per la stampante che deve essere registrato nella stampante fiscale.
- GetSupportedRegistrableEventsDocumentProviderRequest - restituisce l'elenco degli eventi da sottoscrivere. Attualmente, i seguenti eventi sono supportati: vendita, stampa del report X e stampa del report Z.
- SaveFiscalRegistrationResultDocumentProviderRequest- salva la risposta dalla stampante.


### <a name="configuration"></a>Configurazione
Il file di configurazione si trova nella cartella Configuration del Progetto di estensione. Lo scopo del file è di consentire di configurare le impostazioni per il fornitore di documenti dalla sede centrale. Il formato di file si allinea ai requisiti di configurazione dell'integrazione fiscale. Sono stati aggiunte i seguenti impostazioni:
- Mapping aliquote IVA
- Mapping tipo di metodo di pagamento

## <a name="hardware-station-extension-design"></a>Progettazione dell'estensione stazione hardware

Lo scopo dell'estensione (Connettore) è di comunicare con la stampante fiscale.

### <a name="request-handler"></a>Gestore richieste
Il gestore richieste EpsonFP90IIISample è il punto di ingresso per la gestione della richiesta alla periferica fiscale. Il gestore viene ereditato dall'interfaccia INamedRequestHandler. Metodo HandlerName è responsabile della restituzione del nome del gestore, deve corrispondere al nome del connettore fiscale specificato nella sede centrale.

Il connettore supporta le seguenti richieste:
- SubmitDocumentFiscalDeviceRequest - invia il documento alle stampanti e restituisce la risposta dalla stampante fiscale.
- IsReadyFiscalDeviceRequest - Utilizzato per un controllo di integrità del dispositivo.
- InitializeFiscalDeviceRequest - utilizzato per l'inizializzazione della stampante.


### <a name="configuration"></a>Configurazione
Il file di configurazione si trova nella cartella **Configuration** del Progetto di estensione. Lo scopo del file è di consentire di configurare le impostazioni per il fornitore di connettore dalla sede centrale. Il formato di file si allinea ai requisiti di configurazione dell'integrazione fiscale. Sono stati aggiunte i seguenti impostazioni:
- Indirizzo endpoint - URL della stampante.
- Sincronizzazione data e ora - indica se è necessaria la sincronizzazione di data e ora della stampante con la stazione hardware collegata. La data e l'ora della stampante verranno sincronizzate con l'orario della stazione hardware.

