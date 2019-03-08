---
title: Creare una richiesta di offerta
description: Questa procedura mostra come creare una richiesta di offerta.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c09149fcbe5731126c2e48a37fafdf71c1d49df
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "334452"
---
# <a name="create-a-request-for-quotation"></a>Creare una richiesta di offerta

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come creare una richiesta di offerta. Questa operazione viene in genere eseguita da un addetto agli acquisti. È necessario impostare le classificazioni del contratto di acquisto prima di iniziare. Per iniziare, cccorre avere impostato i tipi di sollecito. Dopo aver completato l'attività e creato e inviato una RdO, è possibile immettere le risposte per fornitore, confrontarle e assegnare il contratto.


## <a name="prepare-a-new-rfq"></a>Preparare una nuova RdO
1. Andare ad Approvvigionamento > Richieste di offerta > Tutte le richieste di offerta.
2. Fare clic su Nuovo.
    * Sono disponibili i seguenti tipi di acquisto: Ordine fornitore (questa è l'impostazione predefinita): un documento che conferma l'offerta di acquisto di prodotti o l'accettazione di un'offerta di vendita di prodotti in cambio di pagamento. Richiesta di acquisto: questo tipo viene selezionato automaticamente se si crea una RdO direttamente da una richiesta di acquisto. Se si seleziona manualmente questa opzione, verrà visualizzato un errore. Contratto di acquisto: un contratto che prevede l'acquisto di una quantità o un valore specifico di prodotti nel tempo. Se si sceglie questa opzione, è necessario selezionare l'intervallo di date applicabile al contratto di acquisto.  
3. Nel campo Titolo documento digitare un valore.
4. Nel campo Tipo di sollecito immettere o selezionare un valore.
    * Se un metodo di assegnazione del punteggio è associato al tipo di sollecito, questo sarà il metodo predefinito per la RdO che si sta creando. È possibile cambiare il metodo di assegnazione del punteggio in seguito.  
    * Immettere una data nel campo Data di consegna.  
    * Selezionare la data entro cui si desidera ricevere gli articoli.  
    * Nel campo Data e ora di scadenza immettere una data e un'ora.  
    * Specificare la data e l'ora entro cui i fornitori devono rispondere alla RdO.  
5. Nel campo Magazzino immettere o selezionare un valore.
    * L'indirizzo di consegna sarà l'indirizzo del magazzino, per impostazione predefinita.  
6. Fare clic su OK.

## <a name="add-lines"></a>Aggiungi righe
    * Dopo avere specificato informazioni di base sulla richiesta di offerta, specificare le merci o i servizi su cui si desidera che i fornitori facciano un'offerta. L'articolo è il tipo di riga predefinito.   
1. Nel campo Numero di articoli immettere o selezionare un valore.
    * Se si utilizza USMF, sarà possibile selezionare T0020.  
2. Nel campo Quantità immettere un numero.
3. Fare clic su Aggiungi riga.
4. Nel campo Tipo di riga selezionare "Categoria".
    * È possibile utilizzare il tipo di riga Categoria per creare RdO per le merci o i servizi non in magazzino. Sarà quindi necessario selezionare il tipo di merci o servizi da una gerarchia di categorie di approvvigionamento.  
5. Nel campo Categoria di approvvigionamento immettere o selezionare un valore.
6. Digitare un valore nel campo Nome prodotto.
7. Nel campo Quantità immettere un numero.
8. Nel campo Unità immettere o selezionare un valore.

## <a name="add-vendors"></a>Aggiungi fornitori
1. Fare clic sull'intestazione per passare dalla visualizzazione Righe alla visualizzazione Intestazione. 
2. Espandere la sezione Fornitore.
3. Fare clic su Aggiungi automaticamente fornitori.
    * È possibile aggiungere fornitori alla RdO automaticamente in base alla categoria di approvvigionamento degli articoli richiesti. Se non sono presenti fornitori approvati per le categorie incluse nelle righe, sarà possibile aggiungerli manualmente.  
4. Scegliere Aggiungi.
5. Nel campo Conto fornitore, immettere o selezionare un valore.
6. Scegliere Aggiungi.
7. Nel campo Conto fornitore, immettere o selezionare un valore.
    * Una volta selezionato un fornitore, lo stato diventa Creata. In questo modo è possibile salvare le informazioni relative al fornitore nella richiesta di offerta senza tuttavia inviare la richiesta al fornitore. È possibile aggiungere un fornitore a una richiesta di offerta indipendentemente dallo stato del fornitore.  

## <a name="send-the-rfq-to-vendors"></a>Inviare le RdO ai fornitori
1. Fare clic su Invia.
    * Nella pagina Invio richiesta di offerta verificare che i fornitori nell'elenco siano quelli che si desidera ricevano la RdO.  
2. Fare clic su Stampa.
    * Questa finestra di dialogo consente di stampare la RdO. Se si sceglie di stampare un foglio di risposta, il relativo contenuto è definito nei parametri Approvvigionamento. Per scegliere come stampare fogli di risposta, una volta aperta la finestra di dialogo Stampa, fare clic su Opzioni di stampa avanzate. Per ciascun fornitore verrà stampata una RdO contenente le righe con stato Creata o Inviata. Le righe annullate e le righe con risposte registrate non verranno stampate.   
3. Scegliere Annulla.
4. Fare clic su OK.
5. Chiudere la pagina.
6. Chiudere la pagina.

## <a name="view-the-rfq-journal"></a>Visualizzare il giornale di registrazione richieste di offerta
1. Andare ad Approvvigionamento > Richieste di offerta > Follow-up richiesta di offerte > Giornali di registrazione richieste di offerta.
2. Fare clic su Anteprima/Stampa.
3. Fare clic su Anteprima originale.
4. Chiudere la pagina.
5. Chiudere la pagina.

