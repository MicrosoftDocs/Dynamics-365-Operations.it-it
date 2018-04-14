---
title: "Esplora origine contabilità"
description: "Questo articolo fornisce informazioni su Esplora origine contabilità, che è possibile utilizzare per analisi dettagliate delle informazioni di origine relative alle voci della contabilità generale."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d5d9f7ff6b4d3ea764717240f9736a81c1aee6c1
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="accounting-source-explorer"></a><span data-ttu-id="e50d2-103">Esplora origine contabilità</span><span class="sxs-lookup"><span data-stu-id="e50d2-103">Accounting source explorer</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e50d2-104">Questo articolo fornisce informazioni su Esplora origine contabilità, che è possibile utilizzare per analisi dettagliate delle informazioni di origine relative alle voci della contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="e50d2-104">This article provides information about Accounting source explorer, which you can use for detailed analysis of the source information behind general ledger accounting entries.</span></span>

<span data-ttu-id="e50d2-105">Esplora origine contabilità è una nuova pagina contenente le informazioni relative all'origine.</span><span class="sxs-lookup"><span data-stu-id="e50d2-105">Accounting source explorer is a new page that shows source information.</span></span> <span data-ttu-id="e50d2-106">È possibile utilizzare Esplora origine contabilità come strumento autonomo oppure per analizzare i dettagli relativi alle voci contabili di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="e50d2-106">You can use Accounting source explorer either as a stand-alone tool or to analyze the details behind general ledger accounting entries.</span></span> <span data-ttu-id="e50d2-107">Ad esempio, è possibile eseguire Esplora  origine contabilità per ottenere informazioni più dettagliate sull'origine per un saldo in Bilancio di verifica o per una transazione giustificativo.</span><span class="sxs-lookup"><span data-stu-id="e50d2-107">For example, you can use Accounting source explorer to get the most detailed source information for a balance in Trail balance or for a voucher transaction.</span></span> <span data-ttu-id="e50d2-108">È quindi possibile utilizzare la funzionalità Esporta in MS Excel per visualizzare le informazioni in modo ancora più dettagliato in Microsoft Excel (ad esempio, in una tabella Pivot o in un report di tabella pivot).</span><span class="sxs-lookup"><span data-stu-id="e50d2-108">You can then use the Export to MS Excel feature to further slice and dice the information in Microsoft Excel (for example, in a PivotTable or on a PivotTable report).</span></span>

<span data-ttu-id="e50d2-109">Esplora origine contabilità mostra sempre lo stesso importo totale per conto CoGe in base a quanto indicato in Contabilità generale (ad esempio, in Bilancio di verifica).</span><span class="sxs-lookup"><span data-stu-id="e50d2-109">Accounting source explorer always shows the same total amount per ledger account as General ledger shows (for example, in Trial balance).</span></span> <span data-ttu-id="e50d2-110">Come in Bilancio di verifica, è possibile visualizzare segmenti in colonne separate.</span><span class="sxs-lookup"><span data-stu-id="e50d2-110">As in Trial balance, you can display segments in separate columns.</span></span> <span data-ttu-id="e50d2-111">È sufficiente selezionare il set di dimensioni finanziarie appropriato.</span><span class="sxs-lookup"><span data-stu-id="e50d2-111">Just select the appropriate financial dimension set.</span></span> 

<span data-ttu-id="e50d2-112">È possibile utilizzare i parametri per definire un intervallo di date per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e50d2-112">You can use parameters to define a date interval for the analysis.</span></span> <span data-ttu-id="e50d2-113">Anche questa funzionalità è simile a quella presente in Bilancio di verifica.</span><span class="sxs-lookup"><span data-stu-id="e50d2-113">This functionality also resembles the functionality in Trial balance.</span></span>

<span data-ttu-id="e50d2-114">Per tutti i documenti che utilizzano il framework documento di origine, Esplora origine contabilità mostra informazioni aggiuntive, in base alle distribuzioni contabili e, se applicabile, alle distribuzioni contabili di progetto.</span><span class="sxs-lookup"><span data-stu-id="e50d2-114">For all documents that use the source document framework, Accounting source explorer shows additional information, based on accounting distributions and, if applicable, project accounting distributions.</span></span> <span data-ttu-id="e50d2-115">Queste informazioni includono tipo di importo monetario, progetto, attività, categoria e proprietà riga.</span><span class="sxs-lookup"><span data-stu-id="e50d2-115">This information includes the monetary amount type, project, activity, category, and line property.</span></span> <span data-ttu-id="e50d2-116">Di seguito sono riportati alcuni esempi dell'analisi che è possibile effettuare:</span><span class="sxs-lookup"><span data-stu-id="e50d2-116">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="e50d2-117">Scostamenti tra ordini di acquisto e fatture fornitore, poiché ogni scostamento viene rappresentato da un tipo di importo monetario, ad esempio lo scostamento addebiti</span><span class="sxs-lookup"><span data-stu-id="e50d2-117">Variances between purchase orders and vendor invoices, because each variance is represented by a monetary amount type, such as charge variance</span></span>
-   <span data-ttu-id="e50d2-118">Ore e spese fatturabili rispetto a quelle non fatturabili per progetto, Business Unit e conto principale</span><span class="sxs-lookup"><span data-stu-id="e50d2-118">Billable versus non-billable hours and expenses per project, business unit, and main account</span></span>

<span data-ttu-id="e50d2-119">Per i documenti di origine che utilizzano il concetto di identità di riferimento del documento di origine, Esplora origine contabilità mostra un numero maggiore di dettagli, ad esempio il cliente, il fornitore, il lavoratore, il prodotto, la quantità, il testo unità e le descrizioni.</span><span class="sxs-lookup"><span data-stu-id="e50d2-119">For source documents that use the source document reference identities concept, Accounting source explorer shows even more details, such as the customer, vendor, worker, product, quantity, unit text, and descriptions.</span></span> <span data-ttu-id="e50d2-120">Di seguito sono riportati alcuni esempi dell'analisi che è possibile effettuare:</span><span class="sxs-lookup"><span data-stu-id="e50d2-120">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="e50d2-121">Spese di albergo per Business Unit e catena alberghiera per un periodo fiscale, in base alle note spese</span><span class="sxs-lookup"><span data-stu-id="e50d2-121">Hotel expenses per business unit and hotel brand for a fiscal period, based on expense reports</span></span>
-   <span data-ttu-id="e50d2-122">Sconti per fornitore, prodotto, reparto</span><span class="sxs-lookup"><span data-stu-id="e50d2-122">Discounts per vendor, product, department</span></span>

<span data-ttu-id="e50d2-123">Per questi documenti, è possibile inoltre passare al documento di origine effettivo da Esplora origine contabilità.</span><span class="sxs-lookup"><span data-stu-id="e50d2-123">For these documents, you can also navigate to the actual source document from Accounting source explorer.</span></span>




