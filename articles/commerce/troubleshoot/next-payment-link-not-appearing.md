---
title: L'opzione Salva per prossimo pagamento non viene visualizzata
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la casella di controllo Salva per prossimo pagamento non viene visualizzata in Metodo di pagamento nella pagina di pagamento di un sito di e-commerce.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d0b398a4ffc5fb698ea04ba8642d05ccd4caf04c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287486"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>L'opzione "Salva per prossimo pagamento" non viene visualizzata

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando la casella di controllo **Salva per prossimo pagamento** non viene visualizzata in **Metodo di pagamento** nella pagina di pagamento di un sito di e-commerce.

## <a name="description"></a>Descrizione

La casella di controllo **Salva per prossimo pagamento** non viene visualizzata nella sezione **Metodo di pagamento** della pagina di pagamento di un sito di e-commerce.

La figura seguente mostra un esempio di una pagina di pagamento che include la casella di controllo **Salva per prossimo pagamento**.

![Casella di controllo Salva per prossimo pagamento nel modulo Pagamento.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Verificare che il Connettore pagamenti di Dynamics 365 per Adyen sia configurato correttamente in Commerce Headquarters

Per verificare che il Connettore pagamenti di Dynamics 365 per Adyen sia configurato correttamente in Commerce Headquarters, procedere come segue.

1. Andare a **Retail e Commerce \> Canali \> Punti vendita online**.
1. Selezionare il punto vendita online.
1. Nella Scheda dettaglio **Conti pagamento**, assicurarsi che il campo **Consenti salvataggio informazioni di pagamento in e-commerce** sia impostato su **True**.

![Campo Consenti salvataggio informazioni di pagamento in e-commerce di Commerce Headquarters.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo pagamento](../payment-module.md)

[Salvare gli strumenti di pagamento online con il connettore Adyen](../dev-itpro/adyen-connector-listPI.md)
