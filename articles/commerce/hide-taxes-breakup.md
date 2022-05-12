---
title: Nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini
description: Questo argomento descrive come nascondere le informazioni di dettaglio imposte nei riepiloghi degli ordini nelle pagine del carrello, del pagamento, della conferma dell'ordine e dei dettagli dell'ordine in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 9890b5cd92f8c07e6feabb26f4fdd076cb7a02bc
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645219"
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

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'IVA](/finance/general-ledger/indirect-taxes-overview)

[Configurare l'IVA per gli ordini online](sales-tax-config.md)

[Risoluzione dei problemi: L'IVA negli ordini online è calcolata in modo errato](troubleshoot/tax-miscalculated-online-order.md)
