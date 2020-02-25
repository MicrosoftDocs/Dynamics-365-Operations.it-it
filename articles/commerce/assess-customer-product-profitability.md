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
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 3218a29995791ce0d9a42d5b6d898d6e548f0f1d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022992"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="26f90-103">Valutare la reddittività di prodotti e clienti</span><span class="sxs-lookup"><span data-stu-id="26f90-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="26f90-104">In questo articolo viene illustrato come utilizzare l'analisi in memoria e in tempo reale per accedere, esplorare e ottenere informazioni dettagliate sui clienti e la redditività dei prodotti dai dati di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="26f90-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="26f90-105">Come parte di Commerce, gli utenti possono analizzare la redditività relativa ai clienti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="26f90-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="26f90-106">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="26f90-106">Sales amount</span></span>
- <span data-ttu-id="26f90-107">Quantità</span><span class="sxs-lookup"><span data-stu-id="26f90-107">Quantity</span></span>
- <span data-ttu-id="26f90-108">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="26f90-108">Gross profit margin</span></span>
- <span data-ttu-id="26f90-109">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="26f90-109">Margin percentage</span></span>

<span data-ttu-id="26f90-110">Per la valutazione, è possibile utilizzare direttamente il report **Primi clienti** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="26f90-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="26f90-111">Area di lavoro **Gestione punto vendita** &gt; **Retail e Commerce** &gt; **Canali** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="26f90-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="26f90-112">Sezione **Richieste di informazioni e report** &gt; **Retail e Commerce** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report primi clienti**</span><span class="sxs-lookup"><span data-stu-id="26f90-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="26f90-113">In modo analogo, gli utenti possono analizzare la redditività relativa ai prodotti principali (da 10 a 100) tra diversi livelli della gerarchia organizzativa, in base a uno dei seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="26f90-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="26f90-114">Importo vendite</span><span class="sxs-lookup"><span data-stu-id="26f90-114">Sales amount</span></span>
- <span data-ttu-id="26f90-115">Quantità</span><span class="sxs-lookup"><span data-stu-id="26f90-115">Quantity</span></span>
- <span data-ttu-id="26f90-116">Margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="26f90-116">Gross profit margin</span></span>
- <span data-ttu-id="26f90-117">Percentuale margine</span><span class="sxs-lookup"><span data-stu-id="26f90-117">Margin percentage</span></span>

<span data-ttu-id="26f90-118">Per la valutazione, è possibile utilizzare direttamente il report **Report prodotti principali** che è possibile aprire tramite uno dei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="26f90-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="26f90-119">Area di lavoro **Gestione punto vendita** &gt; **Retail e Commerce** &gt; **Canali** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="26f90-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="26f90-120">Area di lavoro **Gestione categorie e prodotti** &gt; **Retail e Commerce** &gt; **Prodotti e categorie** &gt; **Gestione punto vendita** &gt; **Report** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="26f90-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="26f90-121">Sezione **Richieste di informazioni e report** &gt; **Retail e Commerce** &gt; **Richieste di informazioni e report** &gt; **Report vendite** &gt; **Report prodotti principali**</span><span class="sxs-lookup"><span data-stu-id="26f90-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
