---
title: I pagamenti vengono saldati automaticamente prima che gli ordini vengano fatturati o spediti
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un pagamento viene liquidato nel portale Adyen subito dopo che è stato effettuato un ordine, anche se l'ordine cliente non è stato fatturato o spedito.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b4fd37a3c45f2559c9659f072ca0b6f02e712f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018262"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>I pagamenti vengono saldati automaticamente prima che gli ordini vengano fatturati o spediti

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un pagamento viene liquidato nel portale Adyen subito dopo che è stato effettuato un ordine, anche se l'ordine cliente non è stato fatturato o spedito.

## <a name="description"></a>Descrizione

Dopo l'esecuzione di un ordine, il pagamento viene liquidato immediatamente nel portale Adyen, anche se l'ordine cliente non è stato fatturato o spedito.

## <a name="resolution"></a>Risoluzione

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Configurare l'acquisizione manuale dei pagamenti e-commerce nel portale Adyen

Per configurare l'acquisizione manuale dei pagamenti e-commerce nel portale Adyen, procedere come segue.

1. Accedere al portale Adyen.
1. Nell'angolo in alto a destra, selezionare l'account esercente per il canale di e-commerce.
1. Nella barra di spostamento superiore, selezionare **Account** e quindi seleziona **Impostazioni**.
1. Nel campo **Ritardo acquisizione**, selezionare **Manuale**.

    ![Impostazione Ritardo acquisizione nel portale Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Risorse aggiuntive

[Acquisizione di pagamenti Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Connettore pagamenti di Dynamics 365 per Adyen](../dev-itpro/adyen-connector.md)

[Impostare il connettore pagamenti di Dynamics 365 per Adyen](https://docs.adyen.com/plugins/microsoft-dynamics)
