--- 
title: Creare e attivare un provider di configurazione per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bdb3a3857a7293828a7766b6988c123a43e0673c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-configuration-providand-mark-it-as-active-for-electronic-reporting-er"></a>Creare e attivare un provider di configurazione per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici. Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione. In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.


## <a name="create-a-provider"></a>Creare un provider
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Provider di configurazione.
3. Fare clic su Nuovo.
    * Un record del provider ha un nome e un URL univoci. Esaminare il contenuto della pagina e ignorare questa procedura se un record per Litware, Inc. (http://www.litware.com) esiste già.  
4. Nel campo Nome digitare Litware, Inc.
    * Litware, Inc.  
5. Nel campo dell'indirizzo Internet immettere http://www.litware.com.
    * http://www.litware.com  
6. Fare clic su Salva.
7. Chiudere la pagina.

## <a name="select-as-an-active-provider"></a>Selezionare il provider come attivo
1. Selezionare il provider Litware, Inc. .
2. Fare clic su Imposta attivo.


