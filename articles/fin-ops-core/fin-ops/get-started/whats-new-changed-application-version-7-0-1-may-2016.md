---
title: Novità o modifiche introdotte in Dynamics AX versione applicazione 7.0.1 (maggio 2016)
description: Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics AX versione applicazione 7.0.1. Questa versione è stata rilasciata nel maggio 2016 e ha numero di build 7.0.1265.23014.
author: sericks007
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 94cebad528facc5537226a3faa5ea9be8448092e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267202"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Novità o modifiche introdotte in Dynamics AX versione applicazione 7.0.1 (maggio 2016)

[!include [banner](../includes/banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics AX versione applicazione 7.0.1. Questa versione è stata rilasciata nel maggio 2016 e ha numero di build 7.0.1265.23014.

## <a name="electronic-reporting-er"></a>Creazione di report elettronici (ER)

| Operazioni che è possibile effettuare | Perché questo è importante? |
|------------------|------------------------|
| Configurare una finestra di dialogo in fase di esecuzione per la progettazione di report elettronici (ER), in modo che gli utenti possono selezionare le dimensioni finanziarie che desiderano. | In fase di esecuzione nella finestra di dialogo per l'esecuzione di un report ER, gli utenti possono selezionare più dimensioni finanziarie. I dettagli delle dimensioni finanziarie selezionate verranno visualizzati nel documento elettronico generato. |
| Configurare l'accesso a più dimensioni finanziarie durante la progettazione di un report ER, tramite un solo mapping all'origine dati desiderata. | La stessa configurazione di report ER può essere utilizzata per generare documenti elettronici che presentano i dati transazionali con i dettagli delle dimensioni finanziarie, indipendentemente dal numero di dimensioni finanziarie che sono selezionate dall'utente o configurate per la persona giuridica o l'istanza corrente. |
| Configurare un report ER per immettere dati in colonne generate in modo dinamico di un documento elettronico che viene creato in formato foglio di lavoro OPENXML. | Un report ER può immettere dati in un foglio di lavoro OPENXML che viene generato, tramite colonne che si replicano in senso orizzontale. Pertanto, la stessa configurazione di report ER può essere riutilizzata per generare documenti elettronici che hanno un diverso numero di colonne generate dinamicamente. |
| Configurare le destinazioni di ER in modo che il risultato di output di un formato sia diretto alla destinazione specifica: file, posta elettronica o archivio (cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure). | In precedenza, quando si eseguiva una configurazione ER, una finestra di messaggio compariva richiedendo l'azione dell'utente di salvare o aprire un file. È possibile ora preconfigurare una destinazione per ciascuna configurazione di formato e per ogni componente di output (una cartella o un file) separatamente. Gli utenti che dispongono di diritti di accesso appropriati anche possono modificare le impostazioni di destinazione in fase di esecuzione. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>POS – Microsoft Dynamics AX Retail

| Operazioni che è possibile effettuare | Perché questo è importante? |
|------------------|------------------------|
| Utilizzare il browser Google Chrome. | I rivenditori possono ora avviare il POS cloud dal browser Chrome e possono utilizzare tutte le funzionalità disponibili nella versione Microsoft Edge e Internet Explorer di POS cloud. |

## <a name="financial-reporting"></a>Creazione di report finanziari

| Operazioni che è possibile effettuare | Perché questo è importante? |
|------------------|------------------------|
| Ricompilare il data mart dei report finanziari. | Quando si spostano i database di Dynamics AX tra ambienti o si apportano altre modifiche invasive all'ambiente, può essere necessario ricompilare il database dei report finanziari. Uno script Windows PowerShell è ora disponibile per la ricompilazione automatica del database. |
| Non è più possibile selezionare opzioni di progettazione di report che non sono valide. | Diverse opzioni della finestra di progettazione di report che erano utilizzate nelle versioni commercializzate di Management Reporter non si applicano a questa versione di Dynamics AX. Queste opzioni erano correlate a progettazione, output e collegamento di report finanziari. Queste opzioni sono state rimosse dalla finestra di progettazione di report finanziari per evitare errori dell'utente. |

## <a name="financial-management"></a>Gestione finanziaria

| Operazioni che è possibile effettuare | Perché questo è importante? |
|------------------|------------------------|
| Generare file pagamenti sicuri per i pagamenti della contabilità fornitori | È possibile generare i file pagamenti sicuri per impedire la frode di assegni. |

## <a name="warehouse-and-production"></a>Magazzino e produzione

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definire un criterio di lavoro di magazzino che controlla la creazione di lavoro per una serie di prodotti in ubicazioni specifiche.</td>
<td>I processi del magazzino non includono sempre del lavoro. Utilizzando i nuovi criteri di lavoro del magazzino, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche.</td>
</tr>
<tr>
<td>Specificare un'ubicazione di uscita di produzione non è controllata da targa.</td>
<td>È ora possibile specificare che un'ubicazione di uscita di produzione non è controllata da targa. Ad esempio, questa funzionalità è utile quando un ordine di produzione a monte segnala articoli come finiti direttamente in una ubicazione che funge da ubicazione di entrata produzione per un ordine di produzione a valle.</td>
</tr>
<tr>
<td>Supportare BDA che comprendono articoli con dimensioni prodotto diverse dello stesso articolo.</td>
<td>Quando si utilizza uno o più delle dimensioni del prodotto in produzione, è possibile avere situazioni in cui si desidera produrre un articolo, basato su una diversa variante dello stesso articolo. Per ulteriori informazioni, vedere <a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">questo blog</a>.</td>
</tr>
<tr>
<td>Ordini di produzione con strutture circolari al primo livello delle loro DBA vengono esclusi dal calcolo livello DBA per la pianificazione delle risorse materiali.</td>
<td>Non è possibile assegnare livelli di DBA corretti a varianti prodotto per gli ordini di produzione che provocano la circolarità della gerarchia DBA.</td>
</tr>
<tr>
<td>Calcolare livelli DBA separati per la pianificazione delle risorse materiali e il calcolo dei costi:
<ul>
<li>Per la pianificazione delle risorse materiali, i livelli DBA vengono calcolati nella nuova tabella <strong>ReqItemLevel</strong>. Ordini di produzione finiti vengono ignorati nel calcolo.</li>
<li>Per il calcolo di costi di produzione, livelli DBA vengono calcolati in <strong>InventTable</strong>. Ordini di produzione finiti vengono inclusi nel calcolo.</li>
</ul>
</td>
<td>
<ul>
<li>Durante l'esecuzione di pianificazione delle risorse materiali, ad esempio, programmazione ed esplosione pianificazione principale, devono essere ricalcolati solo i livelli DBA utilizzati per la pianificazione delle risorse materiali. In altre parole, non è necessario calcolare i livelli DBA utilizzati per il calcolo dei costi di produzione.</li>
<li>Durante l'esecuzione di operazioni determinazione costi, ad esempio la chiusura inventario, è necessario ricalcolare solo i livelli DBA utilizzati per il calcolo di determinazione costi di produzione.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Risorse aggiuntive

[Home page Novità o modifiche in finanza e operazioni](whats-new-changed.md)

[Guide attività nuove o aggiornate (maggio 2016)](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
