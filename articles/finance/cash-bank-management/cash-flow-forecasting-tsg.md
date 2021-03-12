---
title: Risolvere i problemi di configurazione della previsione del flusso di cassa
description: Questo argomento fornisce le risposte alle domande che potrebbero sorgere quando si configura la previsione del flusso di cassa. Risponde alle domande frequenti (FAQ) sulla configurazione del flusso di cassa, sugli aggiornamenti del flusso di cassa e sul flusso di cassa Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985289"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="396bc-104">Risolvere i problemi di configurazione della previsione del flusso di cassa</span><span class="sxs-lookup"><span data-stu-id="396bc-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="396bc-105">Questo argomento fornisce le risposte alle domande che potrebbero sorgere quando si configura la previsione del flusso di cassa.</span><span class="sxs-lookup"><span data-stu-id="396bc-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="396bc-106">Risponde alle domande frequenti (FAQ) sulla configurazione del flusso di cassa, sugli aggiornamenti del flusso di cassa e sul flusso di cassa Power BI.</span><span class="sxs-lookup"><span data-stu-id="396bc-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="396bc-107">Perché il flusso di cassa viene mostrato per una sola persona giuridica?</span><span class="sxs-lookup"><span data-stu-id="396bc-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="396bc-108">La previsione del flusso di cassa è configurata e calcolata per ogni persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="396bc-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="396bc-109">I report Power BI e la funzionalità di previsioni del flusso di cassa in Finance Insights mostrano i risultati.</span><span class="sxs-lookup"><span data-stu-id="396bc-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="396bc-110">La previsione del flusso di cassa deve essere impostata per ogni persona giuridica per la quale desideri visualizzare una previsione.</span><span class="sxs-lookup"><span data-stu-id="396bc-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="396bc-111">Rivedi la configurazione della previsione del flusso di cassa in tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="396bc-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="396bc-112">In alternativa, rivedi la configurazione di tutte le persone giuridiche per la previsione del flusso di cassa e assicurati che siano impostate come previsto.</span><span class="sxs-lookup"><span data-stu-id="396bc-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="396bc-113">Perché Power BI non mostra tutti i dati del flusso di cassa?</span><span class="sxs-lookup"><span data-stu-id="396bc-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="396bc-114">È necessario completare diversi passaggi prima che le previsioni del flusso di cassa possano essere visualizzate in Power BI.</span><span class="sxs-lookup"><span data-stu-id="396bc-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="396bc-115">Rivedi il seguente elenco di controllo e assicurati che ogni passaggio sia stato completato:</span><span class="sxs-lookup"><span data-stu-id="396bc-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="396bc-116">Imposta il flusso di cassa per ciascuna persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="396bc-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="396bc-117">In Parametri di contabilità generale, imposta la valuta di sistema e il tipo di tasso di cambio di sistema.</span><span class="sxs-lookup"><span data-stu-id="396bc-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="396bc-118">Imposta la valuta di contabilizzazione per la contabilità generale e il tipo di tasso di cambio.</span><span class="sxs-lookup"><span data-stu-id="396bc-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="396bc-119">Immetti i tassi di cambio tra la valuta di transazione e la valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="396bc-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="396bc-120">Immetti i tassi di cambio tra la valuta di contabilizzazione e la valuta di sistema.</span><span class="sxs-lookup"><span data-stu-id="396bc-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="396bc-121">Immetti i tassi di cambio tra la valuta di contabilizzazione e ogni valuta di banca.</span><span class="sxs-lookup"><span data-stu-id="396bc-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="396bc-122">Perché il flusso di cassa Power BI funziona nelle versioni precedenti ma ora è vuoto?</span><span class="sxs-lookup"><span data-stu-id="396bc-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="396bc-123">Verifica che le misure "Misura flusso di cassa V2" e "LedgerCovLiquidityMeasurement" dall'archivio entità siano state configurate.</span><span class="sxs-lookup"><span data-stu-id="396bc-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="396bc-124">Per ulteriori informazioni su come lavorare con i dati nell'archivio entità, vedi [Integrazione di Power BI con l'archivio entità](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verifica che tutti i passaggi necessari per visualizzare il contenuto Power BI siano stati completati.</span><span class="sxs-lookup"><span data-stu-id="396bc-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="396bc-125">Per ulteriori informazioni, vedere [Contenuto di Power BI della panoramica situazione di cassa](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="396bc-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="396bc-126">Le entità dell'archivio entità sono state aggiornate?</span><span class="sxs-lookup"><span data-stu-id="396bc-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="396bc-127">È necessario aggiornare periodicamente le entità per garantire che i dati siano aggiornati e accurati.</span><span class="sxs-lookup"><span data-stu-id="396bc-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="396bc-128">Per aggiornare manualmente un'entità specifica, vai a **Amministrazione di sistema \> Impostazione \> Archivio entità**, seleziona l'entità e quindi seleziona **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="396bc-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="396bc-129">I dati possono anche essere aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="396bc-129">The data can also be updated automatically.</span></span> <span data-ttu-id="396bc-130">Nella pagina **Archivio entità** imposta l'opzione **Aggiornamento automatico abilitato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="396bc-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>
