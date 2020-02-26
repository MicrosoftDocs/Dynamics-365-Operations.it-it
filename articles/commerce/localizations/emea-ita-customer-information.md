---
title: Gestione delle informazioni del cliente per l'Italia
description: In questo argomento viene descritto come gestire le informazioni relative al cliente nel POS per l'Italia.
author: ''
manager: annbe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Italy
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: b3df47a9ec5f03e110d817bc4d8f221f804fe74d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004706"
---
# <a name="customer-information-management-for-italy"></a>Gestione delle informazioni cliente per l'Italia

[!include [banner](../includes/banner.md)]


## <a name="introduction"></a>Introduzione

In questo argomento viene descritto come è possibile gestire le informazioni relative al cliente, ad esempio il codice lotteria del cliente, nel POS di Commerce per l'Italia.

È possibile specificare informazioni sul cliente, come il codice fiscale o il codice lotteria, quando si crea o si modifica un record di dati master del cliente nel POS. È inoltre possibile specificare il codice lotteria per una transazione di vendita copiandolo dal cliente della transazione o immettendolo manualmente. Il codice lotteria può quindi essere stampato sia sulle ricevute fiscali e su quelle normali ed essere utilizzato per la lotteria nazionale. I codici fiscali personali possono inoltre essere utilizzati per individuare un cliente in POS.

> [!NOTE]
> Questa funzionalità è disponibile nella versione 10.0.8 e successive.

## <a name="setup"></a>Impostazione

È necessario completare la seguente configurazione per utilizzare questa funzionalità:

- Impostare un tipo di registrazione per il codice lotteria.
- Aggiungere l'operazione **Aggiungi informazioni cliente** ai layout dello schermo.
- Attivare la richiesta di informazioni del cliente.
- Impostare i formati di ricevuta.
- Aggiungere i criteri di ricerca cliente.
- Configurare i componenti del canale.

### <a name="set-up-a-registration-type-for-the-lottery-code"></a>Impostare un tipo di registrazione per il codice lotteria

Prima di poter specificare i codici lotteria nel POS, è necessario creare un tipo di registrazione appropriato per il codice lotteria e collegarlo alla categoria di registrazione **Codice lotteria**. Per ulteriori informazioni su come utilizzare i tipi di registrazione e gli ID registrazione, vedere [ID registrazione](../../finance/localizations/emea-registration-ids.md).

> [!WARNING]
> Se un tipo di registrazione non viene creato o non è collegato alla categoria di registrazione **Codice lotteria**, viene generato un errore nel POS quando il codice lotteria viene immesso per un indirizzo cliente. 

### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a>Aggiungere l'operazione Aggiungi informazioni cliente ai layout dello schermo

L'operazione **Aggiungi informazioni cliente** può essere utilizzata per aggiungere informazioni sul cliente, come il codice lotteria, a una transazione di vendita. Queste informazioni possono essere copiate dal cliente specificato per la transazione oppure possono essere inserite manualmente.

Nella pagina **Griglie dei pulsanti**, selezionare la griglia dei pulsanti in cui dovrebbe apparire l'operazione e aprire la finestra Progettazione griglia dei pulsanti. Aggiungere un nuovo pulsante, quindi nel campo **Azione** selezionare **Aggiungi informazioni cliente**. Per ulteriori informazioni sull'utilizzo dei layout dello schermo e delle griglie dei pulsanti, vedere [Layout delle schermate per il POS](../pos-screen-layouts.md).

### <a name="activate-the-inquiry-for-customer-information"></a>Attivare la richiesta di informazioni del cliente

Se le informazioni del cliente non sono specificate per una transazione di vendita, una richiesta per tali informazioni può essere attivata automaticamente dopo la finalizzazione della transazione. Questo approccio è un'alternativa all'operazione **Aggiungi informazioni cliente**.

Per attivare la richiesta di informazioni cliente, impostare l'opzione **Abilita richiesta informazioni sul cliente nelle transazioni di vendita** su **Sì** nella sezione **Parametri imposte** della Scheda dettaglio **Funzioni** della pagina **Profili funzionalità POS**.

### <a name="set-up-receipt-formats"></a>Impostare formati di ricevuta

È possibile configurare i formati di ricevuta in modo che il codice fiscale e il codice lotteria del cliente siano stampati sulle ricevute.

> [!NOTE]
> La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua. In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.

Nella pagina **Testo lingua**, nella scheda **POS**, aggiungere i record seguenti per le etichette dei campi personalizzati per i formati di ricevuta. Tenere presente che i valori di **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. È possibile modificarli in base alle esigenze. Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.

| ID lingua | ID testo | Text                |
|-------------|---------|---------------------|
| en-US       | 900001  | Codice lotteria        |
| en-US       | 900002  | Codice fiscale         |

Nella pagina **Campi personalizzati**, aggiungere i record seguenti per i campi personalizzati per i formati di ricevuta. Si noti che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.

| Nome                           | Tipo    | ID testo didascalia |
|--------------------------------|---------|-----------------|
| FISCALCUSTOMER\_LOTTERYCODE\_IT| Ricevimento | 900001          |
| CUSTOMER\_FISCALCODE\_IT       | Ricevimento | 900002          |

In Progettazione formato ricevuta, aggiungere i campi personalizzati alla sezione appropriata della ricevuta per ogni formato di ricevuta necessario. Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedere [Modelli e stampa di ricevute](../receipt-templates-printing.md)

### <a name="add-a-customer-search-criterion"></a>Aggiungere i criteri di ricerca cliente

È possibile aggiungere i criteri di ricerca cliente in modo che sia possibile cercare i clienti nel POS in base al codice fiscale.

Nella pagina **Parametri di commercio**, nella scheda **Criteri di ricerca POS**, aggiungere un nuovo criterio di ricerca del cliente. Nel campo **Criteri di ricerca cliente**, selezionare **Partita IVA**. Selezionare la casella di controllo **Visualizza come collegamento**, ma lasciare deselezionata la casella di controllo **Ridefinizione possibile**. Nella pagina **Programmazioni della distribuzione**, eseguire il processo **1110**.

### <a name="configure-channel-components"></a>Configurare i componenti del canale

Per rendere disponibile la funzionalità specifica dell'Italia, è necessario configurare le estensioni per i componenti del canale di commercio. Per ulteriori informazioni, vedere la sezione [Linee guida per la distribuzione](#deployment-guidelines) più avanti in questo argomento.

## <a name="example-scenarios"></a>Scenari di esempio

I seguenti scenari di esempio mostrano come utilizzare le informazioni sui clienti nel POS per l'Italia.

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a>Scenario 1: Effettuare una vendita a un cliente anonimo

1. Accedere a POS.
1. Aggiunge articoli al carrello.
1. Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.
1. Immettere il codice lotteria del cliente e quindi selezionare **OK**.
1. Registrare i pagamenti per la transazione e quindi completare la transazione.
1. Verificare che la ricevuta stampata contenga il codice lotteria del cliente.

### <a name="scenario-2-make-a-sale-to-a-new-named-customer"></a>Scenario 2: Effettuare una vendita a un nuovo cliente denominato

1. Accedere a POS.
1. Aggiunge articoli al carrello.
1. Selezionare **Aggiungi cliente** e quindi selezionare **Nuovo**.
1. Specificare gli attributi del nuovo cliente. Nel campo **Codice fiscale**, immettere il codice fiscale del cliente.
1. Selezionare **Crea una nuova rubrica**. Quindi specificare le informazioni di contatto del nuovo cliente e un indirizzo.
1. Nel campo **Codice lotteria**, immettere il codice lotteria del cliente.
1. Salvare il record cliente e il record indirizzo cliente e aggiungere il cliente alla transazione.
1. Registrare i pagamenti per la transazione e quindi completare la transazione.
1. Poiché la richiesta di informazioni relative al cliente è stata attivata, ma tali informazioni non sono state aggiunte alla transazione, il viene visualizzata la finestra di dialogo **Immettere informazioni cliente**. Selezionare **Sì**, quindi selezionare **Copia dal cliente della transazione**.
1. Verificare il codice lotteria del cliente e quindi selezionare **OK**.
1. Verificare che la ricevuta stampata contenga il codice lotteria del cliente.

> [!NOTE]
> Se è necessario specificare un cliente diverso per la transazione, è necessario cancellare le informazioni sul cliente e copiarle nuovamente dopo aver aggiunto il nuovo cliente.

### <a name="scenario-3-change-the-customer-information-for-a-sale-to-a-named-customer"></a>Scenario 3: Modificare le informazioni relative al cliente per una vendita su un cliente specifico

1. Accedere a POS.
1. Aggiunge articoli al carrello.
1. Selezionare **Aggiungi cliente** e quindi selezionare un account cliente per aggiungerlo alla transazione.
1. Selezionare **Aggiungi informazioni cliente**, quindi selezionare **Copia dal cliente della transazione**.
1. Verificare il codice lotteria del cliente e quindi selezionare **OK**.
1. Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Cancella** per cancellare le informazioni relative al cliente dalla transazione.
1. Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.
1. Specificare il codice lotteria del cliente e quindi selezionare **OK**.
1. Registrare i pagamenti per la transazione e quindi completare la transazione.
1. Verificare che la ricevuta stampata contenga il codice lotteria del cliente.

## <a name="deployment-guidelines"></a>Linee guida per la distribuzione

In questa sezione vengono fornite le linee guida per la distribuzione per consentire la gestione delle informazioni sui clienti nella localizzazione di Commerce per l'Italia.

> [!NOTE]
> Alcuni passaggi in queste procedure variano in base alla versione di Commerce in uso. Per ulteriori informazioni, vedere [Novità o modifiche in Dynamics 365 for Retail](../get-started/whats-new.md).
>
> Se si desidera abilitare l'integrazione del POS con le stampanti fiscali per l'Italia, e in particolare se si desidera stampare i codici lotteria dei clienti sulle ricevute fiscali, è necessario distribuire [l'esempio di integrazione di stampante fiscale per l'Italia](emea-ita-fpi-sample.md).

### <a name="update-customizations"></a>Aggiornare le personalizzazioni

Seguire questi passaggi se una qualsiasi delle personalizzazioni include gestori di richieste per la richiesta SaveCartRequest o CreateSalesOrderServiceRequest.

1. Individuare il gestore per la richiesta **SaveCartRequest**.
1. Individuare la riga di codice che esegue il gestore originale.
1. Sostituire la classe del gestore originale con **TaxRegistrationIdFiscalCustomerService**.

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly.Services;

    ...

    var requestHandler = new TaxRegistrationIdFiscalCustomerService();
    var response = request.RequestContext.Runtime.Execute<SaveCartResponse>(request, request.RequestContext, requestHandler, skipRequestTriggers: false);
    ```

1. Ripetere i passaggi da 1 a 3 per la richiesta **CreateSalesOrderServiceRequest**.

### <a name="update-a-development-environment"></a>Aggiornare un ambiente di sviluppo

Seguire questi passaggi per aggiornare un ambiente di sviluppo.

#### <a name="crt-extension-components"></a>Componenti dell'estensione CRT

1. Individuare il file di configurazione dell'estensione per Commerce Runtime (CRT):

    - **Commerce Scale Unit:** individuare il file **CommerceRuntime.Ext.config** nella cartella **bin\\ext** nella posizione del sito Commerce Scale Unit di Microsoft Internet Information Services (IIS).
    - **CRT locale sul POS moderno:** Trovare il file **CommerceRuntime.MPOSOffline.Ext.config** nella posizione del broker client CRT locale.

1. Registrare l'estensione CRT nel file di configurazione dell'estensione.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
    ```

    > [!WARNING]
    > **Non** modificare i file CommerceRuntime.MPOSOffline.config e CommerceRuntime.config. Questi file non sono progettati per essere personalizzati.

#### <a name="modern-pos-extension-components"></a>Componenti dell'estensione POS moderno

Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.

1. Aprire la soluzione in **RetailSdk\\POS\\ModernPOS.sln**.
1. In **POS.Extensions\\extensions.json**, attivare l'estensione.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. Compilare la soluzione.
1. Aprire POS moderno e verificare la funzionalità.

#### <a name="cloud-pos-extension-components"></a>Componenti dell'estensione POS cloud

Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.

1. Aprire la soluzione in **RetailSdk\\POS\\CloudPOS.sln**.
1. In **POS.Extensions\\extensions.json**, attivare l'estensione.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. Compilare la soluzione.
1. Aprire POS cloud e verificare la funzionalità.

### <a name="update-a-production-environment"></a>Aggiornare un ambiente di produzione

Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare i pacchetti a un ambiente di produzione.

1. Nei file di configurazione **CommerceRuntime.Ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** nella cartella **RetailSdk\\Assets**, aggiungere le seguenti righe alla sezione **composition**.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
    ```

1. Attivare l'estensione POS **TaxRegistrationId.IT**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
            }
        ]
    }
    ```

1. Eseguire **msbuild** per l'intero Retail SDK per creare i pacchetti distribuibili.
1. Applicare i pacchetti via Microsoft Dynamics Lifecycle Services (LCS) o manualmente. Per ulteriori informazioni, vedere [Confezione di Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
