---
title: Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito
description: In questo articolo vengono descritte le considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito dallo sviluppo alla produzione.
author: josaw1
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 77bbc04e849cf1cdeb7ce19226f43354635ddbe0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275621"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito


[!include [banner](includes/banner.md)]

In questo articolo vengono descritte le considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito dallo sviluppo alla produzione.

## <a name="a-site-that-is-under-development"></a>Sito in fase di sviluppo

Per garantire che i motori di ricerca non indicizzino un sito in fase di sviluppo, tutte le pagine del sito devono avere i meta tag **noindex** e **nofollow**. Una buona pratica è creare un frammento basato sul [modulo MetaTag](metatags-module.md) che contiene la seguente voce di meta tag e assicurarsi che il frammento venga aggiunto alla sezione HTML \<head\> di tutti i modelli utilizzati sul tuo sito.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>Soft launch di un sito

Durante un "soft launch", un sito Web è disponibile a un'audience o un mercato limitato prima che venga eseguito il full launch. Se si esegue un soft launch del sito Web, è necessario prendere in considerazione la possibilità di mantenere i meta tag **noindex**. In questo modo, il soft launch rimane disponibile solo per l'audience limitata a cui è destinato.

## <a name="a-site-that-is-in-production"></a>Sito in produzione

Quando un sito è in produzione, è necessario assicurarsi che tutte le pagine del sito siano contrassegnate correttamente. Microsoft Dynamics 365 Commerce utilizza le informazioni immesse per una pagina per eseguire il rendering di tutte le informazioni SEO in quella pagina. I moduli seguenti forniscono queste funzionalità: riepilogo della pagina categoria, riepilogo della pagina elenco e riepilogo della pagina prodotto.

Per ottimizzare l'indicizzazione del motore di ricerca, il framework di rendering utilizza le informazioni delle proprietà SEO configurate in Dynamics 365 Commerce e le informazioni specifiche del modulo. Per un sito in produzione, è necessario assicurarsi che il file robots.txt consenta l'indicizzazione dell'intero sito e contenga collegamenti al documento sulla mappa del sito pubblicato. Attivare la funzionalità di generazione della mappa del sito in **Impostazioni sito \> Mappe del sito abilitate**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Impostazioni SEO delle pagine per anteprima interna, audience limitata e tutte le audience

Poiché Dynamics 365 Commerce supporta le anteprime autenticate WYSIWYG nel generatore di pagine visivo, gli autori possono preparare il contenuto delle pagine senza preoccuparsi che le informazioni saranno visibili ai visitatori del sito. Se è necessario pubblicare una pagina, ma l'esposizione deve essere limitata, deve avere il meta tag **noindex**, di modo che non venga indicizzata dai motori di ricerca. Quindi, quando la pagina è pronta per tutte le audience, tutti i metadati SEO di base devono essere presenti, allo scopo di ottimizzare l'efficienza di indicizzazione dei motori di ricerca. Inoltre, il meta tag **nolimit** deve essere rimosso.

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire utenti e ruoli di e-Commerce](manage-ecommerce-users-roles.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

[Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
