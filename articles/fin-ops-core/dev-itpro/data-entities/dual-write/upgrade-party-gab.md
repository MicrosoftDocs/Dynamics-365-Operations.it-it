---
title: Eseguire l'aggiornamento al modello di parte e di rubrica globale
description: In questo argomento viene descritto come aggiornare i dati a doppia scrittura al modello di parte e rubrica globale.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 7434c2ed486fe0546a746afdd2c4c4aacdcc3d5c
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817290"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Eseguire l'aggiornamento al modello di parte e di rubrica globale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I [modelli di Microsoft Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) consentono di aggiornare i seguenti dati di tabella in doppia scrittura al modello di parte e rubrica globale; dati nelle tabelle **Account**, **Contatto** e **Fornitore** e indirizzi elettronici e postali.

Vengono forniti i tre modelli di Data Factory seguenti. Consentono di riconciliare i dati delle app Finance and Operations e delle app di interazione con i clienti.

- **[Modello di parte](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Aggiorna i dati allo schema Party-GAB in doppia scrittura/arm_template.json)** – Questo modello aiuta l'aggiornamento dei dati **Parte** e **Contatto** associati ai dati **Account**, **Contatto**, e **Fornitore**.
- **[Modello di indirizzo postale di parte](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Aggiorna i dati allo schema Party-GAB in doppia scrittura/Aggiorna all'indirizzo postale della parte - GAB/arm_template.json)** – Questo modello aiuta ad aggiornare gli indirizzi postali associati ai dati **Account**, **Contatto**, e **Fornitore**.
- **[Modello di indirizzo elettronico di parte](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Aggiorna i dati allo schema Party-GAB in doppia scrittura/Aggiorna all'indirizzo elettronico della parte - GAB/arm_template.json)** – Questo modello aiuta ad aggiornare gli indirizzi elettronici associati ai dati **Account**, **Contatto**, e **Fornitore**.

Alla fine del processo, vengono generati i seguenti file con valori separati da virgole (.csv).

| Nome file | Scopo |
|---|---|
| FONewParty.csv | Questo file consente di creare nuovi record **Parte** nell'app Finance and Operations. |
| ImportFONewPostalAddressLocation.csv | Questo file aiuta a creare nuovi record **Posizione indirizzo postale** nell'app Finance and Operations. |
| ImportFONewPartyPostalAddress.csv | Questo file aiuta a creare nuovi record **Indirizzo postale parte** nell'app Finance and Operations. |
| ImportFONewPostalAddress.csv | Questo file aiuta a creare nuovi record **Indirizzo postale** nell'app Finance and Operations. |
| ImportFONewElectronicAddress.csv | Questo file aiuta a creare nuovi record **Indirizzo elettronico** nell'app Finance and Operations. |

In questo argomento vengono fornite istruzioni per utilizzare i modelli Data Factory e aggiornare i dati. Se non disponi di personalizzazioni, puoi utilizzare i modelli così come sono. Tuttavia se hai personalizzazioni per i dati **Account**, **Contatto** e **Fornitore** devi modificare i modelli con le seguenti istruzioni.

> [!IMPORTANT]
> Ci sono istruzioni speciali per l'esecuzione dei modelli di indirizzo postale e indirizzo elettronico della parte. È necessario eseguire prima il modello parte, quindi il modello di indirizzo postale di parte e quindi il modello di indirizzo elettronico di parte.

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere soddisfatti prima di poter eseguire l'aggiornamento al modello di rubrica indirizzi globale e del gruppo:

+ Devi avere una [sottoscrizione di Azure](https://portal.azure.com/).
+ È necessario disporre dell'accesso ai [modelli](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Devi essere un cliente esistente che utilizza la doppia scrittura.

## <a name="prepare-for-the-upgrade"></a>Preparazione per l'aggiornamento

Un aggiornamento richiede la seguente preparazione:

+ **Sincronizzazione completa:** Sia l'ambiente Finance and operations che l'ambiente customer engagement sono in uno stato completamente sincronizzato per le tabelle **Account (Cliente)**, **Contatto**, e **Fornitore**.
+ **Chiavi di integrazione**: le tabelle **Account (cliente)**, **Contatto** e **Fornitore** nelle app di interazione con i clienti utilizzano le chiavi di integrazione predefinite. Se hai personalizzato le chiavi di integrazione, devi personalizzare il modello.
+ **Numero parte:** tutti i record **Account (cliente)**, **Contatto**, e **Fornitore** che verranno aggiornati hanno un numero parte. I record che non hanno un numero parte verranno ignorati. Se desideri aggiornare questi record, aggiungici un numero parte prima di iniziare il processo di aggiornamento.
+ **Interruzione del sistema**: durante il processo di aggiornamento, Finance and Operations e ambienti di interazione con i clienti devono essere offline.
+ **Snapshot**: prendi snapshot delle app Finance and Operations e delle app di interazione dei clienti. Puoi usare gli snapshot per ripristinare lo stato precedente, se necessario.

## <a name="deployment"></a>Distribuzione

1. Scarica i modelli da [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Accedere al [portale Azure](https://portal.azure.com/).
3. Crea un [gruppo di risorse](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Crea un [account di archiviazione](/azure/storage/common/storage-account-create?tabs=azure-portal) nel gruppo di risorse che hai creato.
5. Crea un [data factory](/azure/data-factory/quickstart-create-data-factory-portal) nel gruppo di risorse che hai creato.
6. Apri il data factory e seleziona il riquadro **Creare e monitorare**.
7. Nella scheda **Gestisci**, seleziona **Modello ARM**.
8. Seleziona **Importa modello ARM** per importare il modello **Parte**.
9. Importa il modello nel data factory. Immettere i seguenti valori per **Dettagli del progetto** e **Dettagli dell'istanza**.

    | Campo | Valore |
    |---|---|
    | Abbonamento | Sottoscrizione di Azure |
    | Gruppo di risorse | Fornisci la stessa risorsa in cui viene creato l'account di archiviazione. |
    | Regione | Area geografica |
    | Nome factory | Nome factory |
    | FO Linked Service_service Principal Key | Chiave dell'applicazione |
    | Azure Blob Storage_connection String | Stringa di connessione di Archiviazione BLOB di Azure |
    | Dynamics Crm Linked Service_password | La password per l'account utente specificato come nome utente. |
    | FO Linked Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO Linked Service_properties_type Properties_tenant | Informazioni sul tenant (nome di dominio o ID tenant) in cui risiede l'applicazione |
    | FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO Linked Service_properties_type Properties_service Principal Id | ID client dell'applicazione |
    | Dynamics Crm Linked Service_properties_type Properties_username | Il nome utente usato per la connessione a Dynamics 365 |

    Per ulteriori informazioni, vedere gli argomenti seguenti:

    - [Promuovere manualmente un modello di Resource Manager per ogni ambiente](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Proprietà del servizio collegato](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Copiare i dati usando Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Dopo la distribuzione, convalidare i set di dati, il flusso di dati e il servizio collegato del data factory.

    ![Set di dati, flusso di dati e servizio collegato.](media/data-factory-validate.png)

11. Vai a **Gestisci**. Sotto **Connessioni**, seleziona **Servizio collegato**. Seleziona **DynamicsCrmLinkedService**. Nella finestra di dialogo **Modifica servizio collegato (Dynamics CRM)**, inserisci i seguenti valori.

    | Campo | Valore |
    |---|---|
    | Name | DynamicsCrmLinkedService |
    | descrizione | I servizi collegati per connettersi con l'istanza CRM per recuperare i dati delle entità |
    | Connetti via runtime di integrazione | AutoResolvelntegrationRuntime |
    | Tipo di distribuzione | In linea |
    | Uri servizio | `https://<organization-name>.crm[x].dynamics.com` |
    | Tipo di autenticazione | Office365 |
    | Nome utente | |
    | Password o Azure Key Vault | Password |
    | Password | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Prepararsi a eseguire i modelli di Data Factory

Questa sezione descrive l'impostazione richiesta prima di eseguire i modelli Data Factory per l'indirizzo postale e l'indirizzo elettronico della parte.

### <a name="setup-to-run-the-party-postal-address-template"></a>Impostare per eseguire il modello di indirizzo postale della parte

1. Accedi alle app di coinvolgimento dei clienti e vai a **Impostazioni** \> **Impostazioni personalizzazione**. Poi, nella scheda **Generale** configura l'impostazione del fuso orario per l'account amministratore di sistema. Il fuso orario deve essere in Coordinated Universal Time (UTC) per aggiornare le date "valido da" e "valido fino a" degli indirizzi postali dalle app Finance and Operations.

    ![Impostazione del fuso orario per l'account amministratore di sistema.](media/ADF-1.png)

2. In Data Factory, nella scheda **Gestisci** sotto **Parametri globali**, crea il seguente parametro globale.

    | Numero | Name | Tipo | Valore |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | stringa | Questo parametro aggiunge un numero di serie agli indirizzi postali appena creati come prefisso. Assicurati di fornire una stringa che non sia in conflitto con gli indirizzi postali nelle app Finance and Operations e nelle app per il coinvolgimento dei clienti. Ad esempio, utilizza **ADF-PAD-**. |

    ![Parametro globale PostalAddressIdPrefix creato nella scheda Gestisci.](media/ADF-2.png)

3. Al termine, seleziona **Pubblica tutto**.

    ![Pulsante Pubblica tutto.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>Impostare per eseguire il modello di indirizzo elettronico della parte

1. In Data Factory, nella scheda **Gestisci** sotto **Parametri globali**, crea i seguenti parametri globali.

    | Numero | Name | Tipo | Valore |
    |---|---|---|---|
    | 1 | IsFOSource | bool | Questo parametro determina quali indirizzi di sistema primari vengono sostituiti in caso di conflitti. Se il valore è **vero**, gli indirizzi primari nelle app Finance and Operations sostituiranno gli indirizzi primari nelle app di coinvolgimento dei clienti. Se il valore è **falso**, gli indirizzi primari nelle app di coinvolgimento dei clienti sostituiranno gli indirizzi primari nelle app Finance and Operations. |
    | 2 | ElectronicAddressIdPrefix | stringa | Questo parametro aggiunge un numero di serie agli indirizzi elettronici appena creati come prefisso. Assicurati di fornire una stringa che non sia in conflitto con gli indirizzi elettronici nelle app Finance and Operations e nelle app per il coinvolgimento dei clienti. Ad esempio, utilizza **ADF-EAD-**. |

    ![Parametri globali IsFOSource ed ElectronicAddressIdPrefix creati nella scheda Gestisci.](media/ADF-4.png)

2. Al termine, seleziona **Pubblica tutto**.

## <a name="run-the-templates"></a>Eseguire i modelli

1. Interrompi i mapping a doppia scrittura seguenti di **Account**, **Contatto** e **Fornitore** che usano l'app Finance and Operations:

    + Clienti V3 (conti)
    + Clienti V3(contacts)
    + Contatti CDS V2(contacts)
    + Contatti CDS V2(contacts)
    + Fornitore V2 (msdyn_vendor)

2. Assicurati che le mappe vengano rimosse dalla tabella **msdy_dualwriteruntimeconfig** in Dataverse.
3. Installa le [soluzioni di doppia scrittura per parte e rubrica globale](https://aka.ms/dual-write-gab) da AppSource.
4. Nell'app Finance and Operations, esegui **Sincronizzazione iniziale** per le seguenti tabelle contengono dati:

    + Formule di apertura
    + Tipi di carattere personale
    + Formula di chiusura
    + Titoli contatti
    + Ruoli nel processo decisionale
    + Livelli fedeltà

5. Nell'app di interazione con i clienti, disabilita i seguenti passaggi del plug-in:

    + Aggiornamento account

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account

    + Aggiornamento del contatto

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto

    + Aggiornamento di msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party

    + Aggiornamento di msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor

    + Customeraddress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: creazione di customeraddress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: aggiornamento di customeraddress

        + Elimina

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: eliminazione di customeraddress

    + msdyn_partypostaladdress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: creazione di msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: creazione di msdyn_partypostaladdress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: aggiornamento di msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: aggiornamento di msdyn_partypostaladdress

    + msdyn_postaladdress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: creazione di msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: creazione di msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: creazione di msdyn_postaladdress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: aggiornamento di msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: aggiornamento di msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: creazione di msdyn_partyelectronicaddress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: aggiornamento di msdyn_partyelectronicaddress

        + Elimina

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: eliminazione di msdyn_partyelectronicaddress

6. Nell'app di interazione con i clienti, disabilita i seguenti flussi di lavoro:

    + Creare fornitori nella tabella Conto
    + Creare fornitori nella tabella Conto
    + Creare fornitori di tipo Persona nella tabella Contatti
    + Creare fornitori di tipo Persona nella tabella fornitori
    + Aggiornare fornitori nella tabella Conto
    + Aggiornare fornitori nella tabella Fornitori
    + Aggiornare fornitori di tipo Persona nella tabella Contatti
    + Aggiornare fornitori di tipo Persona nella tabella fornitori

7. Nel data factory, esegui il modello selezionando **Attiva ora** come mostrato nell'immagine seguente. Il completamento di questo processo potrebbe richiedere alcune ore in base al volume di dati.

    ![Esecuzione del modello.](media/data-factory-trigger.png)

    > [!NOTE]
    > Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello.

8. Importa i nuovi record **Parte** nell'app Finance and Operations.

    1. Scarica il file **FONewParty.csv** da archiviazione BLOB di Azure. Il percorso è **partybootstrapping/output/FONewParty.csv**.
    2. Converti il file **FONewParty.csv** in un file Excel e importa il file Excel nell'app Finance and Operations. In alternativa se l'importazione del file CSV funziona, puoi importare direttamente il file CSV. Il completamento di questo processo potrebbe richiedere alcune ore in base al volume di dati. Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../data-import-export-job.md).

    ![Importazione dei record di parte di Dataverse.](media/data-factory-import-party.png)

9. Nel data factory, esegui uno dopo l'altro i modelli Indirizzo postale della parte e Indirizzo elettronico della parte.

    + Il modello di indirizzo postale della parte aggiorna tutti i record dell'indirizzo postale nell'app di coinvolgimento del cliente e li associa ai corrispondenti record **Account**, **Contatto**, e **Fornitore**. Genera anche tre file .csv: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv e ImportFONewPostalAddress.csv.
    + Il modello di indirizzo elettronico della parte aggiorna tutti i record dell'indirizzo elettronico nell'app di coinvolgimento del cliente e li associa ai corrispondenti record **Account**, **Contatto**, e **Fornitore**. Genera anche un file .csv: ImportFONewElectronicAddress.csv.

    ![Esecuzione dei modelli di indirizzo postale della parte e di indirizzo elettronico della parte.](media/ADF-7.png)

10. Per aggiornare l'app Finance and Operations con questi dati, devi convertire i file .csv in una cartella di lavoro Excel e [importalo nell'app Finance and Operations](/data-entities/data-import-export-job). In alternativa se l'importazione del file CSV funziona, puoi importare direttamente i file CSV. Il completamento di questo processo potrebbe richiedere alcune ore in base al volume.

    ![Importazione completata.](media/ADF-8.png)

11. Nell'app di interazione con i clienti, abilita i seguenti passaggi del plug-in:

    + Aggiornamento account

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account

    + Aggiornamento del contatto

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto

    + Aggiornamento di msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party

    + Aggiornamento di msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor

    + msdyn_partypostaladdress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: creazione di msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: creazione di msdyn_partypostaladdress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: aggiornamento di msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: aggiornamento di msdyn_partypostaladdress

    + msdyn_postaladdress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: creazione di msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: creazione di msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: creazione di msdyn_postaladdress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: aggiornamento di msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: aggiornamento di msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Crea

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: creazione di msdyn_partyelectronicaddress

        + Aggiorna

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: aggiornamento di msdyn_partyelectronicaddress

        + Elimina

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: eliminazione di msdyn_partyelectronicaddress

12. Nell'app di interazione con i clienti, attiva i seguenti flussi di lavoro se li hai disattivati in precedenza:

    + Creare fornitori nella tabella Conto
    + Creare fornitori nella tabella Conto
    + Creare fornitori di tipo Persona nella tabella Contatti
    + Creare fornitori di tipo Persona nella tabella fornitori
    + Aggiornare fornitori nella tabella Conto
    + Aggiornare fornitori nella tabella Fornitori
    + Aggiornare fornitori di tipo Persona nella tabella Contatti
    + Aggiornare fornitori di tipo Persona nella tabella fornitori

13. Esegui le mappe correlate a record **Parte** come indicato in [Parte e rubrica globale](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Spiegazione dei modelli Data Factory

Questa sezione illustra i passaggi in ogni modello di Data Factory.

### <a name="steps-in-the-party-template"></a>Passaggi nel modello Parte

1. I passaggi da 1 a 6 identificano le società abilitate per la doppia scrittura e creano una clausola di filtro.
2. I passaggi da 7-1 a 7-9 recuperano i dati da entrambe le app Finance and Operations e di coinvolgimento del cliente e predispongono tali dati per l'aggiornamento.
3. I passaggi da 8 a 9 confrontano il numero della parte per i record **Account**, **Contatto**, e **Fornitore** tra l'app Finance and Operations e l'app di coinvolgimento del cliente. I record che non hanno un numero parte verranno saltati.
4. Il passaggio 10 genera due file .csv per i record della parte che devono essere creati nell'app di coinvolgimento del cliente e nell'app Finance and Operations.

    - **FOCDSParty.csv** – Questo file contiene tutti i record delle parti di entrambi i sistemi, indipendentemente dal fatto che l'azienda sia abilitata per la doppia scrittura.
    - **FONewParty.csv** – Questo file contiene un sottoinsieme dei record della parte che Dataverse è consapevole (ad esempio, account di tipo **Prospect**).

5. Il passaggio 11 crea le parti nell'app di coinvolgimento del cliente.
6. Il passaggio 12 recupera gli identificatori univoci globali (GUID) delle parti dall'app di coinvolgimento del cliente e li organizza in modo che possano essere associati ai record **Account**, **Contatto**, e **Fornitore** nei passaggi successivi.
7. Il passaggio 13 associa i record **Account**, **Contatto**, e **Fornitore** ai GUID di parte.
8. I passaggi da 14-1 a 14-3 aggiornano i record **Account**, **Contatto**, e **Fornitore** nell'app di coinvolgimento del cliente con i GUID di parte.
9. I passaggi da 15-1 a 15-3 preparano i record **Contatto per la parte** per i record **Account**, **Contatto**, e **Fornitore**.
10. I passaggi da 16-1 a 16-7 recuperano dati di riferimento come saluti e tipi di caratteri personali e li associano ai record **Contatto per la parte**.
11. Il passaggio 17 unisce i record **Contatto per la parte** per i record **Account**, **Contatto**, e **Fornitore**.
12. Il passaggio 18 importa i record **Contatto per la parte** nell'app di coinvolgimento del cliente.

### <a name="steps-in-the-party-postal-address-template"></a>Passaggi nel modello di indirizzo postale della parte

1. I passaggi da 1-1 a 1-10 recuperano i dati da entrambe le app Finance and Operations e di coinvolgimento del cliente e predispongono tali dati per l'aggiornamento.
2. Il passaggio 2 denormalizza i dati dell'indirizzo postale nell'app Finance and Operations unendo l'indirizzo postale e l'indirizzo postale della parte.
3. Il passaggio 3 deduplica e unisce i dati dell'account, del contatto e dell'indirizzo del fornitore dall'app di coinvolgimento del cliente.
4. Il passaggio 4 crea file .csv per l'app Finance and Operations per creare nuovi dati di indirizzo basati su indirizzi di account, contatti e fornitori.
5. Il passaggio 5-1 crea file .csv per l'app di coinvolgimento del cliente per creare tutti i dati dell'indirizzo, in base a entrambe le app Finance and Operations e di coinvolgimento del cliente.
6. Il passaggio 5-2 converte i file .csv nel formato di importazione Finance and Operations per l'importazione manuale.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. Il passaggio 6 importa i dati di raccolta dell'indirizzo postale nell'app di coinvolgimento del cliente.
8. Il passaggio 7 recupera i dati di raccolta dell'indirizzo postale dall'app di coinvolgimento del cliente.
9. Il passaggio 8 crea i dati dell'indirizzo del cliente e associa un ID di raccolta dell'indirizzo postale.
10. Passaggi da 9-1 a 9-2 associa gli ID raccolta indirizzi postali e parti con indirizzi postali e indirizzi postali delle parti.
11. I passaggi da 10-1 a 10-3 importano gli indirizzi dei clienti, gli indirizzi postali e gli indirizzi postali delle parti nell'app di coinvolgimento dei clienti.

### <a name="steps-in-the-party-electronic-address-template"></a>Passaggi nel modello di indirizzo elettronico della parte

1. I passaggi da 1-1 a 1-5 recuperano i dati da entrambe le app Finance and Operations e di coinvolgimento del cliente e predispongono tali dati per l'aggiornamento.
2. Il passaggio 2 consolida gli indirizzi elettronici nell'app di coinvolgimento del cliente da entità account, contatti e fornitore.
3. Il passaggio 3 unisce i dati dell'indirizzo elettronico primario dall'app di coinvolgimento del cliente e dall'app Finance and Operations.
4. Il passaggio 4 crea i file .csv.

    - Crea nuovi dati di indirizzo elettronico per l'app Finance and Operations, in base agli indirizzi dell'account, del contatto e del fornitore.
    - Crea nuovi dati di indirizzo elettronico per l'app di coinvolgimento del cliente, in base all'indirizzo elettronico e agli indirizzi di account, contatti e fornitore nell'app Finance and Operations.

5. Il passaggio 5-1 importa gli indirizzi elettronici nell'app di coinvolgimento del cliente.
6. Il passaggio 5-2 crea i file .csv per aggiornare gli indirizzi primari per account e contatti nell'app di coinvolgimento dei clienti.
7. I passaggi da 6-1 a 6-2 importano gli indirizzi primari di contatti e account nell'app di coinvolgimento dei clienti.

## <a name="troubleshooting"></a>Risoluzione dei problemi

1. Se il processo non riesce, esegui nuovamente il data factory. Inizia dall'attività non riuscita.
2. Alcuni file vengono generati dal data factory utilizzabile per la convalida dei dati.
3. Il data factory viene eseguito in base ai file .csv. Pertanto, se è presente un valore di campo con una virgola, potrebbe interferire con i risultati. È necessario rimuovere tutte le virgole dai valori dei campi.
4. La scheda **Monitoraggio** fornisce informazioni su tutti i passaggi e i dati elaborati. Seleziona un passaggio specifico per eseguirne il debug.

    ![Scheda Monitoraggio.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Ulteriori informazioni sul modello

Per ulteriori informazioni sul modello vedi [Commenti per il file Leggimi del modello di Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
