---
title: Creare provider di configurazione e contrassegnarli come attivi
description: I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544911"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Creare provider di configurazione e contrassegnarli come attivi

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici. Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione. In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.


## <a name="create-a-provider"></a>Creare un provider
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Provider di configurazione.
3. Fare clic su Nuovo.
    * Un record del provider ha un nome e un URL univoci. Rivedere il contenuto di questa pagina e ignorare questa procedura se esiste già un record per Litware, Inc. (http://www.litware.com).  
4. Nel campo Nome digitare Litware, Inc.
    * Litware, Inc.  
5. Nel campo Indirizzo Internet digitare "http://www.litware.com".
    * http://www.litware.com  
6. Fare clic su Salva.
7. Chiudere la pagina.

## <a name="select-as-an-active-provider"></a>Selezionare il provider come attivo
1. Selezionare il provider Litware, Inc. .
2. Fare clic su Imposta attivo.

