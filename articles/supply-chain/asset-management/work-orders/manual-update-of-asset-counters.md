---
title: Aggiornamento manuale dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento manuale dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23a94415a662059ddbd41cc6a0ba9dab24aae44e
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889435"
---
# <a name="manual-update-of-asset-counters"></a>Aggiornamento manuale dei contatori di cespiti

[!include [banner](../../includes/banner.md)]



I contatori vengono utilizzati per creare registrazioni su un cespite, ad esempio registrazioni sul numero di ore in cui il cespite è stato in funzione o sulla quantità che è stata prodotta.

Il tipo selezionato per un contatore può essere impostato per ereditare i valori del contatore. In altre parole, l'opzione **Eredita valori contatore cespiti** è impostata su **Sì** nella scheda dettaglio **Generale** della pagina **Contatori** (**Gestione cespiti** > **Impostazioni** > **Tipi del cespite** > **Contatori**). In questo caso, quando si crea una nuova riga per un contatore di quel tipo, ogni cespite figlio che utilizza lo stesso tipo di contatore viene automaticamente aggiornato.

Nella pagina **Tutti i cespiti** si creano le registrazioni contatore di ore o quantità di un cespite, in base alle letture nel cespite.

1. Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.

2. Selezione il cespite e nel riquadro azioni, nella scheda **Cespite**, nel gruppo **Preventivo**, selezionare **Contatori**. Nella pagina **Contatori cespiti** viene visualizzato un elenco di tutte le registrazioni contatore precedenti effettuate per il cespite selezionato.

3. Selezionare **Nuovo** per creare una registrazione. L'ID cespite verrà immesso automaticamente nel campo **Cespite**.

4. Nel campo **Contatore** selezionare il contatore pertinente. Solo i contatori relativi al tipo di cespite selezionato nel cespite sono disponibili per la selezione. L'unità correlata viene immessa automaticamente nel campo **Unità**.

5. Nel campo **Registrato**, selezionare la data e l'ora della registrazione del contatore.

6. Nel campo **Valore**, immettere il numero dell'ultima di registrazione. In alternativa, nel campo **Valore aggregato**, immettere il numero del conteggio totale.

Notare i punti seguenti:

- Se si installa fisicamente un nuovo contatore in un cespite, è necessario registrare la modifica nel cespite nella pagina **Contatori cespiti**. A questo punto, è necessario creare due righe di registrazione con timbro data/ora identico. La prima riga deve essere per il contatore che si sostituisce. Nella riga relativa al nuovo contatore, selezionare la casella di controllo **Reimposta contatore**. Nel campo **Totali**, il conteggio totale è la somma di tutti i valori registrati del contatore in base a quel tipo di contatore.

- Se la casella di controllo **Reimposta contatore** è selezionata in un cespite che utilizza un piano di manutenzione con un tipo di intervallo "Una volta da..." o "Quando...", il contatore è ancora attivo nella riga del nuovo contatore poiché si è creata un riga contatore distinta e si è iniziato con un nuovo contatore.

Nella figura seguente è illustrato un esempio della pagina **Contatori cespiti**.

![Figura 1](media/11-work-orders.png)

Nella pagina **Contatori cespiti** (**Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Contatori cespiti**), è possibile eseguire le registrazioni in più cespiti contemporaneamente, secondo le necessità.

>[!NOTE]
>È possibile impostare un intervallo per definire gli scostamenti rispetto alle registrazioni manuali. È inoltre possibile specificare il tipo di messaggio che verrà visualizzato se le registrazioni non rientrano nell'intervallo definito. Per ulteriori informazioni su come impostare i contatori, vedere [Contatori](../setup-for-objects/counters.md).

