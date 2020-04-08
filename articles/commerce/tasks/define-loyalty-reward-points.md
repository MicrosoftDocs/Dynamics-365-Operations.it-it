---
title: " Definire punti premio fedeltà"
description: In questa procedura vengono descritti i passaggi per definire i punti premio fedeltà.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e40ebcbf3ab1befc641ae34571a8b974bd0425a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140878"
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

