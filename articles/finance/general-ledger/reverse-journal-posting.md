---
title: Stornare registrazione del giornale di registrazione
description: Questo argomento descrive le funzionalità che consentono di stornare i voucher dall'elenco delle transazioni dei voucher o dai giornali finanziari.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248587"
---
# <a name="reverse-journal-posting"></a>Stornare registrazione del giornale di registrazione

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità di Microsoft Dynamics 365 Finance che consentono di stornare un intero giornale di registrazione o stornare uno o più giustificativi dell'elenco delle transazioni giustificativi indipendentemente dall'origine. 

## <a name="reversing-journals"></a>Storno dei giornali di registrazione

È possibile stornare singolarmente le righe del giornale di registrazione. Con lo storno della registrazione del giornale di registrazione, è inoltre possibile stornare un intero giornale finanziario. Per stornare un giornale di registrazione: 
- Aprire il giornale finanziario e filtrare i giornali di registrazione pubblicati
- Fare clic su Storna nel menu sulla parte superiore della pagina
- Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate
- Selezionare Sì per utilizzare le date di transazione esistenti o No per immetterne una nuova. In alcuni casi, il periodo della transazione originale potrebbe essere chiuso e si desidera inserire una nuova data di transazione per lo storno.
- Se si seleziona No, immettere una data di transazione per lo storno. 
- Immettere un commento che si desidera aggiungere alla transazione di storno
- Fare clic sul pulsante Storna

Le transazioni saranno stornate. 

Se il numero di righe giustificativo supera le 100 righe, il processo di storno verrà eseguito utilizzando il processo batch. È possibile rivedere i risultati dello storno visualizzando i commenti nel processo batch che è stato eseguito. Tutti gli errori verranno annotati nella cronologia dei processi batch.

Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente. I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare e il motivo per cui non possono essere stornati. Fare clic su OK per chiudere la finestra di dialogo.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Storno di giustificativi dall'elenco delle transazioni giustificativi. 

È inoltre possibile stornare i giustificativi dall'**elenco transazioni per giustificativo** in tutti i giornali di registrazione secondari . Inoltre, è possibile stornare più di un giustificativo per volta. 

Per stornare uno o più giustificativi: 
- Fare clic su Storna nel menu sulla parte superiore della pagina
- Viene visualizzato il numero totale di giustificativi e righe giustificativo nonché il totale delle righe stornate
- Selezionare Sì per utilizzare le date di transazione esistenti o No per immetterne una nuova. In alcuni casi, il periodo della transazione originale potrebbe essere chiuso e si desidera inserire una nuova data di transazione per lo storno.
- Se si seleziona No, immettere una data di transazione per lo storno. 
- Immettere un commento che si desidera aggiungere alla transazione di storno
- Fare clic sul pulsante Storna

Le transazioni saranno stornate. 

Se il numero di righe giustificativo supera le 100 righe, il processo di storno verrà eseguito utilizzando il processo batch. È possibile rivedere i risultati dello storno visualizzando i commenti nel processo batch che è stato eseguito. Tutti gli errori verranno annotati nella cronologia dei processi batch.

Se il numero di righe giustificativo è pari o inferiore a 100 righe, il processo di storno verrà eseguito immediatamente. I risultati verranno visualizzati in una finestra di dialogo contenente tutti i giustificativi che non è possibile stornare e il motivo per cui non possono essere stornati. Fare clic su OK per chiudere la finestra di dialogo.

