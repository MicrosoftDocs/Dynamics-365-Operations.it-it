---
title: Convenzioni per l'ammortamento dei cespiti
description: In questo argomento vengono descritte le convenzioni per l'ammortamento dei cespiti.
author: saraschi2
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4315f70e7959e2576e9b87dfb3898318f47aa46d
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000271"
---
# <a name="fixed-asset-depreciation-conventions"></a>Convenzioni per l'ammortamento dei cespiti

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le convenzioni per l'ammortamento dei cespiti. Le convenzioni di ammortamento vengono utilizzate per determinare se e come l'ammortamento viene calcolato sia per l'anno in cui il cespite viene acquisito che per l'anno in cui il cespite viene scartato.

Le convenzioni di ammortamento possono essere assegnate all'impostazione di un libro gruppo cespiti. Per visualizzare o assegnare la convenzione di ammortamento, nell'area di impostazione dei cespiti, selezionare gruppi **Cespite**. Selezionare il pulsante **Libri**. In questo caso, le convenzioni di ammortamento assegnate vengono utilizzate come valori predefiniti quando i libri gruppo cespiti vengono creati. Le convenzioni di ammortamento possono inoltre essere impostate in un singolo libro cespiti. A tale scopo, selezionare **Libri** nell'area di impostazione dei cespiti e quindi fare clic sul pulsante **Gruppi di cespiti**.

| Convenzione di ammortamento   | Descrizione |
|---------------------------|-------------|
| Nessuno                      | L'ammortamento dei cespiti inizia nella data di <strong>Messa a servizio</strong>. |
| Semestre                 | Un semestre di ammortamento viene dedotto sia per il primo anno che per l'ultimo di cui si ammortizza la proprietà. Un intero anno di ammortamento viene dedotto ogni due anni durante il periodo di recupero. |
| Mese intero                | I cespiti con una data di <strong>Messa a servizio</strong> che si verifica in qualsiasi momento durante il mese iniziano l'ammortamento i primo giorno di quel mese. Ai fini dell'ammortamento, i beni sono considerati ritirati l'ultimo giorno del mese precedente. Il giorno specifico del mese in cui sono stati ritirati non viene considerato. |
| Metà trimestre               | Per calcolare la detrazione dell'ammortamento per l'anno quando si mette la proprietà a servizio, moltiplicare l'ammortamento per un intero anno per la percentuale per il trimestre in cui la proprietà viene messa a servizio, come illustrato nella tabella seguente.<table><thead><tr><th>Trimestre</th><th>Percentuale</th></tr></thead><tbody><tr><td>Nome</td><td>87.5</td></tr><tr><td>Seconda</td><td>62.5</td></tr><tr><td>Terza</td><td>37.5</td></tr><tr><td>Quarta</td><td>12.5</td></tr></tbody></table>Metà trimestre di ammortamento viene preso nel trimestre di dismissione del cespite (o di completo ammortamento) del cespite. |
| Metà mese (giorno 1 del mese)  | I cespiti con una data di <strong>Messa a servizio</strong> nella prima metà del mese (giorni da 1 a 15) iniziano l'ammortamento il primo giorno del mese in cui cade la data di <strong>Messa a servizio</strong>. I cespiti con una data di <strong>Messa a servizio</strong> nella seconda metà del mese (giorni da 16 fino alla fine del mese) iniziano l'ammortamento il primo giorno del mese successivo a quello in cui cade la data di <strong>Messa a servizio</strong>. I cespiti che sono stati ritirati nella prima metà del mese (giorni da 1 a 15) vengono considerati ritirati per scopi di ammortamento l'ultimo giorno del mese precedente. I cespiti che sono stati ritirati nella seconda metà del mese (giorni da 16 fino alla fine del mese) vengono considerati ritirati per scopi di ammortamento l'ultimo giorno del mese di ritiro. |
| Metà mese (giorno 15 del mese) | Per calcolare la detrazione dell'ammortamento per l'anno quando si mette la proprietà a servizio, moltiplicare l'ammortamento per un intero anno per una frazione. Il numeratore (numero superiore) della frazione è il numero di mesi completi dell'anno in cui la proprietà è a servizio, più 1/2 o (0,5). Il denominatore (numero inferiore) è 12. Se si smaltisce la proprietà prima della fine del periodo di recupero, utilizzare lo stesso metodo per calcolare la detrazione di ammortamento per l'anno di smaltimento. |
| Semestre (inizio anno) | I cespiti con una data di <strong>Messa a servizio</strong> che cade nella prima metà dell'anno iniziano l'ammortamento il primo giorno dell'anno (intero anno). I cespiti con una data di <strong>Messa a servizio</strong> che cade nella seconda metà dell'anno iniziano l'ammortamento a metà anno. |
| Semestre (prossimo anno)     | I cespiti con una data di <strong>Messa a servizio</strong> che cade nella prima metà dell'anno iniziano l'ammortamento il primo giorno dell'anno (intero anno). I cespiti con una data di <strong>Messa a servizio</strong> che cade nella seconda metà dell'anno iniziano l'ammortamento il primo giorno dell'anno successivo. I cespiti che sono stati ritirati nella prima metà dell'anno vengono considerati ritirati per scopi di ammortamento l'ultimo giorno dell'anno precedente. Qualsiasi ammortamento registrato durante l'anno corrente deve essere invertito o rettificato. I cespiti che sono stati ritirati nella seconda metà dell'anno vengono considerati ritirati per scopi di ammortamento l'ultimo giorno dell'anno di ritiro. |
