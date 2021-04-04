---
title: Risoluzione dei problemi relativi all'ottimizzazione della pianificazione
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori all'ottimizzazione della pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 39583c244f09f54551d560e8b1dd9f1a5a1590cc
ms.sourcegitcommit: 72f70c81176e86cda714a4712525f73514c895b7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2021
ms.locfileid: "5457331"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="66702-103">Risoluzione dei problemi relativi all'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="66702-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="66702-104">Questo argomento descrive come risolvere i problemi comuni che potresti riscontrare mentre lavori all'ottimizzazione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="66702-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="66702-105">L'installazione del componente aggiuntivo Ottimizzazione pianificazione non viene completata</span><span class="sxs-lookup"><span data-stu-id="66702-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="66702-106">Ottimizzazione pianificazione richiede un LCS (Lifecycle Services) abilitato, ambiente ad alta disponibilità di livello 2 o superiore (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="66702-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="66702-107">Se tenti di installare il componente aggiuntivo in un ambiente OneBox, l'installazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="66702-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="66702-108">**Soluzione**: annulla l'installazione e utilizza un ambiente ad alta disponibilità, livello 2 o superiore (non un ambiente OneBox).</span><span class="sxs-lookup"><span data-stu-id="66702-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="66702-109">La pianificazione di processi batch non riesce quando è abilitata l'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="66702-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="66702-110">Quando abiliti l'ottimizzazione della pianificazione, il motore di pianificazione principale incorporato viene disabilitato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="66702-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="66702-111">I processi batch di pianificazione generale creati per il motore di pianificazione integrato in Supply Chain Management falliranno se vengono attivati mentre Ottimizzazione pianificazione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="66702-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="66702-112">Puoi ricevere un messaggio di errore come *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span><span class="sxs-lookup"><span data-stu-id="66702-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="66702-113">**Soluzione**: annulla tutti i processi batch di pianificazione generale creati per il motore di pianificazione integrato in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="66702-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="66702-114">I risultati dell'ottimizzazione della pianificazione sono diversi dai risultati precedenti</span><span class="sxs-lookup"><span data-stu-id="66702-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="66702-115">L'ottimizzazione della pianificazione differisce dalla progettazione della pianificazione generale integrata in alcune aree.</span><span class="sxs-lookup"><span data-stu-id="66702-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="66702-116">Ciò può anche essere causato da funzionalità in sospeso.</span><span class="sxs-lookup"><span data-stu-id="66702-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="66702-117">**Soluzione**: esegui l'analisi dell'adattamento dell'ottimizzazione della pianificazione, quindi analizza i risultati facendo riferimento alla documentazione correlata per comprenderne l'impatto.</span><span class="sxs-lookup"><span data-stu-id="66702-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="66702-118">Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="66702-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="66702-119">Impossibile abilitare l'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="66702-119">Can't enable Planning Optimization</span></span>

<span data-ttu-id="66702-120">**Stato connessione** deve essere **Connesso** prima di poter configurare **Usa ottimizzazione di pianificazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="66702-120">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="66702-121">Per ulteriori informazioni, vedere [Introduzione all'ottimizzazione di pianificazione](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="66702-121">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="66702-122">**Soluzione**: assicurati che il componente aggiuntivo Ottimizzazione pianificazione sia stato installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="66702-122">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="66702-123">Il messaggio di errore viene visualizzato durante CTP</span><span class="sxs-lookup"><span data-stu-id="66702-123">Error message is shown during CTP</span></span>

<span data-ttu-id="66702-124">Se tenti di eseguire CTP (capable to promise) da un ordine cliente quando Ottimizzazione pianificazione è abilitato, riceverai il seguente messaggio di errore: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span><span class="sxs-lookup"><span data-stu-id="66702-124">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="66702-125">Ciò è correlato a una funzionalità in sospeso pianificata come parte del supporto per gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="66702-125">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="66702-126">**Soluzione:** evita i calcoli CTP quando Ottimizzazione pianificazione è abilitata fino a quando è disponibile il supporto CTP.</span><span class="sxs-lookup"><span data-stu-id="66702-126">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="66702-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="66702-127">Additional resources</span></span>

[<span data-ttu-id="66702-128">Introduzione all'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="66702-128">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="66702-129">Analisi corrispondenza Ottimizzazione pianificazione</span><span class="sxs-lookup"><span data-stu-id="66702-129">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]