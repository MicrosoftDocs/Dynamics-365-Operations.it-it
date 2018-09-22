---
title: Gestire la convalida del conto IBAN (International Bank Account Number)
description: Questo argomento spiega come gestire la convalida del conto IBAN (International Bank Account Number).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="58f56-103">Gestire la convalida del conto IBAN (International Bank Account Number)</span><span class="sxs-lookup"><span data-stu-id="58f56-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58f56-104">La convalida del conto IBAN (International Bank Account Number) aumenta la convalida che viene effettuata quando si aggiunge un IBAN a un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58f56-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="58f56-105">La struttura dell'IBAN viene archiviata in Microsoft Dynamics 365 for Finance and Operations e viene caricata automaticamente la prima volta che si utilizza l'IBAN nei conti bancari.</span><span class="sxs-lookup"><span data-stu-id="58f56-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="58f56-106">Il numero di conto bancario fa parte della struttura definita per un numero IBAN.</span><span class="sxs-lookup"><span data-stu-id="58f56-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="58f56-107">In base a tale struttura, se la posizione e la lunghezza del numero di conto nell'IBAN non corrispondono alla posizione definita nella struttura per ciascun paese o area, vengono visualizzati messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="58f56-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="58f56-108">Impostare le strutture IBAN</span><span class="sxs-lookup"><span data-stu-id="58f56-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="58f56-109">Passare a **Gestione cassa e banche \> Impostazioni \> Strutture IBAN**.</span><span class="sxs-lookup"><span data-stu-id="58f56-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="58f56-110">Si noti che le strutture IBAN per ogni paese o area sono state impostate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="58f56-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="58f56-111">Se è necessario personalizzare le strutture per un paese o un'area specifica, è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="58f56-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="58f56-112">Le definizioni delle strutture saranno parte di ogni nuova versione.</span><span class="sxs-lookup"><span data-stu-id="58f56-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="58f56-113">È possibile utilizzare il menu **Reimposta strutture** per caricare le definizioni più recenti dopo ogni aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="58f56-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="58f56-114">Convalidare la struttura IBAN in un conto bancario</span><span class="sxs-lookup"><span data-stu-id="58f56-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="58f56-115">Passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="58f56-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="58f56-116">Creare un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58f56-116">Create a bank account.</span></span>
3. <span data-ttu-id="58f56-117">Nella Scheda dettaglio **Informazioni aggiuntive** immettere un IBAN.</span><span class="sxs-lookup"><span data-stu-id="58f56-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="58f56-118">Se la posizione e la lunghezza del numero di conto nell'IBAN non corrispondono alla posizione definita nella struttura per ciascun paese o area, viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58f56-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="58f56-119">Non è possibile procedere se la lunghezza dell'IBAN non corrisponde alla lunghezza nella struttura IBAN.</span><span class="sxs-lookup"><span data-stu-id="58f56-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="58f56-120">La convalida verifica inoltre che il numero di conto bancario corrisponda alla parte dell'IBAN che rappresenta il numero di conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58f56-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="58f56-121">Se il numero di conto bancario non corrisponde, viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="58f56-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="58f56-122">Questo messaggio è solo un avviso.</span><span class="sxs-lookup"><span data-stu-id="58f56-122">This message is only a warning.</span></span> <span data-ttu-id="58f56-123">È possibile continuare nonostante il numero di conto bancario non corrisponda.</span><span class="sxs-lookup"><span data-stu-id="58f56-123">You can continue even if the bank account number doesn't match.</span></span>

