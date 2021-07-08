---
title: Applicare impostazioni relative alle scorte
description: In questo argomento vengono descritte le impostazioni relative alle scorte e il modo in cui applicarle in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3da447c298993794afa49a0fbaddb1c21cf6231a
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271307"
---
# <a name="apply-inventory-settings"></a>Applicare le impostazioni delle scorte

[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le impostazioni relative alle scorte e il modo in cui applicarle in Microsoft Dynamics 365 Commerce.

Le impostazioni relative alle scorte specificano se le scorte devono essere verificate prima di aggiungere prodotti al carrello. Definiscono inoltre messaggi di merchandising, come "In stock" e "Pochi rimasti". Queste impostazioni assicurano che un prodotto non possa essere acquistato se è esaurito.

Dynamics 365 Commerce fornisce stime della disponibilità dei prodotti. Per informazioni su come viene calcolata la disponibilità stimata, vedere [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md).

In Creazione di siti Web di Commerce, è possibile definire soglie e intervalli di scorte per un prodotto o una categoria. Queste determinano se le scorte possono essere classificate come in stock, ridotte o esaurite. Per dettagli, vedere [Configurare buffer e livelli di scorte](inventory-buffers-levels.md).

> [!NOTE]
> Il supporto per le soglie e gli intervalli di inventario è disponibile in Dynamics 365 Commerce versione 10.0.12.

## <a name="inventory-settings"></a>Impostazioni relative alle scorte

In Commerce, è possibile definire le impostazioni relative alle scorte selezionando **Impostazioni sito \> Estensioni \> Gestione articoli** in Creazione di siti Web. Sono disponibili cinque impostazioni relative alle scorte, una delle quali è obsoleta (deprecata):

- **Abilita controllo scorte su app** - Questa impostazione attiva un controllo delle scorte del prodotto. I moduli Casella acquisti, Carrello e Preleva nel punto vendita verificheranno quindi le scorte del prodotto e consentiranno di aggiungere un prodotto al carrello solo se è disponibile.
- **Livello di scorte basato su** - Questa impostazione definisce come vengono calcolati i livelli di scorte. I valori disponibili sono **Totale disponibile**, **Fisico disponibile** e **Soglia esaurito**. In Commerce, è possibile definire soglie e intervalli di scorte per ogni prodotto e categoria. Le API relative alle scorte restituiscono informazioni sulle scorte del prodotto per le proprietà **Totale disponibile** e **Fisico disponibile**. Il rivenditore decide se il valore **Totale disponibile** o **Fisico disponibile** deve essere utilizzato per determinare il conteggio delle scorte e gli intervalli corrispondenti per gli stati In stock o Esaurito.

    Il valore **Soglia esaurito** dell'impostazione **Livello di scorte basato su** è un valore (legacy), obsoleto. Quando selezionato, il conteggio delle scorte viene determinato dai risultati del valore **Totale disponibile**, ma la soglia è definita dall'impostazione numerica **Soglia esaurito** descritta in seguito. Questa impostazione di soglia si applica a tutti i prodotti in un sito di e-commerce. Se le scorte sono inferiori al valore di soglia, un prodotto è considerato esaurito. Altrimenti, è considerato in stock. Le funzionalità dell'impostazione **Soglia esaurito** sono limitate e non è consigliabile utilizzarla nella versione 10.0.12 e successive.

- **Livello di scorte per più magazzini** - Questa impostazione consente di calcolare il livello di scorte rispetto al magazzino predefinito o a più magazzini. L'opzione **Basato su singolo magazzino** calcolerà i livelli di scorte in base al magazzino predefinito. In alternativa, un sito di e-commerce può puntare a più magazzini per facilitare l'evasione. In tal caso, l'opzione **Basato su aggregazione per magazzini di spedizione e prelievo** viene utilizzata per indicare la disponibilità di scorte. Ad esempio, quando un cliente acquista un articolo e seleziona "spedizione" come modalità di consegna, l'articolo può essere spedito da qualsiasi magazzino nel gruppo di evasione ordini che dispone di scorte disponibili. La pagina dei dettagli del prodotto (PDP) mostrerà un messaggio "Disponibile" per la spedizione se un magazzino di spedizione disponibile nel gruppo di evasione ha scorte. 

> [!IMPORTANT] 
> L'impostazione **Livello di scorte per più magazzini** è disponibile a partire dalla versione Commerce 10.0.19. Se stai aggiornando da una versione precedente di Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni, vedi [SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Intervalli scorte** - Questa impostazione definisce gli intervalli delle scorte visualizzati nei moduli del sito. È applicabile solo se il valore **Totale disponibile** o il valore **Fisico disponibile** è selezionato per l'impostazione **Livello di scorte basato su**. I valori disponibili sono **Tutti**, **Ridotto e esaurito** e **Esaurito**.

    - Quando è selezionato **Tutti**, verranno visualizzati tutti gli intervalli di scorte, da In stock (messaggio "Disponibile") a Esaurito (messaggio "Esaurito").
    - Quando è selezionato **Ridotto e esaurito**, verranno visualizzati i messaggi di tutti gli intervalli di scorte, ad eccezione di In stock (messaggio "Disponibile").
    - Quando è selezionato **Esaurito**, verrà visualizzato solo il messaggio "Esaurito".

- **Soglia esaurito** - Questa vecchia impostazione numerica avrà effetto solo se il valore **Soglia esaurito** è selezionato per l'impostazione **Livello di scorte basato su**.

> [!IMPORTANT] 
> Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.12. Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Moduli che utilizzano le impostazioni relative alle scorte

I moduli Casella acquisti, Elenco preferenze, Selettore punto vendita, Carrello e Icona carrello utilizzano le impostazioni relative alle scorte per mostrare gli intervalli e i messaggi delle scorte.

Nell'esempio nella figura seguente, un PDP mostra un messaggio "Disponibile".

![Esempio di modulo PDP con messaggio In stock](./media/pdp-InStock.png)

Nell'esempio nella figura seguente, un PDP mostra un messaggio "Esaurito".

![Esempio di modulo PDP con messaggio Esaurito](./media/pdp-outofstock.png)

Nell'esempio nella figura seguente, un carrello mostra un messaggio "Disponibile".

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
