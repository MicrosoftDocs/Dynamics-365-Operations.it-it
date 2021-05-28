---
title: Eseguire l'aggiornamento al modello di parte e di rubrica globale
description: In questo argomento viene descritto come aggiornare i dati a doppia scrittura al modello di parte e rubrica globale.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 95472a00d34ba939ac89b4e2484f34d50bee3088
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018314"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Eseguire l'aggiornamento al modello di parte e di rubrica globale

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Il [modello di Azure Data Factory](https://aka.ms/dual-write-gab-adf) consente di aggiornare i dati di tabella **Account**, **Contatto** e **Fornitore** in doppia scrittura al modello di parte e rubrica globale. Il modello riconcilia i dati delle app Finance and Operations e delle applicazioni di interazione con i clienti. Alla fine del processo, i campi **Parte** e **Contatto** per i record **Parte** verranno creati e associati ai record **Account**, **Contatto** e **Fornitore** nelle applicazioni di interazione con i clienti. Un file .csv (`FONewParty.csv`) viene generato per creare nuovi record **Parte** nell'app Finance and Operations. In questo argomento vengono fornite istruzioni per utilizzare il modello Data Factory e aggiornare i dati.

Se non disponi di personalizzazioni, puoi utilizzare il modello così com'è. Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello utilizzando le seguenti istruzioni.

> [!Note]
> Il modello aiuta ad aggiornare solo i dati **Parte**. In una versione futura verranno inclusi indirizzi postali ed elettronici.

## <a name="prerequisites"></a>Prerequisiti

Questi prerequisiti sono obbligatori:

+ [Sottoscrizione di Azure](https://portal.azure.com/)
+ [Accesso al modello](https://aka.ms/dual-write-gab-adf)
+ Sei un cliente esistente che utilizza la doppia scrittura.

## <a name="prepare-for-the-upgrade"></a>Preparazione per l'aggiornamento

+ **Completamente sincronizzato**: entrambi gli ambienti sono completamente sincronizzati per **Account (cliente)**, **Contatto** e **Fornitore**.
+ **Chiavi di integrazione**: le tabelle **Account (cliente)**, **Contatto** e **Fornitore** nelle app di interazione con i clienti utilizzano le chiavi di integrazione fornite immediatamente. Se hai personalizzato le chiavi di integrazione, devi personalizzare il modello.
+ **Numero parte**: tutti i record **Account (cliente)**, **Contatto** e **Fornitore** che verranno aggiornati hanno un numero **Parte**. I record senza un numero **Parte** verrà ignorato. Se desideri aggiornare questi record, aggiungici un numero **Parte** prima di iniziare il processo di aggiornamento.
+ **Interruzione del sistema**: durante il processo di aggiornamento, Finance and Operations e ambienti di interazione con i clienti devono essere offline.
+ **Snapshot**: prendi snapshot di Finance and Operations e delle app di interazione dei clienti. Usa le snapshot per ripristinare lo stato precedente, se necessario.

## <a name="deployment"></a>Distribuzione

1. Scarica il modello da [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).

2. Accedi a [Microsoft Azure](https://portal.azure.com/).

3. Crea un [gruppo di risorse](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Crea un [account di archiviazione](/azure/storage/common/storage-account-create?tabs=azure-portal) nel gruppo di risorse che hai creato.

5. Crea un [data factory](/azure/data-factory/quickstart-create-data-factory-portal) nel gruppo di risorse sopra che hai creato.

6. Apri il data factory e seleziona il riquadro **Creare e monitorare**.

7. Nella scheda **Gestisci**, seleziona **Modello ARM**.

8. Seleziona **Importa modello ARM** per importare il modello **Parte**.

9. Importa il modello nel data factory. Immettere i seguenti valori per **Dettagli del progetto** e **Dettagli dell'istanza**.

    Campo | Valore
    ---|---
    Abbonamento | Sottoscrizione di Azure
    Gruppo di risorse | Fornire la stessa risorsa in cui viene creato l'account di archiviazione.
    Stato/regione | Specifica l'area geografica.
    Nome factory | Specifica il nome della factory.
    FO Linked Service_service Principal Key | Specifica la chiave dell'applicazione.
    Azure Blob Storage_connection String | Stringa di connessione di Archiviazione BLOB di Azure.
    Dynamics Crm Linked Service_password | La password per l'account utente specificato come nome utente.
    FO Linked Service_properties_type Properties_url  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    FO Linked Service_properties_type Properties_tenant | Specifica le informazioni sul tenant (nome di dominio o ID tenant) in cui risiede l'applicazione.
    FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com`
    FO Linked Service_properties_type Properties_service Principal Id | Specifica l'ID client dell'applicazione.
    Dynamics Crm Linked Service_properties_type Properties_username | Il nome utente per la connessione a Dynamics.

    Per ulteriori informazioni, vedi [Promuovere manualmente un modello di Resource Manager per ogni ambiente](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Proprietà del servizio collegato](/azure/data-factory/connector-dynamics-ax#linked-service-properties) e [Copiare dati usando Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Dopo la distribuzione, convalidare i set di dati, il flusso di dati e il servizio collegato del data factory.

   ![Set di dati, flusso di dati e servizio collegato](media/data-factory-validate.png)

11. Vai a **Gestisci**. Sotto **Connessioni**, seleziona **Servizio collegato**. Seleziona **DynamicsCrmLinkedService**. Nel modulo **Modifica servizio collegato (Dynamics CRM)**, inserisci i seguenti valori:

    Campo | Valore
    ---|---
    Nome | DynamicsCrmLinkedService
    descrizione | I servizi collegati per connettersi con l'istanza CRM per recuperare i dati delle entità
    Connetti via runtime di integrazione | AutoResolvelntegrationRuntime
    Tipo di distribuzione | In linea
    Uri servizio | `https://<organization-name>.crm[x].dynamics.com`
    Tipo di autenticazione | Office365
    Nome utente |
    Password o Azure Key Vault | Password
    Password |

## <a name="run-the-template"></a>Eseguire il modello

1. Interrompi la doppia scrittura seguente di **Account**, **Contatto** e **Fornitore** utilizzando l'app Finance and Operations.

    + Clienti V3 (conti)
    + Clienti V3(contacts)
    + Contatti CDS V2(contacts)
    + Contatti CDS V2(contacts)
    + Fornitore V2 (msdyn_vendor)

2. Assicurati che le mappe vengano rimosse dalla tabella `msdy_dualwriteruntimeconfig` in Dataverse.

3. Installa le [soluzioni di doppia scrittura per parte e rubrica globale](https://aka.ms/dual-write-gab) da AppSource.

4. Nell'app Finance and Operations, se le seguenti tabelle contengono dati, allora esegui **Sincronizzazione iniziale** per le stesse.

    + Formule di apertura
    + Tipi di carattere personale
    + Formula di chiusura
    + Titoli contatti
    + Ruoli nel processo decisionale
    + Livelli fedeltà

5. Nell'app di interazione con i clienti, disabilita i seguenti passaggi del plug-in.

    + Aggiornamento dell'account
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account
    + Aggiornamento del contatto
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto
    + Aggiornamento di msdyn_party
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party
    + Aggiornamento di msdyn_vendor
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor

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

    ![Attiva ora](media/data-factory-trigger.png)

    > [!NOTE]
    > Se hai personalizzazioni per **Account**, **Contatto** e **Fornitore** devi modificare il modello.

8. Importa i nuovi record **Parte** nell'app Finance and Operations.

    + Scarica il file `FONewParty.csv` da archiviazione BLOB di Azure. Il percorso è `partybootstrapping/output/FONewParty.csv`.
    + Converti il file `FONewParty.csv` in un file Excel e importa il file Excel nell'app Finance and Operations.  Se l'importazione del file CSV funziona, puoi importare direttamente il file CSV. L'esecuzione dell'importazione potrebbe richiedere alcune ore, a seconda del volume di dati. Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../data-import-export-job.md).

    ![Importare i record Parte di Datavers](media/data-factory-import-party.png)

9. Nell'app di interazione con i clienti, abilita i seguenti passaggi del plug-in:

    + Aggiornamento dell'account
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: aggiornamento dell'account
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: aggiornamento dell'account
    + Aggiornamento del contatto
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: aggiornamento del contatto
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: aggiornamento del contatto
    + Aggiornamento di msdyn_party
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: aggiornamento di msdyn_party
    + Aggiornamento di msdyn_vendor
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: aggiornamento di msdyn_vendor

10. Nelle app di interazione con i clienti, attiva i seguenti flussi di lavoro se li hai disattivati nei passaggi precedenti:

    + Creare fornitori nella tabella Conto
    + Creare fornitori nella tabella Conto
    + Creare fornitori di tipo Persona nella tabella Contatti
    + Creare fornitori di tipo Persona nella tabella fornitori
    + Aggiornare fornitori nella tabella Conto
    + Aggiornare fornitori nella tabella Fornitori
    + Aggiornare fornitori di tipo Persona nella tabella Contatti
    + Aggiornare fornitori di tipo Persona nella tabella fornitori

11. Esegui le mappe correlate a **Parte** come indicato in [Parte e rubrica globale](party-gab.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi

1. Se il processo non riesce, esegui nuovamente il data factory a partire dall'attività non riuscita.
2. Alcuni file vengono generati dal data factory utilizzabile per la convalida dei dati.
3. Il data factory viene eseguito in base ai file CSV delimitati da virgole. Se è presente un valore di campo con una virgola, potrebbe interferire con i risultati. Devi rimuovere le virgole.
4. La scheda **Monitoraggio** fornisce informazioni su tutti i passaggi e i dati elaborati. Seleziona un passaggio specifico per eseguirne il debug.

    ![Scheda Monitoraggio](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Ulteriori informazioni sul modello

Puoi trovare commenti relativi al modello nel file [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).