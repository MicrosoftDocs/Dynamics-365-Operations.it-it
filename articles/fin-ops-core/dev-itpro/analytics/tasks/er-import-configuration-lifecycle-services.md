---
title: Importare una configurazione da Lifecycle Services
description: Questo argomento descrive come importare una nuova versione di una configurazione di creazione di report elettronici (ER) da Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 636ed27c157c8322cc1be4ca8eca10ef37eb8bbc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569511"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Importare una configurazione da Lifecycle Services

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per l'importazione di una [configurazione per la creazione di report elettronici (ER)](../general-electronic-reporting.md#Configuration) dalla [raccolta di cespiti a livello di progetto](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).

In questo esempio si dovrà selezionare la versione desiderata della configurazione ER e importarla per una società di esempio denominata Litware, Inc. Queste operazioni possono essere completate in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario completare i passaggi della procedura [Caricare una configurazione ER in Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). È richiesto anche l'accesso a LCS.

1. Accedere all'applicazione utilizzando uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Amministratore di sistema

2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Selezionare **Configurazioni**.

<a name="accessconditions"></a>
> [!NOTE]
> Assicurarsi che l'utente Dynamics 365 Finance corrente sia membro del progetto LCS che contiene la raccolta cespiti a cui l'utente vuole [accedere](../../lifecycle-services/asset-library.md#asset-library-support) per importare le configurazioni ER.
>
> Non è possibile accedere a un progetto LCS da un archivio ER che rappresenta un dominio diverso dal dominio utilizzato in Finance. Se si tenta, verrà visualizzato un elenco vuoto di progetti LCS e non è possibile importare le configurazioni ER dalla raccolta di cespiti a livello di progetto in LCS. Per accedere alle raccolte di cespiti a livello di progetto da un archivio ER utilizzato per importare le configurazioni ER, accedere a Finance utilizzando le credenziali di un utente che appartiene al tenant (dominio) per cui è stata fornita l'istanza di Finance corrente.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Eliminare una versione condivisa di una configurazione del modello dati

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Configurazione del modello di esempio**.

    La prima versione di una configurazione del modello dati di esempio è stata creata e pubblicata in LCS quando è stata completata la procedura in [Caricare una configurazione in Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). In questa procedura verrà eliminata questa versione della configurazione ER. Quindi quella versione verrà importata da LCS più avanti in questo argomento.

2. Nell'elenco trovare e selezionare il record desiderato.

    Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**. Questo stato indica che la configurazione è stata pubblicata in LCS.

3. Selezionare **Cambia stato**.
4. Selezionare **Interrotto**.

    Modificando lo stato della versione selezionata da **Condiviso** a **Interrotto** si rende la versione disponibile per l'eliminazione.

5. Selezionare **OK**.
6. Nell'elenco trovare e selezionare il record desiderato.

    Per questo esempio, selezionare la versione della configurazione con stato **Interrotto**.

7. Selezionare **Elimina**.
8. Selezionare **Sì**.

    Notare che solo la versione bozza 2 della configurazione selezionata del modello dati è ora disponibile.

9. Chiudere la pagina.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Importare una versione condivisa di una configurazione del modello dati da LCS

1. Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.

2. Nella sezione **Provider di configurazione** selezionare il riquadro **Litware, Inc.**.

3. Nel riquadro **Litware, Inc.** selezionare **Archivi**.

    Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.

4. Selezionare **Apri**.

    Per questo esempio, selezionare il record dell'archivio **LCS** e aprirlo. È necessario disporre dell'[accesso](#accessconditions) al progetto LCS e alla raccolta di cespiti a cui si accede dal repository ER selezionato.

5. Nell'elenco contrassegnare la riga selezionata.

    Per questo esempio, selezionare la prima versione della **Configurazione del modello di esempio** nell'elenco delle versioni.

6. Selezionare **Importa**.
7. Selezionare **Sì** per confermare l'importazione della versione selezionata da LCS.

    Un messaggio informativo conferma che la versione selezionata è stata importata correttamente.

8. Chiudere la pagina.
9. Chiudere la pagina.
10. Selezionare **Configurazioni**.
11. Nella struttura ad albero selezionare **Configurazione del modello di esempio**.
12. Nell'elenco trovare e selezionare il record desiderato.

    Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.

    Notare che anche la versione condivisa 1 della configurazione selezionata del modello dati è ora disponibile.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]