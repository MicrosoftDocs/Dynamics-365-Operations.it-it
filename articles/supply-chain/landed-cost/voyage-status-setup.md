---
title: Impostazione dello stato dei viaggi
description: In questo argomento viene descritto come stabilire i valori di stato che gli utenti possono assegnare ai viaggi.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: b7180cc9ab2d13f2260635d717adb7aab2177ab9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500888"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="66907-103">Impostazione dello stato dei viaggi</span><span class="sxs-lookup"><span data-stu-id="66907-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="66907-104">La pagina **Stati viaggio** consente di stabilire una serie di valori di stato che gli utenti possono assegnare ai viaggi.</span><span class="sxs-lookup"><span data-stu-id="66907-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="66907-105">Gli utenti possono assegnare valori di stato di viaggio a tutti i livelli di un viaggio: viaggio, contenitore di spedizione, registrazione, ordine fornitore e articolo (righe di acquisto e righe di ordine di trasferimento).</span><span class="sxs-lookup"><span data-stu-id="66907-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="66907-106">Sono utilizzati per due scopi:</span><span class="sxs-lookup"><span data-stu-id="66907-106">They are used for two purposes:</span></span>

- <span data-ttu-id="66907-107">Informare l'utente sullo stato di viaggio, contenitore di spedizione, registrazione, ordine fornitore o articolo (righe di acquisto e righe di ordine di trasferimento).</span><span class="sxs-lookup"><span data-stu-id="66907-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="66907-108">Limitare l'uso dell'area di costo prevenendone la modifica o l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="66907-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="66907-109">Selezionare **Costo sbarcato \> Impostazioni \> Stati viaggio**</span><span class="sxs-lookup"><span data-stu-id="66907-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="66907-110">per aggiungere, rimuovere e modificare stati utilizzando i pulsanti nel riquadro Azioni.</span><span class="sxs-lookup"><span data-stu-id="66907-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="66907-111">Ogni area di costo comporta un insieme e una gerarchia di stati di viaggio.</span><span class="sxs-lookup"><span data-stu-id="66907-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="66907-112">Pertanto, nella pagina **Stati viaggio**, nel campo **Area di costo**, è necessario dapprima selezionare l'area di costo per la quale si desidera visualizzare o creare stati di viaggio.</span><span class="sxs-lookup"><span data-stu-id="66907-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="66907-113">Quindi, per ogni stato di viaggio, impostare i campi descritti nella tabella seguente, come necessario.</span><span class="sxs-lookup"><span data-stu-id="66907-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="66907-114">Da notare che lo stato di un viaggio può anche essere modificato automaticamente dagli eventi di sistema, come le regole stabilite utilizzando il centro di controllo tracciabilità.</span><span class="sxs-lookup"><span data-stu-id="66907-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="66907-115">Campo</span><span class="sxs-lookup"><span data-stu-id="66907-115">Field</span></span> | <span data-ttu-id="66907-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66907-116">Description</span></span> |
|---|---|
| <span data-ttu-id="66907-117">Stato viaggio</span><span class="sxs-lookup"><span data-stu-id="66907-117">Voyage status</span></span> | <span data-ttu-id="66907-118">Immettere il nome dello stato di viaggio.</span><span class="sxs-lookup"><span data-stu-id="66907-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="66907-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66907-119">Description</span></span> | <span data-ttu-id="66907-120">Immettere una descrizione dello stato di viaggio.</span><span class="sxs-lookup"><span data-stu-id="66907-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="66907-121">Modifica</span><span class="sxs-lookup"><span data-stu-id="66907-121">Modify</span></span> | <span data-ttu-id="66907-122">Selezionare questa casella di controllo se gli utenti possono modificare i viaggi con questo stato.</span><span class="sxs-lookup"><span data-stu-id="66907-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="66907-123">Elimina</span><span class="sxs-lookup"><span data-stu-id="66907-123">Delete</span></span> | <span data-ttu-id="66907-124">Selezionare questa casella di controllo se gli utenti possono eliminare i viaggi con questo stato.</span><span class="sxs-lookup"><span data-stu-id="66907-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="66907-125">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="66907-125">Mandatory</span></span> | <span data-ttu-id="66907-126">Selezionare questa casella di controllo per rendere obbligatorio lo stato del viaggio, in modo che non possa essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="66907-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="66907-127">Padre</span><span class="sxs-lookup"><span data-stu-id="66907-127">Parent</span></span> | <span data-ttu-id="66907-128">Utilizzare questo campo per stabilire una gerarchia tra i valori di stato.</span><span class="sxs-lookup"><span data-stu-id="66907-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="66907-129">Gli stati di viaggio possono essere modificati (manualmente o automaticamente) solo verso il basso nella gerarchia, da uno stato padre a uno dei relativi stati figlio.</span><span class="sxs-lookup"><span data-stu-id="66907-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="66907-130">È necessario impostare solo gli stati di viaggio specifici utilizzati dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66907-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="66907-131">Gli stati di viaggio tipici includono *Confermato*, *Merci in transito*, *Ricevuto*, *Pronto per determinazione costi* e *Preventivato*.</span><span class="sxs-lookup"><span data-stu-id="66907-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="66907-132">Tuttavia, potrebbero essere presenti altri stati.</span><span class="sxs-lookup"><span data-stu-id="66907-132">However, other statuses might be present.</span></span>
