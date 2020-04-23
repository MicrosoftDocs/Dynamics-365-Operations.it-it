---
title: Autorizzare una previsione modificata
description: Non tutti i dati di previsione devono essere autorizzati immediatamente. In questo articolo viene illustrato come è possibile specificare il periodo per cui una previsione viene autorizzata. Viene inoltre illustrato come è possibile autorizzare la previsione per le società e i modelli previsionali specifici.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e511aa8181b5d554f3392bdc5f0c299dc031ee4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203942"
---
# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="70d98-105">Autorizzare una previsione modificata</span><span class="sxs-lookup"><span data-stu-id="70d98-105">Authorize an adjusted forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70d98-106">Non tutti i dati di previsione devono essere autorizzati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="70d98-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="70d98-107">In questo articolo viene illustrato come è possibile specificare il periodo per cui una previsione viene autorizzata.</span><span class="sxs-lookup"><span data-stu-id="70d98-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="70d98-108">Viene inoltre illustrato come è possibile autorizzare la previsione per le società e i modelli previsionali specifici.</span><span class="sxs-lookup"><span data-stu-id="70d98-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="70d98-109">Non tutti i dati di previsione devono essere autorizzati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="70d98-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="70d98-110">È possibile specificare la data di inizio e di fine del periodo per cui la previsione viene autorizzata.</span><span class="sxs-lookup"><span data-stu-id="70d98-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="70d98-111">Questa funzionalità consente di bloccare intervalli specifici.</span><span class="sxs-lookup"><span data-stu-id="70d98-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="70d98-112">Le date di inizio e di fine specificate devono corrispondere alle date di inizio e di fine dell'intervallo in cui la previsione viene generata.</span><span class="sxs-lookup"><span data-stu-id="70d98-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="70d98-113">Il sistema applica questa restrizione e rettifica automaticamente le date, se la rettifica è richiesta.</span><span class="sxs-lookup"><span data-stu-id="70d98-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="70d98-114">Nella scheda **Dettagli** della pagina **Autorizzazione** è possibile visualizzare i dettagli sull'ultima previsione generata.</span><span class="sxs-lookup"><span data-stu-id="70d98-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="70d98-115">È possibile selezionare le società e i modelli previsionali per autorizzare la previsione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="70d98-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="70d98-116">Per impostazione predefinita, la griglia include tutte le società per cui la domanda di previsione è stata creata.</span><span class="sxs-lookup"><span data-stu-id="70d98-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="70d98-117">Per ogni società, il modello previsionale che corrisponde al piano previsionale corrente impostato nei parametri di pianificazione generale è precompilato.</span><span class="sxs-lookup"><span data-stu-id="70d98-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="70d98-118">Tuttavia, è possibile modificare questo modello previsionale impostandolo su qualsiasi modello previsionale che appartiene alla società.</span><span class="sxs-lookup"><span data-stu-id="70d98-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="70d98-119">Se non è stato generato alcun dato di domanda della previsione per una società selezionata, verrà visualizzato un messaggio di avviso al momento dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="70d98-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="70d98-120">È molto importante capire il funzionamento della casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base**.</span><span class="sxs-lookup"><span data-stu-id="70d98-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="70d98-121">Se sono state apportate rettifiche manuali alla previsione di base statistica, i valori rettificati vengono autorizzati per l'utilizzo anche se questa casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="70d98-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="70d98-122">Tuttavia, le modifiche vengono rimosse dopo l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="70d98-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="70d98-123">Di conseguenza, alla successiva generazione di una previsione, quest'ultima è solo una previsione statistica e non dispone di sostituzione manuali, anche se l'opzione **Trasferisci correzioni manuali alla previsione della domanda** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="70d98-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="70d98-124">Di conseguenza, è possibile considerare la casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base** come un meccanismo che consente di mantenere o rimuovere tutte le modifiche manuali.</span><span class="sxs-lookup"><span data-stu-id="70d98-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="additional-resources"></a><span data-ttu-id="70d98-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="70d98-125">Additional resources</span></span>
--------

[<span data-ttu-id="70d98-126">Implementare correzioni manuali nella previsione di base</span><span class="sxs-lookup"><span data-stu-id="70d98-126">Make manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="70d98-127">Monitorare la precisione della previsione</span><span class="sxs-lookup"><span data-stu-id="70d98-127">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)



