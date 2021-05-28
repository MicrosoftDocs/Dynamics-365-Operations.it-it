---
title: Set di dimensioni finanziarie
description: In questo argomento vengono descritti set di dimensioni finanziarie e vengono forniti alcuni suggerimenti per ottimizzarne l'utilizzo.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021830"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="41446-103">Set di dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="41446-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41446-104">In questo argomento vengono descritti set di dimensioni finanziarie e vengono forniti alcuni suggerimenti per ottimizzarne l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="41446-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="41446-105">Un set di dimensioni è un elenco ordinato di dimensioni finanziarie che possono essere utilizzate per riepilogare i dati di contabilità generale in un modo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="41446-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="41446-106">Un utilizzo principale dei set di dimensioni è definire un bilancio di verifica.</span><span class="sxs-lookup"><span data-stu-id="41446-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="41446-107">L'unico set di dimensioni standard è il set di dimensioni che contiene solo il conto principale.</span><span class="sxs-lookup"><span data-stu-id="41446-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="41446-108">La pagina **Set di dimensioni finanziarie** viene utilizzata per creare e gestire set di dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="41446-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="41446-109">Saldi di set di dimensioni</span><span class="sxs-lookup"><span data-stu-id="41446-109">Dimension set balances</span></span>

<span data-ttu-id="41446-110">Un set di dimensioni può avere saldi basati sulle relative dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="41446-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="41446-111">I saldi esistono nella contabilità generale e si basano sulla definizione del set di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="41446-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="41446-112">I saldi vengono riepilogati dai dati di contabilità generale per migliorare le prestazioni quando vengono recuperati (ad esempio, quando viene generato un bilancio di verifica).</span><span class="sxs-lookup"><span data-stu-id="41446-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="41446-113">Crea saldi</span><span class="sxs-lookup"><span data-stu-id="41446-113">Create balances</span></span>

<span data-ttu-id="41446-114">Usare il pulsante **Crea saldi** per inizializzare i saldi per un set di dimensioni che attualmente non dispone di saldi.</span><span class="sxs-lookup"><span data-stu-id="41446-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="41446-115">Si consiglia di limitare il numero di set di dimensioni con saldi, poiché gli aggiornamenti dei saldi influiscono su tutte le attività di registrazione della contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="41446-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="41446-116">Aggiorna saldi</span><span class="sxs-lookup"><span data-stu-id="41446-116">Update balances</span></span>

<span data-ttu-id="41446-117">Usare il pulsante **Aggiorna saldi** per includere l'ultima attività di registrazione di contabilità generale nei saldi.</span><span class="sxs-lookup"><span data-stu-id="41446-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="41446-118">Gli aggiornamenti dei saldi sono operazioni semplici.</span><span class="sxs-lookup"><span data-stu-id="41446-118">Balance updates are light operations.</span></span> <span data-ttu-id="41446-119">Devono elaborare solo l'attività di registrazione della contabilità generale che si è verificata dall'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="41446-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="41446-120">La visualizzazione del bilancio di verifica forza un aggiornamento, per garantire che i saldi visualizzati siano correnti.</span><span class="sxs-lookup"><span data-stu-id="41446-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="41446-121">Considerare l'utilizzo di un processo batch ricorrente in modo che gli aggiornamenti dei set di dimensioni utilizzati più di frequente siano rapidi.</span><span class="sxs-lookup"><span data-stu-id="41446-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="41446-122">In questo modo, è possibile ridurre al minimo il tempo di attesa degli utenti del bilancio di verifica.</span><span class="sxs-lookup"><span data-stu-id="41446-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="41446-123">Ricostruisci saldi</span><span class="sxs-lookup"><span data-stu-id="41446-123">Rebuild balances</span></span>

<span data-ttu-id="41446-124">Usare il pulsante **Ricostruisci saldi** per ricreare i saldi da zero.</span><span class="sxs-lookup"><span data-stu-id="41446-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="41446-125">In questo modo, se ne assicura la corrispondenza ai dati nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="41446-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="41446-126">Una ricostruzione dei saldi richiede molte elaborazioni e di solito non dovrebbe essere necessaria.</span><span class="sxs-lookup"><span data-stu-id="41446-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="41446-127">Se è presente uno scenario che richiede regolarmente una ricostruzione dei saldi, si consiglia di contattare l'assistenza clienti.</span><span class="sxs-lookup"><span data-stu-id="41446-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="41446-128">L'assistenza clienti può aiutare a determinare il motivo per cui i saldi non corrispondono ai dati nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="41446-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="41446-129">Cancella saldi</span><span class="sxs-lookup"><span data-stu-id="41446-129">Clear balances</span></span>

<span data-ttu-id="41446-130">Usare il pulsante **Cancella saldi** per rimuovere i saldi e interrompere eventuali ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="41446-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="41446-131">Il set di dimensioni non avrà più alcun impatto sulle attività di registrazione della contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="41446-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="41446-132">Per ulteriori informazioni, vedere [Dimensioni finanzarie](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="41446-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
