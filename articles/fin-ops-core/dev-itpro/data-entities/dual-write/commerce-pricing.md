---
title: Utilizzare il Dynamics 365 Commerce motore di determinazione dei prezzi con Dynamics 365 Sales
description: Questo articolo descrive come utilizzare il motore di determinazione dei prezzi Microsoft Dynamics 365 Commerce per creare le offerte di vendita in Dynamics 365 Sales.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 11a164ec15c8b7a69172a153b961011a8b324712
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881396"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Utilizzare il Dynamics 365 Commerce motore di determinazione dei prezzi con Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come utilizzare il motore di determinazione dei prezzi Microsoft Dynamics 365 Commerce per creare le offerte di vendita in Dynamics 365 Sales.

Il Dynamics 365 Commerce Il motore di determinazione dei prezzi supporta la maggior parte degli scenari di prezzo business-to-consumer (B2C), come i prezzi a livello di negozio, i prezzi basati sull'affiliazione e sulla fedeltà, gli sconti combinati, gli sconti sulla quantità e gli sconti soglia. Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine.

Quando usi la [doppia scrittura](./dual-write-overview.md), hai tre opzioni per le tue esigenze di prezzo. Puoi utilizzare il prezzo statico che proviene dal listino prezzi in Dynamics 365 Sales, il motore dei prezzi in Dynamics 365 Supply Chain Management o il motore di determinazione dei prezzi in Dynamics 365 Commerce. Tra queste opzioni, il motore di determinazione dei prezzi di Commerce è più adatto agli scenari B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Utilizza il motore di determinazione dei prezzi di Commerce in Sales

> [!NOTE]
> Attualmente, il motore di determinazione dei prezzi di Commerce può essere utilizzato solo per la creazione delle offerte in Sales. L'integrazione dell'ordine del cliente con il motore di determinazione dei prezzi di Commerce non è ancora disponibile.

Quando gli utenti avviano un'offerta in Sales, il framework a doppia scrittura copia i dettagli dell'offerta in Commerce. Eventuali modifiche alle righe di offerta esistenti o alle righe di offerta appena aggiunte in Sales vengono copiate in Commerce. Quando gli utenti desiderano utilizzare il motore di determinazione dei prezzi di Commerce per quotare l'offerta, possono selezionare **Preventivo** per aggiornare i prezzi dell'offerta, in base al motore di determinazione dei prezzi di Commerce. I prezzi vengono quindi aggiornati automaticamente sia in Sales che in Commerce.

## <a name="prerequisites"></a>Prerequisiti

- Prima di poter utilizzare il motore di determinazione dei prezzi di Commerce in Sales, è necessario seguire i passaggi in [Prospetto per uno scenario di liquidazione in doppia scrittura](./dual-write-prospect-to-cash.md).
- È necessario disattivare la valutazione dell'accordo commerciale per l'inserimento manuale seguendo questi passaggi:

    1. Nell'ambiente Commerce, andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
    1. Nella scheda **Prezzi**, nella scheda dettaglio **Valutazione accordi commerciali**, deselezionare la casella di controllo **Inserimento manuale**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Prospect to cash in doppia scrittura](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]