---
title: Caricare una configurazione in Lifecycle Services
description: Questo argomento illustra come creare una nuova configurazione per la creazione di report elettronici e caricarla in Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f17763236594092d04dfe2d2f9912e764b4f8d4
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562639"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Caricare una configurazione in Lifecycle Services

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova [configurazione per la creazione di report elettronici (ER)](../general-electronic-reporting.md#Configuration) e caricarla nella [raccolta di cespiti a livello di progetto](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).

In questo esempio verrà creata una configurazione che sarà caricata in LCS per la società di esempio denominata Litware, Inc. Queste operazioni possono essere completate in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario dapprima completare i passaggi in [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). È richiesto anche l'accesso a LCS.

1. Accedere all'applicazione utilizzando uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Amministratore di sistema

2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Selezionare **Litware, Inc.** e impostarlo come **attivo**.
4. Selezionare **Configurazioni**.

<a name="accessconditions"></a>
> [!NOTE]
> Assicurarsi che l'utente Dynamics 365 Finance corrente sia membro del progetto LCS che contiene la [raccolta cespiti](../../lifecycle-services/asset-library.md#asset-library-support) che viene utilizzata per importare le configurazioni ER.
>
> Non è possibile accedere a un progetto LCS da un archivio ER che rappresenta un dominio diverso dal dominio utilizzato in Finance. Se si tenta, verrà visualizzato un elenco vuoto di progetti LCS e non è possibile importare le configurazioni ER dalla raccolta di cespiti a livello di progetto in LCS. Per accedere alle raccolte di cespiti a livello di progetto da un archivio ER utilizzato per importare le configurazioni ER, accedere a Finance utilizzando le credenziali di un utente che appartiene al tenant (dominio) per cui è stata fornita l'istanza di Finance corrente.

## <a name="create-a-new-data-model-configuration"></a>Creare una nuova configurazione del modello di dati

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni** selezionare **Crea configurazione** per aprire la finestra di dialogo a discesa.

    In questo esempio verrà creata una configurazione che contiene un modello dati di esempio per i documenti elettronici. Questa configurazione del modello dati verrà caricata successivamente in LCS.

3. Nel campo **Nome** digitare **Configurazione del modello di esempio**.
4. Nel campo **Descrizione** digitare **Configurazione del modello di esempio**.
5. Selezionare **Crea configurazione**.
6. Selezionare **Progettazione modello**.
7. Selezionare **Nuovo**.
8. Nel campo **Nome**, immettere **Punto di ingresso**.
9. Selezionare **Aggiungi**.
10. Selezionare **Salva**.
11. Chiudere la pagina.
12. Selezionare **Cambia stato**.
13. Selezionare **Completa**.
14. Selezionare **OK**.
15. Chiudere la pagina.

## <a name="register-a-new-repository"></a>Registrare un nuovo archivio

1. Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.

2. Nella sezione **Provider di configurazione** selezionare il riquadro **Litware, Inc.**.

3. Nel riquadro **Litware, Inc.** selezionare **Archivi**.

    Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.

4. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.

    Ora è possibile aggiungere un nuovo archivio.

5. Nel campo dell'**archivio di configurazioni** selezionare **LCS**.
6. Selezionare **Crea archivio**.
7. Nel campo **Progetto** immettere o selezionare un valore.

    Per questo esempio, selezionare il progetto LCS desiderato. È necessario disporre dell'[accesso](#accessconditions) al progetto.

8. Selezionare **OK**.

    Completare una nuova voce di archivio.

9. Nell'elenco contrassegnare la riga selezionata.

    Per questo esempio, selezionare il record dell'archivio **LCS**.

    Notare che un archivio registrato è contrassegnato dal provider corrente. In altre parole, solo le configurazioni di proprietà di quel provider possono essere inserite in questo archivio e quindi caricate nel progetto LCS selezionato.

10. Selezionare **Apri**.

    Aprire l'archivio per visualizzare l'elenco delle configurazioni ER. Se il progetto selezionato non è stato ancora utilizzato per condividere configurazioni ER, l'elenco sarà vuoto.

11. Chiudere la pagina.
12. Chiudere la pagina.

## <a name="upload-a-configuration-into-lcs"></a>Caricare una configurazione in LCS

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Configurazione del modello di esempio**.

    È necessario selezionare una configurazione creata che è già stata completata.

3. Nell'elenco trovare e selezionare il record desiderato.

    Per questo esempio, selezionare la versione della configurazione selezionata con stato **Completato**.

4. Selezionare **Cambia stato**.
5. Selezionare **Condividi**.

    Lo stato della configurazione viene modificato da **Completato** in **Condiviso** quando la configurazione viene pubblicata in LCS.

6. Selezionare **OK**.
7. Nell'elenco trovare e selezionare il record desiderato.

    Per questo esempio, selezionare la versione della configurazione con stato **Condiviso**.

    Lo stato della versione selezionata è cambiato da **Completato** a **Condiviso**.

8. Chiudere la pagina.
9. Selezionare **Archivi**.

    Ora è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.

10. Selezionare **Apri**.

    Per questo esempio, selezionare il record dell'archivio **LCS** e aprirlo.

    Notare che la configurazione selezionata viene visualizzata come cespite del progetto LCS selezionato.

11. Aprire LCS andando in <https://lcs.dynamics.com>.
12. Aprire un progetto che è stato utilizzato in precedenza per la registrazione del repository.
13. Aprire la raccolta di cespiti del progetto.
14. Selezionare il tipo di cespite **Configurazione ER**.

    La configurazione ER che hai caricato dovrebbe essere elencata.

    La configurazione LCS caricata può essere inclusa in un'altra istanza se i fornitori hanno accesso a questo progetto LCS.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]