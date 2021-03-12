---
title: Configurare i tipi di spesa
description: Nell'argomento viene descritto come configurare i tipi di spesa in Leasing cespite.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3ab31b16c6ae07466d7655832701e71092064fe1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969505"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="7682d-103">Configurare i tipi di spesa</span><span class="sxs-lookup"><span data-stu-id="7682d-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7682d-104">Nell'argomento viene descritto come configurare i tipi di spesa in Leasing cespite.</span><span class="sxs-lookup"><span data-stu-id="7682d-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="7682d-105">I costi che non sono rappresentati dallo scadenziario dei pagamenti sono noti come *costi di spesa*.</span><span class="sxs-lookup"><span data-stu-id="7682d-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="7682d-106">Esempi di questi costi includono le tasse sulla proprietà, i costi di manutenzione delle aree comuni e le spese di assicurazione.</span><span class="sxs-lookup"><span data-stu-id="7682d-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="7682d-107">Aggiungere un tipo di spesa amministrativa</span><span class="sxs-lookup"><span data-stu-id="7682d-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="7682d-108">Vai a **Leasing cespiti \> Imposta \> Tipi di spesa**.</span><span class="sxs-lookup"><span data-stu-id="7682d-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="7682d-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7682d-109">Select **New**.</span></span>
3. <span data-ttu-id="7682d-110">Nei campi appropriati, inserisci il nuovo tipo di spesa e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="7682d-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="7682d-111">Assegnare i conti ai costi amministrativi</span><span class="sxs-lookup"><span data-stu-id="7682d-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="7682d-112">Successivamente, è consigliabile associare i conti ai tipi di spesa.</span><span class="sxs-lookup"><span data-stu-id="7682d-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="7682d-113">Questi conti verranno addebitati quando vengono registrati i movimenti del programma spese.</span><span class="sxs-lookup"><span data-stu-id="7682d-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="7682d-114">Il conto di contropartita è specificato nelle righe **Piano di pagamento dei costi di esecuzione** su ogni leasing.</span><span class="sxs-lookup"><span data-stu-id="7682d-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="7682d-115">Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.</span><span class="sxs-lookup"><span data-stu-id="7682d-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="7682d-116">Nella scheda **Conti**, nella Scheda dettaglio **Costi di esecuzione**, nel campo **Tipo di spesa**, seleziona il tipo di spesa.</span><span class="sxs-lookup"><span data-stu-id="7682d-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="7682d-117">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7682d-117">Select **Add**.</span></span>
4. <span data-ttu-id="7682d-118">Nel campo **Tipo di libro** seleziona il tipo di libro da collegare ai costi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="7682d-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7682d-119">È possibile collegare più tipi di libri allo stesso conto spese.</span><span class="sxs-lookup"><span data-stu-id="7682d-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="7682d-120">Nel campo **Codice conto**, specifica a quali leasing deve essere applicato il libro:</span><span class="sxs-lookup"><span data-stu-id="7682d-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="7682d-121">**Tutti**: applica il libro a tutti i leasing.</span><span class="sxs-lookup"><span data-stu-id="7682d-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="7682d-122">**Gruppo**: applica il libro a un gruppo specifico di leasing.</span><span class="sxs-lookup"><span data-stu-id="7682d-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="7682d-123">**Tabella**: applica il libro a leasing specifichi.</span><span class="sxs-lookup"><span data-stu-id="7682d-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="7682d-124">Se hai selezionato **Gruppo** o **Tabella** nel campo **Codice conto**, seleziona un numero di conto o numero di gruppo nel campo **Numero conto/gruppo**.</span><span class="sxs-lookup"><span data-stu-id="7682d-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="7682d-125">Nei campi appropriati seleziona il conto principale del leasing finanziario e il conto principale del leasing operativo.</span><span class="sxs-lookup"><span data-stu-id="7682d-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="7682d-126">Dopo aver completato questi passaggi, puoi aggiungere le spese tramite le righe **Piano di pagamento dei costi di esecuzione** nella pagina **Dettagli leasing** di un leasing selezionato.</span><span class="sxs-lookup"><span data-stu-id="7682d-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="7682d-127">In alternativa, puoi aggiungere le spese quando crei un nuovo leasing.</span><span class="sxs-lookup"><span data-stu-id="7682d-127">Alternatively, you can add expenses when you create a new lease.</span></span>
