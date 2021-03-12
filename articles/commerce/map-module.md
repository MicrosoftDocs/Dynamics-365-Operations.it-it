---
title: Modulo mappa
description: In questo argomento vengono descritti i moduli mappa e la procedura per configurarli in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e93358a9c76e8eb7bfb4ade4f772dece2aa5f7d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982493"
---
# <a name="map-module"></a>Modulo mappa

[!include [banner](includes/banner.md)]


In questo argomento vengono descritti i moduli mappa e la procedura per configurarli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo mappa mostra le posizioni dei punti vendita su una mappa interattiva il cui rendering viene eseguito utilizzando il [controllo Web Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/). È richiesta una chiave API di Bing Maps che deve essere aggiunta alla pagina Parametri condivisi di commercio in Commerce Headquarters. I moduli mappa offrono viste diverse, come stradale, aerea e Streetside, che gli utenti possono selezionare per visualizzare le posizioni della mappa. Consentono inoltre interazioni come lo zoom e l'utilizzo della posizione dell'utente.

Un modulo mappa interagisce con il modulo selettore punto vendita per determinare le posizioni geografiche dei punti vendita che devono essere visualizzati su una mappa. I moduli mappa e selettore punto vendita interagiscono quando un utente seleziona un punto vendita in uno di questi moduli in una pagina del sito. I moduli mappa possono essere estesi per altri scenari, oltre all'interazione con i moduli selettore punto vendita. Tuttavia, è richiesta la personalizzazione del modulo.

> [!NOTE]
> Il modulo di mapping è disponibile in Dynamics 365 Commerce versione 10.0.13.

L'immagine seguente mostra un esempio di modulo mappa utilizzato in una pagina delle posizioni dei punti vendita.

![Esempio di un modulo selettore punto vendita](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a>Proprietà del modulo

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| Intestazione | Testo | L'intestazione del modulo. |
| Opzioni puntina: icona predefinita | Immagine | L'immagine del simbolo della puntina da utilizzare per i punti vendita mostrati su una mappa. |
| Opzioni puntina: icona attiva | Immagine | L'immagine del simbolo della puntina da utilizzare per un punto vendita selezionato su una mappa. |
| Opzioni puntina: colore icona predefinita | Stringa di caratteri | Il testo o il valore esadecimale per il colore dei simboli della puntina su una mappa. |
| Opzioni puntina: colore icona attiva | Stringa di caratteri | Il testo o il valore esadecimale per il colore dei simboli della puntina selezionati su una mappa. |
| Mostra indice | **True** o **False** | Se questa proprietà è impostata su **True**, ogni simbolo della puntina che indica un punto vendita mostrerà un indice. Questo indice corrisponderà all'indice nella visualizzazione elenco mostrata dal modulo selettore punto vendita. |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a>Aggiungere gli URL di mapping consentiti alle direttive sui criteri di sicurezza dei contenuti di un sito

Affinché il modulo mappa interagisca con Bing Maps, è necessario assicurarsi che i seguenti URL di mapping siano consentiti in base ai criteri di sicurezza dei contenuti (CSP) del sito. Questa configurazione viene eseguita durante la creazione del sito di Commerce, aggiungendo gli URL consentiti a varie direttive CSP del sito (ad esempio, **img-src**). Per altre informazioni, vedere [Criteri di sicurezza dei contenuti](manage-csp.md). 

- Alla direttiva **connect-src**, aggiungere **&#42;bing.com**.
- Alla direttiva **img-src**, aggiungere **&#42; virtualearth.net**.
- Alla direttiva **script-src**, aggiungere **&#42;.bing.com, &#42;.virtualearth.net**.
- Alla direttiva **script style-src**, aggiungere **&#42;.bing.com**.

## <a name="add-a-map-module-to-a-page"></a>Aggiungere un modulo mappa a una pagina

Per informazioni dettagliate su come configurare un modulo mappa in una pagina, vedere [Modulo selettore punto vendita](store-selector.md). 
 
## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo carrello](add-cart-module.md)

[Memorizzare il modulo di selezione](store-selector.md)

[Gestire Bing Mappe per la tua organizzazione](./dev-itpro/manage-bing-maps.md)

[Controllo Web Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/)
