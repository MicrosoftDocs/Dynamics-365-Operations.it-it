---
title: Dimensioni elemento di costo
description: Uno dei pilastri fondamentali della contabilità industriale, le dimensioni elemento di costo vengono utilizzate per categorizzare e tracciare il flusso dei costi.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 037d4971fe0a5a9d08f0ed20d2482b8feb9aa4f2
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178481"
---
# <a name="cost-element-dimensions"></a>Dimensioni elemento di costo

[!include [banner](../includes/banner.md)]

Uno dei pilastri fondamentali della contabilità industriale, le dimensioni elemento di costo vengono utilizzate per categorizzare e tracciare il flusso dei costi. 

Un elemento di costo corrisponde a un articolo pertinente per i costi nel piano dei conti. In sostanza, può essere qualsiasi tipo di elemento al livello più basso di un'azienda in cui i costi possono fluire. Gli elementi di costo come concetto variano dai conti CoGe a tutte le risorse pertinenti per i costi. Attualmente, la contabilità industriale supporta i conti CoGe.

## <a name="two-types-of-cost-elements"></a>Due tipi di elementi di costo
Sono disponibili due tipi di elementi di costo: elementi di costo primari ed elementi di costo secondari. Nella tabella seguente vengono descritte le differenze tra i due tipi.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Elementi di costo primari</strong></td>
<td><strong>Elementi di costo secondari</strong></td>
</tr>
<tr class="even">
<td>Gli elementi di costo primari rappresentano il flusso dei costi dalla contabilità finanziaria alla contabilità industriale. La struttura degli elementi di costo corrisponde alla struttura dei conti profitti e perdite in Contabilità generale, dove un elemento di costo può corrispondere a un conto principale. Non tutti i conti principali possono necessariamente essere rappresentati come elementi di costo in base alle esigenze aziendali. Esempi di elementi di costo primari sono:
<ul>
<li>I costi delle merci vendute (COGs)</li>
<li>Costi indiretti materiali</li>
<li>Costi del personale</li>
<li>Costi energetici</li>
</ul></td>
<td>Gli elementi di costo secondari rappresentano il flusso dei costi internamente perché tali costi vengono creati e utilizzati solo nella contabilità industriale. Vengono utilizzati per assicurare la traccia dell'origine dei costi. Questi elementi di costo vengono utilizzati nelle allocazioni dei costi e nei calcoli dei costi generali. Esempi di elementi di costo secondari sono:
<ul>
<li>Costi di produzione</li>
<li>Costi generali di produzione, materiali e marketing</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Dimensioni elemento di costo e membri di dimensioni elemento di costo
Gli elementi di costo vengono indicati come *dimensioni elemento di costo*. I singoli valori delle dimensioni vengono denominati *membri delle dimensioni elemento di costo*. Ad esempio, si dispone di una struttura del piano dei conti statunitense (COA) che costituisce la base per il reporting statutario. Questo COA viene utilizzato come dimensione elemento di costo. I conti, ovvero elementi di costo primari, sono rappresentati come membri della dimensione elemento di costo nella contabilità industriale. Nella schermata seguente è illustrato un esempio dei conti principali come dimensione elemento di costo con i relativi conti principali effettivi come membri della dimensione elemento di costo. 

[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>Importare i membri delle dimensioni elemento di costo tramite connettori dati
Per semplificare l'impostazione dei membri delle dimensioni elemento di costo nella contabilità industriale, è possibile utilizzare connettori dati predefiniti o personalizzati per recuperare gli elementi di costo primari da uno o più sistemi di origine.

## <a name="implementation-considerations"></a>Considerazioni sull'implementazione
Poiché gli elementi di costo rappresentano il livello minimo dei dettagli di costo, è necessario assicurarsi che tutti gli elementi di costo richiesti per effettuare il reporting gestionale siano inclusi durante l'implementazione della struttura degli elementi di costo. Può essere una sfida individuare un numero appropriato di elementi di costo per il controllo dei costi. La disponibilità di migliaia di elementi di costo può rendere difficile controllare ogni elemento di costo. In alternativa, è possibile raggruppare gli elementi di costo e gestire il controllo costi a livello aggregato.



