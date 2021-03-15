---
title: Creare configurazioni ER in RCS e caricarle nel repository globale
description: Questo argomento spiega come creare una configurazione di report elettronico (ER) in Microsoft Regulatory Configuration Services (RCS) e caricarla nel repository globale.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ef12c911c8953b181db1c0eff0874a3d8cfcb3da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005750"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Creare configurazioni ER in Regulatory Configuration Services (RCS) e caricarle nel repository globale

[!include [banner](../includes/banner.md)]

Puoi utilizzare Microsoft Regulatory Configuration Services (RCS) per progettare configurazioni di reporting elettronico (ER) e pubblicarle in modo che possano essere utilizzate nella tua organizzazione.

Le seguenti procedure spiegano come un utente nel ruolo di amministratore di sistema o sviluppatore di report elettronici può creare una versione derivata di una configurazione ER che è stata configurata in un'istanza RCS e quindi caricare la configurazione derivata nel repository globale. 

Prima di poter completare queste procedure, devi completare i seguenti prerequisiti:

- Accesso a un'istanza RCS.
- Creare fornitore di configurazioni attivo. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Puoi inoltre assicurarti che venga fornito un ambiente RCS per la tua azienda.

1. In un'app Finance and Operations, vai ad **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Se non è stato effettuato il provisioning di nessun ambiente RCS per la società, seleziona **Regulatory services - Configurazione** e segui le istruzioni per il provisioning di un ambiente.

Se è già stato eseguito il provisioning di un ambiente RCS per la tua azienda, utilizza l'URL della pagina per accedervi selezionando l'opzione di accesso.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Crea una versione derivata di una configurazione in RCS

1. Nell'area di lavoro **Creazione di report elettronici**, verifica di disporre di un provider di configurazione attivo per la tua organizzazione. 
2. Selezionare **Configurazioni report**.
3. Seleziona la configurazione da cui vuoi derivare una nuova versione. Puoi utilizzare il campo del filtro sopra l'albero per restringere la ricerca.
4. Seleziona **Crea configurazione** \> **Deriva da nome**.
5. Immetti un nome e una descrizione, quindi seleziona **Crea configurazione** per creare una nuova versione derivata.
6. Seleziona la configurazione appena derivata, aggiungi una descrizione della versione, quindi seleziona **OK**. Lo stato della configurazione viene modificato in **Completato**.

![Nuova versione di configurazione in RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Quando lo stato della configurazione viene modificato, è possibile che venga visualizzato un messaggio di errore di convalida correlato alle applicazioni connesse. Per disattivare la convalida, nel riquadro azioni della scheda **Configurazioni**, seleziona **Parametri utente**, quindi imposta l'opzione **Ignora convalida alla riassegnazione e alla modifica dello stato della configurazione** su **Sì** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Carica una configurazione nel repository globale

Per condividere una configurazione nuova o derivata con la tua organizzazione, puoi caricarla nel repository globale.

1. Seleziona la versione completa della configurazione, quindi **Carica nel repository**.
2. Seleziona l'opzione **Globale (Microsoft)**, quindi **Carica**.

    ![Carica nelle opzioni del repository](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Nella finestra del messaggio di conferma, seleziona **Sì**. 
4. Aggiorna la descrizione della versione come richiesto, quindi seleziona **OK**. 

Lo stato della configurazione viene aggiornato su **Condividi** e la configurazione viene caricata nel repository globale. Da qui, puoi utilizzarla nei seguenti modi:

- Importala nell'istanza di Dynamics 365. Per ulteriori informazioni, vedi [(ER) Importare le configurazioni da RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Condividila con una terza parte o un'organizzazione esterna, vedi [Configurazioni RCS per la condivisione di report elettronici (ER) con organizzazioni esterne](rcs-global-repo-share-configuration.md)

    ![Versione di configurazione Contoso Intrastat derivata nel repository globale](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Eliminare una configurazione dal repository globale
Completa i seguenti passaggi per eliminare una configurazione creata dalla tua organizzazione.

1. Nell'area di lavoro **Creazione di report elettronici**, verifica che il tuo provider di configurazioni sia **Attivo**. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Sul tuo provider di configurazione attivo, seleziona **repository**.
3. Seleziona il tipo di repository **Globale** e seleziona **Aperto**.
4. Nella Scheda dettaglio **Filtro**, trova la configurazione che vuoi eliminare utilizzando la funzionalità **Filtro**.
5. Nella Scheda dettaglio **Versione**, seleziona la versione della configurazione che desideri eliminare, quindi seleziona **Elimina**:

    ![Eliminare la configurazione dal repository globale](media/RCS_Delete_from_GlobalRepo.JPG)

6. Nella finestra del messaggio di conferma, seleziona **Sì**.

    ![Messaggio di conferma di eliminazione della versione di configurazione](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
La versione della configurazione viene eliminata e viene visualizzato un messaggio di conferma. 

> [!NOTE]
> Le configurazioni possono essere eliminate solo dal provider di configurazioni che le ha create. Se la configurazione è stata condivisa con un'altra organizzazione, sarà necessario annullare la condivisione prima di eliminarla.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]