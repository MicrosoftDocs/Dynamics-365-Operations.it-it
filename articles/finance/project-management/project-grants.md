---
title: Sovvenzioni progetto
description: In questo argomento viene illustrato come creare o modificare una sovvenzione.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282834"
---
# <a name="project-grants"></a>Sovvenzioni progetto

[!include [banner](../includes/banner.md)]

Una sovvenzione è un regalo in denaro per uno scopo o un progetto specifico. In genere, esistono restrizioni sulla modalità di spesa di una sovvenzione. In Gestione progetti e contabilità è possibile immettere sovvenzioni tracciate, nonché definirne le relazioni con progetti e contratti di progetto. ad esempio effettuando le seguenti attività:

- Associare sovvenzioni a progetti e fonti di finanziamento tramite collegamenti alle pagine **Progetto** e **Dettagli di contratto progetto**.
- Immettere e tenere traccia delle modifiche a una sovvenzione durante il passaggio da uno stato all'altro.
- Immettere e tenere traccia dei costi, importi richiesti e importi concessi.
- Creare sovvenzioni generali e associarvi sovvenzioni secondarie.

È possibile creare una sovvenzione immettendo tutti i dettagli in un nuovo record oppure copiare i dettagli da una sovvenzione esistente ed aggiornarla.

## <a name="create-a-new-grant"></a>Crea una nuova sovvenzione

1. Andare a **Gestione progetti e contabilità** \> **Sovvenzioni** \> **Sovvenzioni**.
2. Selezionare **Nuovo** \> **Sovvenzioni**.
3. Nella pagina dei dettagli delle sovvenzioni, nella scheda dettaglio **Generale**, nel campo **ID sovvenzione**, inserire un identificatore alfanumerico per la sovvenzione.
4. Nel campo **Nome sovvenzione** immettere un nome univoco per la sovvenzione.
5. Nel campo **Descrizione**, aggiungere dettagli sulla nuova sovvenzione.

    La maggior parte dei campi nella pagina è facoltativa ed è possibile immettere la quantità di informazioni desiderata.

    Nell'elenco riportato vengono descritte le informazioni specificate in ogni scheda dettaglio della pagina dei dettagli della sovvenzione:

    - **Generale** - Immettere il nome della sovvenzione, lo stato, la descrizione, lo scopo e l'importo della sovvenzione.
    - **Informazioni di contratto** – Immettere i dettagli relativi al personale, al dipartimento che gestisce la sovvenzione e al cliente della sovvenzione o all'origine dell'organizzazione della sovvenzione. È inoltre possibile indicare se l'organizzazione è un'entità pass-through che riceve la sovvenzione e quindi la trasferisce a un altro destinatario. Selezionare **Aggiungere** per aggiungere informazioni di contatto, ad esempio numeri di telefono e indirizzi di posta elettronica per l'organizzazione che fornisce la sovvenzione.
    - **Date e scadenze** – Immettere le date correlate alla sovvenzione e alle domanda di sovvenzione. Gli esempi includono la data di scadenza della domanda, la data di presentazione e la data in cui la sovvenzione viene approvata o respinta.
    - **Progetti associati e contratti di progetto** - È possibile inserire informazioni in questa scheda dettaglio solo se il campo **Stato sovvenzione** nella scheda dettaglio **Generale** è impostato su **Attivo** o **Concesso**. Selezionare tra le seguenti opzioni per completare l'attività correlata:

        - **Aggiungi fonte di finanziamento** - Aggiungere una nuova fonte di finanziamento per la sovvenzione. È possibile immettere tutti i dettagli ora o utilizzare le informazioni predefinite e aggiornarle in un secondo momento.
        - **Aggiungi contratto di progetto** - Aggiungere o aggiornare le informazioni sul contratto di progetto.
        - **Aggiungi progetto** - Aggiungere o aggiornare i dettagli del progetto.

    - **Impostazione** - Immettere i dettagli sui fondi corrispondenti, se questa informazione è necessaria. Molte organizzazioni che assegnano sovvenzioni richiedono che i destinatari spendano un determinato importo del proprio denaro o delle proprie risorse, per corrispondere all'importo assegnato nella sovvenzione. Nel campo **ID tracciabilità o progetto locale**, è possibile inserire un identificatore diverso dall'identificatore del progetto.

        > [!NOTE]
        > Se parte della sovvenzione sarà assegnata a un'altra organizzazione, impostare l'opzione **Garante** su **Sì**. Per le sovvenzioni concesse negli Stati Uniti, è possibile specificare se una sovvenzione verrà concessa in virtù di un mandato statale o federale.

    - **Dettagli prelievo di fondi** – Aggiungere o aggiornare le informazioni sulla frequenza con cui i fondi della sovvenzione possono essere ritirati, fatturati o spesi.

## <a name="create-a-new-grant-from-a-copy"></a>Creare una nuova sovvenzione da una copia

1. Andare a **Gestione progetti e contabilità** \> **Sovvenzioni** \> **Sovvenzioni**.
2. Selezionare **Nuovo** \> **Copia dalla sovvenzione**.
3. Immettere un identificatore alfanumerico e un nome per la nuova sovvenzione, quindi selezionare **OK**.
4. Nella pagina dei dettagli della sovvenzione, rivedere i dettagli della sovvenzione copiata e apportare le modifiche necessarie. La maggior parte dei campi nella pagina è facoltativa.

## <a name="view-or-modify-grant-details"></a>Visualizzare o modificare i dettagli della sovvenzione

1. Andare a **Gestione progetti e contabilità** \> **Sovvenzioni** \> **Sovvenzioni**.
2. Selezionare la sovvenzione da modificare.
3. Nel riquadro azioni, nella scheda **Sovvenzione**, nel gruppo **Gestisci**, selezionare **Modifica**.
4. Rivedere i dettagli della sovvenzione e apportare le modifiche necessarie.
