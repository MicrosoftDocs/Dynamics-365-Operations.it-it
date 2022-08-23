---
title: Configurare un prodotto in modo da poterlo acquistare gratuitamente
description: Questo articolo descrive come configurare un prodotto in modo che possa essere acquistato gratuitamente in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88370085de047a5e0be773dde218770cfa242d14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280366"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Configurare un prodotto in modo da poterlo acquistare gratuitamente

[!include [banner](includes/banner.md)]


Questo articolo descrive come configurare un prodotto in modo che possa essere acquistato gratuitamente in Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>Configurare il prodotto

Per vendere un prodotto gratuitamente in Dynamics 365 Commerce, devi impostare il suo prezzo su 0 (zero). Inoltre, devi configurare l'impostazione del prodotto **Prezzo zero valido**.

Per configurare l'impostazione **Prezzo zero valido** in Commerce headquarters, seguire questi passaggi.

1. Vai a **Retail e Commerce \> Prodotti e categorie \> Prodotti relasciati per categorie**.
1. Vai al prodotto che vuoi vendere gratuitamente. 
1. Nella sezione **Commerce** della pagina del prodotto, imposta l'opzione **Prezzo zero valido** su **Sì**.

L'illustrazione seguente mostra un esempio di un prodotto in cui l'opzione **Prezzo zero valido** è impostata su **Sì**.

![Esempio di un prodotto in cui l'opzione Prezzo zero valido è impostata su Sì.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Configura il profilo delle funzionalità del negozio online

Prima che le transazioni gratuite possano essere elaborate, devi configurare l'impostazione **Consenti checkout senza pagamenti** del profilo di funzionalità per il tuo negozio online in modo che siano consentite le transazioni che non hanno pagamenti. Per informazioni su come creare profili di funzionalità, vedi [Crea un profilo di funzionalità online](online-functionality-profile.md).

Per configurare l'impostazione **Consenti checkout senza pagamenti** in Commerce headquarters, seguire questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione canale \> Impostazione punto vendita**.
1. Nella pagina del profilo delle funzionalità del tuo negozio, in **Pagamento**, imposta l'opzione **Consenti checkout senza pagamenti** su **Sì**.

L'illustrazione seguente mostra un esempio di profilo di un negozio online in cui l'opzione **Consenti checkout senza pagamenti** è impostata su **Sì**.

![Esempio di un negozio online in cui l'opzione Consenti checkout senza pagamenti è impostata su Sì.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestione dei prezzi di vendita al dettaglio](price-management.md)

[Creare un profilo funzionalità online](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
