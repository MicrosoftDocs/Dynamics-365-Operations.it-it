---
title: Immettere e confrontare le offerte RdO e assegnare i contratti
description: Questa argomento illustra come immettere le risposte a una richiesta di offerta (RdO), valutare e confrontare le offerte e infine assegnare il contratto a uno dei fornitori.
author: kamaybac
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable, PurchTablePart, PurchRFQCompareLinePrices, PurchRFQCompareRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0f1028211f3c9cc0082e127a24d10cd2fe9ab5ac903570664233b10e5737bee
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717150"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Immettere e confrontare le offerte RdO e assegnare i contratti

[!include [banner](../../includes/banner.md)]

Questa argomento illustra come immettere le risposte a una richiesta di offerta (RdO), valutare e confrontare le offerte e infine assegnare il contratto a uno dei fornitori. È possibile utilizzare questa procedura nella società di dati dimostrativi **USMF**.

Prima di iniziare questa procedura, è necessario disporre di una RdO con due righe e inviata ad almeno due fornitori. Per creare questo RdO, completare la procedura [Creare una richiesta di offerta](create-request-quotation.md). È necessario avere impostato criteri di assegnazione del punteggio per poter completare questa procedura.

È possibile immettere l'offerta come fornitore o responsabile approvvigionamenti. Per ulteriori informazioni, vedere [Impostare e gestire la collaborazione fornitore](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Immettere una risposta come fornitore

1. Vai a **Collaborazione fornitore \> Aree di lavoro \> Offerta fornitore**.
2. Nell'elenco **Nuovi inviti di offerta**, trovare una richiesta di offerta appena inviata. Selezionare la richiesta di offerta per verificare quanto è stato ordinato.
3. Selezionare **Allegati RdO** per esaminare gli eventuali allegati aggiunti.
4. Selezionare **Offerta** per rendere i campi modificabili. Si noti che il campo **Avanzamento offerta** è impostato su **Aggiornamento in corso del fornitore**.
5. Nell'intestazione e nelle righe, immettere i valori dalla risposta alla richiesta di offerta.
6. Se eventuali allegati devono essere aggiunti all'offerta, selezionare **Allegati offerta**.
7. Selezionare la scheda dettaglio **Elementi guida per offerta** per visualizzare se vi sono dei documenti richiesti.
8. Selezionare la scheda dettaglio **Modifiche** per visualizzare se la richiesta di offerta è stata modificata.
9. Selezionare la scheda dettaglio **Questionario**. Tutti i questionari che sono visualizzati in questo campo devono essere completati.
10. Selezionare la scheda dettaglio **Dettagli riga** per visualizzare informazioni estese sulla riga.
11. Selezionare **Reimposta dalla RdO** solo se è necessario reimpostare i valori immessi con i valori originali di offerta.
12. È possibile salvare l'offerta in qualsiasi momento ed eseguire un'ulteriore elaborazione in un secondo momento, a condizione che l'ora e la data di scadenza non siano state superate. In questo caso, è possibile trovare l'offerta nell'elenco **Offerte in corso** nell'area di lavoro **Offerta fornitore**.
13. Quando l'offerta è pronta per l'invio, selezionare **Inviare**. Selezionare **Rifiuta** se non si desidera inviare l'offerta. Le offerte inviate sono disponibili nell'elenco **Offerte inviate** dell'area di lavoro **Offerta fornitore**.  
14. Dopo che l'offerta è stata inviata, è possibile richiamarla in qualsiasi momento prima dell'ora e della data di scadenza. Tenere presente che quando un'offerta viene richiamata, non viene considerata come inviata. Quando l'offerta è stata accettata o rifiutata dal reparto di approvvigionamento, viene visualizzata come **Offerte concesse** o nell'elenco **Offerte perse** dell'area di lavoro. **Offerta fornitore**  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Immettere una risposta di un fornitore come responsabile approvvigionamenti

1. Assicurarsi che l'autorizzazione per modificare le offerte fornitore sia impostata. Passare a **Approvvigionamento \> Impostazione \> Parametri di approvvigionamento**. Nella scheda **Richiesta di offerta**, impostare l'opzione **L'acquirente può modificare l'offerta dei fornitori** su **Sì**.
2. Scegliere **Approvvigionamento \> Richieste di offerta \> Tutte le richieste di offerta**.
3. Selezionare una RdO con stato di **Inviato** e selezionare il collegamento nel campo **Caso richiesta di offerta**.
4. Selezionare **Gestisci risposte**. La pagina che appare mostra una RdO per ogni venditore che è stato invitato a fare un'offerta.
5. Selezionare una richiesta di offerta a cui non è stato risposto. (Il campo **Avanzamento risposta** deve essere impostato su **Non avviata**.)
6. Selezionare **Modifica \> Modifica risposta RdO**. Viene visualizzata la pagina **Risposta alla richiesta di offerta**. Come responsabile approvvigionamenti, è ora possibile immettere la risposta per conto del fornitore. Si noti che il campo **Avanzamento offerta** è impostato su **Aggiornamento in corso dell'acquirente**.  
7. Immettere i dati di offerta. Al termine, selezionare **Invia**.

## <a name="score-the-bids"></a>Assegnare un punteggio alle offerte

1. Nella pagina **Tutte le richieste di offerta**, selezionare il caso RdO per cui si desidera contrassegnare le risposte ricevute.
2. Selezionare **Gestisci risposte**.
3. Selezionare la risposta per il punteggio.
4. Selezionare **Intestazione** in modo da poter visualizzare il punteggio per l'offerta.
5. Nella scheda dettaglio **Punteggio offerta** immettere un numero nel campo **Punteggio** per uno dei criteri di assegnazione del punteggio. Se si passa su un criterio di assegnazione del punteggio, una descrizione comando mostra l'intervallo entro cui scegliere il punteggio da assegnare. In questa demo è possibile aggiungere un numero compreso tra 1 e 5 per uno dei criteri di punteggio.  
6. Ripetere il passaggio 5 per un altro criterio di punteggio.
7. Se il caso RdO contiene un questionario inviato ai fornitori, è possibile immettere le risposte del fornitore nella scheda dettaglio **Questionari**.
8. Chiudere la pagina.
9. Ripetere i passaggi da 1 a 8 per le altre offerte.

## <a name="compare-the-replies"></a>Confrontare le risposte

1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Confronta risposte**.
2. Nel campo **Classificazione** immettere un numero.  
    - Questa pagina mostra le offerte, insieme con l'intestazione e le informazioni sulla riga, oltre che il punteggio totale a livello di intestazione. È possibile confrontare le righe ordinando la griglia in modo che le righe confrontabili siano l'una accanto all'altra. Sono incluse anche le seguenti informazioni:
    - **Quantità**: la quantità dell'offerta del fornitore. Questa potrebbe essere diversa dalla quantità che è specificata nella richiesta di offerta.
    - **Importo netto**: il prezzo offerto da un fornitore, dopo la detrazione di eventuali sconti, per gli articoli nella riga.
    - **Deviazione**: il numero di giorni di differenza tra la data di consegna specificata nella riga o nell'intestazione dell'offerta e la data di consegna richiesta nella riga o nell'intestazione della RdO. È possibile inserire una classificazione per ogni offerta.  
3. Selezionare la riga dell'intestazione dell'altra offerta che si desidera classificare.
4. Nel campo **Classificazione** immettere un numero.
5. Selezionare **Salva**.

## <a name="reject-a-bid"></a>Rifiutare un'offerta

1. Selezionare la riga dell'intestazione dell'offerta che si desidera rifiutare. È possibile accettare, rifiutare o restituire solo un'offerta o le righe di una sola offerta alla volta.
2. Selezionare la casella di controllo **Contrassegna**.  
    - Se si seleziona la casella di controllo **Contrassegna** nell'intestazione dell'offerta, verranno contrassegnate anche tutte le righe. Per rifiutare o accettare solo alcune righe dell'offerta, è possibile contrassegnare tali righe. Inoltre, è possibile accettare l'offerta di un fornitore in alcune righe della richiesta di offerta e quindi assegnare altre righe della richiesta di offerta a un fornitore diverso. Tuttavia, è necessario effettuare un'offerta alla volta.  
    - Se sono presenti righe alternative, è possibile accettare la riga di offerta originale o la relativa alternativa, ma non entrambe.  
3. Selezionare **Rifiuta**.
4. Selezionare **Parametri**, quindi nel campo **Motivo rifiuto**, immettere o selezionare il motivo del rifiuto di offerta. Il motivo viene salvato nella risposta.  
5. Selezionare **OK**.
6. Selezionare **OK**.

## <a name="accept-a-bid"></a>Accettare un'offerta

1. Selezionare l'offerta che si desidera accettare, quindi il collegamento nel campo **Richiesta di offerta**. Se ci si trova nella pagina **Confronta risposte richiesta di offerta**, l'offerta evidenziata con lo stato attivo è l'offerta che il sistema considererà durante l'azione Accetta. È possibile accettare le righe di una sola offerta alla volta.  
2. Nel Riquadro azioni fare clic su **Rispondi**.
3. Selezionare **Accetta**. Se si sono contrassegnate solo righe specifiche, l'azione Accetta includerà solo quelle righe. Se si desidera accettare tutte le righe dell'offerta, non è necessario contrassegnare le righe.  
4. Selezionare **Parametri**, quindi nel campo **Motivo accettazione**, immettere o selezionare il motivo dell'accettazione di offerta. Il motivo viene salvato nell'offerta.  
5. Selezionare **OK**.
6. Selezionare **OK**. Quando si seleziona **OK**, viene generato un ordine fornitore in base alle righe incluse nell'accettazione della RdO. Se sono presenti altre offerte che non sono state elaborate (accettate, rifiutate o restituite), il sistema richiederà di rifiutarle.  

## <a name="view-the-purchase-order-that-is-generated"></a>Visualizzare l'ordine fornitore generato

Nel riquadro azioni, sella scheda **Generale**, selezionare **Ordine fornitore**. La pagina visualizzata mostra l'ordine fornitore generato quando è stata accettata l'offerta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]