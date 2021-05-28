---
title: L'opzione Salva per prossimo pagamento non viene visualizzata
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la casella di controllo Salva per prossimo pagamento non viene visualizzata in Metodo di pagamento nella pagina di pagamento di un sito di e-commerce.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018436"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>L'opzione "Salva per prossimo pagamento" non viene visualizzata

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la casella di controllo **Salva per prossimo pagamento** non viene visualizzata in **Metodo di pagamento** nella pagina di pagamento di un sito di e-commerce.

## <a name="description"></a>Descrizione

La casella di controllo **Salva per prossimo pagamento** non viene visualizzata nella sezione **Metodo di pagamento** della pagina di pagamento di un sito di e-commerce.

La figura seguente mostra un esempio di una pagina di pagamento che include la casella di controllo **Salva per prossimo pagamento**.

![Casella di controllo Salva per prossimo pagamento nel modulo Pagamento](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Verificare che il Connettore pagamenti di Dynamics 365 per Adyen sia configurato correttamente in Commerce Headquarters

Per verificare che il Connettore pagamenti di Dynamics 365 per Adyen sia configurato correttamente in Commerce Headquarters, procedere come segue.

1. Andare a **Retail e Commerce \> Canali \> Punti vendita online**.
1. Selezionare il punto vendita online.
1. Nella Scheda dettaglio **Conti pagamento**, assicurarsi che il campo **Consenti salvataggio informazioni di pagamento in e-commerce** sia impostato su **True**.

![Campo Consenti salvataggio informazioni di pagamento in e-commerce di Commerce Headquarters](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo pagamento](../payment-module.md)

[Salvare gli strumenti di pagamento online con il connettore Adyen](../dev-itpro/adyen-connector-listPI.md)
