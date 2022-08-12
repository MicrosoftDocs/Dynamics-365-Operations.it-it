---
title: Creare configurazioni ER in RCS e caricarle nel repository globale
description: Questo articolo spiega come creare una configurazione di report elettronico (ER) in Microsoft Regulatory Configuration Services (RCS) e caricarla nel repository globale.
author: JaneA07
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f73f7189ad82d85169a4e0df573dd26dab8bb009
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070602"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Creare configurazioni ER in Regulatory Configuration Services (RCS) e caricarle nel repository globale

[!include [banner](../includes/banner.md)]

Puoi utilizzare Microsoft Regulatory Configuration Services (RCS) per progettare configurazioni di reporting elettronico (ER) e pubblicarle in modo che possano essere utilizzate nella tua organizzazione.

Le seguenti procedure spiegano come un utente nel ruolo di amministratore di sistema o sviluppatore di report elettronici può creare una versione derivata di una configurazione ER che è stata configurata in un'istanza RCS e quindi caricare la configurazione derivata nel repository globale. 

Prima di poter completare queste procedure, devi completare i seguenti prerequisiti:

- Avere accesso a un ambiente RCS per la tua organizzazione.
- Creare un provider di configurazione e renderlo attivo. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Devi assicurarti che venga fornito un ambiente RCS per la tua organizzazione. Se non hai un'istanza RCS di cui è stato eseguito il provisioning per la tua organizzazione, puoi farlo seguendo i passaggi seguenti:

1. In un'app per la finanza e le operazioni, vai a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. In **Collegamenti correlati/Collegamenti esterni**, seleziona **Regulatory services - Configurazione**, quindi segui le istruzioni per **iscriverti** per assegnarne uno.

Se è già stato eseguito il provisioning di un ambiente RCS per la tua organizzazione, utilizza l'URL della pagina per accedervi selezionando l'opzione di **accesso**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Crea una versione derivata di una configurazione in RCS

> [!NOTE]
> Se è la prima volta che utilizzi RCS, non avrai alcuna configurazione disponibile da cui creare una versione derivata. Sarà necessario importare una configurazione dal repository globale. Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Accedi** a RCS e seleziona l'area di lavoro **Creazione di report elettronici**.
2. Verifica di disporre di un provider di configurazione attivo per la tua organizzazione impostato su attivo (vedi i prerequisiti). 
3. Selezionare **Configurazioni report**.
4. Seleziona la configurazione da cui vuoi derivare una nuova versione. Puoi utilizzare il campo del filtro sopra l'albero per restringere la ricerca.
5. Seleziona **Crea configurazione** \> **Deriva da nome**.
6. Immetti un nome e una descrizione, quindi seleziona **Crea configurazione** per creare una nuova versione derivata con stato "Bozza".
7. Seleziona la nuova configurazione derivata e apporta ulteriori modifiche al formato di configurazione, se necessario. 
8. Dopo aver completato le modifiche, è necessario impostare **Cambia stato** per la configurazione su **Completato** per poterla pubblicare nel repository. Seleziona **OK**.

![Nuova versione di configurazione in RCS.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Quando lo stato della configurazione viene modificato, è possibile che venga visualizzato un messaggio di errore di convalida correlato alle applicazioni connesse. Per disattivare la convalida, nel riquadro azioni della scheda **Configurazioni**, seleziona **Parametri utente**, quindi imposta l'opzione **Ignora convalida alla riassegnazione e alla modifica dello stato della configurazione** su **Sì** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Carica una configurazione nel repository globale

Per condividere una configurazione nuova o derivata con la tua organizzazione, puoi caricarla nel repository globale seguendo questi passaggi:

1. Seleziona la versione completa della configurazione, quindi **Carica nel repository**.
2. Seleziona l'opzione **Globale (Microsoft)**, quindi **Carica**.

    ![Carica nelle opzioni del repository.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Nella finestra del messaggio di conferma, seleziona **Sì**. 
4. Aggiorna la descrizione della versione come richiesto, quindi seleziona **OK**. Puoi anche caricare facoltativamente la versione su un'applicazione connessa o su un repository GIT.  

Lo stato della configurazione viene aggiornato su **Condiviso** e la configurazione viene caricata nel repository globale. Viene creata anche una bozza della configurazione caricata che può essere utilizzata se sono necessarie modifiche successive.

Dopo che la configurazione è stata caricata nel repository globale, puoi utilizzarla nei seguenti modi:

- Importala nell'istanza di Dynamics 365. Per ulteriori informazioni, vedi [(ER) Importare le configurazioni da RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Condividila con una terza parte o un'organizzazione esterna, vedi [Configurazioni RCS per la condivisione di report elettronici (ER) con organizzazioni esterne](rcs-global-repo-share-configuration.md)

    ![Versione di configurazione Contoso Intrastat derivata nel repository globale.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Eliminare una configurazione dal repository globale
Completa i seguenti passaggi per eliminare una configurazione creata dalla tua organizzazione.

1. Nell'area di lavoro **Creazione di report elettronici**, verifica che il tuo provider di configurazioni sia **Attivo**. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Sul tuo provider di configurazione attivo, seleziona **repository**.
3. Seleziona il tipo di repository **Globale** e seleziona **Aperto**.
4. Nella Scheda dettaglio **Filtro**, trova la configurazione che vuoi eliminare utilizzando la funzionalità **Filtro**.
5. Nella Scheda dettaglio **Versione**, seleziona la versione della configurazione che desideri eliminare, quindi seleziona **Elimina**:

    ![Eliminare la configurazione dal repository globale.](media/RCS_Delete_from_GlobalRepo.JPG)

6. Nella finestra del messaggio di conferma, seleziona **Sì**.

    ![Messaggio di conferma di eliminazione della versione di configurazione.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
La versione della configurazione viene eliminata e viene visualizzato un messaggio di conferma. 

> [!NOTE]
> Le configurazioni possono essere eliminate solo dal provider di configurazioni che le ha create. Se la configurazione è stata condivisa con un'altra organizzazione, sarà necessario annullare la condivisione prima di eliminarla.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

