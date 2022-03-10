---
title: Risoluzione dei problemi durante la sincronizzazione iniziale
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 030e565ffff561f6c1efbdd0de9928f70c7c46c0
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063060"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Risoluzione dei problemi durante la sincronizzazione iniziale

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra Finanza e operazioni e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi che possono verificarsi durante la sincronizzazione iniziale.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Controllare gli errori di sincronizzazione iniziale in un'app per finanza e operazioni

Dopo aver abilitato i modelli di mapping, lo stato delle mappe deve essere **In esecuzione**. Se lo stato è **Non in esecuzione**, si sono verificati errori durante la sincronizzazione iniziale. Per visualizzare gli errori, selezionare la scheda **Dettagli sulla sincronizzazione iniziale** nella pagina **Doppia scrittura**.

![Errore nella scheda dei dettagli della sincronizzazione iniziale.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Impossibile completare la sincronizzazione iniziale: 400 Richiesta non valida

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire il mapping e la sincronizzazione iniziale:

*(\[Richiesta non valida\]. Il server remoto ha restituito un errore: (400) Richiesta non valida). Si è verificato un errore nell'esportazione AX.*

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

1. Accedere alla macchina virtuale (VM) per l'app per finanza e operazioni.
2. Aprire la console di gestione Microsoft.
3. Nel riquadro **Servizi**, assicurarsi che il servizio framework di importazione esportazione dati di Microsoft Dynamics 365 sia in esecuzione. Riavviarlo se è stato arrestato, poiché la sincronizzazione iniziale lo richiede.

## <a name="initial-synchronization-error-403-forbidden"></a>Errore di sincronizzazione iniziale: 403 Accesso negato

È possibile che venga visualizzato il seguente messaggio di errore durante la sincronizzazione iniziale:

*(\[Accesso negato\]. Il server remoto ha restituito un errore: (403) Accesso negato). Si è verificato un errore nell'esportazione AX*

Per risolvere il problema, procedere come segue.

1. Accedere all'app per finanza e operazioni.
2. Nella pagina **Applicazioni Azure Active Directory**, eliminare il client **DtAppID**, quindi aggiungerlo di nuovo.

![Client DtAppID nell'elenco di applicazioni Azure AD.](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Errori di riferimento automatico o di riferimento circolare durante la sincronizzazione iniziale

È possibile ricevere un messaggio di errore se uno dei mapping include riferimenti automatici o circulari. Gli errori rientrano in queste categorie:

- [Errori nel mapping della tabella Fornitori V2 per msdyn_vendors](#error-vendor-map)
- [Errori nel mapping della tabella Clienti V3 per Account](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Risolvere gli errori nel mapping della tabella Fornitori V2 per msdyn_vendors

È possibile che si verifichino errori di sincronizzazione iniziale per il mapping di **Fornitori V2** all'entità **msdyn\_vendors** se le tabelle hanno righe esistenti con valori nelle colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Questi errori si verificano perché **InvoiceVendorAccountNumber** è una colonna di riferimento automatico e **PrimaryContactPersonId** è un riferimento circolare nel mapping del fornitore.

I messaggi di errore che si ricevono avranno il seguente formato.

*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Di seguito sono riportati alcuni esempi.

- *Impossibile risolvere il guid per il campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Impossibile risolvere il guid per il campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La ricerca non è stata trovata: V24-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Se le righe nella tabella fornitore hanno valori nelle colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**, seguire questi passaggi per completare la sincronizzazione iniziale.

1. Nell'app per finanza e operazioni, eliminare le colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** dal mapping e salvare il mapping.

    1. Nella pagina del mapping in doppia scrittura per **Fornitori V2 (msdyn\_vendors)**, nella scheda **Mapping della tabella**, nel filtro a sinistra, seleziona **Finanza e operazioni apps.Vendors V2**. Nel filtro di destra, selezionare **Vendite.Fornitore**.
    2. Cercare **primarycontactperson** per trovare la colonna di origine **PrimaryContactPersonId**.
    3. Selezionare **Azioni**, quindi selezionare **Elimina**.

        ![Eliminazione della colonna PrimaryContactPersonId.](media/vend_selfref3.png)

    4. Ripetere questi passaggi per eliminare la colonna **InvoiceVendorAccountNumber**.

        ![Eliminazione della colonna InvoiceVendorAccountNumber.](media/vend-selfref4.png)

    5. Salvare le modifiche nel mapping.

2. Disattivare il rilevamento delle modifiche per la tabella **Fornitori V2**.

    1. Nell'area di lavoro **Gestione dati** selezionare la scheda **Tabelle dati**.
    2. Selezionare la tabella **Fornitori V2**.
    3. Nel riquadro azioni selezionare **Opzioni**, quindi selezionare **Rilevamento modifiche**.

        ![Selezione dell'opzione Rilevamento modifiche.](media/selfref_options.png)

    4. Selezionare **Disabilita rilevamento modifiche**.

        ![Selezione di Disabilita rilevamento modifiche.](media/selfref_tracking.png)

3. Eseguire la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**. La sincronizzazione iniziale deve essere eseguita correttamente senza errori.
4. Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**. È necessario sincronizzare questo mapping se si desidera sincronizzare la colonna di contatto primario nella tabella fornitori perché la sincronizzazione deve essere eseguita anche per le righe di contatti.
5. Aggiungere di nuovo le colonne **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** al mapping **Fornitori V2 (msdyn\_vendors)** e salvare il mapping.
6. Eseguire di nuovo la sincronizzazione iniziale per il mapping **Fornitori V2 (msdyn\_vendors)**. Tutte le righe verranno sincronizzate perché il rilevamento delle modifiche è disabilitato.
7. Attivare di nuovo il rilevamento delle modifiche per la tabella **Fornitori V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Risolvere gli errori nel mapping della tabella Clienti V3 per Account

È possibile che si verifichino errori di sincronizzazione iniziale per il mapping dell'entità **Clienti V3** all'entità **Account** se le tabelle hanno righe esistenti con valori nelle colonne **ContactPersonID** e **InvoiceAccount**. Questi errori si verificano perché **InvoiceAccount** è una colonna di riferimento automatico e **ContactPersonID** è un riferimento circolare nel mapping del fornitore.

I messaggi di errore che si ricevono avranno il seguente formato.

*Impossibile risolvere il guid per il campo: \<field\>. La ricerca non è stata trovata: \<value\>. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Di seguito sono riportati alcuni esempi.

- *Impossibile risolvere il guid per il campo: primarycontactid.msdyn\_contactpersonid. La ricerca non è stata trovata: 000056. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Impossibile risolvere il guid per il campo: msdyn\_billingaccount.accountnumber. La ricerca non è stata trovata: 1206-1. Provare questi URL per verificare l'esistenza dei dati di riferimento: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Se le righe nella tabella cliente hanno valori nelle colonne **ContactPersonID** e **InvoiceAccount**, seguire questi passaggi per completare la sincronizzazione iniziale. È possibile utilizzare questo approccio per tutte le tabelle predefinite come **Account** e **Contatti**.

1. Nell'app per finanza e operazioni, eliminare le colonne **ContactPersonID** e **InvoiceAccount** dal mapping **Clienti V3 (account)** e quindi salvare il mapping.

    1. Nella pagina del mapping in doppia scrittura per **Clienti V3 (account)**, nella scheda **Mapping della tabella**, nel filtro a sinistra, selezionare **Finanza e operazioni app.Customer V3**. Nel filtro a destra, selezionare **Dataverse.Account**.
    2. Cercare **contactperson** per trovare la colonna di origine **ContactPersonID**.
    3. Selezionare **Azioni**, quindi selezionare **Elimina**.

        ![Eliminazione della colonna ContactPersonID.](media/cust_selfref3.png)

    4. Ripetere questi passaggi per eliminare la colonna **InvoiceAccount**.

        ![Eliminazione della colonna InvoiceAccount.](media/cust_selfref4.png)

    5. Salvare le modifiche nel mapping.

2. Disattivare il rilevamento delle modifiche per la tabella **Clienti V3**.

    1. Nell'area di lavoro **Gestione dati** selezionare la scheda **Tabelle dati**.
    2. Selezionare la tabella **Cliente V3**.
    3. Nel riquadro azioni selezionare **Opzioni**, quindi selezionare **Rilevamento modifiche**.

        ![Selezione dell'opzione Rilevamento modifiche.](media/selfref_options.png)

    4. Selezionare **Disabilita rilevamento modifiche**.

        ![Selezione di Disabilita rilevamento modifiche.](media/selfref_tracking.png)

3. Eseguire la sincronizzazione iniziale per il mapping **Clienti V3 (account)**. La sincronizzazione iniziale deve essere eseguita correttamente senza errori.
4. Eseguire la sincronizzazione iniziale per il mapping **Contatti CDS V2 (contatti)**.

    > [!NOTE]
    > Sono presenti due mappe con lo stesso nome. Assicurarsi di selezionare la mappa con la descrizione **Modello in doppia scrittura per la sincronizzazione tra Contatti fornitore FO.CDS V2 e CDS.Contatti. Necessita un nuovo pacchetto \[Dynamics365SupplyChainExtended\] nella scheda** **Dettagli**.

5. Aggiungere di nuovo le colonne **ContactPersonID** e **InvoiceAccount** al mapping **Clienti V3 (account)** e quindi salvare il mapping. Le colonne **InvoiceAccount** e **ContactPersonId** fanno di nuovo parte della modalità di sincronizzazione in tempo reale. Nel passaggio successivo, eseguire la sincronizzazione iniziale per queste colonne.
6. Eseguire di nuovo la sincronizzazione iniziale per il mapping **Clienti V3 (account)**. Poiché il rilevamento delle modifiche è disattivato, i dati per **InvoiceAccount** e **ContactPersonId** vengono sincronizzati dall'app per finanza e operazioni a Dataverse.
7. Per sincronizzare i dati per **InvoiceAccount** e **ContactPersonId** da Dataverse all'app per finanza e operazioni, è necessario utilizzare un progetto di integrazione dei dati.

    1. In Power Apps, creare un progetto di integrazione dei dati tra le tabelle **Sales.Account** e **Finanza e operazioni apps.Customers V3**. La direzione dei dati deve essere da Dataverse all'app per finanza e operazioni. Poiché **InvoiceAccount** è un nuovo attributo in doppia scrittura, è possibile che si voglia ignorare la sincronizzazione iniziale. Per ulteriori informazioni, vedere [Integrare dati in Dataverse](/power-platform/admin/data-integrator).

        La figura seguente mostra un progetto che aggiorna **CustomerAccount** e **ContactPersonId**.

        ![Progetto di integrazione dei dati per aggiornare CustomerAccount e ContactPersonId.](media/cust_selfref6.png)

    2. Aggiungere i criteri dell'azienda nel filtro sul lato Dataverse in modo che solo le righe che soddisfano i criteri di filtro verranno aggiornati nell'app per finanza e operazioni. Per aggiungere un filtro, selezionare il pulsante del filtro. Nella finestra di dialogo **Modifica query**, è possibile aggiungere una query filtro come **\_msdyn\_company\_value eq '\<guid\>'**.

        > [NOTA] Se il pulsante del filtro non è presente, creare un ticket di supporto per chiedere al team di integrazione dei dati di abilitare la funzionalità sul tenant.

        Se non si immette una query filtro per **\_msdyn\_company\_value**, tutte le righe vengono sincronizzate.

        ![Aggiunta di una query filtro.](media/cust_selfref7.png)

    La sincronizzazione iniziale delle righe è ora completata.

8. Abilitare di nuovo il rilevamento delle modifiche nell'app per finanza e operazioni per la tabella **Clienti V3**.

## <a name="initial-sync-failures-on-maps-with-more-than-10-lookup-fields"></a>Errori di sincronizzazione iniziale su mappe con più di 10 campi di ricerca

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire una sincronizzazione iniziale sui mapping **Clienti V3 - Conti**, **Ordini cliente** o qualsiasi mappa con più di 10 campi di ricerca:

*CRMExport: esecuzione pacchetto completa. Descrizione errore 5 tentativi di ottenere dati da https://xxxxx//datasets/yyyyy/tables/accounts/items?$select=accountnumber, address2_city, address2_country, ... (msdyn_company/cdm_companyid eq 'id')&$orderby=accountnumber asc non riuscito.*

A causa della limitazione della ricerca sulla query, la sincronizzazione iniziale non riesce quando il mapping di entità contiene più di 10 ricerche. Per ulteriori informazioni, vedi [Recuperare i record della tabella correlati con una query](/powerapps/developer/common-data-service/webapi/retrieve-related-entities-query).

Per risolvere questo problema, procedere come segue:

1. Rimuovi i campi di ricerca facoltativi dalla mappa di entità a doppia scrittura in modo che il numero di ricerche sia 10 o inferiore.
2. Salva la mappa ed esegui la sincronizzazione iniziale.
3. Quando la sincronizzazione iniziale per il primo passaggio ha esito positivo, aggiungi i campi di ricerca rimanenti e rimuovi i campi di ricerca sincronizzati nel primo passaggio. Assicurati che il numero di campi di ricerca sia 10 o inferiore. Salva la mappa ed esegui la sincronizzazione iniziale.
4. Ripeti questi passaggi finché tutti i campi di ricerca non sono sincronizzati.
5. Aggiungi tutti i campi di ricerca alla mappa, salva la mappa ed esegui la mappa con **Salta sincronizzazione iniziale**.

Questo processo abilita la mappa per la modalità di sincronizzazione in tempo reale.

## <a name="known-issue-during-initial-sync-of-party-postal-addresses-and-party-electronic-addresses"></a>Problema noto durante la sincronizzazione iniziale degli indirizzi postali e degli indirizzi elettronici della parte

È possibile che venga visualizzato il seguente messaggio di errore quando si tenta di eseguire la sincronizzazione iniziale degli indirizzi postali e degli indirizzi elettronici della parte:

*Impossibile trovare il numero della parte in Dataverse.*

C'è un intervallo impostato su **DirPartyCDSEntity** nelle app per finanza e operazioni che filtra le parti di tipo **Persona** e **Organizzazione**. Di conseguenza, una sincronizzazione iniziale del mapping **Parti CDS – msdyn_parties** non sincronizzerà parti di altri tipi, incluse **Persona giuridica** e **Unità operativa**. Quando la sincronizzazione iniziale viene eseguita per **Indirizzi postali parte CDS (msdyn_partypostaladdresses)** o **Contatti parte V3 (msdyn_partyelectronicaddresses)** potresti ricevere l'errore.

Stiamo lavorando a una soluzione per rimuovere l'intervallo del tipo di parte sull'entità Finanza e operazioni in modo che le parti di tutti i tipi possano essere sincronizzate con Dataverse correttamente.

## <a name="are-there-any-performance-issues-while-running-initial-sync-for-customers-or-contacts-data"></a>Ci sono problemi di prestazioni durante l'esecuzione della sincronizzazione iniziale per i dati dei clienti o dei contatti?

Se hai eseguito la sincronizzazione iniziale per i dati **Cliente**, hai le mappe **Cliente** in esecuzione e quindi esegui la sincronizzazione iniziale per i dati **Contatti**, potrebbero verificarsi problemi di prestazioni durante gli inserimenti e gli aggiornamenti delle tabelle **LogisticsPostalAddress** e **LogisticsPostalAddress** per gli indirizzi **Contatto**. Le stesse tabelle di indirizzi postali e indirizzi elettronici globali vengono monitorate per **CustCustomerV3Entity** e **VendVendorV2Entity** e la doppia scrittura cerca di creare più query per scrivere dati sull'altro lato. Se hai già eseguito la sincronizzazione iniziale per **Cliente**, interrompi la mappa corrispondente durante l'esecuzione della sincronizzazione iniziale per i dati **Contatti**. Fai la stessa cosa per i dati **Fornitore**. Al termine della sincronizzazione iniziale, puoi eseguire tutte le mappe saltando la sincronizzazione iniziale.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
