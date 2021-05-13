---
title: Strumenti di test di gestione qualità
description: Questo argomento descrive come creare strumenti di test che possano essere utilizzati per i test in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc09021f89a9064a3140a726fca74e3eceab13da
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956715"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="a99f4-103">Strumenti di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="a99f4-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a99f4-104">Questo argomento descrive come creare strumenti di test che possano essere utilizzati per i test in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a99f4-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="a99f4-105">Utilizza la pagina **Strumenti di test** per definire e visualizzare i dettagli sui dispositivi utilizzati per eseguire i test sugli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="a99f4-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="a99f4-106">Gli strumenti di test sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a99f4-106">Test instruments are optional.</span></span> <span data-ttu-id="a99f4-107">Tuttavia, possono aiutare gli addetti al controllo qualità a sapere quale dispositivo o strumento dovrebbero utilizzare per eseguire un test specifico.</span><span class="sxs-lookup"><span data-stu-id="a99f4-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="a99f4-108">Esempio di strumento di test</span><span class="sxs-lookup"><span data-stu-id="a99f4-108">Test instrument example</span></span>

<span data-ttu-id="a99f4-109">Stai eseguendo vari test su componenti elettrici.</span><span class="sxs-lookup"><span data-stu-id="a99f4-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="a99f4-110">Alcuni test riguardano la tensione di uscita dei componenti, un test è per la loro temperatura e un test è per il loro peso.</span><span class="sxs-lookup"><span data-stu-id="a99f4-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="a99f4-111">Per eseguire ogni test vengono utilizzati strumenti, dispositivi o apparecchiature diversi.</span><span class="sxs-lookup"><span data-stu-id="a99f4-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="a99f4-112">Ad esempio, un voltmetro viene utilizzato per misurare la tensione, un termometro viene utilizzato per misurare la temperatura e una bilancia viene utilizzata per misurare il peso.</span><span class="sxs-lookup"><span data-stu-id="a99f4-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="a99f4-113">È possibile configurare ciascuno di questi dispositivi come uno strumento di test e indicare l'unità di misura in cui devono essere registrati i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="a99f4-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="a99f4-114">Ad esempio, i risultati del voltmetro vengono registrati in volt, i risultati del termometro vengono registrati in gradi Fahrenheit o gradi Celsius e i risultati della bilancia vengono registrati in libbre o chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="a99f4-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="a99f4-115">Creare uno strumento di test</span><span class="sxs-lookup"><span data-stu-id="a99f4-115">Create a test instrument</span></span>

1. <span data-ttu-id="a99f4-116">Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Strumenti di test**.</span><span class="sxs-lookup"><span data-stu-id="a99f4-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="a99f4-117">Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.</span><span class="sxs-lookup"><span data-stu-id="a99f4-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="a99f4-118">Quindi imposta i seguenti campi per la nuova riga:</span><span class="sxs-lookup"><span data-stu-id="a99f4-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="a99f4-119">**Strumento di test** – Immetti un ID o nome univoco per lo strumento di test.</span><span class="sxs-lookup"><span data-stu-id="a99f4-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="a99f4-120">**Descrizione** - Immettere una descrizione dettagliata dello strumento di test.</span><span class="sxs-lookup"><span data-stu-id="a99f4-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="a99f4-121">**Unità** - Selezionare l'unità in cui lo strumento misura i risultati.</span><span class="sxs-lookup"><span data-stu-id="a99f4-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="a99f4-122">Il campo **Precisione** viene impostato automaticamente, in base all'unità selezionata.</span><span class="sxs-lookup"><span data-stu-id="a99f4-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="a99f4-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a99f4-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a99f4-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a99f4-124">Additional resources</span></span>

- [<span data-ttu-id="a99f4-125">Test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="a99f4-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="a99f4-126">Gruppi di test di gestione qualità</span><span class="sxs-lookup"><span data-stu-id="a99f4-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
