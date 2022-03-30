---
title: Limite di soglia e limite di soglia di eccezione
description: In questo argomento vengono descritti i limiti di soglia e di eccezione per l'imposta dedotta all'origine (TDS, Tax Deducted at Source).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8391953024f302e75f23c72f8078d59a5541e24b
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408206"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Limite di soglia e limite di soglia di eccezione

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i limiti di soglia e di eccezione per l'imposta dedotta all'origine (TDS, Tax Deducted at Source). La TDS su fatture e pagamenti è sempre calcolata considerando il limite di soglia e il limite di soglia di eccezione definiti per i componenti fiscali TDS nella pagina **Componenti ritenuta d'acconto**. I componenti fiscali TDS sono associati ai codici imposta TDS, inclusi nei gruppi di imposte TDS. I gruppi di imposte TDS sono associati a fornitori e clienti per calcolare la TDS a livello di fattura o di pagamento.

La TDS viene calcolata se l'importo di una transazione o le transazioni cumulative registrate con uno specifico gruppo TDS per un fornitore supera il limite di soglia specificato nella pagina **Componenti ritenuta d'acconto**. La TDS non verrà calcolata fino a quando l'importo cumulativo della transazione non supera il limite di soglia specificato.

Se viene specificato un limite di soglia di eccezione insieme al limite di soglia per un componente TDS, la TDS viene calcolata quando un importo di transazione specifico supera il limite di soglia di eccezione anche se l'importo cumulativo della transazione non supera il limite di soglia specificato.

### <a name="example"></a>Esempio
Un componente fiscale denominato TDS viene impostato e associato al gruppo di imposte TDS denominato Terzista. La soglia è 50.000 e la soglia di eccezione è 20.000 per il componente fiscale TDS. Il terzista del gruppo TDS è definito come gruppo TDS predefinito per il fornitore 1.

Una fattura di acquisto 001 viene registrata per il fornitore 1 per 10.000. La TDS non viene calcolata per la fattura perché l'importo della fattura non ha superato il limite di soglia o il limite di soglia di eccezione. Una fattura di acquisto 002 viene registrata per il fornitore 1 per 25.000. La TDS viene calcolata per la fattura perché l'importo della fattura non ha superato il limite di soglia o il limite di soglia di eccezione. Una fattura di acquisto 003 viene registrata per il fornitore 1 per 20.000. La TDS viene calcolato per la fattura perché l'importo totale delle tre fatture emesse per il fornitore ha superato il limite di soglia. La TDS viene calcolata su tutte le fatture emesse per il fornitore su cui la TDS non è stata calcolata in precedenza. Pertanto, la TDS viene calcolata su 30.000, che è l'importo totale delle fatture 001 e 003.

Il limite di soglia e il limite di soglia di eccezione non vengono considerati per il calcolo della TDS se la casella di controllo **ignora soglia** è selezionata per i codici imposta TDS nel gruppo TDS associato alla transazione. Il limite di soglia non verrà utilizzato nei codici imposta TDS nel gruppo TDS per il quale è selezionata la casella di controllo **Ignora soglia**.

Se la casella di controllo **Ignora soglia** è selezionata per un gruppo TDS specifico per alcune fatture, ma non selezionata per altre fatture create per uno specifico fornitore/cliente, è possibile eseguire il calcolo della TDS senza ignorare il limite di soglia per alcune fatture prendendo in considerazione l'importo cumulativo di tutte fatture su cui la TDS non è stato calcolata in precedenza.

Ad esempio, il limite di soglia è 25000. Le seguenti fatture vengono create per il Fornitore A:

- Fattura 1 - 20.000 - (la casella di controllo **Ignora soglia** non è selezionata): la TDS non viene calcolata.

- Fattura 2 - 4.000 - (la casella di controllo **Ignora soglia** è selezionata): la TDS viene calcolata su 4.000.

- Fattura 2 - 3.000 - (la casella di controllo **Ignora soglia** non è selezionata): la TDS viene calcolata come importo cumulativo delle fatture, ovvero 27.000 (20.000 + 4.000 + 3.000) ha superato il limite di soglia. La TDS viene calcolata sull'importo cumulativo delle fatture su cui la TDS non è stata calcolata in precedenza, ovvero 23.000 (20.000 + 3.000).
