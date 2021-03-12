---
title: Risolvere i problemi di rifornimento del magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il rifornimento dei magazzini in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7748a18d2b6f612b3ac9ac1a75efb6ae5f13859a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993885"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="07ca9-103">Risolvere i problemi di rifornimento del magazzino</span><span class="sxs-lookup"><span data-stu-id="07ca9-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07ca9-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il rifornimento dei magazzini in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="07ca9-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="07ca9-105">Viene visualizzato il messaggio di errore seguente"Il lavoro %1 non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".</span><span class="sxs-lookup"><span data-stu-id="07ca9-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="07ca9-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="07ca9-106">Issue description</span></span>

<span data-ttu-id="07ca9-107">Il lavoro di prelievo è bloccato a causa del lavoro di rifornimento dipendente.</span><span class="sxs-lookup"><span data-stu-id="07ca9-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="07ca9-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="07ca9-108">Issue resolution</span></span>

<span data-ttu-id="07ca9-109">Quando si utilizza il rifornimento della domanda ciclo, se un'ubicazione di prelievo deve essere rifornita per soddisfare la domanda dell'ordine di origine, il sistema crea sia il lavoro di rifornimento che il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="07ca9-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="07ca9-110">Tuttavia, blocca il lavoro di prelievo fino al completamento del lavoro di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="07ca9-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="07ca9-111">Questo comportamento è intenzionale, perché l'ubicazione di prelievo non avrà scorte sufficienti a meno che il lavoro di rifornimento non sia completato.</span><span class="sxs-lookup"><span data-stu-id="07ca9-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="07ca9-112">Completare il lavoro di rifornimento e quindi elaborare il lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="07ca9-112">Complete the replenishment work, and then process the picking work.</span></span>
