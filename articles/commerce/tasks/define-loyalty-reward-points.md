---
title: " Definire punti premio fedeltà"
description: In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailLoyaltyRewardPoints
ms.openlocfilehash: 9acd1429d17393f19a5e059b90a48b0b103535d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268894"
---
# <a name="define-loyalty-reward-points"></a> Definire punti premio fedeltà

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà. È necessario impostare i punti premio fedeltà prima di impostare un programma di fedeltà. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Retail e Commerce > Clienti > Fedeltà > Punti premio fedeltà.
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
