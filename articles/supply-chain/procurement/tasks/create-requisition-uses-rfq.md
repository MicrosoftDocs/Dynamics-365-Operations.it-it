---
title: Creare una richiesta che usa una RdO
description: Questa guida mostra come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a9418b526f992008086f10ce78e95cb682bc164
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "344986"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Creare una richiesta che usa una RdO

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida mostra come aggiungere le informazioni su prezzo e fornitore ad una richiesta di acquisto da un processo di RdO. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF e dovete essere collegati come Amministratore per completare tutti i passaggi. Le attività in questa guida sarebbero svolte tipicamente da professionisti dell'approvvigionamento.


## <a name="create-a-requisition"></a>Creare una richiesta
1. Andare ad Approvvigionamento > Richieste di acquisto > Richieste di acquisto preparate dall'utente.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Data richiesta immettere una data.
5. Immettere una data nel campo Data di registrazione.
6. Fare clic su OK.
7. Nel campo Motivo immettere o selezionare un valore.
8. Fare clic su Aggiungi riga.
9. Nel campo Categoria di approvvigionamento, selezionare una categoria nella struttura e poi fare clic su OK.
10. Digitare un valore nel campo Nome prodotto.
11. Nel campo Quantità immettere un numero.
12. Nel campo Unità immettere o selezionare un valore.
13. Fare clic su Salva.
14. Fare clic su Flusso di lavoro per aprire la finestra di dialogo a discesa.
15. Fare clic su Invia.
16. Chiudere la pagina.
17. Fare clic su Invia.

## <a name="reassign-a-workflow-task"></a>Riassegnare un'attività di flusso di lavoro
    * L'attività seguente è creare una RdO per ottenere le offerte dai fornitori per il prodotto. Nei dati dimostrativi USMF, il flusso di lavoro di richiesta è impostato con una regola in modo che se un fornitore non è selezionato, o il prezzo unitario è 0 per una riga, un'attività viene assegnata ad un lavoratore specifico per creare una RdO. Per continuare con questa guida, dovete riassegnare quell'attività ad un altro utente (voi stessi). Potete fare questo solo se siete collegati come Amministratore.  
1. Fare clic su Flusso di lavoro per aprire la finestra di dialogo a discesa.
2. Fare clic su Visualizza storico,
3. Aggiorna la pagina.
4. Espandere la sezione Dettagli tracciabilità.
5. Nella struttura, selezionare la riga che inizia con 'Flusso di lavoro voci attivato il'.
6. Fare clic su Visualizza dettagli flusso di lavoro.
7. Espandere la sezione Elementi di lavoro.
8. Fare clic su Riassegna.
9. Nel campo Utente, selezionare Amministratore.
10. Fare clic su Riassegna.
11. Chiudere la pagina.
12. Chiudere la pagina.

## <a name="create-an-rfq"></a>Creare una RdO
1. Aggiorna la pagina.
2. Fare clic su Richiesta di offerta.
3. Nel campo Persona giuridica acquirente, selezionare USMF.
    * Dovete selezionare la stessa persona giuridica che è sulla riga di richiesta.  
4. Nell'elenco contrassegnare la riga selezionata.
    * Se aveste più righe nella richiesta di acquisto, selezionare tutte le righe che volete aggiungere al RdO.  
5. Fare clic su OK.
6. Aggiorna la pagina.
7. Aprire il Dettaglio informazioni, quindi espandere la sezione Documenti correlati.
    * È possibile che il Dettaglio informazioni sia già aperto. Cercare l'icona con una freccia, a destra degli interruttori Righe/Intestazione. Se la freccia sta indicando la destra, il Dettaglio informazioni è già aperto. Se la freccia indica a sinistra, fare clic per aprire il Dettaglio informazioni.  
8. Fare clic sul collegamento nel campo Richiesta di offerta per aprire l'RdO appena creata.
9. Fare clic su Intestazione.
10. Scegliere Aggiungi.
11. Nel campo Conto fornitore, immettere o selezionare un valore.
12. Scegliere Aggiungi.
13. Nel campo Conto fornitore, immettere o selezionare un valore.
14. Fare clic su Invia.
15. Fare clic su OK.
16. Fare clic su Inserisci risposta.
17. Nel Riquadro azioni fare clic su Rispondi.
18. Fare clic su Copia dati per rispondere.
    * Ciò copia i dati, quali la quantità e le date, dalla RdO alla risposta.  
19. Nel campo Prezzo unitario immettere un numero.
    * Questo è il prezzo che avete ricevuto dal fornitore. Potreste anche volere immettere ulteriori informazioni dal fornitore.  
20. Fare clic su Accetta.
21. Fare clic su OK.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Verificare che il prezzo ed il fornitore siano stati trasferiti nella richiesta
1. Chiudere la pagina.
2. Fare clic su Righe.
3. Fare clic su Informazioni correlate.
4. Fare clic su Richiesta di acquisto.
5. Selezionare la riga che è stata trasferita alla RdO.
    * Verificare che il prezzo ed il fornitore siano stati copiati nella richiesta.  
6. Fare clic su Flusso di lavoro per aprire la finestra di dialogo a discesa.
7. Fare clic su Completa.
8. Chiudere la pagina.
9. Fare clic su Completa.

