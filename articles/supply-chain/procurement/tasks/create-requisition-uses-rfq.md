---
title: Creare una richiesta che usa una RdO
description: In questo argomento viene descritto come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05ff98b5fd95fa345d344e54d9116c73434e5de5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018898"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Creare una richiesta che usa una RdO

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF e dovete essere collegati come Amministratore per completare tutti i passaggi. Le attività in questa guida sarebbero svolte tipicamente da professionisti dell'approvvigionamento.


## <a name="create-a-requisition"></a>Creare una richiesta
1. Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Richieste di acquisto > Richieste di acquisto preparate dall'utente**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome**.
4. Nel campo **Data richiesta** immettere una data.
5. Immettere una data nel campo **Data di registrazione**.
6. Selezionare **OK**.
7. Nel campo **Motivo** immettere o selezionare un valore.
8. Selezionare **Aggiungi riga**.
9. Nel campo **Categoria di approvvigionamento**, selezionare una categoria nella struttura e poi fare clic su **OK**.
10. Digitare un valore nel campo **Nome prodotto**.
11. Nel campo **Quantità** immettere un numero.
12. Nel campo **Unità** immettere o selezionare un valore.
13. Selezionare **Salva**.
14. Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.
15. Selezionare **Invia**.
16. Chiudere la pagina.
17. Selezionare **Invia**.

## <a name="reassign-a-workflow-task"></a>Riassegnare un'attività di flusso di lavoro
L'attività seguente è creare una RdO per ottenere le offerte dai fornitori per il prodotto. Nei dati dimostrativi USMF, il flusso di lavoro di richiesta è impostato con una regola in modo che se un fornitore non è selezionato, o il prezzo unitario è 0 per una riga, un'attività viene assegnata ad un lavoratore specifico per creare una RdO. Per continuare con questa guida, dovete riassegnare quell'attività ad un altro utente (voi stessi). Potete fare questo solo se siete collegati come Amministratore.  

1. Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.
2. Selezionare **Visualizza storico**.
3. Aggiorna la pagina.
4. Espandere la sezione **Dettagli tracciabilità**.
5. Nella struttura, selezionare la riga che inizia con "Flusso di lavoro voci attivato il".
6. Selezionare **Visualizza dettagli flusso di lavoro**.
7. Espandere la sezione **Elementi di lavoro**.
8. Selezionare **Riassegna**.
9. Nel campo **Utente**, selezionare **Amministratore**.
10. Selezionare **Riassegna**.
11. Chiudere le due pagine.

## <a name="create-an-rfq"></a>Creare una RdO

1. Aggiorna la pagina.
2. Selezionare **Richiesta di offerta**.
3. Nel campo **Persona giuridica acquirente**, selezionare **USMF**. È necessario selezionare la stessa persona giuridica presente sulla riga di richiesta.  
4. Nell'elenco contrassegnare la riga selezionata. Se aveste più righe nella richiesta di acquisto, selezionare tutte le righe che volete aggiungere al RdO.  
5. Selezionare **OK**.
6. Aggiorna la pagina.
7. Assicurarsi che la Scheda dettaglio sia aperta, quindi espandere la sezione **Documenti correlati**.
8. Selezionare il collegamento nel campo **Richiesta di offerta** per aprire l'RdO appena creata.
9. Selezionare **Intestazione**.
10. Selezionare **Aggiungi**.
11. Nel campo **Conto fornitore**, immettere o selezionare un valore.
12. Selezionare **Aggiungi**.
13. Nel campo **Conto fornitore**, immettere o selezionare un valore.
14. Selezionare **Invia**.
15. Selezionare **OK**.
16. Selezionare **Inserisci risposta**.
17. Nel Riquadro azioni fare clic su **Rispondi**.
18. Selezionare **Copia dati nella risposta**. Ciò copia i dati, quali la quantità e le date, dalla RdO alla risposta.  
19. Immettere un numero nel campo **Prezzo unitario**. Questo è il prezzo ricevuto dal fornitore. Potreste anche volere immettere ulteriori informazioni dal fornitore.  
20. Selezionare **Accetta**.
21. Selezionare **OK**.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Verificare che il prezzo ed il fornitore siano stati trasferiti nella richiesta
1. Chiudere la pagina.
2. Selezionare **Righe**.
3. Selezionare **Informazioni correlate**.
4. Seelzionare **Richiesta di acquisto**.
5. Selezionare la riga che è stata trasferita alla RdO. Verificare che il prezzo ed il fornitore siano stati copiati nella richiesta.  
6. Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.
7. Seleziona Completa.
8. Selezionare la pagina.
9. Seleziona Completa.

