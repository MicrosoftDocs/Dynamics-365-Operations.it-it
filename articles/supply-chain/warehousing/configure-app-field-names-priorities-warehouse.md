---
title: Configurare i nomi di campo app nell'app di magazzino
description: In questo argomento viene descritto come definire e configurare i nomi e le priorità di campo app in Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ac31b3d2b3b1d9ca51919fe75e06f0de1cda0c63
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963437"
---
# <a name="configure-app-field-names-in-the-warehouse-app"></a>Configurare i nomi di campo app nell'app di magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come definire e configurare i nomi e le priorità di campo app in Dynamics 365 Supply Chain Management. 

> [!NOTE]
> Questo argomento si applica alle funzionalità in Gestione magazzino. Non viene applicato alle funzionalità in Gestione inventario. Magazzino è un'applicazione che consente di eseguire attività di magazzino. È possibile definire e configurare i nomi di campo utilizzati nell'app, nonché configurare la priorità da assegnare ai nomi di campo. In questo argomento viene illustrato come definire e configurare i nomi e le priorità di campo dell'app Magazzino e viene descritto come utilizzarli in Magazzino. Per informazioni dettagliate su come configurare la connessione in Magazzino, fare riferimento all'esercitazione [Panoramica sull'installazione e sulla configurazione dell'app del magazzino](install-configure-warehousing-app.md).

## <a name="configure-warehouse-app-field-names"></a>Configurare i nomi di campo dell'app Magazzino

Quando si utilizza Magazzino sul dispositivo mobile, è possibile configurare la modalità di visualizzazione dei metadati sul dispositivo nella pagina **Nomi campo per app magazzino**. In una nuova società, selezionare **Crea impostazione predefinita** per generare tutti i nomi di campo che verranno utilizzati nei flussi di lavoro del dispositivo mobile di magazzino, quindi assegnare loro una modalità e un tipo di input preferiti. Dopo aver generato tutti i nomi di campo, è possibile selezionare le seguenti opzioni di input.

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
<td>Questa opzione definisce se un campo di scansione o un campo di input di immissione manuale deve essere visualizzato per il nome di campo selezionato. Questa opzione è utile per distinguere i campi a seconda che vengano utilizzati o meno codici a barre per il campo. <strong>Nota:</strong> per i nomi di campo con modalità di input preferita impostata su <strong>Scansione</strong>, è possibile immettere manualmente le informazioni se il codice a barre è illeggibile o danneggiato.</td>
</tr>
<tr class="even">
<td>Tipo di input</td>
<td>Questa opzione definisce il tipo di input da utilizzare per il nome di campo selezionato. Sono disponibili quattro opzioni:
<ul>
<li><strong>Selezione</strong> - Contiene un elenco di opzioni tra cui scegliere. I nomi di campo con questa opzione non sono modificabili.</li>
<li><strong>Data</strong> - I nomi di campo specificati come data verranno visualizzati in un formato data con l'etichetta. Ciò consente ai lavoratori di magazzino di individuare in quale formato immettere la data. I nomi di campo con questa opzione non sono modificabili.</li>
<li><strong>Ordine alfabetico</strong> - Se l'opzione è selezionata, la tastiera del dispositivo verrà utilizzata quando si immettono le informazioni manualmente nell'app. L'esperienza della tastiera può essere modificata in base al dispositivo utilizzato.</li>
<li><strong>Numerico</strong> - Per i nomi di campo che utilizzano l'input solo numerico, è possibile selezionare questa opzione per visualizzare una tastiera numerica personalizzata con il campo di input anziché la tastiera del dispositivo.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a>Configurare la priorità di campo nell'app Magazzino

Nella pagina **Priorità campo per app magazzino**, è possibile inserire i nomi di campo in gruppi di priorità diversi. Ciò consente di scegliere le informazioni da visualizzare nella pagina dell'attività principale quando i lavoratori di magazzino eseguono attività mediante l'app. Se si fa clic su **Crea impostazione predefinita**, verrà generato un set predefinito di gruppi di priorità. È possibile creare un numero illimitato di gruppi di priorità, se necessario, ma solo tre gruppi di priorità verranno visualizzati nella pagina dell'attività. Quando il sistema invia metadati all'app, a ogni campo verrà assegnata una priorità relativa a seconda del rispettivo gruppo di priorità e l'app visualizzerà i primi tre gruppi di priorità contenuti nei metadati nella pagina dell'attività. Il resto dei metadati aggiuntivi verranno visualizzati in una pagina dei dettagli secondaria. Nella tabella seguente viene illustrato un esempio di cinque gruppi di priorità.

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

Ad esempio, quando un lavoratore di magazzino esegue un'attività su un dispositivo mobile, se i metadati visualizzati nell'app sono costituiti dai seguenti campi:

-   Articolo
-   Quantità
-   Unità di misura
-   Descrizione articolo
-   Dimensione e ubicazione

In base alla priorità di campo dell'app Magazzino impostata nella tabella precedente, le seguenti 3 righe di informazioni verranno visualizzate nella pagina dell'attività:

-   Riga 1: Articolo, Quantità, Unità di misura
-   Riga 2: Descrizione dell'articolo
-   Riga 3: Dimensione

I metadati rimanenti, ad esempio l'ubicazione, non verranno visualizzati nella pagina dell'attività, ma verranno visualizzati in una pagina dei dettagli. Per ulteriori informazioni e per visualizzare esempi dell'interfaccia utente, fare riferimento al post di blog [Presentazione di Finance and Operations - Magazzino](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica sull'installazione e sulla configurazione dell'app di magazzino](install-configure-warehousing-app.md)
