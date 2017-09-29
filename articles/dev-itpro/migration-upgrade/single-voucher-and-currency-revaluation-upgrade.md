---
title: Aggiornamento relativo a rivalutazione valuta e singolo giustificativo
description: "Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 13ad43cc77731727525aae1edc4d405c166acbc1
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a><span data-ttu-id="bac36-104">Aggiornamento relativo a rivalutazione valuta e singolo giustificativo</span><span class="sxs-lookup"><span data-stu-id="bac36-104">Single voucher and currency revaluation upgrade</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bac36-105">Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="bac36-105">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="bac36-106">In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="bac36-106">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="bac36-107">Quando si esegue l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="bac36-107">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="bac36-108">Prima di eseguire l'aggiornamento a Dynamics 365 for Operations, eseguire i processi di rivalutazione valuta estera per la Contabilità clienti e la Contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="bac36-108">Before you upgrade to Dynamics 365 for Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="bac36-109">Impostare il campo **Metodo** su **Data fattura**.</span><span class="sxs-lookup"><span data-stu-id="bac36-109">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="bac36-110">Viene creata una transazione di rivalutazione che annulla l'ultima rivalutazione valuta estera.</span><span class="sxs-lookup"><span data-stu-id="bac36-110">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="bac36-111">Di conseguenza, le transazioni aperte vengono valutate alla valuta di contabilizzazione originale.</span><span class="sxs-lookup"><span data-stu-id="bac36-111">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="bac36-112">Eseguire l'aggiornamento a Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="bac36-112">Upgrade to Dynamics 365 for Operations version 1611.</span></span>
3.  <span data-ttu-id="bac36-113">Eseguire di nuovo il processo di rivalutazione valuta esterna per la contabilità fornitori e la contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="bac36-113">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="bac36-114">Impostare questa volta il campo **Metodo** su **Standard**.</span><span class="sxs-lookup"><span data-stu-id="bac36-114">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="bac36-115">Viene creata una nuova transazione di rivalutazione basata sui tassi di cambio correnti.</span><span class="sxs-lookup"><span data-stu-id="bac36-115">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="bac36-116">Questa transazione registra il profitto/la perdita non realizzati e il conto CoGe riepilogativo corretto.</span><span class="sxs-lookup"><span data-stu-id="bac36-116">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>





