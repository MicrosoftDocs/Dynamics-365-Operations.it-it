---
title: Intervalli di tempo
description: È possibile utilizzare gli intervalli di tempo per ottimizzare la programmazione delle righe di ordine di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63a166806c2c8ac84cc1d71d6ec84fcb28033feb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206521"
---
# <a name="time-windows"></a><span data-ttu-id="1e14e-103">Intervalli di tempo</span><span class="sxs-lookup"><span data-stu-id="1e14e-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1e14e-104">È possibile utilizzare gli intervalli di tempo per ottimizzare la programmazione delle righe di ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="1e14e-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="1e14e-105">È possibile impostare il sistema in modo da creare automaticamente gli ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="1e14e-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="1e14e-106">In base ai criteri specificati da un intervallo di tempo, è possibile collegare qualsiasi numero possibile di righe di ordine di assistenza al minor numero possibile di pochi ordini di assistenza.</span><span class="sxs-lookup"><span data-stu-id="1e14e-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="1e14e-107">Gli intervalli di tempo definiscono il numero massimo di giorni di cui una riga di un ordine di assistenza può essere spostata rispetto alla data calcolata.</span><span class="sxs-lookup"><span data-stu-id="1e14e-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="1e14e-108">La data calcolata è la data in cui è stata programmata la riga ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="1e14e-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="1e14e-109">La data è basata sulla relativa impostazione di intervallo e sul periodo di assistenza definiti nella pagina **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="1e14e-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="1e14e-110">Per definire un intervallo di tempo utilizzando i valori nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="1e14e-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="1e14e-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="1e14e-111">Method</span></span> | <span data-ttu-id="1e14e-112">descrizione</span><span class="sxs-lookup"><span data-stu-id="1e14e-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1e14e-113">Settimana</span><span class="sxs-lookup"><span data-stu-id="1e14e-113">Week</span></span>   | <span data-ttu-id="1e14e-114">La data in cui la riga dell'ordine di assistenza può essere spostata in qualsiasi giorno lavorativo nella stessa settimana della data calcolata in origine.</span><span class="sxs-lookup"><span data-stu-id="1e14e-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="1e14e-115">Mese</span><span class="sxs-lookup"><span data-stu-id="1e14e-115">Month</span></span>  | <span data-ttu-id="1e14e-116">La data in cui la riga dell'ordine di assistenza può essere spostata in qualsiasi giorno lavorativo nello stesso mese della data calcolata in origine.</span><span class="sxs-lookup"><span data-stu-id="1e14e-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="1e14e-117">Ad esempio, la data calcolata per una riga dell'ordine di assistenza è il 15 febbraio 2017.</span><span class="sxs-lookup"><span data-stu-id="1e14e-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="1e14e-118">La riga di ordine di assistenza può essere programmata per qualsiasi giorno della settimana tra il 1 febbraio e il 28 febbraio 2017.</span><span class="sxs-lookup"><span data-stu-id="1e14e-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="1e14e-119">Manuale</span><span class="sxs-lookup"><span data-stu-id="1e14e-119">Manual</span></span> | <span data-ttu-id="1e14e-120">Definire il numero massimo di giorni di cui la riga dell'ordine di assistenza può essere spostata prima o dopo la data calcolata in origine.</span><span class="sxs-lookup"><span data-stu-id="1e14e-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="1e14e-121">Se per una riga di un contratto di assistenza non è stato specificato un intervallo di tempo, la riga dell'ordine di assistenza risultante dal contratto di assistenza dovrà essere eseguita nella data esatta programmata inizialmente.</span><span class="sxs-lookup"><span data-stu-id="1e14e-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e14e-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1e14e-122">Related topics</span></span>

[<span data-ttu-id="1e14e-123">Creare intervalli di tempo</span><span class="sxs-lookup"><span data-stu-id="1e14e-123">Create time windows</span></span>](create-time-windows.md)

