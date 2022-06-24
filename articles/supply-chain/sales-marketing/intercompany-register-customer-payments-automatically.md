---
title: Registrare automaticamente i pagamenti per le fatture cliente interaziendali
description: In questo articolo viene descritto come registrare automaticamente i pagamenti per le fatture cliente interaziendali
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4e8f784cd310026f0a647a0f509999e11ab26ce5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878789"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Registrare automaticamente i pagamenti per le fatture cliente interaziendali

[!include [banner](../../includes/banner.md)]

In Microsoft Dynamics 365 Supply Chain Management viene creata una transazione cliente quando viene registrata una fattura cliente interaziendale. Tale transazione cliente resta aperta fino a quando non viene liquidata, ovvero pagata. Quando la quantità dell'ordine fornitore interaziendale corrispondente viene aggiornata in fattura, viene creata una transazione fornitore corrispondente alla transazione cliente. Anche questa transazione fornitore resta aperta fino a quando non viene liquidata. Per ridurre il rischio di discrepanze, è possibile creare e registrare automaticamente un giornale pagamenti della contabilità clienti quando viene registrato il giornale pagamenti della contabilità fornitori.

1. Vai a **Vendite e marketing \> Clienti \> Tutti i clienti**.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Per impostare i pagamenti di contabilità clienti interaziendali nella pagina **Interaziendale** per gli ordini cliente, selezionare il collegamento **Criteri ordine cliente**.
1. Nel campo **Giornale di registrazione pagamenti** selezionare il giornale pagamenti della contabilità clienti in cui si desidera registrare i pagamenti fornitore interaziendali. È possibile impostare questa opzione nella pagina **Parametri di contabilità clienti**.
1. Se si desidera registrare su questo giornale di registrazione automaticamente, selezionare la casella di controllo **Registra giornale di registrazione automaticamente**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
