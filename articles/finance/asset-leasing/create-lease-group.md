---
title: Creare un gruppo di leasing
description: In questo argomento viene spiegato come configurare i gruppi di leasing. I gruppi di leasing sono obbligatori per creare nuovi leasing.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5d5efb02c95d9368fbc178cfd9bcd7ce088d1c66
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816054"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="8f42d-104">Creare un gruppo di leasing</span><span class="sxs-lookup"><span data-stu-id="8f42d-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f42d-105">In questo argomento viene spiegato come configurare i gruppi di leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="8f42d-106">I gruppi di leasing sono obbligatori per creare nuovi leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="8f42d-107">I libri di leasing sono associati a ogni gruppo di leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="8f42d-108">I libri di leasing determinano i libri predefiniti che devono essere creati per ogni leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="8f42d-109">Puoi assegnare account specifici a un gruppo di leasing nella pagina **Parametri di registrazione del leasing**.</span><span class="sxs-lookup"><span data-stu-id="8f42d-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="8f42d-110">Crea un libro di leasing e aggiungi un gruppo di leasing</span><span class="sxs-lookup"><span data-stu-id="8f42d-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="8f42d-111">Vai a **Leasing cespiti \> Imposta \> Gruppi di leasing**.</span><span class="sxs-lookup"><span data-stu-id="8f42d-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="8f42d-112">Nel riquadro azioni seleziona **Nuovo** per aggiungere un gruppo di leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="8f42d-113">Una riga viene aggiunta alla griglia.</span><span class="sxs-lookup"><span data-stu-id="8f42d-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="8f42d-114">Sulla nuova riga, nel campo **Gruppo di leasing**, immetti un valore.</span><span class="sxs-lookup"><span data-stu-id="8f42d-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="8f42d-115">Nel campo **Descrizione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="8f42d-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="8f42d-116">Le informazioni appena inserite vengono aggiunte al campo **Gruppo di leasing** nella pagina **Aggiungi leasing**.</span><span class="sxs-lookup"><span data-stu-id="8f42d-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="8f42d-117">Associare un libro a un gruppo di leasing</span><span class="sxs-lookup"><span data-stu-id="8f42d-117">Associate a book with a lease group</span></span>

<span data-ttu-id="8f42d-118">Dopo aver creato i gruppi di leasing, puoi assegnare libri a ciascun gruppo.</span><span class="sxs-lookup"><span data-stu-id="8f42d-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="8f42d-119">Quando crei un leasing e lo assegni a un gruppo di leasing, il sistema crea una serie di scadenziari per ogni libro associato a quel gruppo di leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="8f42d-120">I libri devono essere configurati prima di poter essere assegnati a un gruppo di leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="8f42d-121">Vai a **Leasing cespiti \> Imposta \> Gruppo di leasing**.</span><span class="sxs-lookup"><span data-stu-id="8f42d-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="8f42d-122">Seleziona un gruppo di leasing, quindi seleziona **Libri**.</span><span class="sxs-lookup"><span data-stu-id="8f42d-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="8f42d-123">Seleziona **Nuovo**, quindi, nel campo **Tipo di libro**, seleziona il libro da assegnare al gruppo di leasing.</span><span class="sxs-lookup"><span data-stu-id="8f42d-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="8f42d-124">Puoi assegnare più libri a un gruppo di leasing se un leasing deve essere contabilizzato in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="8f42d-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]