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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: a7ba4fa4771324b4bcb8464649bd8ce8f32024c0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683564"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Risoluzione dei problemi durante la sincronizzazione iniziale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificare la presenza di errori di sincronizzazione iniziale in un'app Finance and Operations

Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**. Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale. Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.

![Errore nella scheda dei dettagli della sincronizzazione iniziale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:

*(\[Richiesta non valida\]. Il server remoto ha restituito un errore: (400) Richiesta non valida). Si è verificato un errore nell'esportazione AX*

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

![Client DtAppID nell'elenco di applicazioni Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Errori di riferimento automatico o di riferimento circolare durante la sincronizzazione iniziale

È possibile ricevere un messaggio di errore se uno dei mapping include riferimenti automatici o circulari. Gli errori rientrano in queste categorie:

- [Errori nel mapping della tabella Fornitori V2 per msdyn_vendors](#error-vendor-map)
- [Errori nel mapping della tabella Clienti V3 per Account](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Risolvere gli errori nel mapping della tabella Fornitori V2 per msdyn_vendors

È possibile che si verifichino errori di sincronizzazione iniziale per il mapping di **Fornitori V2** all'entità **msdyn\_vendors** se le tabelle hanno righe esistenti con valori nei campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Questi errori si verificano perché **InvoiceVendorAccountNumber** è un campo di riferimento automatico e **PrimaryContactPersonId** è un riferimento circolare nel mapping del fornitore.

I messaggi di errore che si ricevono avranno il seguente formato.

*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Di seguito sono riportati alcuni esempi.

- *Impossibile risolvere il guid per il campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Impossibile risolvere il guid per il campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La ricerca non è stata trovata: V24-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Se le righe nell'entità fornitore hanno valori nei campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**, seguire questi passaggi per completare la sincronizzazione iniziale.

1. Nell'app Finance and Operations, eliminare i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** dal mapping e salvare il mapping.

    1. Nella pagina del mapping in doppia scrittura per **Fornitori V2 (msdyn\_vendors)**, nella scheda **Mapping della tabella**, nel filtro a sinistra, selezionare **Finance and Operationsapps.Vendors V2**. Nel filtro di destra, selezionare **Vendite.Fornitore**.
    2. Cercare **primarycontactperson** per trovare il campo di origine **PrimaryContactPersonId**.
    3. Selezionare **Azioni**, quindi selezionare **Elimina**.

        ![Eliminazione del campo PrimaryContactPersonId](media/vend_selfref3.png)

    4. Ripetere questi passaggi per eliminare il campo **InvoiceVendorAccountNumber**.

        ![Eliminazione del campo InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. Salvare le modifiche nel mapping.

2. Disattivare il rilevamento delle modifiche per l'entità **Fornitori V2**.

    1. Nell'area di lavoro **Gestione dati** selezionare la scheda **Tabelle dati**.
    2. Selezionare l'entità **Fornitori V2**.
    3. Nel riquadro azioni selezionare **Opzioni**, quindi selezionare **Rilevamento modifiche**.

        ![Selezione dell'opzione Rilevamento modifiche](media/selfref_options.png)

    4. Selezionare **Disabilita rilevamento modifiche**.

        ![Selezione di Disabilita rilevamento modifiche](media/selfref_tracking.png)

3. Eseguire la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**. La sincronizzazione iniziale deve essere eseguita correttamente senza errori.
4. Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**. È necessario sincronizzare questo mapping se si desidera sincronizzare il campo di contatto primario nell'entità fornitori perché la sincronizzazione deve essere eseguita anche per le righe di contatti.
5. Aggiungere di nuovo i campi **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** al mapping **Fornitori V2 (msdyn\_vendors)** e salvare il mapping.
6. Eseguire di nuovo la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**. Tutte le righe verranno sincronizzate perché il rilevamento delle modifiche è disabilitato.
7. Attivare di nuovo il rilevamento delle modifiche per l'entità **Fornitori V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Risolvere gli errori nel mapping della tabella Clienti V3 per Account

È possibile che si verifichino errori di sincronizzazione iniziale per il mapping dell'entità **Clienti V3** all'entità **Account** se le tabelle hanno righe esistenti con valori nei campi **ContactPersonID** e **InvoiceAccount**. Questi errori si verificano perché **InvoiceAccount** è un campo di riferimento automatico e **ContactPersonID** è un riferimento circolare nel mapping del fornitore.

I messaggi di errore che si ricevono avranno il seguente formato.

*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Di seguito sono riportati alcuni esempi.

- *Impossibile risolvere il guid per il campo: primarycontactid.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Impossibile risolvere il guid per il campo: msdyn\_billingaccount.accountnumber. La ricerca non è stata trovata: 1206-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Se le righe nell'entità cliente hanno valori nei campi **ContactPersonID** e **InvoiceAccount**, seguire questi passaggi per completare la sincronizzazione iniziale. È possibile utilizzare questo approccio per tutte le tabelle predefinite come **Account** e **Contatti**.

1. Nell'app Finance and Operations, eliminare i campi **ContactPersonID** e **InvoiceAccount** dal mapping **Clienti V3 (account)** e quindi salvare il mapping.

    1. Nella pagina del mapping in doppia scrittura per **Clienti V3 (account)**, nella scheda **Mapping della tabella**, nel filtro a sinistra, selezionare **Finance and Operations app.Customer V3**. Nel filtro a destra, selezionare **Dataverse.Account**.
    2. Cercare **contactperson** per trovare il campo di origine **ContactPersonID**.
    3. Selezionare **Azioni**, quindi selezionare **Elimina**.

        ![Eliminazione del campo ContactPersonID](media/cust_selfref3.png)

    4. Ripetere questi passaggi per eliminare il campo **InvoiceAccount**.

        ![Eliminazione del campo InvoiceAccount](media/cust_selfref4.png)

    5. Salvare le modifiche nel mapping.

2. Disattivare il rilevamento delle modifiche per l'entità **Clienti V3**.

    1. Nell'area di lavoro **Gestione dati** selezionare la scheda **Tabelle dati**.
    2. Selezionare l'entità **Clienti V3**.
    3. Nel riquadro azioni selezionare **Opzioni**, quindi selezionare **Rilevamento modifiche**.

        ![Selezione dell'opzione Rilevamento modifiche](media/selfref_options.png)

    4. Selezionare **Disabilita rilevamento modifiche**.

        ![Selezione di Disabilita rilevamento modifiche](media/selfref_tracking.png)

3. Eseguire la sincronizzazione iniziale per il mapping **Clienti V3 (account)**. La sincronizzazione iniziale deve essere eseguita correttamente senza errori.
4. Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.

    > [!NOTE]
    > Sono presenti due mappe con lo stesso nome. Assicurarsi di selezionare la mappa con la descrizione **Modello in doppia scrittura per la sincronizzazione tra Contatti fornitore FO.CDS V2 e CDS.Contatti. Necessita un nuovo pacchetto \[Dynamics365SupplyChainExtended\] nella scheda** **Dettagli**.

5. Aggiungere di nuovo i campi **ContactPersonID** e **InvoiceAccount** al mapping **Clienti V3 (account)** e quindi salvare il mapping. I campi **InvoiceAccount** e **ContactPersonId** fanno di nuovo parte della modalità di sincronizzazione in tempo reale. Nel passaggio successivo, eseguire la sincronizzazione iniziale per questi campi.
6. Eseguire di nuovo la sincronizzazione iniziale per il mapping **Clienti V3 (account)**. Poiché il rilevamento delle modifiche è disattivato, i dati per **InvoiceAccount** e **ContactPersonId** vengono sincronizzati dall'app Finance and Operations a Dataverse.
7. Per sincronizzare i dati per **InvoiceAccount** e **ContactPersonId** da Dataverse all'app Finance and Operations, è necessario utilizzare un progetto di integrazione dei dati.

    1. In Power Apps, creare un progetto di integrazione dei dati tra le tabelle **Sales.Account** e **Finance and Operations apps.Customers V3**. La direzione dei dati deve essere da Dataverse all'app Finance and Operations. Poiché **InvoiceAccount** è un nuovo attributo in doppia scrittura, è possibile che si voglia ignorare la sincronizzazione iniziale. Per ulteriori informazioni, vedere [Integrare dati in Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).

        La figura seguente mostra un progetto che aggiorna **CustomerAccount** e **ContactPersonId**.

        ![Progetto di integrazione dei dati per aggiornare CustomerAccount e ContactPersonId](media/cust_selfref6.png)

    2. Aggiungere i criteri dell'azienda nel filtro sul lato Dataverse in modo che solo le righe che soddisfano i criteri di filtro verranno aggiornati nell'app Finance and Operations. Per aggiungere un filtro, selezionare il pulsante del filtro. Nella finestra di dialogo **Modifica query**, è possibile aggiungere una query filtro come **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [NOTA] Se il pulsante del filtro non è presente, creare un ticket di supporto per chiedere al team di integrazione dei dati di abilitare la funzionalità sul tenant.

        Se non si immette una query filtro per **\_msdyn\_company\_value**, tutte le righe vengono sincronizzate.

        ![Aggiunta di una query filtro](media/cust_selfref7.png)

    La sincronizzazione iniziale delle righe è ora completata.

8. Abilitare di nuovo il rilevamento delle modifiche nell'app Finance and Operations per l'entità **Clienti V3**.
