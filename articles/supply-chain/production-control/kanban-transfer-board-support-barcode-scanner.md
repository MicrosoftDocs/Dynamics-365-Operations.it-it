---
title: Supporto della tavola di trasferimento Kanban per scanner di codici a barre
description: La tavola di trasferimento Kanban supporta l'input di uno scanner di codici a barre per selezionare, avviare, completare e svuotare un lavoro kanban.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566813"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>Supporto della tavola di trasferimento Kanban per scanner di codici a barre

[!include [banner](../includes/banner.md)]

La tavola di trasferimento Kanban supporta l'input di uno scanner di codici a barre per selezionare, avviare, completare e svuotare un lavoro kanban.

## <a name="registration-modes"></a>Modalità di registrazione

Nella scheda dettaglio **Registrazione scanner** è possibile selezionare la modalità di registrazione, che controlla l'azione quando si digitalizza un numero di scheda kanban o si digita manualmente il numero nel campo del numero della scheda kanban.

| Imposta modalità di registrazione | Descrizione                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Inizia                 | Registra un processo di trasferimento kanban come in corso.                                                 |
| Completata              | Registra un processo di trasferimento kanban come completato.                                                   |
| Vuoto                 | Registra l'unità movimentazione materiali a cui fa riferimento una scheda kanban come vuota.              |
| Seleziona                | Registra un numero di scheda kanban e seleziona automaticamente il processo di riferimento nell'elenco di processi kanban. |

 
## <a name="registration-mode-select"></a>Modalità di registrazione Seleziona

Quando si utilizza un lettore di codice a barre per selezionare un processo, la modalità di visualizzazione della bacheca kanban cambia. In questa modalità, sono valide le seguenti condizioni:

-   Viene visualizzato solo il processo kanban sottoposto a scansione.
-   I dettagli del processo selezionato vengono visualizzati nella scheda dettaglio **Dettagli**.
-   Nella scheda dettaglio **Messaggi** vengono visualizzati i messaggi solo per il processo selezionato.
-   È possibile modificare lo stato del processo con le funzioni disponibili nel riquadro azioni. La bacheca di trasferimento kanban continua a visualizzare solo un singolo processo durante questo intervallo di tempo.
-   È possibile aggiornare le informazioni nell'elenco di processi manualmente facendo clic su **Aggiorna** (MAIUSC + F5) nel riquadro azioni. Dopo aver aggiornato le informazioni, i risultati completi per il filtro del processo vengono nuovamente visualizzati.

## <a name="job-status-and-possible-actions"></a>Stato del processo e azioni possibili
Lo stato del processo selezionato e lo stato di tutti i processi sottoposti a pegging per i kanban evento stabiliscono se è possibile elaborare il processo ulteriormente. Nella seguente tabella vengono visualizzate le informazioni sugli stati e le attività:
-   Gli stati disponibili per i processi, o per unità movimentazione a cui i processi fanno riferimento.
-   Ogni attività che è possibile eseguire per il processo.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di processo</th>
<th>Stato del processo o stato dell'unità movimentazione</th>
<th>Aggiorna distinta di prelievo</th>
<th>Inizia</th>
<th>Aggiorna registrazione</th>
<th>Completata</th>
<th>Vuoto</th>
<th>Crea kanban evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Trasferito</td>
<td><ul>
<li>Non pianificato</li>
<li>Non esistono processi sottoposti a pegging o i processi sottoposti a pegging sono Completati</li>
</ul></td>
<td>Sì</td>
<td>Sì</td>
<td>Sì</td>
<td>Sì</td>
<td>No</td>
<td>Sì</td>
</tr>
<tr class="even">
<td>Trasferito</td>
<td><ul>
<li>Non pianificato</li>
<li>Il processo sottoposto a pegging non è Completato</li>
</ul></td>
<td>Sì</td>
<td>No</td>
<td>Sì</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Trasferito</td>
<td>In corso</td>
<td>Sì</td>
<td>No</td>
<td>Sì</td>
<td>Sì</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="even">
<td>Trasferito</td>
<td>Completato</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>Sì</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Trasferimento o processo</td>
<td>Vuoto</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="even">
<td>Trasferimento o processo</td>
<td>Non è stata rilevata una scheda kanban</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Trasferimento o processo</td>
<td>È stata rilevata una scheda kanban, ma non è stata assegnata a un kanban</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="even">
<td>Elaborazione</td>
<td><ul>
<li>Non pianificato</li>
<li>Preparato</li>
<li>In corso</li>
</ul></td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
<tr class="odd">
<td>Elaborazione</td>
<td>Completato</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
<td>No</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]