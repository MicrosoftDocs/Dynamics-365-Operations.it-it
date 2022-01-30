---
title: Panoramica della ricerca basata su cloud
description: In questo argomento viene fornita una panoramica della ricerca basata su cloud in Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/29/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: eb34780d5bdd41a128fff543fe0f1ef73cfead8b
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983671"
---
# <a name="cloud-powered-search-overview"></a>Panoramica della ricerca basata su cloud

[!include [banner](includes/banner.md)]

In questo argomento viene fornita una panoramica della ricerca basata su cloud in Microsoft Dynamics 365 Commerce.

L'individuazione dei prodotti garantisce ai clienti di trovare in modo semplice e rapido i prodotti esplorando le categorie, eseguendo ricerche e applicando filtri. Per i rivenditori, l'individuazione dei prodotti è uno strumento principale per l'interazione dei clienti in tutti i canali.

I clienti sono abituati ai tempi di risposta quasi istantanei dei motori di ricerca Web, ai siti Web di e-Commerce sofisticati, alle app social, ai suggerimenti automatici visualizzati quando digitano i termini di ricerca, all'esplorazione in base a facet e alla messa in risalto dei prodotti. Se i clienti non possono trovare il prodotto che stanno cercando in tempi brevi in un punto vendita di e-Commerce, non esiteranno a visitare un altro punto vendita di e-Commerce.

L'individuazione di prodotti basata su cloud in Dynamics 365 Commerce consente ai rivenditori di continuare ad aumentare i tassi di conversione e conservazione dei consumatori in tutti i canali, sia quelli di e-Commerce che POS.

L'esperienza di ricerca in Dynamics 365 Commerce include funzionalità migliorate che consentono ai rivenditori di avere una migliore individuazione dei prodotti. Nello stesso tempo, queste funzionalità offrono la scalabilità e le prestazioni necessarie per il traffico di e-Commerce.

## <a name="browse-and-search"></a>Esplorare e cercare

La pertinenza e le prestazioni delle ricerche sono fattori chiave nell'esperienza multicanale, poiché l'individuazione dei prodotti si basa principalmente sulla funzionalità di ricerca per il recupero di informazioni e l'esplorazione del contenuto. Un'esperienza di esplorazione e ricerca efficace ed efficiente consente di aumentare la conversione.

Nella figura seguente è illustrato un esempio di funzionalità di esplorazione e ricerca tipica.

![Pagina di destinazione della ricerca.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Esplorazione in base a facet e riepilogo delle scelte 

L'esplorazione in base a facet facilita l'esplorazione dei contenuto da parte dei clienti consentendo agli stessi di filtrare in base a criteri di affinamento collegati ai termini in un set di termini. Dopo che un cliente ha selezionato e applicato i criteri di affinamento, viene visualizzato un riepilogo delle scelte. 

Utilizzando l'esplorazione in base a facet, è possibile configurare differenti criteri di affinamento per diversi termini in un set di termini, senza dover creare pagine aggiuntive. 

Nella figura seguente è illustrato un esempio in cui l'esplorazione in base a facet è utilizzata in una ricerca.

![Riepilogo delle scelte.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Suggerimento automatico immersivo

La funzionalità di suggerimento automatico corrente mostra le parole chiave che avviano una ricerca della parola chiave corrispondente. Grazie a nuovi miglioramenti in Dynamics 365 Commerce, i clienti possono spesso individuare collegamenti a prodotti prima di aver terminato di digitare.

Dynamics 365 Commerce supporta inoltre funzionalità per le corrispondenze con parole chiave in varie categorie. Questa funzionalità consente ai clienti di vedere il numero di parole chiave corrispondenti nelle categorie e di attivare la ricerca di una parola chiave in altre categorie.

Nella figura seguente è illustrato un esempio di utilizzo della funzionalità di suggerimento automatico immersivo.

![Suggerimento automatico immersivo.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Ordina

L'ordinamento migliorato in Dynamics 365 Commerce consente ai clienti di ordinare, cercare ed esaminare i risultati della ricerca e di affinarli tramite criteri quali prezzo, nome del prodotto e numero del prodotto. I clienti possono inoltre ordinare i risultati a seconda se un prodotto è nuovo, tra i più venduti o aggiunto di recente.

>[!NOTE]
>Queste funzionalità di ricerca basate su cloud sono disponibili a partire dalla versione 10.0.8. Verifica che in **Parametri di commercio > Parametri di configurazione** c'è una voce per "ProductSearch.UseAzureSearch impostata su 'true'". 
![Parametri di configurazione per la ricerca basata su cloud.](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati di ricerca predefinite](category-search-page-overview.md)

[Gestire i metadati SEO](manage-seo-metadata.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
