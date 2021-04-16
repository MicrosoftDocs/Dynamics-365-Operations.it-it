---
title: Spese varie per chilogrammo in una dichiarazione Intrastat
description: Questo argomento spiega come attivare, configurare e utilizzare la funzionalità per le spese varie per chilogrammo in una dichiarazione Intrastat.
author: ilkond
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: c0ccba4a5a377f6cff2e7324d7840dc056b6013a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814932"
---
# <a name="miscellaneous-charges-per-kilogram-in-an-intrastat-declaration"></a><span data-ttu-id="5bcbe-103">Spese varie per chilogrammo in una dichiarazione Intrastat</span><span class="sxs-lookup"><span data-stu-id="5bcbe-103">Miscellaneous charges per kilogram in an Intrastat declaration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5bcbe-104">Intrastat è il sistema utilizzato per la raccolta di informazioni e la generazione di statistiche sugli scambi commerciali tra paesi dell'Unione Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="5bcbe-104">Intrastat is the system that is used to collect information and generate statistics about the trade of goods among countries and regions in the European Union (EU).</span></span> <span data-ttu-id="5bcbe-105">Per ulteriori informazioni, vedere [Panoramica Intrastat](emea-intrastat.md).</span><span class="sxs-lookup"><span data-stu-id="5bcbe-105">For more information, see [Intrastat overview](emea-intrastat.md).</span></span>

<span data-ttu-id="5bcbe-106">Tra gli altri elementi di segnalazione, una dichiarazione Intrastat contiene informazioni sulle spese varie.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-106">Among other reporting elements, an Intrastat declaration contains information about miscellaneous charges.</span></span> <span data-ttu-id="5bcbe-107">Le spese varie sono di solito calcolate come percentuale dell'importo della fattura.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-107">Miscellaneous charges are usually calculated as a percentage of the invoice amount.</span></span> <span data-ttu-id="5bcbe-108">Tuttavia, in Italia, vengono spesso calcolati moltiplicando il costo di ciascun chilogrammo e il peso delle merci in chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-108">However, in Italy, they are often calculated by multiplying the cost of each kilogram and the weight of goods in kilograms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5bcbe-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5bcbe-109">Prerequisites</span></span>

- <span data-ttu-id="5bcbe-110">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-110">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="5bcbe-111">Nell'area di lavoro **Gestione funzionalità** attivare la funzionalità **Spese varie per chilogrammo in una dichiarazione Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-111">In the **Feature management** workspace, turn on the **Miscellaneous charges per kilogram in Intrastat declaration** feature.</span></span> <span data-ttu-id="5bcbe-112">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5bcbe-112">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-miscellaneous-charges-per-kilogram"></a><span data-ttu-id="5bcbe-113">Impostare le spese varie per chilogrammo</span><span class="sxs-lookup"><span data-stu-id="5bcbe-113">Set up miscellaneous charges per kilogram</span></span>

<span data-ttu-id="5bcbe-114">Sulla pagina **Dati master prodotti rilasciati**, sulla Scheda dettaglio **Commercio estero**, nella sezione **Intrastat** nel campo **Spese per chilogrammo**, inserire l'importo delle spese per chilogrammo.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-114">On the **Released products master data** page, on the **Foreign trade** FastTab, in the **Intrastat** section, in the **Charges per kilogram** field, enter the amount of the charges per kilogram.</span></span>

![Campo Spese per chilogrammo](media/emea-ita-exil-misc-charge-kg-pic1.jpg)

> [!NOTE]
> <span data-ttu-id="5bcbe-116">Verificare che il peso del prodotto sia definito in chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="5bcbe-116">Verify that the product weight is defined in kilograms.</span></span>

## <a name="calculation-of-miscellaneous-charges"></a><span data-ttu-id="5bcbe-117">Calcolo delle spese varie</span><span class="sxs-lookup"><span data-stu-id="5bcbe-117">Calculation of miscellaneous charges</span></span>

<span data-ttu-id="5bcbe-118">Quando le transazioni vengono trasferite a una dichiarazione Intrastat, il valore **Importo spese statistico** viene calcolato utilizzando la seguente formula:</span><span class="sxs-lookup"><span data-stu-id="5bcbe-118">When transactions are transferred to an Intrastat declaration, the **Statistical charges amount** value is calculated by using the following formula:</span></span>

<span data-ttu-id="5bcbe-119">*Importo spese statistico* = *Costo di ogni chilogrammo* × *Peso netto (in chilogrammi)*</span><span class="sxs-lookup"><span data-stu-id="5bcbe-119">*Statistical charges amount* = *Cost of each kilogram* × *Net weight (in kilograms)*</span></span>

<span data-ttu-id="5bcbe-120">Se viene anche inserito un valore **Percentuale spese**, nel calcolo vengono utilizzati entrambi i tipi di spese varie:</span><span class="sxs-lookup"><span data-stu-id="5bcbe-120">If a **Charges percentage** value is also entered, both types of miscellaneous charges are used in the calculation:</span></span>

<span data-ttu-id="5bcbe-121">*Importo spese statistico* = ( *Importo fattura* × *Percentuale spese*) + ( *Costo di ogni chilogrammo* × *Peso netto \[in chilogrammi\]*)</span><span class="sxs-lookup"><span data-stu-id="5bcbe-121">*Statistical charges amount* = (*Invoice amount* × *Charges percentage*) + (*Cost of each kilogram* × *Net weight \[in kilograms\]*)</span></span>

![Calcolo spese](media/emea-ita-exil-misc-charge-kg-pic2.jpg)

<span data-ttu-id="5bcbe-123">Per ulteriori informazioni, vedere [Trasferire le transazioni a Intrastat](tasks/transfer-transactions-intrastat.md)</span><span class="sxs-lookup"><span data-stu-id="5bcbe-123">For more information, see [Transfer transactions to the Intrastat](tasks/transfer-transactions-intrastat.md)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]