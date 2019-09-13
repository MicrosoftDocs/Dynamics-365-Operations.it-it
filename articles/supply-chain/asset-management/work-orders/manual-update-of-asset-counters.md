---
title: Aggiornamento manuale dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento manuale dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875737"
---
# <a name="manual-update-of-asset-counters"></a>Aggiornamento manuale dei contatori di cespiti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


I contatori sono utilizzati per creare registrazioni in un cespite in relazione, ad esempio, al numero di ore in esecuzione o al numero di quantità prodotte.

Se il tipo di contatore selezionato per un contatore è impostato per ereditare valori di contatore (**Gestione cespiti** > **Impostazione** > **Tipi di cespite** > **Contatori** >  Scheda dettaglio **Generale** > interruttore **Eredita valori contatore cespiti** impostato su "Sì"), quando si crea una nuova riga contatore di quel tipo, ogni cespite figlio che utilizza lo stesso tipo di contatore viene aggiornato automaticamente.

In **Tutti i cespiti** si creano registrazioni contatore di ore o quantità di un cespite, in base alle letture nel cespite.

1. Fare clic su **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.

2. Selezionare il cespite nell'elenco e fare clic su **Contatori**. Nel modulo **Contatori cespiti**, viene visualizzato un elenco di tutte le registrazioni contatore precedenti del cespite selezionato.

3. Fare clic su **Nuovo** per creare una nuova registrazione. L'ID cespite viene immesso automaticamente.

4. Nel campo **Contatore** selezionare il contatore pertinente. Solo i contatori relativi al tipo di cespite selezionato nel cespite sono disponibili. L'unità correlata viene immessa automaticamente nel campo **Unità**.

5. Selezionare la data e l'ora per la registrazione contatore.

6. Nel campo **Valore**, immettere il numero dall'ultima registrazione contatore o, nel campo **Valore aggregato**, immettere il conteggio totale.

- Se si installa fisicamente un nuovo contatore in un cespite, è necessario registrare la modifica nel cespite in **Contatori cespiti**. Successivamente, è necessario creare due righe di registrazione con timbri data/ora identici e nella riga relativa al nuovo contatore, selezionare la casella di controllo **Reimposta contatore**. Quando si creano due righe di registrazione, la prima deve essere per il contatore che si sostituisce. Nel campo **Totali**, il conteggio totale è la somma di tutti i valori registrati del contatore in base a quel tipo di contatore.  
- Se la casella di controllo **Reimposta contatore** è selezionata in un cespite che utilizza un piano di manutenzione con un tipo di intervallo "Una volta da..." o "Quando...", il contatore è ancora attivo nella riga del nuovo contatore poiché si è creata un riga contatore distinta e si è iniziato con un nuovo contatore.

![Figura 1](media/11-work-orders.png)


Se è necessario eseguire registrazioni contatore in più cespiti, è possibile farlo in **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Contatori cespiti**.

>[!NOTE]
>È possibile impostare un intervallo per definire gli scostamenti nelle registrazioni contatore manuali e il tipo di messaggio da visualizzare se le registrazioni non rientrano nell'intervallo definito. Leggere l'argomento [Contatori](../setup-for-objects/counters.md) relativo all'impostazione di contatori.
