---
title: Preparare una persona giuridica per il processo di consolidamento
description: Durante un consolidamento le transazioni di alcuni set di conti di persone giuridiche vengono raccolte in un unico set di conti. In questo argomento viene illustrato come preparare una persona giuridica per un consolidamento.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 07988e71276c6439e392bce2087f3a8923f5f40b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230204"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="4b185-104">Preparare una persona giuridica per il processo di consolidamento</span><span class="sxs-lookup"><span data-stu-id="4b185-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b185-105">Durante un consolidamento le transazioni di alcuni set di conti di persone giuridiche vengono raccolte in un unico set di conti.</span><span class="sxs-lookup"><span data-stu-id="4b185-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="4b185-106">In questo argomento viene illustrato come preparare una persona giuridica per un consolidamento.</span><span class="sxs-lookup"><span data-stu-id="4b185-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="4b185-107">Ti consigliamo di utilizzare Management Reporter per Microsoft Dynamics 365 Finance per combinare i risultati finanziari per più persone giuridiche in un formato consolidato.</span><span class="sxs-lookup"><span data-stu-id="4b185-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="4b185-108">Management Reporter ti consente di creare report finanziari consolidati tra persone giuridiche, utilizzare Excel per importare dati di consolidamento da altre origini e convertire gli importi in un numero qualsiasi di valute di reporting senza dover eseguire il processo di consolidamento in Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="4b185-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="4b185-109">Puoi stampare report, ad esempio rendiconti finanziari, dalla persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="4b185-110">Tuttavia, non è possibile utilizzare la persona giuridica consolidata per le transazioni giornaliere.</span><span class="sxs-lookup"><span data-stu-id="4b185-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="4b185-111">Puoi consolidare i dati delle persone giuridiche che utilizzano database diversi da quello della persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="4b185-112">Questo processo di consolidamento è denominato *consolidamento di importazione*.</span><span class="sxs-lookup"><span data-stu-id="4b185-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="4b185-113">In alternativa, le persone giuridiche possono utilizzare lo stesso database della persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="4b185-114">Questo processo di consolidamento è denominato *consolidamento online*.</span><span class="sxs-lookup"><span data-stu-id="4b185-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="4b185-115">La persona giuridica consolidata raccoglie i risultati e i saldi delle filiali.</span><span class="sxs-lookup"><span data-stu-id="4b185-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="4b185-116">Per preparare una persona giuridica consolidata per un consolidamento, è necessario completare i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="4b185-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="4b185-117">Vai a **Contabilità generale \> Impostazione \> Organizzazione \> Persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="4b185-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="4b185-118">Seleziona **Nuovo** per creare una nuova persona giuridica che sarà la persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="4b185-119">Seleziona la casella di controllo **Utilizza per processo di consolidamento finanziario** quindi immetti le informazioni sulla persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="4b185-120">Assicurati di immettere le informazioni esattamente come vuoi che vengano riportate nei rendiconti finanziari per la persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="4b185-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4b185-121">Close the page.</span></span>
5. <span data-ttu-id="4b185-122">Seleziona la persona giuridica consolidata nel campo nell'angolo in alto a destra della pagina, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b185-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="4b185-123">Vai a **Contabilità generale \> Impostazione \> Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="4b185-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="4b185-124">Seleziona il piano dei conti, il calendario fiscale, la valuta di contabilizzazione, la valuta di dichiarazione facoltativa e il tipo di tasso di cambio predefinito per la persona giuridica consolidata.</span><span class="sxs-lookup"><span data-stu-id="4b185-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="4b185-125">Vai a **Contabilità generale \> Impostazione \> Valuta \> Tassi di cambio valutario**.</span><span class="sxs-lookup"><span data-stu-id="4b185-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="4b185-126">Imposta i tassi di cambio valutario in periodi appropriati per le valute delle persone giuridiche affiliate.</span><span class="sxs-lookup"><span data-stu-id="4b185-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="4b185-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4b185-127">Close the page.</span></span>
11. <span data-ttu-id="4b185-128">Se la persona giuridica consolidata ha filiali che utilizzano valute estere, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="4b185-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="4b185-129">Vai a **Contabilità generale \> Impostazione \> Registrazione \> Conti per transazioni automatiche**.</span><span class="sxs-lookup"><span data-stu-id="4b185-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="4b185-130">Nel campo **Tipo di registrazione** seleziona un conto appropriato:</span><span class="sxs-lookup"><span data-stu-id="4b185-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="4b185-131">Se la persona giuridica ha filiali estere che sono finanziariamente o operativamente interdipendenti con la persona giuridica madre, seleziona un conto appropriato per il tipo di registrazione **Conto profitti e perdite per differenze di consolidamento**.</span><span class="sxs-lookup"><span data-stu-id="4b185-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="4b185-132">Se stai consolidando una filiale che è finanziariamente e funzionalmente indipendente dalla persona giuridica padre o una persona giuridica che contiene i risultati di più società affiliate finanziariamente e funzionalmente indipendente dalla persona giuridica padre e se usi i metodi di conversione per consolidare i dati, seleziona un conto appropriato per il tipo di registrazione **Conto collettivo per differenze di consolidamento**.</span><span class="sxs-lookup"><span data-stu-id="4b185-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="4b185-133">Nel campo **Conto principale** seleziona i conti principali che devono essere utilizzati per le rettifiche di rivalutazione valuta estera.</span><span class="sxs-lookup"><span data-stu-id="4b185-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="4b185-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4b185-134">Close the page.</span></span>

    <span data-ttu-id="4b185-135">Se crei la persona giuridica consolidata nella parte iniziale di un periodo, puoi rivalutare gli importi in valuta estera conformemente alla modifica dei tassi di cambio durante il periodo di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="4b185-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="4b185-136">La persona giuridica consolidata ora è impostata per il processo periodico **Consolidamento**.</span><span class="sxs-lookup"><span data-stu-id="4b185-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="4b185-137">È possibile eseguire un consolidamento dell'importazione o un consolidamento online.</span><span class="sxs-lookup"><span data-stu-id="4b185-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="4b185-138">Per eseguire un consolidamento dell'importazione, vai a **Contabilità generale \> Periodico \> Consolida \> Consolida \[Importa da\]**.</span><span class="sxs-lookup"><span data-stu-id="4b185-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="4b185-139">Per eseguire un consolidamento online, vai a **Contabilità generale \> Periodico \> Consolida \> Consolida \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="4b185-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="4b185-140">Prima di eseguire il consolidamento, devi preparare le persone giuridiche affiliate per il consolidamento.</span><span class="sxs-lookup"><span data-stu-id="4b185-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="4b185-141">Per ulteriori informazioni, vedi [Impostare una persona giuridica affiliata per il consolidamento](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="4b185-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]