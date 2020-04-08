---
title: Creare un modello di record per facilitare l'immissione dei dati
description: In questo argomento viene descritto come creare un modello di record in modo che non sia necessario inserire in modo esplicito i valori dei campi che vengono utilizzati spesso per ogni nuovo record.
author: margoc
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec21415158ad611d0ad55778e76aa128f53561bd
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143386"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="69e2a-103">Creare un modello di record per facilitare l'immissione dei dati</span><span class="sxs-lookup"><span data-stu-id="69e2a-103">Create a record template to facilitate data entry</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69e2a-104">In questo argomento viene descritto come creare un modello di record in modo che non sia necessario inserire in modo esplicito i valori dei campi che vengono utilizzati spesso per ogni nuovo record.</span><span class="sxs-lookup"><span data-stu-id="69e2a-104">This topic demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="69e2a-105">In questa procedura, verrà creato un nuovo record per i nuovi computer portatili che devono essere aggiunti ai cespiti.</span><span class="sxs-lookup"><span data-stu-id="69e2a-105">In this procedure, you'll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="69e2a-106">Questa procedura utilizza la società di esempio USMF.</span><span class="sxs-lookup"><span data-stu-id="69e2a-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="69e2a-107">Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="69e2a-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-108">Select **New**.</span></span>
3. <span data-ttu-id="69e2a-109">Nel campo **Gruppo cespite** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69e2a-109">In the **Fixed asset group** field, enter or select a value.</span></span>
4. <span data-ttu-id="69e2a-110">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-110">In the **Name** field, type a value.</span></span> <span data-ttu-id="69e2a-111">Ad esempio, immettere **Corporate lead laptop**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-111">For example, enter **Corporate lead laptop**.</span></span>  
5. <span data-ttu-id="69e2a-112">Digitare un valore nel campo **Nome di ricerca**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-112">In the **Search name** field, type a value.</span></span> <span data-ttu-id="69e2a-113">Ad esempio, immettere **laptop**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-113">For example, enter **laptop**.</span></span>  
6. <span data-ttu-id="69e2a-114">Espandere la sezione **Informazioni tecniche**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-114">Expand the **Technical information** section.</span></span>
7. <span data-ttu-id="69e2a-115">Nei campi **Marca**, **Modello** e **Anno modello**, immettere i valori.</span><span class="sxs-lookup"><span data-stu-id="69e2a-115">In the **Make**, **Model**, and **Model year** fields, type values.</span></span>
8. <span data-ttu-id="69e2a-116">Nel riquadro azioni selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-116">On the Action Pane, select **Options**.</span></span>
9. <span data-ttu-id="69e2a-117">Selezionare **Informazioni sui record**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-117">Select **Record info**.</span></span>
10. <span data-ttu-id="69e2a-118">Selezionare **Modello utente**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-118">Select **User template**.</span></span>
11. <span data-ttu-id="69e2a-119">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-119">In the **Name** field, type a value.</span></span>
12. <span data-ttu-id="69e2a-120">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="69e2a-120">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="69e2a-121">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-121">Select **OK**.</span></span>
14. <span data-ttu-id="69e2a-122">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="69e2a-122">Select **Close**.</span></span>

