---
title: Spese personali in una nota spese
description: In questo argomento vengono descritti i due metodi per la gestione delle spese personali di un lavoratore in Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b072fa9e78563d3e89b4d60e9ce61473902fee76
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "1794993"
---
# <a name="personal-expenses-on-an-expense-report"></a><span data-ttu-id="dca4f-103">Spese personali in una nota spese</span><span class="sxs-lookup"><span data-stu-id="dca4f-103">Personal expenses on an expense report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dca4f-104">Durante i viaggi di lavoro potrebbe accadere che a volte i lavoratori utilizzino la carta di credito aziendale per le spese personali.</span><span class="sxs-lookup"><span data-stu-id="dca4f-104">During business travel, workers might sometimes charge personal expenses to their corporate credit cards.</span></span> <span data-ttu-id="dca4f-105">Se non si definisce un processo per la gestione delle spese personali, è possibile che il processo di approvazione delle note spese venga interrotto quando i lavoratori inviano i dettagli delle note spese.</span><span class="sxs-lookup"><span data-stu-id="dca4f-105">If you don't define a process for handling personal expenses, the approval process for expense reports might be disrupted when workers submit their itemized expense reports.</span></span> 

<span data-ttu-id="dca4f-106">In Microsoft Dynamics 365 for Finance and Operations sono disponibili due metodi per la gestione delle spese personali di un lavoratore:</span><span class="sxs-lookup"><span data-stu-id="dca4f-106">In Microsoft Dynamics 365 for Finance and Operations, there are two methods for handling a worker's personal expenses:</span></span>

- <span data-ttu-id="dca4f-107">**Pagate dal dipendente**: l'organizzazione non paga le spese personali che appaiono sull'estratto conto della carta di credito aziendale.</span><span class="sxs-lookup"><span data-stu-id="dca4f-107">**Paid by employee** – Your organization doesn't pay personal expenses that appear on the bill for the corporate credit card.</span></span> <span data-ttu-id="dca4f-108">Crea, invece, un report in cui sono riportate le spese personali insieme a quelle aziendali addebitate sulla carta di credito aziendale.</span><span class="sxs-lookup"><span data-stu-id="dca4f-108">Instead, it creates a report that shows personal expenses together with the corporate expenses that were charged to the corporate credit card.</span></span>
- <span data-ttu-id="dca4f-109">**Pagate dalla società**: l'organizzazione paga l'intero importo dell'estratto conto della carta di credito aziendale, quindi addebita le spese personali sul conto del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="dca4f-109">**Paid by company** – Your organization pays the whole bill for the corporate credit card and then debits the worker's account for the personal expenses.</span></span>

<span data-ttu-id="dca4f-110">È possibile selezionare il metodo utilizzato dall'organizzazione nella pagina **Parametri di gestione spese**.</span><span class="sxs-lookup"><span data-stu-id="dca4f-110">You can select the method that your organization uses on the **Expense management parameters** page.</span></span>
