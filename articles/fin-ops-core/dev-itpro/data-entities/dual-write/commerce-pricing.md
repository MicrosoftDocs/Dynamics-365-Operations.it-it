---
title: Utilizzare il Dynamics 365 Commerce motore di determinazione dei prezzi con Dynamics 365 Sales
description: Questo argomento descrive come utilizzare il motore di determinazione dei prezzi Microsoft Dynamics 365 Commerce per creare le offerte di vendita in Dynamics 365 Sales.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: cd784bb37eddfc74699d1070eab453a3b527201a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560275"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Utilizzare il Dynamics 365 Commerce motore di determinazione dei prezzi con Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come utilizzare il motore di determinazione dei prezzi Microsoft Dynamics 365 Commerce per creare le offerte di vendita in Dynamics 365 Sales.

Il Dynamics 365 Commerce Il motore di determinazione dei prezzi supporta la maggior parte degli scenari di prezzo business-to-consumer (B2C), come i prezzi a livello di negozio, i prezzi basati sull'affiliazione e sulla fedeltà, gli sconti combinati, gli sconti sulla quantità e gli sconti soglia. Il motore di determinazione del prezzo utilizza regole complesse per determinare il prezzo migliore per un determinato preventivo od ordine.

Quando usi la [doppia scrittura](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview), hai tre opzioni per le tue esigenze di prezzo. Puoi utilizzare il prezzo statico che proviene dal listino prezzi in Dynamics 365 Sales, il motore dei prezzi in Dynamics 365 Supply Chain Management o il motore di determinazione dei prezzi in Dynamics 365 Commerce. Tra queste opzioni, il motore di determinazione dei prezzi di Commerce è più adatto agli scenari B2C.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Utilizza il motore di determinazione dei prezzi di Commerce in Sales

> [!NOTE]
> Attualmente, il motore di determinazione dei prezzi di Commerce può essere utilizzato solo per la creazione delle offerte in Sales. L'integrazione dell'ordine del cliente con il motore di determinazione dei prezzi di Commerce non è ancora disponibile.

Quando gli utenti avviano un'offerta in Sales, il framework a doppia scrittura copia i dettagli dell'offerta in Commerce. Eventuali modifiche alle righe di offerta esistenti o alle righe di offerta appena aggiunte in Sales vengono copiate in Commerce. Quando gli utenti desiderano utilizzare il motore di determinazione dei prezzi di Commerce per quotare l'offerta, possono selezionare **Preventivo** per aggiornare i prezzi dell'offerta, in base al motore di determinazione dei prezzi di Commerce. I prezzi vengono quindi aggiornati automaticamente sia in Sales che in Commerce.

## <a name="prerequisites"></a>Prerequisiti

- Prima di poter utilizzare il motore di determinazione dei prezzi di Commerce in Sales, è necessario seguire i passaggi in [Prospetto per uno scenario di liquidazione in doppia scrittura](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/).
- È necessario disattivare la valutazione dell'accordo commerciale per l'inserimento manuale seguendo questi passaggi:

    1. Nell'ambiente Commerce, andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
    1. Nella scheda **Prezzi**, nella scheda dettaglio **Valutazione accordi commerciali**, deselezionare la casella di controllo **Inserimento manuale**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Prospect to cash in doppia scrittura](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]