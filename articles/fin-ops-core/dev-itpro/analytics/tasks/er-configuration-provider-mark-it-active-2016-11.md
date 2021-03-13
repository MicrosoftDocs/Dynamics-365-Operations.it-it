---
title: Creare provider di configurazioni e contrassegnarli come attivi
description: In questo argomento viene descritto come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 835e35ef233ba5734e5a4d47f624629e95ae5b89
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092062"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="a7335-103">Creare fornitori di configurazioni e contrassegnarli come attivi</span><span class="sxs-lookup"><span data-stu-id="a7335-103">Create configuration providers and mark them as active</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7335-104">In questo argomento viene descritto come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="a7335-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="a7335-105">Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="a7335-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="a7335-106">In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="a7335-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="a7335-107">Creare un provider</span><span class="sxs-lookup"><span data-stu-id="a7335-107">Create a provider</span></span>
1. <span data-ttu-id="a7335-108">Andare al **pannello di navigazione** nell'angolo in alto a sinistra e selezionare **Amministrazione organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="a7335-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="a7335-109">Andare a **Aree di lavoro > Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="a7335-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="a7335-110">Andare a **Collegamenti correlati > Provider di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a7335-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="a7335-111">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a7335-111">Select **New**.</span></span>
    - <span data-ttu-id="a7335-112">Un record del provider ha un nome e un URL univoci.</span><span class="sxs-lookup"><span data-stu-id="a7335-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="a7335-113">Rivedere il contenuto di questa pagina e ignorare questa procedura se esiste già un record per Litware, Inc. (https://www.litware.com).</span><span class="sxs-lookup"><span data-stu-id="a7335-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="a7335-114">Nel campo Nome, digitare `Litware, Inc.`.</span><span class="sxs-lookup"><span data-stu-id="a7335-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="a7335-115">Nel campo Indirizzo Internet digitare `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="a7335-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="a7335-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a7335-116">Select **Save**.</span></span>
8. <span data-ttu-id="a7335-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a7335-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="a7335-118">Selezionare il provider come attivo</span><span class="sxs-lookup"><span data-stu-id="a7335-118">Select as an active provider</span></span>
1. <span data-ttu-id="a7335-119">Selezionare il provider Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="a7335-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="a7335-120">Selezionare **Imposta come attivo**.</span><span class="sxs-lookup"><span data-stu-id="a7335-120">Select **Set active**.</span></span>

![Pagina dell'area di lavoro Creazione di report elettronici](../media/GER-Task-ActiveProvider-1.png)
