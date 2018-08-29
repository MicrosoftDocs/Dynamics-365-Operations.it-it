--- 
title: Caricare configurazioni per la creazione di report elettronici in Lifecycle Services
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) e caricarla in Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 6aa6bf7e08285d18210741ba6618878955009280
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="upload-electronic-reporting-configurations-into-lifecycle-services"></a>Caricare configurazioni per la creazione di report elettronici in Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici (ER) e caricarla in Microsoft Lifecycle Services (LCS).

In questo esempio verrà creata una configurazione che sarà caricata in LCS per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo". L'accesso a LCS è necessario anche per il completamento delle operazioni indicate di seguito.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Selezionare "Litware, Inc." e impostarlo come attivo.
3. Fare clic Configurazioni:

## <a name="create-a-new-data-model-configuration"></a>Crea una nuova configurazione di modello dati
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
    * Verrà creata una configurazione che contiene un modello dati di esempio per i documenti elettronici. Questa configurazione del modello dati verrà caricata successivamente in LCS.  
2. Nel campo Nome digitare "Configurazione del modello di esempio".
    * Configurazione del modello di esempio  
3. Nel campo Descrizione digitare "Configurazione del modello di esempio".
    * Configurazione del modello di esempio  
4. Fare clic su Crea configurazione.
5. Fare clic su Progettazione modello.
6. Fare clic su Nuovo.
7. Nel campo Nome digitare "Punto di ingresso".
    * Punto di ingresso  
8. Scegliere Aggiungi.
9. Fare clic su Salva.
10. Chiudere la pagina.
11. Fare clic su Cambia stato.
12. Fare clic su Completa.
13. Fare clic su OK.

## <a name="register-a-new--repository"></a>Registrare un nuovo archivio
1. Chiudere la pagina.
2. Fare clic su Archivi.
    * In questo modo è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.  
3. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
    * Ciò consente di aggiungere un nuovo archivio.  
4. Nel campo Tipo di archivio di configurazioni selezionare LCS.
5. Fare clic su Crea archivio.
6. Nel campo Progetto immettere o selezionare un valore.
    * Selezionare il progetto LCS desiderato. È necessario disporre dell'accesso al progetto.  
7. Fare clic su OK.
    * Completare una nuova voce di archivio.  
8. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare il record Archivio LCS.  
    * Un archivio registrato è contrassegnato dal fornitore corrente, pertanto le sole configurazioni di proprietà dal fornitore possono essere posizionate nell'archivio e, di conseguenza, essere caricate nel progetto LCS selezionato.  
9. Fare clic su Apri.
    * Aprire l'archivio per visualizzare l'elenco delle configurazioni ER. Sarà vuoto se questo progetto non è stato ancora utilizzato per condividere configurazioni ER.  
10. Chiudere la pagina.
11. Chiudere la pagina.

## <a name="upload-configuration-into-lcs"></a>Caricare la configurazione in LCS
1. Fare clic Configurazioni:
2. Nella struttura selezionare "Configurazione del modello di esempio".
    * Selezionare una configurazione creata che è già stata completata.  
3. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la versione della configurazione selezionata con stato "Completato".  
4. Fare clic su Cambia stato.
5. Fare clic su Condividi.
    * Lo stato della configurazione verrà cambiato da "Completato “a "Condiviso" quando verrà pubblicato in LCS.  
6. Fare clic su OK.
7. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la versione di configurazione con stato "Condiviso".  
    * Lo stato della versione selezionata è cambiato da "Completato" a "Condiviso".  
8. Chiudere la pagina.
9. Fare clic su Archivi.
    * In questo modo è possibile aprire l'elenco di archivi per il provider di configurazione Litware, Inc.  
10. Fare clic su Apri.
    * Selezionare l'archivio LCS e aprirlo.  
    * La configurazione selezionata viene visualizzata come cespite del progetto LCS selezionato.  
    * Aprire LCS usando https://lcs.dynamics.com. Aprire un progetto utilizzato in precedenza per la registrazione di archivio, quindi aprire "Raccolta di risorse" di questo progetto ed espandere il contenuto del tipo di risorsa "Configurazione GER": la configurazione ER caricata sarà disponibile. La configurazione LCS caricata può essere inclusa in un'altra istanza di Microsoft Dynamics 365 for Finance and Operations se i fornitori hanno accesso a questo progetto LCS.  


