---
title: Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio
description: In questo articolo viene descritto come modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: bcd4bdb29a967130f4ad57a57b67f56a8ea81d89
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848926"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Modificare le dimensioni finanziarie

Per modificare le dimensioni finanziare per le transazioni di vendita al dettaglio in Commerce Headquarters, seguire questi passaggi.

1. Aprire la pagina **Configurazione dimensione finanziaria per integrazione applicazioni**.
1. Selezionare il record **Integrazione dimensioni predefinite**.
1. Nella Scheda dettaglio **Dimensioni finanziarie**, assicurarsi che tutte le dimensioni che si desidera modificare nel foglio di lavoro Excel siano presenti nell'elenco **Selezionata**. Per ulteriori informazioni, vedere [Entità di dati](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).
1. Scaricare e aprire il file Excel dalla pagina **Rendiconti**, la pagina **Transazioni vendita al dettaglio** o il riquadro **Errori di convalida transazioni** nell'area di lavoro **Dati finanziari punto vendita**.
1. Per modificare la dimensione finanziaria della transazione, selezionare **Progettazione**, quindi selezionare il simbolo della matita accanto alla riga **Transazione (verificabile)**.
1. Trovare e selezionare il campo **FinancialDimensionDisplayValue**, selezionare una cella nella parte dell'intestazione del foglio di lavoro di Excel, quindi selezionare **Aggiungi etichetta**.
1. Selezionare una cella sotto la cella selezionata nel passaggio precedente, selezionare **Aggiungi valore** e quindi selezionare **Aggiorna**. Le dimensioni finanziarie vengono aggiunte al foglio di lavoro di Excel e possono quindi essere modificate e pubblicate.
1. Per modificare le dimensioni nelle righe di transazione, selezionare la riga **Transazioni di vendita (verificabili)**, selezionare il simbolo della matita, quindi ripetere i passaggi 6 e 7.
1. Per modificare le dimensioni nelle righe di pagamento, selezionare la riga **Transazioni di pagamento (verificabili)**, selezionare il simbolo della matita, quindi ripetere i passaggi 6 e 7.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa](edit-cash-trans.md)

[Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni](edit-order-trans.md)

[Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](create-excel-edit.md)

[Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]