---
title: Risoluzione dei problemi durante la sincronizzazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410083"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Risoluzione dei problemi durante la sincronizzazione iniziale

[!include [banner](../../includes/banner.md)]

In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations

Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**. Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale. Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.

![Scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:

*Il server remoto ha restituito un errore: (400) Richiesta non valida. Si è verificato un errore nell'esportazione AX*

Di seguito è riportato un esempio del messaggio di errore completo.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Se questo errore si verifica in modo coerente e non è possibile completare la sincronizzazione iniziale, attenersi alla seguente procedura per risolvere il problema.

1. Accedere alla macchina virtuale (VM) per l'app Finance and Operations.
2. Aprire la console di gestione Microsoft.
3. Nel riquadro **Servizi**, assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione. Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.

## <a name="initial-synchronization-error-403-forbidden"></a>Errore di sincronizzazione iniziale: 403 Accesso negato

È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:

*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*

Per risolvere il problema, procedere come segue.

1. Accedere all'app Finance and Operations.
2. Nella pagina **Applicazioni Azure Active Directory**, eliminare il client **DtAppID**, quindi aggiungerlo di nuovo.

![Elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Errori di riferimento automatico o di riferimento circolare durante la sincronizzazione iniziale

È possibile ricevere un messaggio di errore se uno dei mapping include riferimenti automatici o circulari. Gli errori rientrano in queste categorie:

- [Mapping dell'entità Fornitori V2 all'entità msdyn_vendors](#error-vendor-map)
- [Mapping dell'entità Clienti V3 all'entità Account](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Risolvere un errore nel mapping dell'entità Fornitori V2 all'entità msdyn_vendors

È possibile che si verifichino i seguenti errori di sincronizzazione iniziale nel mapping dell'entità **Fornitori V2** all'entità **msdyn_vendors** se le entità hanno record esistenti con valori nei campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Questo perché **InvoiceVendorAccountNumber** è un campo di riferimento automatico e **PrimaryContactPersonId** è un riferimento circolare nel mapping del fornitore.

*Impossibile risolvere il guid per il campo: <field>. La ricerca non è stata trovata: <value>. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

Qui di seguito sono riportati alcuni esempi:

- *Impossibile risolvere il guid per il campo: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Impossibile risolvere il guid per il campo: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. La ricerca non è stata trovata: V24-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*

Se si hanno record con valori in questi campi nell'entità fornitore, seguire i passaggi nella sezione seguente per completare correttamente la sincronizzazione iniziale.

1. Nell'app Finance and Operations, eliminare i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** dal mapping e salvare le modifiche.

    1. Passare alla pagina del mapping in doppia scrittura per **Fornitori V2 (msdyn_vendors)** e selezionare la scheda **Mapping entità**. Nel filtro a sinistra, selezionare **App Finance and Operations.Fornitori V2**. Nel filtro di destra, selezionare **Vendite.Fornitore**.

    2. Cercare **primarycontactperson** per trovare il campo sorgente **PrimaryContactPersonId**.
    
    3. Fare clic sul pulsante **Azioni**, quindi selezionare **Elimina**.
    
        ![Riferimento automatico o circolare 3](media/vend_selfref3.png)
    
    4. Ripetere l'operazione per eliminare il campo **InvoiceVendorAccountNumber**.
    
        ![Riferimento automatico o circolare 4](media/vend-selfref4.png)
    
    5. Salvare le modifiche al mapping.

2. Disabilitare il rilevamento delle modifiche per l'entità **Fornitori V2**.

    1. Accedere a **Gestione dati \> Entità dati**.
    
    2. Selezionare l'entità **Fornitori V2**.
    
    3. Fare clic su **Opzioni** nella barra dei menu, quindi selezionare **Rilevamento modifiche**.
    
        ![Riferimento automatico o circolare 5](media/selfref_options.png)
    
    4. Fare clic su **Disabilita rilevamento modifiche**.
    
        ![Riferimento automatico o circolare 6](media/selfref_tracking.png)

3. Eseguire la sincronizzazione iniziale del mapping **Fornitori V2 (msdyn_vendors)**. La sincronizzazione iniziale deve essere eseguita correttamente senza errori.

4. Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**. È necessario sincronizzare questo mapping se si desidera sincronizzare il campo di contatto primario nell'entità fornitori poiché anche i record di contatti devono essere sincronizzati inizialmente.

5. Aggiungere di nuovo i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** al mapping **Fornitori V2 (msdyn_vendors)** e salvare il mapping.

6. Eseguire di nuovo la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn_vendors)**. Tutti i record verranno sincronizzati poiché il rilevamento delle modifiche è disabilitato.

7. Abilitare il rilevamento delle modifiche per l'entità **Fornitori V2**.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Risolvere un errore nel mapping dell'entità Clienti V3 all'entità Account

È possibile che si verifichino i seguenti errori di sincronizzazione iniziali nel mapping di **Clienti V3** a **Account** se le entità hanno record esistenti con valori nei campi **ContactPersonID** e **InvoiceAccount**. Questo perché **InvoiceAccount** è un campo di riferimento automatico e **ContactPersonID** è un riferimento circolare nel mapping del fornitore.

*Impossibile risolvere il guid per il campo: <field>. La ricerca non è stata trovata: <value>. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

- *Impossibile risolvere il guid per il campo: primarycontactid.msdyn_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Impossibile risolvere il guid per il campo: msdyn_billingaccount.accountnumber. La ricerca non è stata trovata: 1206-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Se si hanno record con valori in questi campi nell'entità cliente, seguire i passaggi nella sezione seguente per completare correttamente la sincronizzazione iniziale. È possibile utilizzare questo approccio per tutte le entità predefinite come Account e Contatti.

1. Nell'app Finance and Operations, eliminare i campi **ContactPersonID** e **InvoiceAccount** dal mapping **Clienti V3 (account)** e salvare il mapping.

    1. Passare alla pagina del mapping in doppia scrittura per **Clienti V3 (account)** e selezionare la scheda **Mapping entità**. Nel filtro a sinistra, selezionare **App Finance and Operations.Clienti V3**. Nel filtro a destra, selezionare **Common Data Service.Account**.

    2. Cercare **contactperson** per trovare il campo sorgente **ContactPersonID**.
    
    3. Fare clic sul pulsante **Azioni**, quindi selezionare **Elimina**.
    
        ![Riferimento automatico o circolare 3](media/cust_selfref3.png)
    
    4. Ripetere l'operazione per eliminare il campo **InvoiceAccount**.
    
        ![Riferimento automatico o circolare](media/cust_selfref4.png)
    
    5. Salvare le modifiche al mapping.

2. Disabilitare il rilevamento delle modifiche per l'entità **Clienti V3**.

    1. Accedere a **Gestione dati \> Entità dati**.
    
    2. Selezionare l'entità **Clienti V3**.
    
    3. Fare clic su **Opzioni** nella barra dei menu, quindi selezionare **Rilevamento modifiche**.
    
        ![Riferimento automatico o circolare 5](media/selfref_options.png)
    
    4. Fare clic su **Disabilita rilevamento modifiche**.
    
        ![Riferimento automatico o circolare 6](media/selfref_tracking.png)

3. Eseguire la sincronizzazione iniziale per il mapping **Clienti V3 (account)**. La sincronizzazione iniziale deve essere eseguita correttamente senza errori.

4. Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**. Ci sono 2 mappe con lo stesso nome. Selezionare quella con la descrizione **Modello in doppia scrittura per la sincronizzazione tra Contatti fornitore FO.CDS V2 e CDS.Contatti. Necessita un nuovo pacchetto \[Dynamics365SupplyChainExtended\].** nella scheda **Dettagli** della mappa.

5. Aggiungere di nuovo i campi **ContactPersonID** e **InvoiceAccount** al mapping **Clienti V3 (account)** e salvare il mapping. Adesso i campi **InvoiceAccount** e **ContactPersonId** fanno di nuovo parte della modalità di sincronizzazione in tempo reale. Nel passaggio successivo, completare la sincronizzazione iniziale per questi campi.

6. Eseguire di nuovo la sincronizzazione iniziale per il mapping **Clienti V3 (account)**. Poiché il rilevamento delle modifiche è disabilitato, l'esecuzione della sincronizzazione sincronizzerà i dati per **InvoiceAccount** e **ContactPersonId** dall'app Finance and Operations a Common Data Service.

7. Per sincronizzare i dati per **InvoiceAccount** e **ContactPersonId** da Common Data Service a Finance and Operations, si utilizza un progetto di integrazione dei dati.

    1. In Power Apps, creare un progetto di integrazione dei dati tra le entità **Vendite.Account** e **App Finance and Operations.Clienti V3**. La direzione dei dati deve essere da Common Data Service all'app Finance and Operations.  Poiché **InvoiceAccount** è un nuovo attributo in doppia scrittura, è possibile che si voglia ignorare la sincronizzazione iniziale per questo attributo. Per ulteriori informazioni, vedere [Integrare dati in Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        L'immagine seguente mostra un progetto che aggiorna **CustomerAccount** e **ContactPersonId**.

        ![Riferimento automatico o circolare](media/cust_selfref6.png)

    2. Aggiungere i criteri dell'azienda nel filtro sul lato Common Data Service, poiché solo i record che soddisfano i criteri di filtro verranno aggiornati nell'app Finance and Operations. Per aggiungere un filtro, fare clic sull'icona filtro. Nella finestra di dialogo **Modifica query**, è possibile aggiungere una query filtro come **_msdyn_company_value eq '\<guid\>'**. Se l'icona filtro non è presente, creare un ticket di supporto per chiedere al team di integrazione dei dati di abilitare la funzionalità sul tenant. Se non si immette una query filtro per **_msdyn_company_value**, tutti i record vengono sincronizzati.

        ![Riferimento automatico o circolare](media/cust_selfref7.png)

        La sincronizzazione iniziale dei record risulta completata.

8. Abilitare il rilevamento delle modifiche per l'entità **Clienti V3** nell'app Finance and Operations.

