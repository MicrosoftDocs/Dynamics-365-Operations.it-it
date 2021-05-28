---
title: Il giustificativo non viene generato
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi che possono essere utili quando un giustificativo deve essere generato ma non lo è.
author: qire
ms.date: 04/13/2021
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
ms.openlocfilehash: ba23b597b1d7d283b99638fb7d5d91da00afb09c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018759"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="4d866-103">Il giustificativo non viene generato</span><span class="sxs-lookup"><span data-stu-id="4d866-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d866-104">Se un giustificativo dovrebbe essere generato ma la pagina **Transazioni giustificativo** non ne mostra alcuno, segui i passaggi nelle sezioni seguenti come richiesto per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="4d866-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="4d866-105">[![Pagina Transazioni giustificativo senza giustificativi](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="4d866-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="4d866-106">Verificare l'applicabilità fiscale</span><span class="sxs-lookup"><span data-stu-id="4d866-106">Check the tax applicability</span></span>

1. <span data-ttu-id="4d866-107">Vai a **Imposta** \> **Attività periodiche** \> **Inserimenti nel giornale di registrazione secondario non ancora trasferiti**.</span><span class="sxs-lookup"><span data-stu-id="4d866-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="4d866-108">Se è presente un record di giornale di registrazione, selezionalo e quindi seleziona **Trasferisci ora**.</span><span class="sxs-lookup"><span data-stu-id="4d866-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="4d866-109">[![Pulsante Trasferisci ora nella pagina Inserimenti nel giornale di registrazione secondario non ancora trasferiti](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="4d866-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="4d866-110">Apri di nuovo la pagina **Transazioni giustificativo** per vedere se il giustificativo è stato generato.</span><span class="sxs-lookup"><span data-stu-id="4d866-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="4d866-111">Determinare se esiste la personalizzazione</span><span class="sxs-lookup"><span data-stu-id="4d866-111">Determine whether customization exists</span></span>

<span data-ttu-id="4d866-112">Se hai completato i passaggi nella sezione precedenti ma non hai riscontrato alcun problema, determina se esiste la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d866-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="4d866-113">Se non esiste alcuna personalizzazione, creare una richiesta di assistenza Microsoft per ulteriore supporto.</span><span class="sxs-lookup"><span data-stu-id="4d866-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
