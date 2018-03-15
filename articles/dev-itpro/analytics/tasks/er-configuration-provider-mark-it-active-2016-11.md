--- 
title: Creare e attivare un provider di configurazione per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
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
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 018aee917c13f576759ebd812d31cbc9d83e2d1a
ms.contentlocale: it-it
ms.lasthandoff: 02/23/2018

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a>Creare e attivare un provider di configurazione per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici. Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione. In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.


## <a name="create-a-provider"></a>Creare un provider
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Provider di configurazione.
3. Fare clic su Nuovo.
    * Un record del provider ha un nome e un URL univoci. Rivedere il contenuto di questa pagina e ignorare questa procedura se un record per (`http://www.litware.com`) è già esistente.  
4. Nel campo Nome digitare Litware, Inc.
    * Litware, Inc.  
5. Nel campo Indirizzo Internet digitare `http://www.litware.com`.
6. Fare clic su Salva.
7. Chiudere la pagina.

## <a name="select-as-an-active-provider"></a>Selezionare il provider come attivo
1. Selezionare il provider Litware, Inc. .
2. Fare clic su Imposta attivo.


