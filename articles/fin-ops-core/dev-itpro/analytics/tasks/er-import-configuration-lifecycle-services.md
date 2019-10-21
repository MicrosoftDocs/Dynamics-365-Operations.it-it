---
title: ER importa una configurazione da Lifecycle Services
description: I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può importare una nuova configurazione per la creazione di report elettronici (ER) da Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable,  ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0830707885e8ed52581aa789df0279d78e3a9c10
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184832"
---
# <a name="er-import-a-configuration-from-lifecycle-services"></a>ER importa una configurazione da Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può importare una nuova configurazione per la creazione di report elettronici (ER) da Microsoft Lifecycle Services (LCS).

In questo esempio si dovrà selezionare la versione desiderata della configurazione ER e importarla per la società di esempio, Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario completare i passaggi della procedura "Caricare una configurazione ER in Lifecycle Services". L'accesso a LCS è necessario anche per il completamento delle operazioni indicate di seguito.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic Configurazioni:

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Eliminare una versione condivisa della configurazione del modello dati
1. Nella struttura selezionare "Configurazione del modello di esempio".
    * La prima versione di una configurazione del modello dati di esempio è stata creata e pubblicata in LCS durante la procedura "Caricare una configurazione ER in Lifecycle Services". In questa procedura verrà eliminata questa versione della configurazione ER. Questa versione di una configurazione del modello dati di esempio verrà importata più avanti da LCS.  
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la versione di questa configurazione con stato "Condiviso". Questo stato indica che la configurazione è stata pubblicata in LCS.  
3. Fare clic su Cambia stato.
4. Fare clic su Sospendi.
    * Modificare lo stato della versione selezionata da "Condiviso" a “Interrotto" per renderla disponibile per l'eliminazione.  
5. Fare clic su OK.
6. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la versione di questa configurazione con stato "Interrotto".  
7. Fare clic su Elimina.
8. Fare clic su Sì.
    * Solo la versione bozza 2 della configurazione selezionata del modello dati è disponibile.  
9. Chiudere la pagina.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Importare una versione condivisa della configurazione del modello dati da LCS
1. Nell'elenco contrassegnare la riga selezionata.
    * Aprire l'elenco degli archivi per il provider di configurazione per Litware, Inc.  
2. Fare clic su Archivi.
3. Fare clic su Apri.
    * Selezionare l'archivio LCS e aprirlo.  
4. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare la prima versione della "Configurazione del modello di esempio" nell'elenco delle versioni.  
5. Fare clic su Importa.
6. Fare clic su Sì.
    * Confermare l'importazione della versione selezionata dal LCS.  
    * Il messaggio informativo (sopra il modulo) conferma il completamento dell'importazione della versione selezionata.  
7. Chiudere la pagina.
8. Chiudere la pagina.
9. Fare clic Configurazioni:
10. Nella struttura selezionare "Configurazione del modello di esempio".
11. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la versione di questa configurazione con stato "Condiviso".  
    * Anche la versione condivisa 1 della configurazione selezionata del modello dati è ora disponibile.  

