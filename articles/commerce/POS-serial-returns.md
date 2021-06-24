---
title: Restituire prodotti controllati dal numero di serie in POS
description: Questo argomento descrive le funzionalità per la convalida degli articoli con numero di serie come parte del processo di reso nell'applicazione POS di Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129815"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="b6ac9-103">Restituire prodotti controllati dal numero di serie in POS</span><span class="sxs-lookup"><span data-stu-id="b6ac9-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="b6ac9-104">Questo argomento descrive le funzionalità per la convalida degli articoli con numero di serie come parte del processo di reso nell'applicazione POS di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ac9-105">Nella versione di Commerce 10.0.20 e successive, è disponibile una nuova funzionalità denominata **Esperienza di elaborazione dei resi unificata in POS**.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="b6ac9-106">Per utilizzare la convalida del numero di serie durante l'elaborazione degli ordini di reso in POS, è necessario attivare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="b6ac9-107">Per informazioni su altre funzionalità fornite da questa funzione quando è attivata, vedere [Creare resi in POS)](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="b6ac9-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="b6ac9-108">Una volta attivata, la funzione non può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="b6ac9-109">Opzioni per la convalida dei resi con numero di serie</span><span class="sxs-lookup"><span data-stu-id="b6ac9-109">Options for validating serialized returns</span></span>

<span data-ttu-id="b6ac9-110">Quando la funzione **Esperienza di elaborazione dei resi unificata in POS** è attivata, le organizzazioni possono eseguire una convalida sui resi di articoli controllati dal numero di serie tramite POS.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="b6ac9-111">Questa funzionalità può avvisare gli utenti se il numero di serie restituito è diverso dal numero di serie originale che è stato venduto.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="b6ac9-112">Nella versione di Commerce 10.0.20 e successive, il messaggio che gli utenti ricevono è solo un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="b6ac9-113">Gli utenti possono continuare a elaborare un reso in base a un numero di serie diverso dal numero di serie originariamente venduto.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="b6ac9-114">Per configurare la convalida del numero di serie per un'organizzazione dopo l'attivazione della funzione **Esperienza di elaborazione dei resi unificata in POS**, accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di Commerce** in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="b6ac9-115">Nella scheda **Inventario**, scheda di dettaglio **Operazioni scorte di magazzino**, impostare l'opzione **Abilita convalida dei numeri di serie sui resi POS** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="b6ac9-116">Elaborare resi per articoli con numero di serie in POS</span><span class="sxs-lookup"><span data-stu-id="b6ac9-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="b6ac9-117">Se l'opzione **Abilita convalida dei numeri di serie sui resi POS** è stata impostata su **Sì**, quando un articolo controllato dal numero di serie viene reso tramite il POS, l'utente può immettere il numero di serie per la riga del reso nel riquadro dei dettagli nella pagina **Prodotti restituibili**.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="b6ac9-118">Se il numero di serie immesso non corrisponde al numero di serie originale venduto per la transazione di vendita, l'utente riceve un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="b6ac9-119">Tuttavia, l'applicazione non impedisce all'utente di continuare a pubblicare il reso.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ac9-120">Attualmente, il POS supporta la convalida dei numeri di serie solo sulle righe di reso in cui la quantità ordinata originale non è superiore a uno.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="b6ac9-121">Se la riga dell'ordine cliente originale è stata creata in un canale non POS e la quantità ordinata per l'articolo con numero di serie in una determinata riga di vendita è maggiore di uno, l'articolo non può essere restituito correttamente tramite il POS.</span><span class="sxs-lookup"><span data-stu-id="b6ac9-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6ac9-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b6ac9-122">Additional resources</span></span>

[<span data-ttu-id="b6ac9-123">Creare resi in POS</span><span class="sxs-lookup"><span data-stu-id="b6ac9-123">Create returns in POS</span></span>](POS-returns.md)
