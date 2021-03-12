---
title: Valutare la redditività di prodotti e clienti
description: In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Dynamics 365 Commerce.
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
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 3770832cb8eee96931d8f8e68c726d5e09d3fceb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980056"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="b56ea-103">Valutare la reddittività di prodotti e clienti</span><span class="sxs-lookup"><span data-stu-id="b56ea-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b56ea-104">In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b56ea-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="b56ea-105">Come parte di Commerce, gli utenti possono analizzare la redditività relativa ai clienti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="b56ea-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="b56ea-106">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="b56ea-106">Sales amount</span></span>
- <span data-ttu-id="b56ea-107">Quantità</span><span class="sxs-lookup"><span data-stu-id="b56ea-107">Quantity</span></span>
- <span data-ttu-id="b56ea-108">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="b56ea-108">Gross profit margin</span></span>
- <span data-ttu-id="b56ea-109">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="b56ea-109">Margin percentage</span></span>

<span data-ttu-id="b56ea-110">Per la valutazione, è possibile utilizzare direttamente il report **Primi clienti** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="b56ea-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="b56ea-111">Area di lavoro **Gestione punto vendita** &gt; **Retail e Commerce** &gt; **Canali** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="b56ea-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="b56ea-112">Sezione **Richieste di informazioni e report** &gt; **Retail e Commerce** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="b56ea-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="b56ea-113">In modo analogo, gli utenti possono analizzare la redditività relativa ai prodotti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="b56ea-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="b56ea-114">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="b56ea-114">Sales amount</span></span>
- <span data-ttu-id="b56ea-115">Quantità</span><span class="sxs-lookup"><span data-stu-id="b56ea-115">Quantity</span></span>
- <span data-ttu-id="b56ea-116">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="b56ea-116">Gross profit margin</span></span>
- <span data-ttu-id="b56ea-117">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="b56ea-117">Margin percentage</span></span>

<span data-ttu-id="b56ea-118">Per la valutazione, è possibile utilizzare direttamente il report **Report prodotti principali** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="b56ea-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="b56ea-119">Area di lavoro **Gestione punto vendita** &gt; **Retail e Commerce** &gt; **Canali** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="b56ea-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="b56ea-120">Area di lavoro **Gestione categorie e prodotti** &gt; **Retail e Commerce** &gt; **Prodotti e categorie** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="b56ea-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="b56ea-121">Sezione **Richieste di informazioni e report** &gt; **Retail e Commerce** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="b56ea-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
