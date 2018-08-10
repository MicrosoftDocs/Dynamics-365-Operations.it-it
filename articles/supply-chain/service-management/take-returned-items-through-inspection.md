---
title: Sottoporre a ispezione i resi
description: Sottoporre a ispezione i resi.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: df209cfdbdef591e9f24161b3651316c43d69ee0
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---


# <a name="take-returned-items-through-inspection"></a>Sottoporre a ispezione i resi 

[!include [banner](../includes/banner.md)]


1.  Fare clic su **Gestione articoli** \> **Periodico** \> **Gestione qualità** \> **Ordini di quarantena**.

2.  Individuare la riga di ordine che corrisponde all'articolo di reso sottoposto a ispezione.

    > [!NOTE]
    > <P>È possibile associare un ordine di quarantena a un solo numero articolo. Se dieci articoli con numeri differenti vengono restituiti in un'unica spedizione e messi in quarantena, verranno creati dieci ordini di quarantena distinti.</P>

3.  Una volta esaminato l'articolo, selezionare un valore nel campo **Codice smaltimento** per indicare le operazioni da eseguire relativamente all'articolo e la modalità di gestione delle transazioni finanziarie correlate. È ad esempio possibile specificare di restituire l'articolo al magazzino e rimborsare il cliente, scartare l'articolo e inviare al cliente un articolo sostitutivo oppure restituire l'articolo al cliente senza procedere a un accredito.
    
    > [!NOTE]
    > <P>Se non è possibile assegnare lo stesso codice smaltimento a più articoli resi inclusi in un lotto, è necessario dividere l'ordine di quarantena (<STRONG>Funzioni</STRONG> &gt; <STRONG>Dividi</STRONG>) per assegnare un codice smaltimento diverso a ogni lotto secondario.</P>


4.  Al termine dell'ispezione, fare clic su **Dichiarazione di finito** per rilasciare gli articoli di reso e creare un inserimento nel giornale di registrazione arrivi articoli. La persona o il reparto che riceverà gli articoli si occuperà di elaborare il giornale di registrazione in base agli articoli che devono essere restituiti al magazzino.
    
    oppure
    
    Terminare l'ordine di quarantena e inviare di nuovo gli articoli al magazzino utilizzando una delle funzioni **Scorte**.

5.  Chiudere il modulo per salvare le modifiche.

## <a name="see-also"></a>Vedere anche

[Specificare la modalità di smaltimento dei resi](specify-how-to-dispose-of-returned-items.md)

  



