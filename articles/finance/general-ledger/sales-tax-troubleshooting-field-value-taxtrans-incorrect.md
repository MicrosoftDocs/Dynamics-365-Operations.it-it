---
title: Valore di campo errato in TaxTrans
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi relativi a valori di campo errati in TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020165"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="b550a-103">Valore di campo errato in TaxTrans</span><span class="sxs-lookup"><span data-stu-id="b550a-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b550a-104">Se un valore di campo in **TaxTrans** non è corretto, utilizza le informazioni in questo argomento per provare a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="b550a-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="b550a-105">Panoramica dei valori</span><span class="sxs-lookup"><span data-stu-id="b550a-105">Overview of values</span></span>
<span data-ttu-id="b550a-106">Il seguente elenco mostra come **TaxTrans**, **TaxUncommitted**, e **TmpTaxWorkTrans** sono set di dati simili, ma funzionano in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="b550a-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="b550a-107">**TaxTrans** è il risultato finale della transazione fiscale registrata mantenuto nel database.</span><span class="sxs-lookup"><span data-stu-id="b550a-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="b550a-108">**TaxUncommitted** è il risultato intermedio dell'imposta calcolata mantenuto nel database (se applicabile), che verrà utilizzato successivamente nella registrazione.</span><span class="sxs-lookup"><span data-stu-id="b550a-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="b550a-109">**TmpTaxWorkTrans** è il risultato temporaneo dell'imposta calcolata nella tabella in memoria (Tipo di tabella = InMemory).</span><span class="sxs-lookup"><span data-stu-id="b550a-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="b550a-110">Se trovi la causa principale di una colonna **TaxTrans** errata, hai anche trovato la causa principale di una colonna **TaxUncommitted** o **TmpTaxWorkTrans** errata.</span><span class="sxs-lookup"><span data-stu-id="b550a-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="b550a-111">Questo perché le tre colonne vengono copiate l'una dall'altra.</span><span class="sxs-lookup"><span data-stu-id="b550a-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="b550a-112">In genere, durante il calcolo delle imposte, **TmpTaxWorkTrans** viene generato e quindi, se applicabile, **TaxUncommitted** viene generato.</span><span class="sxs-lookup"><span data-stu-id="b550a-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="b550a-113">Durante la registrazione delle imposte, **TaxTrans** viene generato.</span><span class="sxs-lookup"><span data-stu-id="b550a-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="b550a-114">Aggiungere punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="b550a-114">Add breakpoints</span></span>
<span data-ttu-id="b550a-115">Per aggiungere punti di interruzione, completa i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="b550a-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="b550a-116">Aggiungi estensioni e punti di interruzione in *insert()* e *update()* nelle estensioni come mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b550a-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="b550a-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="b550a-117">**TaxTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="b550a-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="b550a-118">**TaxUncommitted**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="b550a-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="b550a-119">**TmpTaxWorkTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. <span data-ttu-id="b550a-120">In alternativa, puoi aggiungere direttamente i punti di interruzione quando **TaxUncommitted** non è incluso.</span><span class="sxs-lookup"><span data-stu-id="b550a-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="b550a-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="b550a-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="b550a-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="b550a-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="b550a-123">Riprodurre ed eseguire il debug</span><span class="sxs-lookup"><span data-stu-id="b550a-123">Reproduce and debug</span></span>

<span data-ttu-id="b550a-124">Dopo aver impostato i punti di interruzione, ogni modifica alla persistenza dei dati è visibile durante il debug.</span><span class="sxs-lookup"><span data-stu-id="b550a-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="b550a-125">Per trovare la causa principale di una colonna errata di **TaxTrans**, **TaxUncommitted**, o **TmpTaxWorkTrans**, rivedi e prendi nota dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="b550a-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="b550a-126">L'ultimo punto di interruzione in cui la colonna è corretta.</span><span class="sxs-lookup"><span data-stu-id="b550a-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="b550a-127">Il primo punto di interruzione in cui la colonna è errata.</span><span class="sxs-lookup"><span data-stu-id="b550a-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="b550a-128">Cosa succede tra questi due punti.</span><span class="sxs-lookup"><span data-stu-id="b550a-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="b550a-129">Determinare se esiste la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="b550a-129">Determine whether customization exists</span></span>
<span data-ttu-id="b550a-130">Se hai completato i passaggi nelle sezioni precedenti ma non il problema persiste, determina se esiste la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="b550a-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="b550a-131">Se non esiste alcuna personalizzazione, contattare il supporto Microsoft per assistenza.</span><span class="sxs-lookup"><span data-stu-id="b550a-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

