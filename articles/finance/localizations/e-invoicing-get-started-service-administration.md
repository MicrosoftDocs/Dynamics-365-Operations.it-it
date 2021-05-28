---
title: Introduzione all'amministrazione dei servizi per la fatturazione elettronica
description: Questo argomento spiega come iniziare a usare la fatturazione elettronica.
author: gionoder
ms.date: 05/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f389e111006327fe8d82581d01140b4cff2e200d
ms.sourcegitcommit: 35fdcc6501e099c54a58583b1e3aba16f02a5ccc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5980977"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Introduzione all'amministrazione dei servizi per la fatturazione elettronica

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:

- Devi avere accesso al tuo account Microsoft Dynamics Lifecycle Services (LCS).
- Devi disporre di un progetto LCS che includa la versione 10.0.17 o successiva di Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Inoltre, queste app devono essere distribuite in una delle seguenti aree geografiche di Azure:

    - Stati Uniti
    - Europa
    - Regno Unito
    - Asia

- Devi avere accesso al tuo account Dynamics 365 Regulatory Configuration Services (RCS).
- Devi attivare la funzionalità di globalizzazione per il tuo account RCS in Gestione funzionalità. Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).
- Devi creare un insieme di credenziali delle chiavi e un account di archiviazione in Azure. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Installa il componente aggiuntivo per microservizi in Lifecycle Services

1. Accedi al tuo account LCS.
2. Seleziona il riquadro **Anteprima gestione funzionalità**.
3. Nella sezione **Funzionalità di anteprima pubblica** seleziona **Fatturazione elettronica**.
4. Verifica che l'opzione **Funzionalità di anteprima abilitata** sia impostata su **Sì**.
5. Nel dashboard Progetto LCS, seleziona un progetto LCS.
6. Nel progetto LCS, nel dashboard dell'ambiente LCS, seleziona il progetto di distribuzione LCS. Il progetto di distribuzione LCS deve essere in esecuzione.
7. Nella scheda **Integrazione di Power Platform**, nel gruppo di campi **Componenti aggiuntivi dell'ambiente**, seleziona **Installa un nuovo componente aggiuntivo**.
8. Seleziona **Fatturazione elettronica**.
9. Nel campo **ID applicazione AAD** inserisci **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Questo è un valore fisso.
10. Nel campo **ID tenant AAD** immettere l'ID tenant dell'account di sottoscrizione di Azure.
11. Esaminare i termini e le condizioni e quindi selezionare la casella di controllo.
12. Seleziona **Installa**.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Configurare i parametri per l'integrazione RCS con la fatturazione elettronica

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Parametri per la creazione di report elettronici**.
3. Nella scheda **Servizio di fatturazione elettronica** nel campo **URI endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.

    | Area geografica del data center di Azure | URI endpoint servizio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Stati Uniti              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Regno Unito             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

4. Verifica che il campo **ID applicazione** sia impostato su **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Questo valore è un valore fisso.
5. Nel campo **ID ambiente LCS** immetti l'ID del tuo ambiente LCS.
6. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="create-key-vault-references"></a>Creare riferimenti insieme di credenziali delle chiavi

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.
4. Seleziona **Nuovo** per creare un riferimento dell'insieme di credenziali delle chiavi.
5. Nel campo **Nome** immetti il nome del riferimento dell'insieme di credenziali delle chiavi. Nel campo **Descrizione** immettere una descrizione.
6. Nel campo **URI Key Vault** incolla il segreto dell'insieme di credenziali delle chiavi da Azure Key Vault. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).
7. Selezionare **Salva**.

## <a name="create-storage-account-secret"></a>Creare un segreto dell'account di archiviazione

1. Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** > **Parametri Key Vault**.
2. Seleziona un **Riferimento dell'insieme di credenziali delle chiavi** e nella sezione **Certificati** seleziona **Aggiungi**.
3. Nel campo **Nome** immetti il nome del segreto dell'account di archiviazione. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).
4. Nel campo **Descrizione** immettere una descrizione.
5. Nel campo **Tipo** seleziona **Segreto**.
6. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="create-a-digital-certificate-secret"></a>Creare un segreto del certificato digitale

1. Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.
2. Seleziona un **Riferimento dell'insieme di credenziali delle chiavi** e quindi nella sezione **Certificati** seleziona **Aggiungi**.
3. Nel campo **Nome** immetti il nome del segreto del certificato digitale. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).
4. Nel campo **Descrizione** immettere una descrizione.
5. Nel campo **Tipo** seleziona **Certificato**.
6. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="create-a-service-environment"></a>Creare un ambiente del servizio

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Configurazioni dell'ambiente**, nel riquadro Azioni seleziona **Ambiente del servizio**.
4. Seleziona **Nuovo** per creare un nuovo ambiente del servizio.
5. Nel campo **Nome** immettere il nome dell'ambiente di fatturazione elettronica. Nel campo **Descrizione** immettere una descrizione.
6. Nel campo **Segreto token SAS di archiviazione** seleziona il nome del segreto dell'account di archiviazione che deve essere utilizzato per autenticare l'accesso all'account di archiviazione.
7. Nella sezione **Utenti** seleziona **Aggiungi** per aggiungere un utente a cui è consentito inviare fatture elettroniche attraverso l'ambiente e connettersi anche all'account di archiviazione.
8. Nel campo **ID utente** immetti l'alias dell'utente. Nel campo **E-mail** immetti l'indirizzo di posta elettronica dell'utente.
9. Selezionare **Salva**.
10. Se le fatture specifiche per paese/area geografica richiedono una catena di certificati per applicare una firma digitale, seleziona nel riquadro azioni **Parametri Key Vault**, quindi seleziona **Catena di certificati** e segui questi passaggi:
    1. Seleziona **Nuovo** per creare una catena di certificati.
    2. Nel campo **Nome** immettere il nome della catena di certificati. Nel campo **Descrizione** immettere una descrizione.
    3. Nella sezione **Certificati** seleziona **Aggiungi** per aggiungere un certificato alla catena.
    4. Usa il pulsante **Su** o **Giù** per modificare la posizione del certificato nella catena.
    5. Selezionare **Salva**, quindi chiudere la pagina.
    6. Chiudere la pagina.
11. Nella pagina **Ambiente del servizio** nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente nel cloud. Il valore del campo **Stato** viene modificato in **Pubblicato**.

## <a name="create-a-connected-application"></a>Creare un'applicazione connessa

1. Nella pagina **Configurazioni dell'ambiente**, nel riquadro azioni seleziona **Applicazioni connesse**.
2. Seleziona **Nuovo** per creare un'applicazione connessa.
3. Nel campo **Nome** immettere il nome dell'applicazione da connettere.
4. Nel campo **Applicazione** immetti l'URL dell'ambiente Finance e Supply Chain Management da connettere.
4. Nel campo **Tenant** immetti il tenant dell'ambiente Finance e Supply Chain Management.
5. Selezionare **Salva**.
6. Nel riquadro azioni seleziona **Verificare connessione** per testare la connessione con l'ambiente. Quindi, chiudere la pagina.

## <a name="link-connected-applications-to-environments"></a>Collegare le applicazioni connesse agli ambienti

1. Nella pagina **Configurazioni ambiente** seleziona **Nuovo** per assegnare un'applicazione connessa a un ambiente.
2. Nel campo **Applicazione connessa** seleziona un'applicazione connessa.
3. Nel campo **Ambiente del servizio**, seleziona un ambiente del servizio.
4. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Configurare l'integrazione della fatturazione elettronica in Finance o Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Attivare la funzionalità di integrazione della fatturazione elettronica

1. Accedi alla tua istanza Finance o Supply Chain Management.
2. Nell'area di lavoro **Gestione funzionalità**, cerca la funzionalità **Integrazione della fatturazione elettronica**. Se questa funzionalità non viene visualizzata nella pagina, seleziona **Controlla aggiornamenti**.
3. Seleziona la funzionalità, quindi seleziona **Abilita ora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurare l'URL dell'endpoint di servizio

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Servizio di invio** nel campo **URL endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.

    | Area geografica del data center di Azure | URI endpoint servizio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Stati Uniti              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Regno Unito             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Nel campo **Ambiente** immetti il nome dell'ambiente del servizio pubblicato in Fatturazione elettronica.
4. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="enable-flighting-keys"></a>Abilitare le chiavi della versione di anteprima

Abilita le chiavi della versione di anteprima per Microsoft Dynamics 365 Finance o Microsoft Dynamics 365 Supply Chain Management versioni 10.0.17 o precedenti. 
1. Eseguire il seguente comando SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)

2. Esegui un comando IISreset per tutti gli AOS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
