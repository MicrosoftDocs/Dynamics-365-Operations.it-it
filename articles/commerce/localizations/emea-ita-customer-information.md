---
ms.openlocfilehash: 9a7276e940142620244d3044d75589c50e92a939
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279105"
---
# <a name="customer-information-management-for-italy"></a>Gestione delle informazioni cliente per l'Italia
---

title: Gestione delle informazioni cliente per l'Italia [!include [banner](../includes/banner.md)]
description: In questo articolo viene descritto come gestire le informazioni relative al cliente nel POS per l'Italia.

author: josaw1

ms.date: 09/21/2021
## <a name="introduction"></a>Introduzione
ms.topic: article

ms.prod: In questo articolo viene descritto come è possibile gestire le informazioni relative al cliente, ad esempio il codice lotteria del cliente, nel POS di Commerce per l'Italia.
ms.technology: 

audience: Application User È possibile specificare informazioni sul cliente, come il codice fiscale o il codice lotteria, quando si crea o si modifica un record di dati master del cliente nel POS. È inoltre possibile specificare il codice lotteria per una transazione di vendita copiandolo dal cliente della transazione o immettendolo manualmente. Il codice lotteria può quindi essere stampato sia sulle ricevute fiscali e su quelle normali ed essere utilizzato per la lotteria nazionale. I codici fiscali personali possono inoltre essere utilizzati per individuare un cliente in POS.
ms.reviewer: josaw

ms.search.region: Italy
> [!NOTE]
ms.author: josaw Non è possibile specificare un codice lotteria per un cliente nel POS quando l'opzione **Crea cliente in modalità asincrona** è abilitata nel profilo di funzionalità POS. Il supporto per la modalità di creazione del cliente asincrono potrebbe essere aggiunto in futuri aggiornamenti.
> ms.search.validFrom: 2019-10-08

ms.dyn365.ops.version: 10.0.7
## <a name="setup"></a>Impostazione
ms.search.industry: Retail

ms.search.form: RetailFunctionalityProfile, RetailParameters È necessario completare la seguente configurazione per utilizzare questa funzionalità:

---
- Impostare un tipo di registrazione per il codice lotteria.

- Aggiungere l'operazione **Aggiungi informazioni cliente** ai layout dello schermo.
### <a name="update-a-development-environment"></a>Aggiornare un ambiente di sviluppo
- Attivare la richiesta di informazioni del cliente.

- Impostare i formati di ricevuta.
Seguire questi passaggi per aggiornare un ambiente di sviluppo.
- Aggiungere i criteri di ricerca cliente.

- Configurare i componenti del canale.
#### <a name="crt-extension-components"></a>Componenti dell'estensione CRT


### <a name="set-up-a-registration-type-for-the-lottery-code"></a>Impostare un tipo di registrazione per il codice lotteria
1. Individuare il file di configurazione dell'estensione per Commerce Runtime (CRT):


Prima di poter specificare i codici lotteria nel POS, è necessario creare un tipo di registrazione appropriato per il codice lotteria e collegarlo alla categoria di registrazione **Codice lotteria**. Per ulteriori informazioni su come utilizzare i tipi di registrazione e gli ID registrazione, vedere [ID registrazione](../../finance/localizations/emea-registration-ids.md).
    - **Commerce Scale Unit:** individuare il file **CommerceRuntime.Ext.config** nella cartella **bin\\ext** nella posizione del sito Commerce Scale Unit di Microsoft Internet Information Services (IIS).

    - **CRT locale sul POS moderno:** Trovare il file **CommerceRuntime.MPOSOffline.Ext.config** nella posizione del broker client CRT locale.
> [!WARNING]

> Se un tipo di registrazione non viene creato o non è collegato alla categoria di registrazione **Codice lotteria**, viene generato un errore nel POS quando il codice lotteria viene immesso per un indirizzo cliente.
1. Registrare l'estensione CRT nel file di configurazione dell'estensione.


### <a name="add-the-add-customer-information-operation-to-screen-layouts"></a>Aggiungere l'operazione Aggiungi informazioni cliente ai layout dello schermo
    ``` xml

    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
L'operazione **Aggiungi informazioni cliente** può essere utilizzata per aggiungere informazioni sul cliente, come il codice lotteria, a una transazione di vendita. Queste informazioni possono essere copiate dal cliente specificato per la transazione oppure possono essere inserite manualmente.
    ```


Nella pagina **Griglie dei pulsanti**, selezionare la griglia dei pulsanti in cui dovrebbe apparire l'operazione e aprire la finestra Progettazione griglia dei pulsanti. Aggiungere un nuovo pulsante, quindi nel campo **Azione** selezionare **Aggiungi informazioni cliente**. Per ulteriori informazioni sull'utilizzo dei layout dello schermo e delle griglie dei pulsanti, vedere [Layout delle schermate per il POS](../pos-screen-layouts.md).
    > [!WARNING]

    > Do **not** edit the CommerceRuntime.config and CommerceRuntime.MPOSOffline.config files. These files aren't intended for any customizations.
### <a name="activate-the-inquiry-for-customer-information"></a>Attivare la richiesta di informazioni del cliente


#### <a name="modern-pos-extension-components"></a>Componenti dell'estensione POS moderno
Se le informazioni del cliente non sono specificate per una transazione di vendita, una richiesta per tali informazioni può essere attivata automaticamente dopo la finalizzazione della transazione. Questo approccio è un'alternativa all'operazione **Aggiungi informazioni cliente**.


Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.
Per attivare la richiesta di informazioni cliente, abilitare la funzionalità **(Italia) Gestione delle informazioni cliente in Retail POS** nell'area di lavoro **Gestione funzionalità** e impostare l'opzione **Abilita richiesta informazioni sul cliente nelle transazioni di vendita** su **Sì** nella sezione **Parametri fiscali** nella Scheda dettaglio **Funzioni** della pagina **Profili funzionalità POS**.


1. Aprire la soluzione in **RetailSdk\\POS\\ModernPOS.sln**.
### <a name="set-up-receipt-formats"></a>Impostare formati di ricevuta
1. In **POS.Extensions\\extensions.json**, attivare l'estensione.


È possibile configurare i formati di ricevuta in modo che il codice fiscale e il codice lotteria del cliente siano stampati sulle ricevute.
    ``` json

    {
> [!NOTE]
        "extensionPackages": [ La società predefinita dell'utente che crea l'impostazione della ricevuta deve essere la stessa persona giuridica in cui viene creata l'impostazione del testo della lingua. In alternativa, i testi nella stessa lingua devono essere creati sia nella società predefinita dell'utente sia nella persona giuridica del negozio per cui è stata creata l'impostazione.
> {

                "baseUrl": "Microsoft/TaxRegistrationId.IT"
Nella pagina **Testo lingua**, nella scheda **POS**, aggiungere i record seguenti per le etichette dei campi personalizzati per i formati di ricevuta. Tenere presente che i valori di **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. È possibile modificarli in base alle esigenze. Tuttavia, i valori **ID testo** utilizzati devono essere univoci e devono essere uguali o maggiori di 900001.
}

        ]
| ID lingua | ID testo | Testo                | } |-------------|---------|---------------------|
    ```
| en-US       | 900001  | Codice lotteria        |

| en-US       | 900002  | Codice fiscale        |
1. Compilare la soluzione.

1. Aprire POS moderno e verificare la funzionalità.
Nella pagina **Campi personalizzati**, aggiungere i record seguenti per i campi personalizzati per i formati di ricevuta. Si noti che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.


#### <a name="cloud-pos-extension-components"></a>Componenti dell'estensione POS cloud
| Nome                           | Tipo    | ID testo didascalia |

|--------------------------------|---------|-----------------| Seguire questi passaggi per rendere disponibile l'estensione TaxRegistrationId.IT.
| FISCALCUSTOMER\_LOTTERYCODE\_IT| Ricevuta | 900001          |

| CUSTOMER\_FISCALCODE\_IT       | Ricevuta | 900002          |
1. Aprire la soluzione in **RetailSdk\\POS\\CloudPOS.sln**.

1. In **POS.Extensions\\extensions.json**, attivare l'estensione.
In Progettazione formato ricevuta, aggiungere i campi personalizzati alla sezione appropriata della ricevuta per ogni formato di ricevuta necessario. Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedere [Modelli e stampa di ricevute](../receipt-templates-printing.md)


    ``` json
### Add a customer search criterion
    {

        "extensionPackages": [
You can add a customer search criterion so that customers can be searched for in POS by their fiscal codes.
            {

                "baseUrl": "Microsoft/TaxRegistrationId.IT"
On the **Commerce parameters** page, on the **POS search criteria** tab, add a new customer search criterion. In the **Customer search criteria** field, select **Tax registration number**. Select the **Display as shortcut** check box, but leave the **Can be refined** check box cleared. Then, on the **Distribution schedules** page, run the **1110** job.
            }

        ]
### Configure channel components
    }

    ```
Per rendere disponibile la funzionalità specifica dell'Italia, è necessario configurare le estensioni per i componenti del canale di commercio. Per ulteriori informazioni, vedi la sezione [Linee guida per la distribuzione](#deployment-guidelines) più avanti in questo articolo.


1. Compilare la soluzione.
## <a name="example-scenarios"></a>Scenari di esempio
1. Aprire POS cloud e verificare la funzionalità.


I seguenti scenari di esempio mostrano come utilizzare le informazioni sui clienti nel POS per l'Italia.
### <a name="update-a-production-environment"></a>Aggiornare un ambiente di produzione


### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a>Scenario 1: Effettuare una vendita a un cliente anonimo
Attenersi alla procedura seguente per creare pacchetti distribuibili contenenti componenti Commerce e per applicare i pacchetti a un ambiente di produzione.


1. Accedere a POS.
1. Nei file di configurazione **CommerceRuntime.Ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** nella cartella **RetailSdk\\Assets**, aggiungere le seguenti righe alla sezione **composition**.
1. Aggiunge articoli al carrello.

1. Selezionare **Aggiungi informazioni cliente** e quindi selezionare **Immetti manualmente**.
    ``` xml
1. Enter the customer's lottery code, and then select **OK**.
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly" />
1. Register payments for the transaction, and then finalize the transaction.
    ```
1. Verificare che la ricevuta stampata contenga il codice lotteria del cliente.


1. Attivare l'estensione POS **TaxRegistrationId.IT**.
### <a name="scenario-2-make-a-sale-to-a-new-named-customer"></a>Scenario 2: Effettuare una vendita a un nuovo cliente denominato


    ``` json
1. Accedere a POS.
    {
1. Aggiunge articoli al carrello.
        "extensionPackages": [
1. Selezionare **Aggiungi cliente** e quindi selezionare **Nuovo**.
            {
1. Specificare gli attributi del nuovo cliente. Nel campo **Codice fiscale**, immettere il codice fiscale del cliente.
                "baseUrl": "Microsoft/TaxRegistrationId.IT"
1. Selezionare **Crea una nuova rubrica**. Quindi specificare le informazioni di contatto del nuovo cliente e un indirizzo.
            }
1. Nel campo **Codice lotteria**, immettere il codice lotteria del cliente.
        ]
1. Salvare il record cliente e il record indirizzo cliente e aggiungere il cliente alla transazione.
    }
1. Registrare i pagamenti per la transazione e quindi completare la transazione.
    ```
1. Because the inquiry for customer information has been activated, but customer information hasn't been added to the transaction, the **Enter customer information** dialog box is opened. Select **Yes**, and then select **Copy from transaction customer**.

1. Verify the customer's lottery code, and then select **OK**.
1. Run **msbuild** for the whole Retail software development kit (SDK) to create deployable packages.
1. Verify that the printed receipt contains the customer's lottery code.
1. Apply the packages via Microsoft Dynamics Lifecycle Services (LCS) or manually. For more information, see [Retail SDK packaging](../dev-itpro/retail-sdk/retail-sdk-packaging.md).


> [!NOTE]

> If you must specify a different customer for the transaction, you must clear the customer information and then copy it again after the new customer is added.
[!INCLUDE[footer-include](../../includes/footer-banner.md)]

### Scenario 3: Change the customer information for a sale to a named customer

1. Sign in to POS.
1. Add items to the cart.
1. Select **Add customer**, and then select a customer account to add it to the transaction.
1. Select **Add customer information**, and then select **Copy from transaction customer**.
1. Verify the customer's lottery code, and then select **OK**.
1. Select **Add customer information**, and then select **Clear** to clear the customer information from the transaction.
1. Select **Add customer information**, and then select **Enter manually**.
1. Specify the customer's lottery code, and then select **OK**.
1. Register payments for the transaction, and then finalize the transaction.
1. Verify that the printed receipt contains the customer's lottery code.

## Deployment guidelines

This section provides deployment guidance for enabling customer information management in the localization of Commerce for Italy.

> [!NOTE]
> Some steps in these procedures vary, depending on the version of Commerce that you're using. For more information, see [What's new or changed in Dynamics 365 for Retail](../get-started/whats-new.md).
>
> If you want to enable the integration of POS with fiscal printers for Italy, and specifically if you want to print customer lottery codes on fiscal receipts, you must deploy the [fiscal printer integration sample for Italy](emea-ita-fpi-sample.md).

### Update customizations

Follow these steps to update customizations.

# [Retail 10.0.7 and later](#tab/retail-10-0-7)

If any of your customizations include request handlers for the `SaveCartRequest` or `CreateSalesOrderServiceRequest` requests:

1. Find the request handler for `SaveCartRequest`.
1. Find the line of code that runs the original request handler.
1. Add the following lines before calling the original request handler:

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly.Services;

    ...

    new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

1. Trovare il gestore delle richieste per `CreateSalesOrderServiceRequest`.
1. Individuare la riga di codice che esegue il gestore delle richieste originale.
1. Sostituirlo con il codice seguente:

    ```cs
    using Microsoft.Dynamics.Commerce.Runtime.TaxRegistrationIdItaly.Services;

    ...

    return new TaxRegistrationIdFiscalCustomerService().Execute(request);
    ```

# <a name="retail-10012-and-later"></a>[Retail 10.0.12 e versioni successive](#tab/retail-10-0-12)

Se le personalizzazioni includono riferimenti al servizio `TaxRegistrationIdFiscalCustomerService`, questi devono essere rimossi.

---
