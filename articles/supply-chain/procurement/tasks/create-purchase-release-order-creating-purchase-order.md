---
title: Creare un ordine di rilascio acquisto quando si crea l'ordine fornitore
description: Questa procedura mostra come utilizzare un contratto di acquisto quando si crea un ordine fornitore.
author: RichardLuan
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f82cabebea5c9e86e898c064c70a0e7a48b49d3
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016605"
---
# <a name="create-a-purchase-release-order-when-creating-the-purchase-order"></a>Creare un ordine di rilascio acquisto quando si crea l'ordine fornitore

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come utilizzare un contratto di acquisto quando si crea un ordine fornitore. Il contratto di acquisto deve essere applicato quando si crea l'ordine fornitore perché sono termini generali che devono essere copiati nell'intestazione dell'ordine fornitore. In genere questa attività sarà svolta da un addetto acquisti. Come prerequisito per la guida, è necessario disporre di un contratto di acquisto valido con un impegno quantità di prodotto per un fornitore e gli articoli. La stessa procedura può essere utilizzata se si dispone di un contratto di acquisto con altri tipi di impegni. È possibile eseguire questa guida nella società di dati dimostrativi USMF. Se si utilizza USMF, è possibile "Creare un contratto di acquisto" innanzitutto per impostare i presupposti necessari per la guida.


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Aprire l'area di lavoro preparazione ordine fornitore.
2. Fare clic su Nuovo ordine fornitore.
3. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Attivare/disattivare l'espansione della sezione Generale.
7. Nel campo Contratto di acquisto fare clic sul pulsante a discesa per aprire la ricerca.
    * Tutti i contratti disponibili per il fornitore sono elencati in questo campo. Individuare il contratto valido da utilizzare.  
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Fare clic su Sì.
10. Fare clic su OK.

## <a name="add-a-line"></a>Aggiungere una riga
1. Nel campo Numero articolo, digitare un valore.
    * Se sono presenti dimensioni inventariali o di ubicazione sull'impegno, è necessario immettere gli stessi valori nella riga ordine fornitore per utilizzare il contratto.  
2. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
    * Il sito può già essere popolato con il valore predefinito dall'ordine o dal fornitore. In questo caso, ignorare questo passaggio.  
3. Nell'elenco trovare e selezionare il record desiderato.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Quantità immettere un numero.
    * Verificare che il prezzo sia copiato dall'impegno.  

## <a name="look-up-the-commitment"></a>Cercare l'impegno
1. Fare clic su Aggiorna riga.
2. Fare clic su Collegata.
    * In questo punto è possibile ottenere i dettagli del contratto di acquisto. Ad esempio, è possibile visualizzare il prezzo e se il prezzo e lo sconto sono fissi. Ciò significa che se si modifica il prezzo o lo sconto nell'ordine fornitore su un valore diverso di quello dell'impegno, il collegamento verrà rimosso in modo che la riga ordine fornitore non soddisfi l'impegno. È inoltre possibile visualizzare se l'opzione Valore massimo applicato è selezionata. In tal caso, la quantità relativa all'impegno non può essere superata sommando tutti gli acquisti correlati all'impegno.  
3. Chiudere la pagina.

## <a name="look-up-the-purchase-agreement"></a>Cercare il contratto di acquisto
1. Nel riquadro azioni fare clic su Generale.
2. Fare clic su Contratto di acquisto.
3. Chiudere la pagina.
4. Chiudere la pagina.

