---
title: Configurare i tassi di indicizzazione
description: In questo argomento viene spiegato come configurare i tassi di indicizzazione. I tassi di indicizzazione sono obbligatori se la tua organizzazione associa gli importi del canone di leasing a una serie di tassi di indicizzazione.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f362bf4a6b5de3ce16330aea08880b07b4145792
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992866"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="eab4b-104">Configurare i tassi di indicizzazione</span><span class="sxs-lookup"><span data-stu-id="eab4b-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eab4b-105">Se i canoni di leasing dipendono da un indice, i tipi di tasso di indicizzazione possono essere aggiunti e gestiti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="eab4b-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="eab4b-106">Per rivalutare i canoni di leasing dalla pagina **Tipo di tasso di indicizzazione**, il processo di rivalutazione del tasso di indicizzazione utilizza il tasso di indicizzazione più recente dalla data di rivalutazione.</span><span class="sxs-lookup"><span data-stu-id="eab4b-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="eab4b-107">Per aggiungere tipi di tassi di indicizzazione e tassi di indicizzazione, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="eab4b-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="eab4b-108">Vai a **Leasing cespiti \> Imposta \> Tipi di tassi di indicizzazione**.</span><span class="sxs-lookup"><span data-stu-id="eab4b-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="eab4b-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="eab4b-109">Select **New**.</span></span>
3. <span data-ttu-id="eab4b-110">Nei campi appropriati, immetti il tipo di tasso e il nome del tasso di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="eab4b-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="eab4b-111">Per aggiungere un nuovo valore di tasso di indicizzazione, seleziona il tipo di tasso di indicizzazione, quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="eab4b-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="eab4b-112">Seleziona la data di inizio effettiva del tasso e seleziona il valore del tasso.</span><span class="sxs-lookup"><span data-stu-id="eab4b-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="eab4b-113">Devi selezionare **Differenza di valore del tasso di indicizzazione** o **Valore del tasso di indicizzazione** come metodo del tasso di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="eab4b-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="eab4b-114">Seleziona il metodo **Differenza di valore del tasso di indicizzazione** per calcolare un nuovo canone di leasing, basato sulla differenza tra il tasso di indicizzazione alla data di inizio e il tasso di indicizzazione più recente.</span><span class="sxs-lookup"><span data-stu-id="eab4b-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="eab4b-115">Il tasso di indicizzazione è definito nel campo **Tasso di indicizzazione (%)**.</span><span class="sxs-lookup"><span data-stu-id="eab4b-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="eab4b-116">Seleziona il metodo **Valore del tasso di indicizzazione** per calcolare il canone di leasing utilizzando la percentuale specificata nel campo **Tasso di indicizzazione (%)**.</span><span class="sxs-lookup"><span data-stu-id="eab4b-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>
