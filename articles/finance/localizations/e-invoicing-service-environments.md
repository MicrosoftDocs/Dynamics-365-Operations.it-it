---
title: Ambienti del servizio
description: Questo articolo fornisce informazioni sugli ambienti di servizio per la funzionalità di Fatturazione elettronica e spiega come configurarli.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8c743c5b2fbc7dcc3ae04fa4d7ca0e65de6c2507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901249"
---
# <a name="service-environments"></a>Ambienti di servizio

[!include [banner](../includes/banner.md)]

Gli ambienti del servizio sono partizioni logiche create per supportare le funzionalità di globalizzazione e documenti corrispondenti elaborati nel servizio di fatturazione elettronica. I segreti di sicurezza, i certificati digitali e le autorizzazioni di accesso (governance) devono essere configurati a livello di ambiente del servizio.

È possibile creare tutti gli ambienti di servizio necessari. Tutti gli ambienti del servizio creati sono indipendenti l'uno dall'altro. Come procedura consigliata, ti consigliamo di creare almeno due ambienti di servizio:

- Un ambiente per i principali scopi di sviluppo e convalida. Questo ambiente è in genere un ambiente di test di accettazione dell'utente (UAT).
- Un ambiente per scopi di produzione. Questo ambiente è in genere un ambiente di produzione.

Questo tipo di partizionamento aiuta a garantire che i processi di fatturazione elettronica siano convalidati e personalizzati nella sandbox prima che entrino in produzione.

Gli ambienti di servizio devono essere creati e gestiti in Regulatory Configuration Service (RCS). Quindi, quando sono pronti, devono essere pubblicati nel servizio di fatturazione elettronica. Il processo di pubblicazione invia i parametri dell'ambiente di servizio dall'istanza RCS al servizio di fatturazione elettronica.

Se non completi il processo di pubblicazione dopo aver creato un nuovo ambiente di servizio o modificato un ambiente di servizio esistente (ad esempio, aggiungendo o rimuovendo utenti o segreti Microsoft Azure Key Vault), le modifiche non avranno effetto. È possibile accedere solo agli ambienti pubblicati da Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Stati dell'ambiente del servizio

Gli ambienti del servizio possono essere gestiti tramite lo stato. È possibile visualizzare lo stato di un ambiente nella pagina **Ambienti di servizio**. Sono disponibili gli stati seguenti:

- **Non pubblicato** - L'ambiente è stato creato, ma non è stato ancora pubblicato.
- **Pubblicato** - L'ambiente è stato pubblicato nel servizio di fatturazione elettronica.
- **Modificato** - Gli attributi di un ambiente pubblicato sono stati modificati, ma le modifiche non sono state ancora pubblicate.

## <a name="users"></a>Utenti

Ogni ambiente del servizio deve elencare gli utenti che possono connettersi a Fatturazione elettronica da Finance o Supply Chain Management.

## <a name="applications"></a>Candidature

In alcuni scenari, applicazioni diverse da Finance o Supply Chain Management potrebbero doversi connettere al servizio di fatturazione elettronica per inviare documenti elettronici per un'ulteriore elaborazione o per recuperare informazioni come lo stato di invio di un documento. In questi scenari, l'applicazione deve essere definita nell'elenco delle applicazioni. In questo modo avrà accesso al servizio di fatturazione elettronica. L'applicazione deve anche essere registrata come applicazione in Azure Active Directory (Azure AD) e l'ID oggetto deve essere utilizzato per identificarle. 

Poiché Microsoft richiede un elevato livello di controllo di sicurezza sulle applicazioni che possono connettersi al servizio di fatturazione elettronica, è necessario contattare Microsoft all'indirizzo <DGXRegulatoryservicesengineering@service.microsoft.com> e fornisci i seguenti dettagli della tua domanda:

- ID tenant Azure AD
- ID ambiente Microsoft Dynamics Lifecycle Services (LCS)
- ID applicazione (ID client)
- ID oggetto
- Giustificazione e descrizione di alto livello della domanda

Microsoft valuterà la richiesta e registrerà l'applicazione nel registro di sicurezza per garantire che possa funzionare con la fatturazione elettronica.

## <a name="number-sequences"></a>Sequenze numeriche

Se i tuoi scenari richiedono sequenze numeriche (ad esempio, nei nomi di file), puoi utilizzare sequenze numeriche definite per un ambiente specifico, ma che possono essere utilizzate tra le funzionalità di globalizzazione o per una specifica funzionalità di globalizzazione. Dopo aver definito una sequenza numerica, è possibile utilizzarla nelle variabili e nelle pipeline di elaborazione. Per tener traccia del suo utilizzo, nella pagina **Sequenze numeriche**, cerca un valore **Corrente** per il parametro **In uso**.

### <a name="working-with-number-sequences"></a>Utilizzo delle sequenze numeriche
Nella pagina **Sequenze numeriche**: 

- Seleziona **Nuovo** per creare una sequenza numerica. Immetti quindi un nome e una descrizione. 
- Seleziona **Elimina** per eliminare una sequenza numerica se non è più utilizzata.
- Non devi selezionare **Pubblica** nel riquadro azioni per pubblicare le modifiche a una sequenza numerica. L'aggiornamento viene effettuato automaticamente.

## <a name="create-a-key-vault-reference"></a>Creare un riferimento Key Vault

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Configurazione ambiente**, nel riquadro Azioni seleziona **Ambienti del servizio**.
4. Nella pagina **Ambienti del servizio**, nel riquadro azioni seleziona **Parametri Key Vault**.
5. Nella pagina **Parametri Key Vault**, seleziona **Nuovo** per creare un riferimento Key Vault.
6. Nel campo **Nome** immetti il nome del riferimento Key Vault.
7. Nel campo **Descrizione** immettere una descrizione.
8. Nel campo **URI Key Vault** incolla l'URI del Key Vault dal Key Vault (`https://<your key vault>.vault.azure.net/`). Per ulteriori informazioni, vedi [Creare un Azure Key Vault nel portale di Azure](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Seleziona **Salva**.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>Creare un segreto per il token segreto dell'account di archiviazione

1. Nella pagina **Parametri Key Vault** seleziona il riferimento Key Vault creato nella procedura precedente e quindi nella sezione **Certificati** seleziona **Aggiungi**.
2. Nel campo **Nome** immetti il nome del segreto dell'account di archiviazione. Questo nome deve corrispondere al nome del segreto Key Vault che contiene il token della firma di accesso condiviso (SAS) di archiviazione. Per ulteriori informazioni, vedi [Creare un account di archiviazione Azure nel portale di Azure](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Tipo** seleziona **Segreto**.
5. Seleziona **Salva**.
    
## <a name="create-a-service-environment"></a>Creare un ambiente del servizio

1. Nella pagina **Ambienti del servizio**, seleziona **Nuovo** per creare un ambiente del servizio.
2. Nel campo **Nome** immettere il nome dell'ambiente di fatturazione elettronica.
3. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Segreto token SAS di archiviazione** seleziona il nome del segreto dell'account di archiviazione che deve essere utilizzato per autenticare l'accesso all'account di archiviazione.
5. Nella sezione **Utenti** seleziona **Aggiungi** per aggiungere un utente a cui è consentito inviare fatture elettroniche attraverso l'ambiente e connettersi all'account di archiviazione.
6. Nel campo **ID utente** immetti l'alias dell'utente. 
7. Nel campo **E-mail** immetti l'indirizzo di posta elettronica dell'utente.
8. Seleziona **Salva**.
9. Nel riquadro azioni, seleziona **Pubblica** per pubblicare l'ambiente sul servizio di fatturazione elettronica. Verifica che il valore del campo **Stato** venga modificato in **Pubblicato**.
