---
title: Creare nuovo ordine di rifornimento spedizione
description: In questa procedura viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3e33008d04ea8bb7d145c7b63cec23a4a45dd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549887"
---
# <a name="create-a-consignment-replenishment-order"></a>Creare nuovo ordine di rifornimento spedizione

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione. Viene inoltre illustrato come registrare un'entrata prodotti in modo da registrare l'inventario di spedizione come scorte disponibili di proprietà del fornitore. Questa procedura viene in genere eseguita da un responsabile approvvigionamenti. È possibile utilizzare questa guida nella società di dati dimostrativi USMF. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.




## <a name="create-a-consignment-replenishment-order"></a>Creare nuovo ordine di rifornimento spedizione
1. Andare ad Approvvigionamento > Spedizione > Ordini di rifornimento spedizione.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore selezionare il fornitore US-104.
    * È necessario selezionare un fornitore registrato come proprietario nella pagina Proprietari inventario.  
4. Fare clic su OK.
5. Fare clic su Aggiungi riga.
6. Nel campo Numero articolo digitare M9211CI.
    * È necessario selezionare un articolo impostato per l'inventario di spedizione.  
7. Nel campo Quantità immettere un numero.
8. Nel campo Data di consegna richiesta immettere una data.
    * Le date di richiesta e conferma vengono utilizzate dal motore MRP per l'arrivo previsto delle merci.  
9. Immettere una data nel campo Data di consegna confermata.
10. Espandere la sezione Dettagli riga.
11. Fare clic sulla scheda Dimensioni inventariali.
12. Per visualizzare il proprietario nel campo del proprietario Dimensioni inventariali, aggiornare la pagina.
    * Il fornitore US-104 è ora elencato come proprietario.  

## <a name="check-the-inventory-transaction-status"></a>Controllare lo stato delle transazioni di inventario
1. Fare clic su Scorte.
2. Fare clic su Transazioni.
3. Nell'elenco contrassegnare la riga selezionata.
    * Si noti che il campo Entrata è impostato su Ordinato.  
4. Chiudere la pagina.

## <a name="receive-items"></a>Ricevi articoli
1. Fare clic su Entrata prodotti.
2. Digitare un valore nel campo Entrata prodotti esterna.
3. Nel campo Quantità, immettere un numero minore del numero riportato lì. 
4. Fare clic su OK.

## <a name="check-the-on-hand-inventory"></a>Controllare le scorte disponibili.
1. Fare clic su Scorte.
2. Fare clic su Disponibilità.
3. Fare clic su Panoramica.
    * Gli articoli ricevuti come inventario di spedizione di proprietà del fornitore sono scorte disponibili. La quantità rimanente nell'ordine di rifornimento spedizione è indicata nel campo Ordinata in totale.  
4. Chiudere la pagina.
5. Fare clic su Chiudi.

