---
title: Integrazione di note
description: In questo articolo viene descritta l'integrazione dei dati delle note in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f09d455181b7929e25d5238949a0236ac60d457b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289018"
---
# <a name="note-integration"></a>Integrazione di note

[!include [banner](../../includes/banner.md)]



Durante i processi aziendali, gli utenti di Microsoft Dynamics 365 spesso raccolgono informazioni sui propri clienti. Queste informazioni vengono registrate come attività e note. In questo articolo viene descritta l'integrazione dei dati delle note in doppia scrittura.

Le informazioni sui clienti possono essere classificate nei seguenti modi:

+ **Informazioni utilizzabili che un utente Dynamics 365 gestisce per conto di un cliente** - Ad esempio, Contoso (un utente di Dynamics 365) conduce un gioco a premi. Uno dei clienti di Contoso (un cliente) vuole partecipare al gioco a premi. Il cliente chiede a un dipendente di Contoso di iscriverlo a tale gioco a premi. La prenotazione viene effettuata nel calendario del partecipante all'evento di Contoso.
+ **Informazioni utilizzabili per un utente Dynamics 365** - Ad esempio, un cliente che acquista un'unità Surface inserisce istruzioni speciali con cui richiede una confezione regalo per il dispositivo prima della consegna. Queste istruzioni sono informazioni utilizzabili che devono essere gestite dal dipendente Contoso responsabile della confezione regalo.
+ **Informazioni non utilizzabili** - Ad esempio, un cliente visita il punto vendita Contoso e, durante la conversazione con un addetto del punto vendita, esprime interesse per i giochi e gli accessori per giochi *Halo*. L'addetto del punto vendita prende nota di queste informazioni. Il motore dei suggerimenti sui prodotti le utilizza quindi per fornire suggerimenti al cliente.

In genere, le informazioni utilizzabili vengono acquisite come *attività* nelle app per la finanza e le operazioni e nelle app di interazione con i clienti. Le informazioni non utilizzabili vengono acquisite come *note* nelle app per la finanza e le operazioni e come *annotazioni* nelle app di interazione con i clienti.

> [!TIP]
> Sebbene le note siano destinate alle informazioni non utilizzabili, le app non ne impediranno l'utilizzo per archiviare e gestire informazioni utilizzabili se si intende farlo.

Microsoft sta attualmente rilasciando funzionalità per l'integrazione delle note. (la funzionalità per l'integrazione delle attività verrà rilasciata in seguito). L'integrazione delle note è disponibile per clienti, fornitori, ordini di vendita e ordine fornitore.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Creare una nota in un'app di interazione con i clienti

Per creare una nota in un'app di interazione con i clienti e quindi sincronizzarla con un'app per la finanza e le operazioni, procedere come segue.

1. Nell'app di interazione con i clienti, aprire il record account per un cliente.
2. Nel riquadro **Sequenza temporale**, selezionare il segno più (**+**), quindi selezionare **Nota** per creare una nota.

    ![Creare una nota nell'app di interazione con i clienti.](media/notes-ce-1.png)

3. Immettere un titolo e una descrizione, quindi selezionare **Aggiungi nota**.

    ![Immettere un titolo e una descrizione.](media/notes-ce-2.png)

    La nuova nota viene aggiunta alla sequenza temporale del cliente.

    ![Nuova nota nella sequenza temporale del cliente.](media/notes-ce-3.png)

4. Accedere all'app per la finanza e le operazioni e aprire lo stesso record cliente. Si noti che il pulsante **Allegati** (simbolo della graffetta) nell'angolo in alto a destra indica che il record ha un allegato.

    ![Notifica su un allegato.](media/notes-ce-4.png)

5. Selezionare il pulsante **Allegati** per aprire la pagina **Allegati**. La nota creata dovrebbe essere nell'app di interazione con i clienti.

    ![Nota nell'app di interazione con i clienti.](media/notes-ce-5.png)

Tutti gli aggiornamenti della nota vengono sincronizzati tra l'app per la finanza e le operazioni e l'app di interazione con i clienti.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Creare una nota in un'app per la finanza e le operazioni

È anche possibile creare una nota in un'app per la finanza e le operazioni, che verrà sincronizzata con un'app di interazione con i clienti.

Per creare una nota in un'app per la finanza e le operazioni e quindi sincronizzarla con un'app di interazione con i clienti, procedere come segue.

1. Nell'app per la finanza e le operazioni, nella pagina **Allegati**, selezionare **Nuovo** \> **Nota**.

    ![Creazione di una nota nell'app per la finanza e le operazioni.](media/notes-fo-1.png)

2. Immettere un titolo e una breve serie di istruzioni, quindi selezionare **Salva**.

    ![Immettere un titolo e istruzioni.](media/notes-fo-2.png)

3. Nell'app di di interazione con i clienti, aggiornare il record. La nuova nota dovrebbe essere nella sequenza temporale.

    ![Nuova nota nella sequenza temporale dell'app di interazione con i clienti.](media/notes-fo-3.png)

È possibile classificare una nota come interna o esterna.

- Nell'app per la finanza e le operazioni, nella pagina **Allegati**, aprire la nota e nel campo **Restrizione**, selezionare **Interna** o **Esterna**.

    ![Campo Restrizione.](media/notes-fo-4.png)

È inoltre possibile creare un URL.

1. Nell'app per la finanza e le operazioni, nella pagina **Allegati**, selezionare **Nuovo** \> **URL**.
2. Immettere un titolo e un URL.
3. Nel campo **Restrizione**, selezionare **Interna** o **Esterna**.

    ![Creazione di un URL nell'app per la finanza e le operazioni.](media/notes-fo-5.png)

4. Seleziona **Salva**.

    Poiché le app di interazione dei clienti non hanno un tipo di URL, l'URL è integrato con la doppia scrittura come nota.

    ![URL visualizzato come nota nell'app di interazione con i clienti.](media/notes-ce-6.png)

> [!NOTE]
> Gli allegati di file non sono supportati.

## <a name="templates"></a>Modelli

L'integrazione delle note include una raccolta di mappe della tabella che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App per la finanza e le operazioni | App di interazione con i clienti | Description |
|----------------------------|-------------------------|-------------|
| [Allegati cliente](mapping-reference.md#230) | Annotazioni | Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sui clienti (per le organizzazioni e per le persone). |
| [Allegati documento fornitore](mapping-reference.md#231) | Annotazioni | Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sui fornitori (per le organizzazioni e per le persone). |
| [Allegati documento intestazione ordine cliente](mapping-reference.md#229) | Annotazioni | Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sugli ordini di vendita. |
| [Allegati documento intestazione ordine fornitore](mapping-reference.md#232) | Annotazioni | Aziende che utilizzano testo normale e URL per acquisire informazioni specifiche sugli ordine fornitore. |

## <a name="limitations"></a>Limiti

Una volta installata la soluzione per le note, non è possibile disinstallarla. 

Per ulteriori informazioni, vedere [Riferimento per il mapping a doppia scrittura](mapping-reference.md).

