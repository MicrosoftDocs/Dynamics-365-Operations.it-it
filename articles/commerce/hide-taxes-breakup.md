---
title: Nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini
description: Questo argomento descrive come nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini nelle pagine del carrello, del pagamento, della conferma dell'ordine e dei dettagli dell'ordine in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 9a0bff7afaa10e49ec05f18e2b0fae7a19b5e8af
ms.sourcegitcommit: 48d094d083c1bd45c3d72f8b666926b48ec7ae35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2022
ms.locfileid: "8767816"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento descrive come nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini nelle pagine del carrello, del pagamento, della conferma dell'ordine e dei dettagli dell'ordine in Microsoft Dynamics 365 Commerce.

Per impostazione predefinita Dynamics 365 Commerce mostra le informazioni di dettaglio imposte nei riepiloghi degli ordini nelle pagine del carrello, del pagamento, della conferma dell'ordine e dei dettagli dell'ordine. A partire dalla versione 10.0.27 di Commerce, il generatore di siti di Commerce include un'opzione che consente di nascondere le informazioni dei dettagli imposte nei riepiloghi degli ordini.

Nella figura seguente viene illustrato un esempio di due riepiloghi ordine. Il primo mostra le informazioni di dettaglio imposte e il secondo le nasconde.

![Esempi di carrelli in cui vengono mostrate e nascoste le informazioni di dettaglio imposte.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - L'opzione per nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini è disponibile solo quando l'opzione **Prezzi IVA inclusa** per il canale e-commerce è impostata su **sì** in Commerce headquarters, in **Vendita al dettaglio e commercio \> Canali \> Punti vendita \> Tutti i punti vendita**. 
> - Per impostazione predefinita, l'opzione **Mostra dettaglio imposte in riepilogo ordine** è abilitata nel generatore di siti.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini

Per nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini, segui questi passaggi.

1. Nel generatore di siti di Commerce vai al sito che desideri aggiornare.
1. Andare a **Impostazioni del sito \> Estensioni**.
1. Deseleziona la casella di controllo **Mostra dettaglio imposte in riepilogo ordine**.

Per mostrare le informazioni di dettaglio imposte nei riepiloghi degli ordini, seleziona la casella di controllo **Mostra dettaglio imposte in riepilogo ordine**.  

L'illustrazione seguente mostra la casella di controllo **Mostra dettaglio imposte in riepilogo ordine** evidenziata e selezionata nel generatore di siti.

![Opzione Mostra dettaglio imposte in riepilogo ordin nel generatore di siti.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

> [!NOTE]
> Se disponi di moduli di riepilogo degli ordini personalizzati e non desideri ereditare la funzionalità "nascondi le informazioni sulla ripartizione delle imposte nei riepiloghi degli ordini" in Commerce versione 10.0.27 o successiva, vedi [Il totale parziale del riepilogo ordine non include le imposte sugli addebiti quando si utilizzano moduli di riepilogo ordine personalizzati](troubleshoot/summary-taxes-custom-modules-10.0.27.md#resolution).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'IVA](/finance/general-ledger/indirect-taxes-overview)

[Configurare l'IVA per gli ordini online](sales-tax-config.md)

[Risoluzione dei problemi: L'IVA negli ordini online è calcolata in modo errato](troubleshoot/tax-miscalculated-online-order.md)
