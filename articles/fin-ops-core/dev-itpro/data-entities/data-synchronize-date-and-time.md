---
title: Sincronizzare la data e l'ora nei processi di importazione
description: Utilizza i fusi orari UTC nei processi di importazione per evitare problemi con le conversioni di fuso orario.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae04b09a68e64d6d70c0329e689ab08c3903fca0
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798721"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="1a913-103">Sincronizzare la data e l'ora nei processi di importazione</span><span class="sxs-lookup"><span data-stu-id="1a913-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a913-104">È importante impostare il fuso orario per il processo di importazione su UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="1a913-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="1a913-105">Potresti visualizzare date e ore impreviste nei dati importati se utilizzi un'impostazione diversa.</span><span class="sxs-lookup"><span data-stu-id="1a913-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="1a913-106">Senza l'impostazione corretta, il processo di importazione converte la data UTC nel formato locale, quindi le impostazioni di sistema la convertono di nuovo.</span><span class="sxs-lookup"><span data-stu-id="1a913-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="1a913-107">Questa doppia conversione fa sì che le date cambino tra le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1a913-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="1a913-108">Ad esempio, la doppia conversione potrebbe far sì che la data di inizio di un dipendente sia diversa tra Dynamics 365 Human Resources e Dynamics 365 Finance a causa delle differenze nei fusi orari locali.</span><span class="sxs-lookup"><span data-stu-id="1a913-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="1a913-109">L'impostazione del processo di importazione su UTC risolve questo problema.</span><span class="sxs-lookup"><span data-stu-id="1a913-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="1a913-110">In Dynamics 365 Finance and Operations, seleziona **Gestione dati**.</span><span class="sxs-lookup"><span data-stu-id="1a913-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="1a913-111">Seleziona **Importa progetti** e quindi seleziona il progetto.</span><span class="sxs-lookup"><span data-stu-id="1a913-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="1a913-112">In **Formato data di origine**, seleziona **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="1a913-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="1a913-113">[![Modificare il formato della data di origine in UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="1a913-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="1a913-114">Modificare **Fuso orario** in **Fuso orario UTC** e cambiare **Lingua** in **En-US**.</span><span class="sxs-lookup"><span data-stu-id="1a913-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>


