---
title: Impossibile rimuovere la dimensione di previsione della domanda di magazzino dalle righe di previsione
description: Impossibile rimuovere la dimensione di previsione della domanda di magazzino dalle righe di previsione.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026646"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="d272d-103">Impossibile rimuovere la dimensione di previsione della domanda di magazzino dalle righe di previsione</span><span class="sxs-lookup"><span data-stu-id="d272d-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="d272d-104">Numero KB: 4614408</span><span class="sxs-lookup"><span data-stu-id="d272d-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="d272d-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="d272d-105">Symptoms</span></span>

<span data-ttu-id="d272d-106">Questo problema si verifica quando la dimensione **Magazzino** non è assegnata nella scheda **Dimensioni previsione** della pagina **Parametri di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="d272d-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="d272d-107">Tuttavia, la colonna **Magazzino** è visualizzata nella **Previsione della domanda** (**Pianificazione generale \> Previsioni \> Voce di previsione \> Righe di previsione della domanda**).</span><span class="sxs-lookup"><span data-stu-id="d272d-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="d272d-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d272d-108">Resolution</span></span>

<span data-ttu-id="d272d-109">Le impostazioni nella scheda **Dimensioni previsione** della pagina **Parametri di previsione della domanda** non influiscono sulla pagina **Previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="d272d-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="d272d-110">Controllano la previsione di base generata e mostrata nella previsione della domanda modificata.</span><span class="sxs-lookup"><span data-stu-id="d272d-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="d272d-111">Tuttavia, non controllano le dimensioni necessarie per la previsione della domanda "reale".</span><span class="sxs-lookup"><span data-stu-id="d272d-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="d272d-112">Autorizzando i record visualizzati nella pagina **Previsione della domanda modificata** è possibile convertirli in voci di previsione "reali" per un modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="d272d-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="d272d-113">Quel modello può quindi essere utilizzato per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="d272d-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="d272d-114">Nella pagina **Previsione della domanda**, le dimensioni per la previsione "reale" visualizzate nelle righe di previsione della domanda fanno parte delle dimensioni inventariali</span><span class="sxs-lookup"><span data-stu-id="d272d-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="d272d-115">(questo comportamento è simile a quello delle righe di ordine cliente). Se il sistema non è configurato per utilizzare **Magazzino** come dimensione inventariale obbligatoria, puoi personalizzare la pagina per nascondere la colonna.</span><span class="sxs-lookup"><span data-stu-id="d272d-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>
