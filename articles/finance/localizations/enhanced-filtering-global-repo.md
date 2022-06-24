---
title: Filtro avanzato RCS nel repository globale/RCS
description: Questo articolo descrive le funzionalità di filtro avanzate per il repository globale RCS, che sono state migliorate per includere i filtri aggiuntivi.
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a343b9f1af68a727cb2a8d1e390f85e10aab2d39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901214"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>RCS ha migliorato le opzioni del filtro per trovare le configurazioni nel repository globale/RCS

[!include [banner](../includes/banner.md)]

Questo articolo descrive le funzionalità di filtro avanzate per il repository globale Regulatory Configuration Services (RCS), le quali sono state migliorate per includere la possibilità di filtrare con i seguenti criteri: 
- **Paese/regione** - Basato sui codici ISO del paese  
- Tipi di **tag** per:
  - Area funzionale
  - Area funzionale
  - Settore 
  - Documento aziendale 

Per facilitare l'individuazione di configurazioni specifiche o correlate, è possibile applicare filtri, singolarmente o in gruppo. Ad esempio, per trovare un singolo tipo di documenti aziendali configurabili correlati alle fatture del fornitore, è possibile fare riferimento al filtro **Tipo di documento aziendale** per cercare il tipo di documento. 

[![Sezione del filtro per il repository globale.](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

È possibile affinare ulteriormente la ricerca selezionando il tipo di documento, ad esempio "fattura fornitore" e facendo clic sul tasto **Applica filtro**. L'esempio seguente mostra i risultati quando il filtro è attivo in **Tipo di documento aziendale** con il tipo di documento aggiunto. 

[![Filtro applicato e importazione per tipo di documento aziendale.](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

I risultati filtrati possono essere importati in un repository RCS dell'utente o in un ambiente Dynamics 365 Finance, singolarmente o come set. A questo scopo, selezionare il gruppo di configurazioni e fare clic su **Importa**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]