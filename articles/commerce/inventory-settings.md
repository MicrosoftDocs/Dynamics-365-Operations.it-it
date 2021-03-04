---
title: Applicare impostazioni relative alle scorte
description: In questo argomento vengono descritte le impostazioni relative alle scorte e il modo in cui applicarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: dfa8b2bdc03e3698feda26932db757421097140d
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517066"
---
# <a name="apply-inventory-settings"></a>Applicare impostazioni relative alle scorte

[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le impostazioni relative alle scorte e il modo in cui applicarle in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Le impostazioni relative alle scorte specificano se le scorte devono essere verificate prima di aggiungere prodotti al carrello. Definiscono inoltre messaggi di merchandising, come "In stock" e "Pochi rimasti". Queste impostazioni assicurano che un prodotto non possa essere acquistato se è esaurito.

Dynamics 365 Commerce fornisce stime della disponibilità dei prodotti. Per informazioni su come viene calcolata la disponibilità stimata, vedere [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md).

In Creazione di siti Web di Commerce, è possibile definire soglie e intervalli di scorte per un prodotto o una categoria. Queste determinano se le scorte possono essere classificate come in stock, ridotte o esaurite. Per dettagli, vedere [Configurare buffer e livelli di scorte](inventory-buffers-levels.md).

> [!NOTE]
> Il supporto per le soglie e gli intervalli di inventario è disponibile in Dynamics 365 Commerce versione 10.0.12.

## <a name="inventory-settings"></a>Impostazioni relative alle scorte

In Commerce, è possibile definire le impostazioni relative alle scorte selezionando **Impostazioni sito \> Estensioni \> Gestione articoli** in Creazione di siti Web. Sono disponibili quattro impostazioni relative alle scorte, una delle quali è obsoleta (deprecata):

- **Abilita controllo scorte su app** - Questa impostazione attiva un controllo delle scorte del prodotto. I moduli Casella acquisti, Carrello e Preleva nel punto vendita verificheranno quindi le scorte del prodotto e consentiranno di aggiungere un prodotto al carrello solo se è disponibile.
- **Livello di scorte basato su** - Questa impostazione definisce come vengono calcolati i livelli di scorte. I valori disponibili sono **Totale disponibile**, **Fisico disponibile** e **Soglia esaurito**. In Commerce, è possibile definire soglie e intervalli di scorte per ogni prodotto e categoria. Le API relative alle scorte restituiscono informazioni sulle scorte del prodotto per le proprietà **Totale disponibile** e **Fisico disponibile**. Il rivenditore decide se il valore **Totale disponibile** o **Fisico disponibile** deve essere utilizzato per determinare il conteggio delle scorte e gli intervalli corrispondenti per gli stati In stock o Esaurito.

    Il valore **Soglia esaurito** dell'impostazione **Livello di scorte basato su** è un valore (legacy), obsoleto. Quando selezionato, il conteggio delle scorte viene determinato dai risultati del valore **Totale disponibile**, ma la soglia è definita dall'impostazione numerica **Soglia esaurito** descritta in seguito. Questa impostazione di soglia si applica a tutti i prodotti in un sito di e-commerce. Se le scorte sono inferiori al valore di soglia, un prodotto è considerato esaurito. Altrimenti, è considerato in stock. Le funzionalità dell'impostazione **Soglia esaurito** sono limitate e non è consigliabile utilizzarla nella versione 10.0.12 e successive.

- **Intervalli scorte** - Questa impostazione definisce gli intervalli delle scorte visualizzati nei moduli del sito. È applicabile solo se il valore **Totale disponibile** o il valore **Fisico disponibile** è selezionato per l'impostazione **Livello di scorte basato su**. I valori disponibili sono **Tutti**, **Ridotto e esaurito** e **Esaurito**.

    - Quando è selezionato **Tutti**, verranno visualizzati tutti gli intervalli di scorte, da In stock (messaggio "Disponibile") a Esaurito (messaggio "Esaurito").
    - Quando è selezionato **Ridotto e esaurito**, verranno visualizzati i messaggi di tutti gli intervalli di scorte, ad eccezione di In stock (messaggio "Disponibile").
    - Quando è selezionato **Esaurito**, verrà visualizzato solo il messaggio "Esaurito".

- **Soglia esaurito** - Questa vecchia impostazione numerica avrà effetto solo se il valore **Soglia esaurito** è selezionato per l'impostazione **Livello di scorte basato su**.

> [!IMPORTANT] 
> Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.12. Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Moduli che utilizzano le impostazioni relative alle scorte

I moduli Casella acquisti, Elenco preferenze, Selettore punto vendita, Carrello e Icona carrello utilizzano le impostazioni relative alle scorte per mostrare gli intervalli e i messaggi delle scorte.

L'immagine seguente mostra un esempio di pagina dettagli prodotto (PDP) che mostra un messaggio In stock ("Disponibile").

![Esempio di modulo PDP con messaggio In stock](./media/pdp-InStock.png)

L'immagine seguente mostra un esempio di PDP che mostra un messaggio "Esaurito".

![Esempio di modulo PDP con messaggio Esaurito](./media/pdp-outofstock.png)

L'immagine seguente mostra un esempio di carrello che mostra un messaggio In stock ("Disponibile").

![Esempio di modulo Carrello con messaggio In stock](./media/cart-instock.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Configurare buffer scorte e livelli scorte](inventory-buffers-levels.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Moduli e pagine gestione conti](account-management.md)

[Memorizzare il modulo di selezione](store-selector.md)

[SDK e aggiornamenti libreria dei moduli](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]