--- 
title: " Definire punti premio fedeltà"
description: "In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 05237a0ba3aa785432c8b1fc36284a47f9aabd4a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-loyalty-reward-points"></a> Definire punti premio fedeltà

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà. È necessario impostare i punti premio fedeltà prima di impostare un programma di fedeltà. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Vendita al dettaglio e commercio > Clienti > Fedeltà > Punti premio fedeltà.
2. Fare clic su Nuovo.
3. Nel campo ID punto premio, immettere un valore.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo di punto premio selezionare un'opzione.
    * Selezionare Quantità se si desidera che i punti premio vengano arrotondati all'intero più vicino. Selezionare Importo se si desidera che i punti premio vengano arrotondati secondo le regole di arrotondamento valuta. Se si seleziona Quantità, ignorare il passaggio successivo di questa procedura.  
6. Digitare un valore nel campo Valuta.
    * Per i punti premio di tipo Importo, tutti i punti emessi avranno la valuta selezionata. Per i punti di ricompensa di tipo Quantità, questo campo viene applicato, ignorare questo passaggio.  
7. Selezionare o deselezionare la casella di controllo Riscattabile.
8. Immettere un numero nel campo Classificazione di riscatto.
    * Classificazione di riscatto viene utilizzato quando due o più punti premio riscattabili possono essere utilizzati per pagare i prodotti. Se i due punti premio hanno la stessa classificazione di riscatto, verrà utilizzato quello per cui è necessario ridurre il numero di punti.  
9. Immettere un numero nel campo Valore ora di scadenza.
    * I punti premio scadono dopo il numero specificato di giorni, mesi o anni a partire dall'emissione. Il valore "0" indica che i punti premio fedeltà non hanno scadenza.  
10. Selezionare un'opzione nel campo Unità ora di scadenza.
11. Fare clic su Salva.


