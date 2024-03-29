---
title: Ricerca per navigazione
description: Questo articolo illustra come utilizzare la funzionalità di ricerca per esplorare le pagine.
author: jasongre
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.openlocfilehash: 4c362e4cd83f926e7e21d775abd24ae6ddfcbbed
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292339"
---
# <a name="navigation-search"></a>Ricerca per navigazione

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Questo articolo illustra come utilizzare la funzionalità di ricerca per esplorare le pagine.

L'applicazione include una serie di aree e pagine utili per eseguire attività diverse. Per trovare rapidamente le pagine necessarie per completare le attività, utilizzare la funzionalità di ricerca per navigazione.

Per utilizzare questa funzionalità, fare clic sull'icona **Cerca** per visualizzare la casella **Cerca**. È possibile quindi digitare una o più parole nella casella. Il sistema cerca immediatamente nell'applicazione le pagine che corrispondono alle parole immesse. Ad esempio, è possibile immettere "fattura fornitore" come input, quindi il sistema visualizza i risultati che corrispondono all'input.

> [!NOTE]
> La casella **Cerca** consente di trovare e visualizzare le pagine. Non aiuterà a cercare azioni o dati specifici.

![casella di ricerca.](media/navigation-search.png "Casella di ricerca")

## <a name="quickly-navigate-to-a-particular-page"></a>Spostamento rapido a una pagina specifica

La funzionalità di ricerca per navigazione funge anche come ottimo modo per spostarsi rapidamente a una pagina specifica. Se ad esempio si dispone del ruolo di addetto alla contabilità fornitori che utilizza spesso la pagina **Giornale di registrazione pagamenti**, è possibile immettere "giornale di registrazione pagamenti" nella **casella di ricerca**. Poiché l'input è la corrispondenza esatta del titolo della pagina, la pagina viene elencata nella parte superiore dei risultati della ricerca ed è possibile accedervi rapidamente.

Nell'elenco dei risultati della ricerca vengono visualizzati il titolo della pagina e il percorso di navigazione. Mostra l'ubicazione della pagina nell'applicazione. Consente anche di fare una distinzione tra due o più pagine simili nei risultati.

Durante la ricerca di una pagina l'input viene abbinato al titolo della pagina, nonché al relativo percorso di navigazione. Ad esempio, se si immette "contabilità", nella casella **Cerca**, saranno visibili i risultati delle pagine disponibili nell'area Contabilità clienti, anche se i titoli delle pagine non includono la parola "contabilità".

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Spostamento rapido a una pagina in base al nome del tecnico modulo

La funzionalità di ricerca di navigazione include inoltre una funzione molto richiesta dai power user: la capacità di esplorare rapidamente una pagina in base al nome tecnico del modulo. Molti utenti hanno così tanta familiarità con il sistema che conoscono i nomi esatti dei moduli con cui lavorano. Se si è uno di questi utenti, è possibile immettere **modulo:** seguito dal nome del modulo che si ricerca. Ad esempio, se si immette **modulo: vendinvoice**, i risultati della ricerca mostreranno tutte le pagine in cui il nome del modulo inizia con **vendinvoice**.

## <a name="administration-and-security"></a>Amministrazione e sicurezza

Dal punto di vista della sicurezza e dell'amministrazione, la funzionalità di ricerca di navigazione visualizza solo due tipi di risultati.

- Pagine abilitate nella configurazione corrente (tramite chiavi di configurazione).
- Pagine a cui l'utente può accedere in base al ruolo utente.

L'elenco dei risultati della ricerca è limitato a 10 voci. Se nei risultati non è presente cosa si ricerca, è necessario provare a ridefinire o aggiornare l'input.

## <a name="development"></a>Sviluppo

Dal punto di vista dello sviluppo, la funzionalità di ricerca di navigazione è semplice da utilizzare poiché di fatto non esiste alcun ritardo tra la distribuzione delle voci di menu e la loro capacità di apparire nei risultati della ricerca. A condizione che il collegamento alle voci di menu sia stabilito sia tramite il pannello di navigazione che il dashboard, tali voci diventeranno automaticamente esplorabili.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
