--- 
title: Immettere e confrontare le offerte RdO e assegnare i contratti
description: Questa procedura mostra come immettere le risposte a una RdO, valutare e confrontare le offerte e infine assegnare l'offerta a uno dei fornitori.
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Immettere e confrontare le offerte RdO e assegnare i contratti

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come immettere le risposte a una RdO, valutare e confrontare le offerte e infine assegnare l'offerta a uno dei fornitori. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. Prima di iniziare, è necessario disporre di una RdO con due righe inviata ad almeno due fornitori. È possibile eseguire la procedura "Creare richieste di offerta" come prerequisito per la creazione. È necessario avere impostato criteri di assegnazione del punteggio per poter eseguire questa procedura.


## <a name="enter-a-reply-from-a-vendor"></a>Immettere una risposta di un fornitore
1. Andare ad Approvvigionamento > Richieste di offerta > Tutte le richieste di offerta.
2. Selezionare una RdO con stato di inviato e fare clic sul collegamento nel numero di caso Richiesta di offerta.
    * La richiesta di offerta deve essere stata inviata ad almeno 2 fornitori.  
3. Fare clic sull'intestazione per accedere all'elenco dei fornitori.
4. Selezionare il fornitore per cui si desidera immettere una risposta alla RdO.
5. Fare clic su Inserisci risposta.
6. Nel Riquadro azioni fare clic su Rispondi.
7. Fare clic su Copia dati per rispondere.
    * Questa azione copierà i dati selezionati, ad esempio, la quantità del caso RdO nella risposta RdO. In alternativa, è possibile ignorare questa azione e compilare tutti i campi di risposta manualmente quando si modifica la risposta.  
8. Fare clic su Modifica.
9. Nel campo Prezzo unitario immettere un numero.
10. Selezionare l'altra riga dell'offerta.
11. Nel campo Prezzo unitario immettere un numero.

## <a name="score-the-bid"></a>Assegnare un punteggio all'offerta
1. Fare clic sull'intestazione per accedere al punteggio dell'offerta.
2. Espandere la sezione Punteggio offerta.
3. Nel campo Punteggio immettere un numero per uno dei criteri di assegnazione del punteggio.
    * Se si passa su uno dei criteri di assegnazione del punteggio, una descrizione comando mostra l'intervallo entro cui scegliere il punteggio da assegnare. In questo demo è possibile aggiungere un numero compreso tra 1 e 5 a uno dei criteri.  
4. Selezionare un altro criterio di assegnazione del punteggio.
5. Nel campo Punteggio immettere un numero.
6. Espandere la sezione Questionari.
    * Se il caso RdO contiene un questionario inviato ai fornitori, è possibile immettere le relative risposte nella sezione del questionario.  
7. Chiudere la pagina.

## <a name="enter-a-reply-for-another-vendor"></a>Immettere una risposta per un altro fornitore
1. Selezionare il fornitore successivo deselezionando il fornitore per il quale è stata appena immessa la risposta, quindi selezionando la riga per il fornitore successivo.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Fare clic su Inserisci risposta.
4. Fare clic su Copia dati per rispondere.
5. Fare clic su Modifica.
6. Nel campo Prezzo unitario immettere un numero.
7. Selezionare l'altra riga dell'offerta.
8. Nel campo Prezzo unitario immettere un numero.

## <a name="score-the-second-bid"></a>Assegnare un punteggio alla seconda offerta
1. Fare clic sull'intestazione per accedere al punteggio dell'offerta.
2. Nel campo Punteggio immettere un numero.
3. Nell'elenco trovare e selezionare il record desiderato.
4. Nel campo Punteggio immettere un numero.

## <a name="compare-the-replies"></a>Confrontare le risposte
1. Nel riquadro azioni fare clic su Generale.
2. Fare clic su Confronta risposte-
3. Nel campo Classificazione immettere un numero.
    * In questa pagina vengono visualizzate le offerte con l'intestazione e le righe e il punteggio totale a livello di intestazione. È possibile confrontare le righe ordinandole nella griglia in modo che le righe confrontabili siano l'una accanto all'altra. Sono indicate inoltre le seguenti informazioni. Quantità: la quantità indicata dal fornitore. Questa potrebbe essere diversa dalla quantità nella richiesta di offerta specificata.   Importo netto: il prezzo offerto da un fornitore, dopo la detrazione di eventuali sconti, per gli articoli nella riga.   Deviazione: il numero di giorni di differenza tra la data di consegna specificata nella riga o nell'intestazione dell'offerta e la data di consegna richiesta nella riga o nell'intestazione della RdO.   È possibile inserire una classificazione per ogni offerta.  
4. Selezionare la riga dell'intestazione dell'altra offerta che si desidera classificare.
5. Nel campo Classificazione immettere un numero.
6. Fare clic su Salva.

## <a name="reject-a-bid"></a>Rifiutare un'offerta
1. Selezionare la riga dell'intestazione dell'offerta che si desidera rifiutare.
    * È possibile solo accettare, rifiutare o restituire un'offerta o righe di un'offerta alla volta.  
2. Selezionare la casella di controllo Contrassegna.
    * Se si seleziona la casella di controllo Contrassegna nell'intestazione dell'offerta, verranno contrassegnate anche tutte le righe. È inoltre possibile scegliere di contrassegnare un sottoinsieme di righe nell'offerta per rifiutare o accettare tale sottoinsieme. È possibile accettare l'offerta di un fornitore per alcune righe di una RdO, quindi assegnare altre righe RdO a un fornitore diverso; tuttavia è necessario effettuare questa operazione in 2 passaggi, un'offerta alla volta. Se sono presenti righe alternative, è possibile accettare solo la riga di offerta originale o la relativa alternativa, ma non entrambe.  
3. Fare clic su Rifiuta.
4. Fare clic su Parametri per aprire la finestra di dialogo a discesa.
5. Nel campo Motivo rifiuto immettere o selezionare un valore.
    * Il motivo del rifiuto verrà archiviato nella risposta.  
6. Fare clic su OK.
7. Fare clic su OK.
8. Chiudere la pagina.
9. Chiudere la pagina.
10. Aggiorna la pagina.

## <a name="accept-a-bid"></a>Accettare un'offerta
1. Selezionare l'offerta che si desidera accettare, quindi fare clic sul collegamento nel campo Richiesta di offerta.
2. Nel Riquadro azioni fare clic su Rispondi.
3. Fare clic su Accetta.
    * Se sono state contrassegnate righe specifiche e non altre, l'azione di accettazione comprenderà solo le righe contrassegnate. Non è necessario contrassegnare le righe se si desidera accettare tutte quelle dell'offerta.  
4. Fare clic su Parametri per aprire la finestra di dialogo a discesa.
    * Consente di registrare un motivo per l'accettazione dell'offerta. Il motivo verrà archiviato nell'offerta.  
5. Nel campo Motivo accettazione immettere o selezionare un valore.
6. Fare clic su OK.
7. Fare clic su OK.
    * Quando si fa clic su OK, viene generato un ordine fornitore in base alle righe incluse nell'accettazione della RdO. Se sono presenti altre offerte che non sono state elaborate (accettate, rifiutate o restituite), il sistema chiederà di rifiutare le offerte rimanenti.  

## <a name="view-the-purchase-order-thats-been-generated"></a>Visualizzare l'ordine fornitore generato
1. Nel riquadro azioni fare clic su Generale.
2. Fare clic su Ordine acquisto.
    * Qui è possibile visualizzare l'ordine fornitore generato quando è stata accettata l'offerta.  
3. Chiudere la pagina.
4. Chiudere la pagina.
5. Chiudere la pagina.
6. Chiudere la pagina.


