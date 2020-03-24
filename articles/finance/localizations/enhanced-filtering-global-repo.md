---
title: Filtro avanzato nel repository globale RCS
description: Questo argomento descrive le funzionalità di filtro avanzate per il repository globale RCS, che sono state migliorate per includere i filtri aggiuntivi.
author: JaneA07
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ed5a217b8844bfc76d53370ab4c4c339f5bece36
ms.sourcegitcommit: 0dcdfedec7125562f6b33deb009a3e044a1243eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "3099869"
---
# <a name="enhanced-filtering-options-for-finding-configurations-in-the-global-repository"></a>Opzioni di filtro avanzate per la ricerca di configurazioni nel repository globale

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento descrive le funzionalità di filtro avanzate per il repository globale Regulatory Configuration Services (RCS), che sono state migliorate per includere i filtri seguenti: 
- **Paese/Area geografica** - basato sui codici ISO del paese  
- **Tag** - per area funzionale/caratteristica, settore, tipo di documento aziendale 

È possibile applicare filtri, individualmente o in gruppi, per trovare configurazioni specifiche o correlate. Ad esempio, per trovare tutti i documenti aziendali configurabili relativi alle fatture del fornitore, è possibile applicare il filtro **Tipo di documento aziendale**. 

È possibile affinare ulteriormente una ricerca selezionando il codice paese e facendo clic su **Applica filtro**.  

[![Sezione del filtro per il repository globale](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

L'esempio seguente mostra i risultati quando il filtro è attivo in **Tipo di documento aziendale**. 

[![Filtro applicato e importazione per tipo di documento aziendale](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

I risultati filtrati possono essere importati negli ambienti RCS o Dynamics 365 Finance degli utenti, individualmente o come set (selezionando il gruppo di configurazioni) e facendo clic su **Importa**.






