---
title: Creare fornitori di configurazioni e contrassegnarli come attivi
description: In questo articolo viene descritto come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione.
author: kfend
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
ms.openlocfilehash: db5226720a4e0c0f167921a972429c0a5ecdd2e9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267815"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Creare fornitori di configurazioni e contrassegnarli come attivi

[!include [banner](../../includes/banner.md)]

In questo articolo viene descritto come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici. Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione. In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.

## <a name="create-a-provider"></a>Creare un provider
1. Andare al **pannello di navigazione** nell'angolo in alto a sinistra e selezionare **Amministrazione organizzazione**.
2. Andare a **Aree di lavoro > Creazione di report elettronici**.
3. Andare a **Collegamenti correlati > Provider di configurazione**.
4. Selezionare **Nuovo**.
    - Un record del provider ha un nome e un URL univoci. Rivedere il contenuto di questa pagina e ignorare questa procedura se esiste già un record per Litware, Inc. (https://www.litware.com).  
5. Nel campo Nome, digitare `Litware, Inc.`.
6. Nel campo Indirizzo Internet digitare `https://www.litware.com`.
7. Selezionare **Salva**.
8. Chiudere la pagina.

## <a name="select-as-an-active-provider"></a>Selezionare il provider come attivo
1. Selezionare il provider Litware, Inc. .
2. Selezionare **Imposta come attivo**.

![Pagina dell'area di lavoro Creazione di report elettronici.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
