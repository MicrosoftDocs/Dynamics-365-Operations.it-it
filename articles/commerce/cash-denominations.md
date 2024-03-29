---
title: Configurare le denominazioni del contante per il POS
description: Le denominazioni del contante per banconote e monete possono essere definite nel back office per l'uso da parte di cassieri, assistenti alle vendite e responsabili nel punto vendita dal POS.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.industry: Retail
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
ms.openlocfilehash: c61cde76bf2bfe3ff48b306a8a161fa27f50ac41
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273695"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a>Configurare le denominazioni del contante per il POS

[!include [banner](includes/banner.md)]

Le denominazioni del contante per banconote e monete possono essere definite nel back office per l'uso da parte di cassieri, assistenti alle vendite e responsabili nel punto vendita dal POS. Queste denominazioni possono essere utilizzate per agevolare il conteggio del contante per i riepiloghi incassi alla fine della giornata o per incassare rapidamente una vendita.

## <a name="define-denominations"></a>Definire le denominazioni

È possibile impostare le denominazioni per punto vendita selezionando **Imposta** \> **Riepilogo di cassa** nella pagina delle proprietà dei punti vendita.

![Opzione Riepilogo di cassa.](./media/image1-denomination.png)

Per definire una denominazione:

1. Fare clic su **Nuovo**.
1. Specificare il tipo (moneta o banconota).
1. Specificare l'importo (valore).

![Pagina Denominazioni riepilogo di cassa.](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Configurare il profilo funzionalità

In caso di pagamento in contanti nel POS, l'utente può utilizzare le denominazioni delle banconote per immettere rapidamente l'importo pagato dal cliente. Nel profilo funzionalità, è possibile configurare le due opzioni per la visualizzazione della denominazione nel POS.

- **Maggiore o uguale all'importo dovuto**: per impostazione predefinita, il POS visualizzerà solo le denominazioni delle banconote superiori all'importo dovuto. Ciò consente di effettuare il pagamento con un singolo tocco. Ad esempio, se l'importo dovuto è 7,50 USD, il POS visualizza le denominazioni 10, 20, 50 e 100 USD. Toccando una di quelle denominazioni, si incassa automaticamente l'importo della vendita. Le banconote da 1 e 5 USD non sono visualizzate in quanto inferiori all'importo dovuto.
- **Tutte le denominazioni**: selezionare questa opzione per visualizzare sempre tutte le denominazioni delle banconote nel POS, indipendentemente dall'importo dovuto. In tal modo, l'utente può utilizzare una combinazione di banconote per ottenere l'importo dovuto. Ad esempio, se l'importo dovuto è 25 USD, l'utente può scegliere 20 USD e 5 USD per completare la vendita.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
