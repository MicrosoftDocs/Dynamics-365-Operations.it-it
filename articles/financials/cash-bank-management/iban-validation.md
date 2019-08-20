---
title: Gestire la convalida del conto IBAN (International Bank Account Number)
description: Questo argomento spiega come gestire la convalida del conto IBAN (International Bank Account Number).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 70c497ec575ffcaa6f2fdc3fe77bae7b41dc02fb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842427"
---
# <a name="manage-international-bank-account-number-iban-validation"></a><span data-ttu-id="cfcbd-103">Gestire la convalida IBAN (International Bank Account Number)</span><span class="sxs-lookup"><span data-stu-id="cfcbd-103">Manage International Bank Account Number (IBAN) validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cfcbd-104">La convalida IBAN (International Bank Account Number) aumenta la convalida che viene effettuata quando si aggiunge un IBAN a un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="cfcbd-105">Le informazioni sulla struttura dell'IBAN vengono archiviate in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="cfcbd-106">Quelle informazioni vengono caricate automaticamente durante la prima utilizzo dell'IBAN sui conti bancari.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="cfcbd-107">Contengono la lunghezza IBAN, le posizioni iniziali del numero di conto bancario e il numero di registrazione e la lunghezza del numero e del numero di registrazione del conto bancario.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="cfcbd-108">Impostare le strutture IBAN</span><span class="sxs-lookup"><span data-stu-id="cfcbd-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="cfcbd-109">Passare a **Gestione cassa e banche \> Impostazioni \> Strutture IBAN**.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="cfcbd-110">Si noti che le strutture IBAN per ogni paese o area sono state impostate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="cfcbd-111">Se si desidera personalizzare le strutture per un paese o un'area geografica specifica, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="cfcbd-112">Le definizioni delle strutture saranno parte di ogni nuova versione.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="cfcbd-113">È possibile utilizzare il menu **Reimposta strutture** per caricare le definizioni più recenti dopo ogni aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="cfcbd-114">Convalidare la struttura IBAN in un conto bancario</span><span class="sxs-lookup"><span data-stu-id="cfcbd-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="cfcbd-115">Passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="cfcbd-116">Creare un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-116">Create a bank account.</span></span>
3. <span data-ttu-id="cfcbd-117">Nella Scheda dettaglio **Informazioni aggiuntive** immettere un IBAN.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="cfcbd-118">Se la lunghezza IBAN non corrisponde alla lunghezza definita per ciascun paese/area geografica, verrà visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="cfcbd-119">Non è possibile procedere se la lunghezza dell'IBAN non corrisponde alla lunghezza specificata nella struttura IBAN.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="cfcbd-120">La convalida verifica inoltre che il numero di conto bancario corrisponda alla parte dell'IBAN che rappresenta il numero di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="cfcbd-121">Se il numero di conto bancario non corrisponde, viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="cfcbd-122">Questo messaggio è solo un avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-122">This message is only a warning.</span></span> <span data-ttu-id="cfcbd-123">È possibile continuare nonostante il numero di conto bancario non corrisponda.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="cfcbd-124">La convalida verifica inoltre che il numero di registrazione banca corrisponda alla parte dell'IBAN che rappresenta il numero di registrazione banca.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="cfcbd-125">Il numero di registrazione include un numero banca e spesso una succursale bancaria aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="cfcbd-126">Se il numero di registrazione banca non corrisponde, viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="cfcbd-127">Questo messaggio è solo un avviso.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-127">This message is only a warning.</span></span> <span data-ttu-id="cfcbd-128">È possibile continuare nonostante il numero di registrazione banca non corrisponda.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-128">You can continue even if the bank routing number doesn't match.</span></span>
