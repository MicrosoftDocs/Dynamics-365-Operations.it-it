---
title: Impostare gli scadenzari pagamenti con allocazione TDS
description: Questo argomento descrive come impostare scadenziari pagamenti con l'allocazione TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 55bfdfb97c418ec9fd856a151da46c1bcf94aa2cb4df85185b47f722d8526ef2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769724"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Impostare gli scadenzari pagamenti con allocazione TDS

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare scadenziari pagamenti con l'allocazione TDS.

1. Vai a **Contabilità fornitori \> Impostazione pagamenti \> Scadenziari pagamenti**.

    [![Pagina Scadenziari pagamenti.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. Nel riquadro azioni, seleziona **Nuovo** per creare uno scadenziario pagamenti e immettere i dettagli necessari.
3. Nel campo **Allocazione** seleziona il metodo da utilizzare per allocare il pagamento per lo scadenziario pagamenti:

    - Totale
    - Importo fisso
    - Quantità fissa
    - Specificato

    Il campo **Allocazione ritenuta d'acconto** mostra il metodo di allocazione della TDS per lo scadenziario pagamenti. Se selezioni **Totale** nel campo **Allocazione**, il campo **Allocazione ritenuta d'acconto** viene impostato automaticamente impostato su **Totale**. Se selezioni **Importo fisso**, **Quantità fissa** o **Specificato** nel campo **Allocazione**, il campo **Allocazione ritenuta d'acconto** viene impostato automaticamente su **In maniera proporzionale**.

    > [!NOTE]
    > Se il campo **Allocazione ritenuta d'acconto** è impostato su **Totale**, le rate di pagamento sono calcolate in base all'importo lordo, che include l'importo TDS. Se il campo **Allocazione ritenuta d'acconto** è impostato su **In maniera proporzionale**, le rate di pagamento sono calcolate in base all'importo fattura netto dopo la detrazione dell'importo TDS.

4. Immetti gli altri dettagli necessari e chiudi la pagina.
