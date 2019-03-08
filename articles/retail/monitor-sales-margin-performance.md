---
title: Monitorare le prestazioni di vendite e margine
description: È possibile monitorare le prestazioni di vendite e margine in tempo reale tramite Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e2b3591f6403542c79457d12ae850ad40d9253a1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "357268"
---
# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="0c566-103">Monitorare le prestazioni di vendite e margini</span><span class="sxs-lookup"><span data-stu-id="0c566-103">Monitor sales and margin performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c566-104">È possibile monitorare le prestazioni di vendite e margine in tempo reale tramite Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="0c566-104">You can monitor sales and margin performance in real time using Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="0c566-105">Nell'ambito di Dynamics 365 for Retail, gli utenti possono monitorare le prestazioni di vendite e margine in tempo reale tra livelli diversi della gerarchia organizzativa per le seguenti dimensioni:</span><span class="sxs-lookup"><span data-stu-id="0c566-105">As part of Dynamics 365 for Retail, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

- <span data-ttu-id="0c566-106">Prodotti</span><span class="sxs-lookup"><span data-stu-id="0c566-106">Products</span></span>
- <span data-ttu-id="0c566-107">Categorie</span><span class="sxs-lookup"><span data-stu-id="0c566-107">Categories</span></span>
- <span data-ttu-id="0c566-108">Sconti</span><span class="sxs-lookup"><span data-stu-id="0c566-108">Discounts</span></span>
- <span data-ttu-id="0c566-109">Anni come periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="0c566-109">Years as time period</span></span>
- <span data-ttu-id="0c566-110">Registratori/terminali</span><span class="sxs-lookup"><span data-stu-id="0c566-110">Registers/terminals</span></span>
- <span data-ttu-id="0c566-111">Personale/dipendenti</span><span class="sxs-lookup"><span data-stu-id="0c566-111">Staff/employees</span></span>
- <span data-ttu-id="0c566-112">Clienti</span><span class="sxs-lookup"><span data-stu-id="0c566-112">Customers</span></span>
- <span data-ttu-id="0c566-113">Unità operative</span><span class="sxs-lookup"><span data-stu-id="0c566-113">Operating units</span></span>

<span data-ttu-id="0c566-114">Inoltre, due report unici che sfruttano la struttura a griglia gerarchica consentono agli utenti di monitorare le prestazioni di vendite e margine eseguendo il drill down del noto di categoria superiore fino ai singoli nodi foglia della categoria nella gerarchia di categorie di prodotti al dettaglio predefinita.</span><span class="sxs-lookup"><span data-stu-id="0c566-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default retail product category hierarchy.</span></span> <span data-ttu-id="0c566-115">Gli utenti possono anche eseguire il drill down dall'unità operativa fino al singolo canale nella gerarchia organizzativa definita come gerarchia organizzativa predefinita per scopi di reporting sulla gerarchia di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="0c566-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for retail reporting hierarchy purposes.</span></span> <span data-ttu-id="0c566-116">È quindi possibile aprire i report da qualsiasi delle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="0c566-116">You can open the reports from any of the following locations:</span></span>

- <span data-ttu-id="0c566-117">Area di lavoro **Gestione punto vendita al dettaglio** &gt; **Vendita al dettaglio** &gt; **Canali** &gt; **Gestione punto vendita al dettaglio** &gt; **Report**</span><span class="sxs-lookup"><span data-stu-id="0c566-117">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="0c566-118">Area di lavoro **Gestione categorie e prodotti** &gt; **Vendita al dettaglio** &gt; **Prodotto e categorie** &gt; **Gestione punto vendita al dettaglio** &gt; **Report**</span><span class="sxs-lookup"><span data-stu-id="0c566-118">**Category and product management** workspace &gt; **Retail** &gt; **Product and categories** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="0c566-119">Area di lavoro **Gestione prezzi e sconti** &gt; **Vendita al dettaglio** &gt; **Prezzi e sconti** &gt; **Gestione punto vendita al dettaglio** &gt; **Report**</span><span class="sxs-lookup"><span data-stu-id="0c566-119">**Pricing and discount management** workspace &gt; **Retail** &gt; **Pricing and discounts** &gt; **Retail store management** &gt; **Reports**</span></span>
- <span data-ttu-id="0c566-120">Sezione **Richieste di informazioni e report**  &gt; **Vendita al dettaglio** &gt; **Richieste di informazioni e report** &gt; **Report vendite**</span><span class="sxs-lookup"><span data-stu-id="0c566-120">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>
