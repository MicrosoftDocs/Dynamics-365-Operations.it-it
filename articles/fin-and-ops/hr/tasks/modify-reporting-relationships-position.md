---
title: Modificare le relazioni gerarchiche per una posizione
description: Questa procedura indica come modificare la relazione gerarchica di un dipendente.
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e779a337ff8f8e0199a60e094f4bec9eba49e701
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "322699"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="d661b-103">Modificare le relazioni gerarchiche per una posizione</span><span class="sxs-lookup"><span data-stu-id="d661b-103">Modify reporting relationships for a position</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d661b-104">Questa procedura indica come modificare la relazione gerarchica di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="d661b-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="d661b-105">La relazione gerarchica può essere utilizzata per distribuire i documenti tramite il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d661b-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="d661b-106">La procedura illustra anche come assegnare il dipendente alle gerarchie aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d661b-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="d661b-107">Ad esempio, un dipendente potrebbe far parte di un team di progetto con una relazione gerarchica informale a un supervisore di progetto.</span><span class="sxs-lookup"><span data-stu-id="d661b-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="d661b-108">Le relazioni gerarchiche aggiuntive possono essere definite sulla posizione per soddisfare i diversi scenari di matrice o di progetto.</span><span class="sxs-lookup"><span data-stu-id="d661b-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="d661b-109">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d661b-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="d661b-110">Andare a Risorse umane > Posizioni > Posizioni.</span><span class="sxs-lookup"><span data-stu-id="d661b-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="d661b-111">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="d661b-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d661b-112">Ad esempio, filtrare nel campo Posizione con un valore '000091'.</span><span class="sxs-lookup"><span data-stu-id="d661b-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="d661b-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d661b-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d661b-114">Espandere la sezione Subordinato a.</span><span class="sxs-lookup"><span data-stu-id="d661b-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="d661b-115">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d661b-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="d661b-116">Nel campo Subordinato a immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d661b-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="d661b-117">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="d661b-117">Click Create.</span></span>
8. <span data-ttu-id="d661b-118">Espandere la sezione Relazioni.</span><span class="sxs-lookup"><span data-stu-id="d661b-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="d661b-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="d661b-119">Click Add.</span></span>
10. <span data-ttu-id="d661b-120">Selezionare la casella di controllo a sinistra della griglia.</span><span class="sxs-lookup"><span data-stu-id="d661b-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="d661b-121">Nel campo Nome gerarchia immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d661b-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="d661b-122">Esempio: Progetto</span><span class="sxs-lookup"><span data-stu-id="d661b-122">Example: Project</span></span>  
12. <span data-ttu-id="d661b-123">Nel campo Subordinato a immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d661b-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="d661b-124">Esempio: 000437</span><span class="sxs-lookup"><span data-stu-id="d661b-124">Example:  000437</span></span>
13. <span data-ttu-id="d661b-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d661b-125">Click Save.</span></span>

