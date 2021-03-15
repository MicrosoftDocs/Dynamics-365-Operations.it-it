---
title: Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica
description: Questo argomento spiega come iniziare a usare il componente aggiuntivo per la fatturazione elettronica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104398"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:

- Devi avere accesso al tuo account Microsoft Dynamics Lifecycle Services (LCS).
- Devi disporre di un progetto LCS che includa la versione 10.0.13 o successiva di Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Inoltre, queste app devono essere distribuite in una delle seguenti aree geografiche di Azure:

    - Stati Uniti orientali
    - Stati Uniti occidentali
    - UE settentrionale
    - UE occidentale

- Devi avere accesso al tuo account Dynamics 365 Regulatory Configuration Services (RCS).
- Devi attivare la funzionalità di globalizzazione per il tuo account RCS in Gestione funzionalità. Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).
- Devi creare un insieme di credenziali delle chiavi e un account di archiviazione in Azure. Per ulteriori informazioni, vedi [Creare un account di archiviazione di Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>Installa il componente aggiuntivo per microservizi in Lifecycle Services

1. Accedi al tuo account LCS.
2. Seleziona il riquadro **Anteprima gestione funzionalità**.
3. Nella sezione **Funzionalità di anteprima pubblica** seleziona **Servizio di fatturazione elettronica**.
4. Verifica che l'opzione **Funzionalità di anteprima abilitata** sia impostata su **Sì**.

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>Configurare i parametri per l'integrazione RCS con il componente aggiuntivo per la fatturazione elettronica

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Collegamenti correlati**, selezionare **Parametri per la creazione di report elettronici**.
3. Nella scheda **Servizio di fatturazione elettronica** nel campo **URI endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.

    | Area geografica del data center di Azure | URI endpoint servizio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Stati Uniti orientali                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Stati Uniti occidentali                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | UE settentrionale                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | UE occidentale                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Verifica che il campo **ID applicazione** sia impostato su **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Questo valore è un valore fisso.
5. Nel campo **ID ambiente LCS** immetti l'ID del tuo account di sottoscrizione LCS.
6. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="create-key-vault-secret"></a>Creare il segreto Key Vault

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Configurazioni dell'ambiente** nel riquadro azioni seleziona **Ambiente del servizio** e quindi seleziona **Parametri Key Vault**.
4. Seleziona **Nuovo** per creare un segreto dell'insieme di credenziali delle chiavi.
5. Nel campo **Nome** immettere il nome del segreto dell'insieme di credenziali delle chiavi. Nel campo **Descrizione** immettere una descrizione.
6. Nel campo **URI Key Vault** incolla il segreto da Azure Key Vault.
7. Selezionare **Salva**.

## <a name="create-storage-account-secret"></a>Creare un segreto dell'account di archiviazione

1. Nella pagina **Parametri insieme di credenziali delle chiavi** nella sezione **Certificati** seleziona **Aggiungi**.
2. Nel campo **Nome** immettere lo stesso nome del segreto dell'account di archiviazione. Nel campo **Descrizione** immettere una descrizione.
3. Nel campo **Tipo** seleziona **Certificato**.
4. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Creare un ambiente del componente aggiuntivo per la fatturazione elettronica

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.

## <a name="create-a-service-environment"></a>Creare un ambiente del servizio

1. Nella pagina **Configurazioni dell'ambiente**, nel riquadro azioni seleziona **Ambiente del servizio**.
2. Seleziona **Nuovo** per creare un nuovo ambiente del servizio.
3. Nel campo **Nome** immettere il nome dell'ambiente di fatturazione elettronica. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Segreto token SAS di archiviazione** seleziona il nome del certificato che deve essere utilizzato per autenticare l'accesso all'account di archiviazione.
5. Nella sezione **Utenti** seleziona **Aggiungi** per aggiungere un utente a cui è consentito inviare fatture elettroniche attraverso l'ambiente e connettersi anche all'account di archiviazione.
6. Nel campo **ID utente** immetti l'alias dell'utente. Nel campo **E-mail** immetti l'indirizzo di posta elettronica dell'utente.
7. Selezionare **Salva**.
8. Se le fatture specifiche per paese/area geografica richiedono una catena di certificati per applicare una firma digitale, seleziona nel riquadro azioni **Parametri Key Vault**, quindi seleziona **Catena di certificati** e segui questi passaggi:

    1. Seleziona **Nuovo** per creare una catena di certificati.
    2. Nel campo **Nome** immettere il nome della catena di certificati. Nel campo **Descrizione** immettere una descrizione.
    3. Nella sezione **Certificati** seleziona **Aggiungi** per aggiungere un certificato alla catena.
    4. Usa il pulsante **Su** o **Giù** per modificare la posizione del certificato nella catena.
    5. Selezionare **Salva**, quindi chiudere la pagina.
    6. Chiudere la pagina.
9. Nella pagina **Ambiente del servizio** nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente nel cloud. Il valore del campo **Stato** viene modificato in **Pubblicato**.

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

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Configurare l'integrazione del componente aggiuntivo per la fatturazione elettronica in Finance e Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Attivare la funzionalità di integrazione del componente aggiuntivo per la fatturazione elettronica

1. Accedi alla tua istanza Finance o Supply Chain Management.
2. Nell'area di lavoro **Gestione funzionalità**, cerca la funzionalità **Integrazione del componente aggiuntivo per la fatturazione elettronica**. Se questa funzionalità non viene visualizzata nella pagina, seleziona **Controlla aggiornamenti**.
3. Seleziona la funzionalità, quindi seleziona **Abilita ora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurare l'URL dell'endpoint di servizio

1. Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.
2. Nella scheda **Servizio di invio** nel campo **URL endpoint del servizio** immetti l'endpoint del servizio appropriato per l'area geografica di Azure, come mostrato nella tabella seguente.

    | Area geografica del data center di Azure | URL endpoint servizio                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Stati Uniti orientali                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Stati Uniti occidentali                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | UE settentrionale                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | UE occidentale                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. Nel campo **Ambiente** immettere il nome dell'ambiente del componente aggiuntivo Fatturazione elettronica.
4. Selezionare **Salva**, quindi chiudere la pagina.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]