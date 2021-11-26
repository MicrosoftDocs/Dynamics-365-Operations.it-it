---
title: Impostare il commercio interaziendale
description: In questo argomento viene illustrato come impostare il commercio interaziendale
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7288cc8f336b6b1f5174fe2bef38017e0c96e560
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777718"
---
# <a name="set-up-intercompany-trade"></a>Impostare il commercio interaziendale

[!include [banner](../../includes/banner.md)]

Per consentire l'esecuzione di operazioni di commercio interaziendale da parte di Microsoft Dynamics 365 Supply Chain Management, è necessario impostare di conseguenza i clienti e i fornitori. È inoltre necessario impostare la contabilità fornitori, la contabilità clienti, l'approvvigionamento e le vendite e marketing.

## <a name="before-you-set-up-intercompany-trade"></a>Prima di impostare il commercio interaziendale

Prima di impostare il commercio interaziendale, è necessario decidere quali clienti e fornitori saranno clienti e fornitori interaziendali. Per ogni persona giuridica in Microsoft Dynamics 365 Supply Chain Management, è necessario definire i criteri commerciali da applicare alla relazione commerciale interaziendale con il cliente o il fornitore interaziendale in questione.

In particolare, si dovrebbe acquisire familiarità sia personalmente che come organizzazione con i parametri interaziendali.

- Discutere delle implicazioni dell'impostazione con i dirigenti responsabili del commercio interaziendale per ogni persona giuridica.
- Impostare i valori appropriati per ogni persona giuridica.

## <a name="set-up-trading-relations"></a>Impostare le relazioni commerciali

Per impostare il commercio interaziendale per clienti e fornitori, attenersi alla procedura indicata di seguito.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Selezionare un account cliente.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Specificare i parametri interaziendali di impostazione per il conto cliente. Questi parametri includono la persona giuridica che contiene il fornitore corrispondente e il conto fornitore. I parametri includono inoltre i criteri dell'ordine fornitore, i criteri dell'ordine cliente, il mapping di valori e i criteri dei contratti di vendita e di acquisto. È inoltre necessario specificare se utilizzare i valori di dati di base dal conto cliente o dal conto fornitore in un'altra persona giuridica.
1. Ripetere i passaggi da 1 a 4 per i clienti interaziendali rimanenti della persona giuridica.
1. Andare a **Contabilità fornitori \>Fornitori \> Tutti i fornitori**.
1. Selezionare un conto fornitore.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Specificare i parametri interaziendali di impostazione per il conto fornitore. Questi parametri includono la persona giuridica che contiene il cliente corrispondente e il conto cliente. I parametri includono inoltre i criteri dell'ordine cliente, i criteri dell'ordine fornitore, il mapping di valori e i criteri dei contratti di acquisto e di vendita. È inoltre necessario specificare se utilizzare i valori di dati di base dal conto fornitore o dal conto cliente in un'altra persona giuridica.
1. Ripetere i passaggi da 6 a 9 per i fornitori interaziendali rimanenti della persona giuridica.

## <a name="set-up-products"></a>Impostare i prodotti

Per impostare il commercio interaziendale per clienti e fornitori, attenersi alla procedura indicata di seguito.

1. Andare a **Gestione informazioni sul prodotto \> Prodotti \> Tutti i prodotti e tutte le rappresentazioni generali prodotto**.
1. Definire i prodotti che vengono rilasciati alle persone giuridiche con cui si desidera effettuare il commercio interaziendale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
