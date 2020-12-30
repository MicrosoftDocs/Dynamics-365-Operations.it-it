---
title: Configurare nomi di giornale di leasing
description: Questo argomento spiega come definire i nomi dei giornali di leasing. I nomi dei giornali di leasing specificano i giornali di registrazione in cui vengono registrati i movimenti che hanno origine in Leasing cespite.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8b1b908dfd6d1d6072b6efa83f13ae5784c85c1
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444974"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="2e40f-104">Configurare nomi di giornale di leasing</span><span class="sxs-lookup"><span data-stu-id="2e40f-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e40f-105">I nomi dei giornali di leasing specificano i giornali di registrazione in cui vengono registrate le transazioni di Leasing cespite.</span><span class="sxs-lookup"><span data-stu-id="2e40f-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="2e40f-106">Solo i nomi di giornale di registrazione assegnati al tipo di giornale di registrazione **Leasing cespite** vengono visualizzati nei campi **Riconoscimento iniziale** e **Nome giornale di registrazione mensile** della pagina **Parametri del leasing cespite**.</span><span class="sxs-lookup"><span data-stu-id="2e40f-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="2e40f-107">Solo il tipo di giornale di registrazione **registrazione fattura fornitore** può essere assegnato al campo **Nome giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="2e40f-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="2e40f-108">Per configurare i nomi dei giornali di leasing, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="2e40f-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="2e40f-109">Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.</span><span class="sxs-lookup"><span data-stu-id="2e40f-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="2e40f-110">Nella scheda **Generale**, nel campo **Nome giornale di registrazione riconoscimento iniziale**, seleziona un giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="2e40f-111">Tutte le registrazioni a giornale di riconoscimento iniziale verranno registrate in questo nome di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="2e40f-112">Nel campo **Nome giornale di registrazione fatture**, seleziona un giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="2e40f-113">Se l'opzione **Paga a fornitore** è impostata su **Sì** per il libro di leasing, le fatture di pagamento di leasing e spese verranno registrate in questo nome di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="2e40f-114">Nel campo **Nome giornale di registrazione leasing**, seleziona un giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="2e40f-115">Tutti i movimenti di ammortamento, interessi e riclassificazione a breve termine verranno registrati in questo nome giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="2e40f-116">Se l'opzione **Paga a fornitore** è impostata su **No** per il libro di leasing, anche i movimenti di pagamento di leasing e spese verranno registrati in questo nome di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2e40f-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>
