---
title: Modulo Selettore punto vendita
description: In questo argomento viene descritto il modulo selettore punto vendita e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157342"
---
# <a name="store-selector-module"></a>Modulo Selettore punto vendita

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo selettore punto vendita e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo selettore punto vendita viene utilizzato per lo scenario del cliente "acquisto online, ritiro in negozio" (BOPIS). Visualizza un elenco di negozi in cui un prodotto è disponibile per il ritiro, nonché gli orari e l'inventario del prodotto per ciascun negozio.

Il modulo selettore punto vendita richiede il contesto di un prodotto e una posizione di ricerca per trovare i punti vendita. In assenza di un percorso di ricerca, viene impostato automaticamente il percorso del browser del cliente, a condizione che il cliente fornisca il consenso. Il modulo ha una casella di input che consente al cliente di inserire una posizione (codice postale o città e stato) per trovare i negozi nelle vicinanze.

Il modulo Selettore punto vendita è integrato nell'API di geocodifica di Bing Maps per convertire l'ubicazione in una latitudine e una longitudine. È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di commercio in Dynamics 365 Commerce.

Il modulo selettore punto vendita può essere aggiunto a un modulo casella acquisti nella pagina dei dettagli del prodotto (PDP) per visualizzare i negozi in cui un prodotto è disponibile per il ritiro. Può anche essere aggiunto a un modulo carrello. Quando aggiunto a un modulo carrello, il modulo selettore punto vendita visualizza le opzioni di ritiro per ciascun articolo nel carrello. Inoltre, con la codifica personalizzata questo modulo può essere aggiunto ad altre pagine o moduli tramite estensioni e personalizzazioni.

Affinché lo scenario BOPIS funzioni, i prodotti devono essere configurati con la modalità di consegna "ritiro del cliente". Altrimenti, il modulo non verrà mostrato nelle rispettive pagine. Per i dettagli su come configurare la modalità di consegna, vedere [Impostare le modalità di consegna](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

L'immagine seguente mostra un esempio di un modulo selettore punto vendita utilizzato su un PDP.

![Esempio di un modulo selettore punto vendita](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Utilizzo del modulo selettore punto vendita in e-Commerce

- Un modulo selettore punto vendita può essere usato come pagina dei dettagli del prodotto (PDP) per trovare i negozi nelle vicinanze in cui un prodotto è disponibile per il ritiro.
- Un modulo selettore punto vendita può essere usato in una pagina carrello per trovare i negozi nelle vicinanze in cui un prodotto nel carrello è disponibile per il ritiro.

## <a name="store-selector-module-properties"></a>Proprietà del modulo selettore punto vendita

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| Raggio di ricerca | Numero | Definisce il raggio di ricerca dei negozi, in miglia. Se non viene specificato alcun valore, viene utilizzato il raggio di ricerca predefinito, ovvero 50 miglia.|
|Condizioni d'uso | URL    |  L'URL delle condizioni d'utilizzo è necessario per il servizio Bing Maps. |

## <a name="add-a-store-selector-module-to-a-page"></a>Aggiungere un modulo selettore punto vendita a una pagina

Un modulo modulo selettore punto vendita ha bisogno del contesto di un prodotto, quindi può essere utilizzato solo nei moduli acquisto e carrello. I moduli modulo selettore punto vendita non funzionano al di fuori di questi moduli.

- Per informazioni su come aggiungere un modulo modulo selettore punto vendita a un modulo di acquisto, vedere [Modulo casella acquisti](add-buy-box.md). 
- Per informazioni su come aggiungere un modulo modulo selettore punto vendita a un modulo carrello, vedere [Modulo carrello](add-cart-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo carrello](add-cart-module.md)

[Demo veloce di PDP](quick-tour-pdp.md)

[Demo veloce di carrello e check out](quick-tour-cart-checkout.md)

[Imposta la modalità di consegna](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
