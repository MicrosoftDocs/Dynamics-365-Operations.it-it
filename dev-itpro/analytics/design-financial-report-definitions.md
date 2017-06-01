---
title: Definizioni di report in Progettazione report finanziari
description: "In questo articolo vengono fornite informazioni sulle definizioni di report. Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell&quot;albero gerarchico per creare un report. Una definizione di report prevede inoltre opzioni e impostazioni che per la personalizzazione di un report."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 86b527b72ef0c9af71e70fe280bcdfe3992a36b1
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="report-definitions-in-financial-report-designer"></a>Definizioni di report in Progettazione report finanziari

[!include[banner](../includes/banner.md)]


In questo articolo vengono fornite informazioni sulle definizioni di report. Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report. Una definizione di report prevede inoltre opzioni e impostazioni che per la personalizzazione di un report. 

Una definizione di report è un componente di report (o blocco predefinito) che utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report. Una definizione di report fornisce anche opzioni e impostazioni da utilizzare per personalizzare un report. Dopo aver definito le definizioni di riga e le definizioni di colonna, è necessario combinarle in una definizione di report. In questa fase, vengono anche definiti altri aspetti delle definizioni, ad esempio la data del report e il livello di dettaglio. È quindi possibile salvare e generare un report. I report finanziari offrono i seguenti livelli di dettaglio:

-   Finanziario
-   Finanziario e contabile
-   Finanziario, contabile e di transazione

Tuttavia, a seconda di come i dati vengono archiviati nel sistema Microsoft Dynamics ERP, i dettagli sulle transazioni potrebbero non essere disponibili nei report.

## <a name="create-a-report-definition"></a>Creare una definizione del report
1.  In Progettazione report, nel menu **File** fare clic su **Nuovo**, quindi selezionare **Definizione di report**.
2.  Specificare le informazioni appropriate nelle schede **Report**, **Output e distribuzione**, **Intestazioni e piè di pagina** e **Impostazioni**.

## <a name="contents-of-a-report-definition"></a>Contenuto di una definizione di report
Nella seguente tabella sono descritte le schede in una definizione di report e come le informazioni vengono utilizzate.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>TAB</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Report</td>
<td>Creare un report, configurare un report o modificare un report esistente.</td>
</tr>
<tr class="even">
<td>Output e distribuzione</td>
<td>Modificare il tipo e la destinazione di output del report.</td>
</tr>
<tr class="odd">
<td>Intestazioni e piè di pagina</td>
<td>Definire e formattare le intestazioni e i piè di pagina del report. Ad esempio, è possibile aggiungere testo o immagini nell'intestazione o nel piè di pagina. I report finanziari supportano file con estensione bmp, jpg e png per le immagini. È inoltre possibile aggiungere i codici di testo automatico per inserire altre informazioni, ad esempio un nome di società, il nome del report o un numero di pagina.</td>
</tr>
<tr class="even">
<td>Impostazioni</td>
<td>Specificare le impostazioni di definizione di report, ad esempio le seguenti impostazioni:
<ul>
<li>Formattazione e arrotondamento di importi</li>
<li>Formattare report dettagli</li>
<li>Formattare alberi gerarchici</li>
<li>Generare un report eccezioni</li>
<li>Specificare la conversione valuta</li>
<li>Eseguire subtotali e filtrare dettagli dei conti</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Vedere anche
--------

[Creazione di report finanziari](financial-reporting-intro.md)




