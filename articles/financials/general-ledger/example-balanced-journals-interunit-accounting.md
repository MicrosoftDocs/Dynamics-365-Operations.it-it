---
title: Giornali di registrazione bilanciati per la contabilizzazione interunità
description: Questo articolo mostra in che modo un giornale di registrazione viene automaticamente bilanciato quando si seleziona una dimensione finanziaria di bilanciamento nella pagina Contabilità generale.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b596a2332a9ada01df7b4e718a79eb624ee52fc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549106"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="a0403-103">Giornali di registrazione bilanciati per la contabilizzazione interunità</span><span class="sxs-lookup"><span data-stu-id="a0403-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0403-104">Questo articolo mostra in che modo un giornale di registrazione viene automaticamente bilanciato quando si seleziona una dimensione finanziaria di bilanciamento nella pagina Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="a0403-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="a0403-105">Se la voce contabile non è in pareggio a livello dei valori di dimensione finanziaria, le voci contabili aggiuntive vengono create automaticamente per bilanciare la voce contabile.</span><span class="sxs-lookup"><span data-stu-id="a0403-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="a0403-106">Queste voci contabili utilizzano i tipi di registrazione **Interunit di debito** e**Interunit di credito** nella pagina **Conti per transazioni automatiche** per determinare il conto principale.</span><span class="sxs-lookup"><span data-stu-id="a0403-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="a0403-107">Ad esempio, Business Unit, ovvero il secondo segmento del conto CoGe, è selezionato come dimensione finanziaria di compensazione e le seguenti voci contabili stanno per essere create.</span><span class="sxs-lookup"><span data-stu-id="a0403-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="a0403-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="a0403-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="a0403-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="a0403-109">100.00 DR</span></span> |
| <span data-ttu-id="a0403-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="a0403-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="a0403-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="a0403-111">100.00 DR</span></span> |
| <span data-ttu-id="a0403-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="a0403-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="a0403-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="a0403-113">200.00 CR</span></span> |

<span data-ttu-id="a0403-114">In questo caso, i seguenti saldi sono determinati:</span><span class="sxs-lookup"><span data-stu-id="a0403-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="a0403-115">Per Business Unit MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="a0403-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="a0403-116">Per Business Unit NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="a0403-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="a0403-117">Pertanto, le seguenti voci contabili vengono create automaticamente per bilanciare il giornale di registrazione a livello dei valori di dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="a0403-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="a0403-118">(Interunità - Dare) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="a0403-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="a0403-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="a0403-119">100.00 DR</span></span> |
| <span data-ttu-id="a0403-120">(Interunità - Avere– NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="a0403-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="a0403-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="a0403-121">100.00 CR</span></span> |





