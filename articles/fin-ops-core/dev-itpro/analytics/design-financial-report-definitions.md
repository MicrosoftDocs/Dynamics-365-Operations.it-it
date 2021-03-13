---
title: Definizioni di report in Progettazione report finanziari
description: In questo articolo vengono fornite informazioni sulle definizioni di report.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7d5531112cfb803912849af3af785b2a69a79f3d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093416"
---
# <a name="report-definitions-in-financial-report-designer"></a>Definizioni di report in Progettazione report finanziari

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sulle definizioni di report. Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report. Una definizione di report prevede inoltre opzioni e impostazioni che per la personalizzazione di un report. 

Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report. Nella definizione di report sono inoltre disponibili varie opzioni e impostazioni per la personalizzazione di un report. Dopo aver definito le definizioni di riga e le definizioni di colonna, è necessario combinarle in una definizione di report. In questa fase, vengono anche definiti altri aspetti delle definizioni, ad esempio la data del report e il livello di dettaglio. È quindi possibile salvare e generare un report. I report finanziari offrono i seguenti livelli di dettaglio:

- Finanziario
- Finanziario e contabile
- Finanziario, contabile e di transazione

A seconda della modalità di archiviazione dei dati nel sistema Microsoft Dynamics ERP, i dettagli delle transazioni potrebbero tuttavia non essere disponibili nei report.

## <a name="create-a-report-definition"></a>Creare una definizione del report
1. In Progettazione report, nel menu **File** fare clic su **Nuovo**, quindi selezionare **Definizione di report**.
2. Specificare le informazioni appropriate nelle schede **Report**, **Output e distribuzione**, **Intestazioni e piè di pagina** e **Impostazioni**.

## <a name="contents-of-a-report-definition"></a>Contenuto di una definizione di report
Nella seguente tabella sono descritte le schede in una definizione di report e come le informazioni vengono utilizzate.

<table>
<thead>
<tr>
<th>Scheda</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr>
<td>Report</td>
<td>Creare un report, configurare un report o modificare un report esistente.</td>
</tr>
<tr>
<td>Output e distribuzione</td>
<td>Modificare il tipo e la destinazione di output del report.</td>
</tr>
<tr>
<td>Intestazioni e piè di pagina</td>
<td>Definire e formattare le intestazioni e i piè di pagina del report. Ad esempio, è possibile aggiungere testo o immagini nell'intestazione o nel piè di pagina. I report finanziari supportano file con estensione bmp, jpg e png per le immagini. È inoltre possibile aggiungere i codici di testo automatico per inserire altre informazioni, ad esempio un nome di società, il nome del report o un numero di pagina.</td>
</tr>
<tr>
<td>Impostazioni</td>
<td>Specificare le impostazioni di definizione di report, ad esempio le seguenti impostazioni:
<ul>
<li>Formattazione e arrotondamento di importi</li>
<li>Formattare report dettagli</li>
<li>Formattare alberi gerarchici</li>
<li>Generare un report eccezioni</li>
<li>Specificare la conversione valuta</li>
<li>Eseguire subtotali e filtrare dettagli dei conti</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Risorse aggiuntive

[Creazione di report finanziari](financial-reporting-intro.md)
