---
title: Configurare i nomi del campo dell&quot;app Approvazioni nell&quot;app Approvazioni di immagazzinamento
description: "In questo argomento viene descritto come impostare e configurare i nomi e le priorità del campo dell&quot;app Approvazioni di magazzino in Dynamics 365 per le operazioni."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Configurare i nomi del campo dell'app Approvazioni nell'app Approvazioni di immagazzinamento

In questo argomento viene descritto come impostare e configurare i nomi e le priorità del campo dell'app Approvazioni di magazzino in Dynamics 365 per le operazioni. 

** Nota: ** In questo argomento viene applicato alle funzionalità della gestione magazzino. Non è applicabile alle funzionalità di Gestione articoli. Dynamics 365 per le operazioni di magazzino è un'applicazione che consentono di eseguire attività di magazzino. È possibile definire e configurare i nomi dei campi utilizzati nell'app Approvazioni nonché configurare la priorità a cui i nomi dei campi devono essere assegnati. In questo argomento viene illustrato come definire e configurare questi per immagazzinare i nomi e le priorità del campo dell'app Approvazioni e come vengono utilizzati in Dynamics 365 per le operazioni di immagazzinando. Per informazioni dettagliate sulla configurazione della connessione in Dynamics 365 per le operazioni di immagazzinando, fare riferimento al esercitazione [impostare e configurare Dynamics 365 per le operazioni di immagazzinanti install-configure-warehousing-app.md] ().

<a name="configure-warehouse-app-field-names"></a>Configurare i nomi del campo dell'app Approvazioni di magazzino
===================================

Quando si utilizza Dynamics 365 per le operazioni di immagazzinando sul dispositivo mobile, è possibile configurare la modalità dei metadati da visualizzare sull'unità ** immagazzinate nei nomi del campo dell'app Approvazioni ** pagina. In una nuova società in Dynamics 365 per le operazioni, selezionare ** creare l'impostazione predefinita ** generare tutti i nomi dei campi che verranno utilizzati nei flussi di lavoro del dispositivo mobile di magazzino e quindi specificare la modalità di input e un tipo di input preferiti. Dopo aver generato alcun nome del campo, è possibile selezionare le seguenti operazioni in cui immettere le opzioni.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Modalità di input preferita</td>
<td>Questa opzione indica se un campo della scansione o un campo di input di immissione manuale deve essere visualizzato per il nome del campo selezionato. Questa opzione è utile per distinguere i campi in base ai codici a barre vengono utilizzati per il campo. <strong>Nota:</strong> Per i nomi dei campi con la modalità di input preferito impostata <strong>Scansione</strong>su, è possibile immettere manualmente le informazioni se il codice a barre è illeggibile o spostato.</td>
</tr>
<tr class="even">
<td>Tipo di input</td>
<td>Questa opzione indica il tipo di input da utilizzare per il nome del campo selezionato. Quattro opzioni disponibili:
<ul>
<li><strong>Selezione</strong> - contiene un elenco di opzioni per effettuare la selezione da. I nomi dei campi con questa opzione non sono modificabili.</li>
<li><strong>Data</strong>i nomi dei campi - specificati come data verranno visualizzati un formato di data all'etichetta. In questo modo i lavoratori magazzino a individuare la formato di data. I nomi dei campi con questa opzione non sono modificabili.</li>
<li><strong>Alpha</strong> - se l'opzione è selezionata, la tastiera per unità verrà utilizzato per fornire le informazioni manualmente nell'app Approvazioni. Esperienza tastiera può essere modificata in base all'unità viene utilizzata.</li>
<li><strong>Numerico</strong> - per i nomi dei campi che utilizzano l'input solo numerico, è possibile selezionare questa opzione per visualizzare una tastiera numerica personalizzato al campo di entrata anziché tastiera dell'unità.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Configurare la priorità del campo dell'app Approvazioni di magazzino
======================================

** Magazzino la priorità del campo dell'app Approvazioni ** nella pagina, è possibile impostare i nomi dei campi nei gruppi di priorità diversi. Ciò consente di scegliere le informazioni da visualizzare nella pagina della principale quando i lavoratori di magazzino eseguono le attività nell'app Approvazioni. ** Se si sceglie di creare l'impostazione predefinita **, un gruppo predefinito dei gruppi di priorità viene generato. È possibile creare un numero illimitato di gruppi di priorità se necessario, ma solo tre gruppi di priorità verranno visualizzati nell'attività. Quando Dynamics 365 per le operazioni invia i metadati al manager app, la modalità di assegnazione di priorità relative in base al relativo gruppo di priorità e il app visualizzare i primi tre gruppi di priorità contenuti nei metadati nell'attività. Il resto dei metadati di straripamento vengono visualizzati in una pagina dei dettagli secondaria. Nella tabella seguente viene illustrato un esempio di cinque gruppi di priorità.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo di priorità</th>
<th>Campi assegnati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Priorità 10</td>
<td><ul>
<li>Articolo</li>
<li>Quantità</li>
<li>Unità di misura</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorità 20</td>
<td><ul>
<li>Posizione cluster</li>
<li>Cluster</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorità 30</td>
<td><ul>
<li>Descrizione articolo</li>
</ul></td>
</tr>
<tr class="even">
<td> Priorità 40</td>
<td><ul>
<li>Configurazione</li>
<li>Colore</li>
<li>Dimensioni</li>
<li>Stile</li>
</ul></td>
</tr>
<tr class="odd">
<td> Priorità 50</td>
<td><ul>
<li>Posizione</li>
<li>Targa</li>
</ul></td>
</tr>
</tbody>
</table>

Ad esempio, quando un lavoratore di magazzino è in esecuzione un'attività in un dispositivo mobile, se il metadati visualizzate nell'app Approvazioni è costituita dai seguenti campi:

-   Articolo
-   Quantità
-   Unità di misura
-   Descrizione articolo
-   Dimensione e ubicazione

In base all'impostazione di priorità del campo dell'app Approvazioni di magazzino nella tabella precedente, le seguenti 3 righe di informazioni vengono visualizzate nella pagina di attività:

-   Riga 1: Articolo, quantità, unità di misura
-   Riga 2: Descrizione dell'articolo
-   Riga 3: Dimensione

Metadati rimanenti, ad esempio, l'ubicazione, non viene visualizzato nell'attività, ma verranno visualizzati in una pagina dei dettagli. Per ulteriori informazioni e visualizzare esempi dell'interfaccia utente, fare riferimento al di registrazione blog [che annuncia Dynamics 365 per le operazioni immagazzinando] - (https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Vedere anche
--------

[Installare e configurare Microsoft Dynamics 365 per le operazioni di immagazzinando] () install-configure-warehousing-app.md


