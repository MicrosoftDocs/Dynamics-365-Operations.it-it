---
title: Valutare la redditività di prodotti e clienti
description: In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 28d4eeaa3fcae33f817690ad496b4b123a5838ce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "326011"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="45e76-103">Valutare la reddittività di prodotti e clienti</span><span class="sxs-lookup"><span data-stu-id="45e76-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="45e76-104">In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="45e76-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span>

<span data-ttu-id="45e76-105">Come parte di Dynamics 365 for Retail, gli utenti possono analizzare la redditività relativa ai clienti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="45e76-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="45e76-106">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="45e76-106">Sales amount</span></span>
- <span data-ttu-id="45e76-107">Quantità</span><span class="sxs-lookup"><span data-stu-id="45e76-107">Quantity</span></span>
- <span data-ttu-id="45e76-108">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="45e76-108">Gross profit margin</span></span>
- <span data-ttu-id="45e76-109">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="45e76-109">Margin percentage</span></span>

<span data-ttu-id="45e76-110">Per la valutazione, è possibile utilizzare direttamente il report **Primi clienti** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="45e76-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="45e76-111">Area di lavoro **Gestione punto vendita al dettaglio** &gt; **Vendita al dettaglio** &gt; **Canali** &gt; **Gestione punto vendita al dettaglio** &gt; **Report** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="45e76-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="45e76-112">Sezione **Richieste di informazioni e report** &gt; **Vendita al dettaglio** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="45e76-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="45e76-113">In modo analogo, gli utenti possono analizzare la redditività relativa ai prodotti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="45e76-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="45e76-114">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="45e76-114">Sales amount</span></span>
- <span data-ttu-id="45e76-115">Quantità</span><span class="sxs-lookup"><span data-stu-id="45e76-115">Quantity</span></span>
- <span data-ttu-id="45e76-116">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="45e76-116">Gross profit margin</span></span>
- <span data-ttu-id="45e76-117">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="45e76-117">Margin percentage</span></span>

<span data-ttu-id="45e76-118">Per la valutazione, è possibile utilizzare direttamente il report **Report prodotti principali** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="45e76-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="45e76-119">Area di lavoro **Gestione punto vendita al dettaglio** &gt; **Vendita al dettaglio** &gt; **Canali** &gt; **Gestione punto vendita al dettaglio** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="45e76-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="45e76-120">Area di lavoro **Gestione categorie e prodotti** &gt; **Vendita al dettaglio e commercio** &gt; **Prodotti e categorie** &gt; **Gestione punto vendita al dettaglio** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="45e76-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="45e76-121">Sezione **Richieste di informazioni e report** &gt; **Vendita al dettaglio** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="45e76-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
