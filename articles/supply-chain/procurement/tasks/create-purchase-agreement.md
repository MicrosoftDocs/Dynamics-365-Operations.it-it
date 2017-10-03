--- 
title: Creare un contratto di acquisto
description: Questa procedura descrive la creazione di un contratto di acquisto
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 22a252d98da5415f50a1d6ffb28f57aae19b5d14
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-purchase-agreement"></a>Creare un contratto di acquisto

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive la creazione di un contratto di acquisto e viene in genere effettuata da un responsabile acquisti. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. È necessario impostare le classificazioni del contratto di acquisto prima di iniziare. Una volta creato un contratto, è possibile utilizzarlo quando si crea un ordine fornitore. In questo modo le condizioni del contratto di acquisto verranno copiate nell'intestazione e in tutte le righe nell'ordine in cui sono interessate dal contratto.


## <a name="create-a-new-purchase-agreement"></a>Creare un nuovo contratto di acquisto
1. Andare ad Approvvigionamento > Contratti di acquisto > Contratti di acquisto.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Classificazione contratto di acquisto fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Espandere la sezione Generale.
10. Nel campo Data di scadenza immettere una data.
    * La data di scadenza verrà impostata per tutti le righe di impegno e determinerà il periodo di validità di ogni impegno specifico.  
11. Nel campo Titolo documento digitare un nome per il contratto di acquisto.
    * Lasciare il campo Impegno predefinito impostato su Impegno quantità prodotto o modificarlo se non è impostato su tale valore.  
    * Il valore di impegno predefinito determina le opzioni nelle righe del contratto. Se è necessarie un nuovo tipo di impegno durante la creazione delle righe del contratto, è necessario modificare l'impegno predefinito nell'intestazione.  Sono presenti i 4 tipi di impegni seguenti. Impegno quantità prodotto - per una specifica quantità di prodotto, Impegno valore prodotto - per un importo in valuta specifico del prodotto, Impegno valore categoria prodotto - per un importo in valuta specifico in una categoria di approvvigionamento in cui l'importo può essere correlato a un articolo del catalogo oppure a un articolo fuori catalogo, Impegno valore - per un importo in valuta specifico che può essere soddisfatto da qualsiasi prodotto o da qualsiasi categoria di approvvigionamento.  
12. Fare clic su OK.

## <a name="add-a-commitment"></a>Aggiungere un impegno
1. Fare clic su Aggiungi riga.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare il prodotto per cui si desidera aggiungere un impegno.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Quantità immettere un numero.
    * Si tratta della quantità totale accettata per l'acquisto dal fornitore.  
7. Nel campo Prezzo unitario immettere un numero.
8. Espandere la sezione Dettagli riga.
9. Impostare l'opzione Valore massimo applicato su Sì.
    * L'opzione Valore massimo applicato limita l'utilizzo dell'impegno. È possibile acquistare una quantità pari al massimo al valore specificato nel campo Quantità per la riga.  
10. Comprimere la sezione Dettagli riga.

## <a name="add-header-conditions"></a>Aggiungere condizioni di intestazione
1. Nel riquadro azioni fare clic su Opzioni.
2. Fare clic su Cambia visualizzazione.
3. Fare clic su Visualizzazione intestazione.
4. Espandere la sezione Termini.
5. Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.
    * I termini di pagamento del conto fornitore vengono visualizzati in questo punto per impostazione predefinita.       
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Modalità di consegna fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Nel campo Termini di consegna fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="confirm-and-activate-the-agreement"></a>Confermare e attivare il contratto
1. Nel riquadro azioni fare clic su Contratto di acquisto.
2. Fare clic su Conferma.
    * Impostare l'opzione Contrassegna contratto come valido su Sì.  
3. Fare clic su OK.
4. Nel riquadro azioni fare clic su Contratto di acquisto.
5. Fare clic su Conferme contratto di acquisto.
    * L'opzione Anteprima/Stampa consente di generare un documento per il contratto di acquisto che successivamente è possibile stampare o inviare al fornitore. Se in seguito si aggiorna il contratto e lo si riconferma, entrambe le versioni verranno visualizzate in questo punto.  
6. Chiudere la pagina.


