---
title: Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito
description: In questo argomento vengono descritte le considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito dallo sviluppo alla produzione.
author: psimolin
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 52a10c754315bfef2a01c593f5fa5366e9054982
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791801"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito


[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito dallo sviluppo alla produzione.

## <a name="a-site-that-is-under-development"></a>Sito in fase di sviluppo

Quando un sito è in fase di sviluppo, tutte le pagine del sito deve avere i tag **NOFOLLOW** e **NOINDEX**, di modo che i motori di ricerca non indicizzino le pagine e memorizzino le versioni di sviluppo del sito nella cache. Per eseguire questa configurazione, è necessario aggiungere il modulo Tag meta predefinito al modello di pagina del sito. Le proprietà dei tag meta predefiniti saranno quindi disponibili nella sezione delle proprietà SEO nell'editor di pagine. È possibile utilizzare queste proprietà per gestire i tag meta.

## <a name="soft-launch-of-a-site"></a>Soft launch di un sito

Durante un "soft launch", un sito Web è disponibile a un'audience o un mercato limitato prima che venga eseguito il full launch. Se si esegue un soft launch del sito Web, è necessario prendere in considerazione la possibilità di mantenere i tag meta **NOINDEX**. In questo modo, il soft launch rimane disponibile solo per l'audience limitata a cui è destinato.

## <a name="a-site-that-is-in-production"></a>Sito in produzione

Quando un sito è in produzione, è necessario assicurarsi che tutte le pagine del sito siano contrassegnate correttamente. Microsoft Dynamics 365 Commerce utilizza le informazioni immesse per una pagina per eseguire il rendering di tutte le informazioni SEO in quella pagina. I moduli seguenti forniscono queste funzionalità: riepilogo della pagina categoria, riepilogo della pagina elenco e riepilogo della pagina prodotto.

Per ottimizzare l'indicizzazione del motore di ricerca, il framework di rendering utilizza le informazioni delle proprietà SEO configurate in Dynamics 365 Commerce e le informazioni specifiche del modulo. Per un sito in produzione, è necessario assicurarsi che il file robots.txt consenta l'indicizzazione dell'intero sito e contenga collegamenti al documento sulla mappa del sito pubblicato. Attivare la funzionalità di generazione della mappa del sito in **Impostazioni sito \> Mappe del sito abilitate**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Impostazioni SEO delle pagine per anteprima interna, audience limitata e tutte le audience

Poiché Dynamics 365 Commerce supporta le anteprime autenticate WYSIWYG nel generatore di pagine visivo, gli autori possono preparare il contenuto delle pagine senza preoccuparsi che le informazioni saranno visibili ai visitatori del sito. Se è necessario pubblicare una pagina, ma l'esposizione deve essere limitata, deve avere il tag meta **NOINDEX**, di modo che non venga indicizzata dai motori di ricerca. Quindi, quando la pagina è pronta per tutte le audience, tutti i metadati SEO di base devono essere presenti, allo scopo di ottimizzare l'efficienza di indicizzazione dei motori di ricerca. Inoltre, il tag meta **NOLIMIT** deve essere rimosso.

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire utenti e ruoli di e-Commerce](manage-ecommerce-users-roles.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

[Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]