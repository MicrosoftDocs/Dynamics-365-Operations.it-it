---
title: Spostare, sostituire e installare cespiti
description: Viene descritto come spostare, sostituire e installare cespiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0e6306698d351d33cae627e3741ad9a2eb6d893
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783389"
---
# <a name="move-replace-and-install-assets"></a>Spostare, sostituire e installare cespiti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Viene descritto come spostare, sostituire e installare cespiti in Gestione cespiti. È possibile creare singoli cespiti che non hanno relazioni ad altri cespiti, oppure creare una struttura di cespiti che include un cespite padre (cespite di primo livello) e cespiti figlio correlati (cespiti secondari). In Gestione cespiti, sono disponibili tre metodi per spostare e di cambiare l'ubicazione di un cespite:

- **Spostamento**- sposta il cespite in un'altra struttura di cespiti o in un'altra ubicazione nella stessa struttura di cespiti.
- **Sostituzione** - Rimuove temporaneamente un cespite da una struttura di cespiti perché possa essere riparato o rinnovato, quindi aggiunge il cespite rinnovato alla stessa struttura di cespiti in un secondo momento. In alternativa, sostituisce definitivamente un cespite con un nuovo cespite.
- **Installazione** - Installa un cespite padre e tutti i cespiti figlio correlati in una unità funzionale.

> [!NOTE]
> Cespite che si sposta, sostituisce o installa potrebbe essere correlato a un'altra unità funzionale. In tal caso, il cespite potrebbe utilizzare le dimensioni finanziarie dell'unità funzionale. Nella pagina **Tipi di unità funzionali**, è possibile impostare la gestione delle dimensioni finanziarie nelle unità funzionali.

## <a name="move-asset"></a>Sposta cespite

Usare la funzione **Sposta cespite** per spostare il cespite in un'altra struttura di cespiti o in un'altra ubicazione nella stessa struttura di cespiti. È inoltre possibile spostare un cespite da una struttura dei cespiti in modo che si trasformi in un cespite autonomo che non ha relazioni di struttura.

> [!NOTE]
> Non utilizzare questa funzione se i cespiti sono in riparazione o vengono temporaneamente sostituiti. Invece, utilizzare la funzionalità **Sostituisci cespite** che viene descritta più avanti in questo argomento.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.
2. Selezionare il cespite da spostare nell'elenco. Se il cespite ha cespiti figlio, si spostano anche quelli.
3. Selezionare **Sposta cespite**.
4. Per spostare il cespite in modo che diventi parte di una struttura di cespiti, selezionare il nuovo cespite padre nel campo **Cespite padre**. Se si sposta un cespite figlio e si desidera renderlo un cespite autonomo che non ha relazioni di struttura, lasciare vuoto il campo **Cespite padre**.
5. Il campo **Validità** viene impostato automaticamente sulla data e ora corrente. Tuttavia, è possibile selezionare una data e un'ora diverse per l'inizio della validità dello movimento del cespite.
6. Selezionare **OK**.

## <a name="replace-asset"></a>Sostituisci cespite

Utilizzare la funzione **Sostituisci cespite** in relazione alle riparazioni, al rinnovo, o la sostituzione permanente di un cespite logoro con un nuovo cespite. Questa funzione viene utilizzata per sostituire i cespiti figlio in una struttura di cespiti. Per i cespiti padre (ovvero cespiti che non hanno attualmente un cespite padre), la sostituzione viene effettuata in un'unità funzionale. Per ulteriori informazioni su come sostituire i cespiti padre in un'unità funzionale, vedere [Installare cespiti nelle unità funzionali](../functional-locations/install-objects-on-functional-locations.md).

> [!NOTE]
> Se l'officina riparazioni è correlata al reparto di produzione, è possibile creare unità funzionali quali **Riparazione**, **Scarti** e **Immagazzinamento** per gestire la riparazione e la sostituzione dei cespiti.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.
2. Nell'elenco selezionare il cespite figlio da sostituire. Se il cespite ha cespiti figlio, si sostituiscono anche quelli.
3. Selezionare **Sostituisci cespite**.

    Il campo **Struttura modificata** indica la data e ora dell'ultimo spostamento del cespite selezionato e i cespiti figlio correlati nella struttura di cespiti.

4. Nella sezione **Cespite selezionato**, nel campo **Unità funzionale di destinazione**, selezionare l'unità funzionale in cui spostare il cespite. Ad esempio, selezionare **Scarti** o **Riparazione**.

    Nella sezione **Cespite padre**, il campo **Validità** indica la data e ora dell'ultima installazione o spostamento del cespite padre e i cespiti figlio correlati nell'unità funzionale corrente.

5. Nella sezione **Nuovo cespite**, nel campo **Cespite**, selezionare il cespite da inserire in sostituzione permanente o temporanea del cespite selezionato. Questo cespite potrebbe essere attualmente ubicato in un'altra unità funzionale, ad esempio **Immagazzinamento**.
7. Nella sezione **Data di inizio validità** Il campo **Validità** viene impostato automaticamente sulla data e ora corrente. Tuttavia, è possibile selezionare una data e un'ora diverse per l'inizio della validità della sostituzione del cespite.
8. Selezionare **OK**.

## <a name="install-asset"></a>Installa cespite

Utilizzare la funzione **Installa cespite** per installare una struttura di cespiti in una unità funzionale.

> [!NOTE]
> Selezionare sempre un cespite padre. Il cespite padre e i cespiti figlio correlati verranno spostati nell'unità funzionale selezionata.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.
2. Nell'elenco, selezionare il cespite padre da installare in un'altra unità funzionale.
3. Selezionare **Installa cespite**.

    La sezione **Attributi** mostra gli attributi cespite impostati sul cespite padre.

4. Selezionare la nuova ubicazione nel campo **Unità funzionale**.
5. Il campo **Validità** viene impostato automaticamente sulla data e ora corrente. Tuttavia, è possibile selezionare una data e un'ora diverse per l'inizio della validità della installazione nella struttura di cespiti.
6. Selezionare **OK**.
