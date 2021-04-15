---
title: Valutare la redditività di prodotti e clienti
description: In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 80a2f38f2b3f039b17556116d6aea738faa1db50
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797331"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="35fbb-103">Valutare la reddittività di prodotti e clienti</span><span class="sxs-lookup"><span data-stu-id="35fbb-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="35fbb-104">In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="35fbb-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="35fbb-105">Come parte di Commerce, gli utenti possono analizzare la redditività relativa ai clienti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="35fbb-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="35fbb-106">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="35fbb-106">Sales amount</span></span>
- <span data-ttu-id="35fbb-107">Quantità</span><span class="sxs-lookup"><span data-stu-id="35fbb-107">Quantity</span></span>
- <span data-ttu-id="35fbb-108">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="35fbb-108">Gross profit margin</span></span>
- <span data-ttu-id="35fbb-109">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="35fbb-109">Margin percentage</span></span>

<span data-ttu-id="35fbb-110">Per la valutazione, è possibile utilizzare direttamente il report **Primi clienti** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="35fbb-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="35fbb-111">Area di lavoro **Gestione punto vendita** &gt; **Retail e Commerce** &gt; **Canali** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="35fbb-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="35fbb-112">Sezione **Richieste di informazioni e report** &gt; **Retail e Commerce** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="35fbb-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="35fbb-113">In modo analogo, gli utenti possono analizzare la redditività relativa ai prodotti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="35fbb-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="35fbb-114">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="35fbb-114">Sales amount</span></span>
- <span data-ttu-id="35fbb-115">Quantità</span><span class="sxs-lookup"><span data-stu-id="35fbb-115">Quantity</span></span>
- <span data-ttu-id="35fbb-116">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="35fbb-116">Gross profit margin</span></span>
- <span data-ttu-id="35fbb-117">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="35fbb-117">Margin percentage</span></span>

<span data-ttu-id="35fbb-118">Per la valutazione, è possibile utilizzare direttamente il report **Report prodotti principali** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="35fbb-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="35fbb-119">Area di lavoro **Gestione punto vendita** &gt; **Retail e Commerce** &gt; **Canali** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="35fbb-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="35fbb-120">Area di lavoro **Gestione categorie e prodotti** &gt; **Retail e Commerce** &gt; **Prodotti e categorie** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="35fbb-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="35fbb-121">Sezione **Richieste di informazioni e report** &gt; **Retail e Commerce** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="35fbb-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]