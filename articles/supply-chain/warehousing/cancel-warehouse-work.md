---
title: Annullare il lavoro di magazzino per la gestione delle eccezioni
description: In questo argomento viene descritta la funzionalità di annullamento del lavoro che consente ai supervisori del magazzino di gestire il lavoro bloccato.
author: omulvad
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 552c83be411ed0be83b15d2541493ff0213fbe58
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831412"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="4c7d7-103">Annullare il lavoro di magazzino per la gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="4c7d7-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c7d7-104">La funzionalità Annulla lavoro in Microsoft Dynamics 365 Supply Chain Management consente all'utente amministratore di annullare il lavoro magazzino specifico attualmente in corso, ma che è bloccato dal sistema o non può essere completato a causa di circostanze eccezionali.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="4c7d7-105">Questa funzionalità è un'alternativa conveniente e sicura agli script correttivi SQL che correggono i dati incoerenti.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="4c7d7-106">Tuttavia, mentre questi script sono in genere richiesti ai professionisti IT, la funzionalità Annulla lavoro può essere utilizzata dagli utenti dell'azienda che dispongono dei diritti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="4c7d7-107">È possibile accedere alla funzionalità Annulla lavoro selezionando **Gestione magazzino** \> **Attività periodiche** \> **Pulitura \> Annulla lavoro**.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="4c7d7-108">Nella finestra di dialogo **Annulla lavoro**, specificare l'ID del lavoro da annullare, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="4c7d7-109">Lavori di magazzino che possono essere annullati</span><span class="sxs-lookup"><span data-stu-id="4c7d7-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="4c7d7-110">Durante le operazioni di prelievo del magazzino, un lavoratore potrebbe riscontrare situazioni in cui ha registrato le quantità come prelevate da un'ubicazione di immagazzinamento nell'ubicazione dell'utente, ma non può registrare l'operazione di inserimento.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="4c7d7-111">Dati di magazzino incoerenti sono spesso, ma non sempre, il motivo per cui il lavoro viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="4c7d7-112">Diversamente dalla normale funzionalità Annulla a cui è possibile accedere utilizzando il pulsante **Annulla** nell'intestazione del lavoro, la funzionalità Annulla lavoro non richiede che l'ultima riga di lavoro completata sia una riga di lavoro di tipo **stoccaggio**.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="4c7d7-113">In altre parole, per la funzionalità Annulla lavoro, la logica di annullamento può essere eseguita anche se la quantità di articoli su una riga di lavoro si trova in un'ubicazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="4c7d7-114">Per lavori che devono essere annullati per motivi operativi, gli utenti del magazzino devono continuare a utilizzare la normale funzionalità Annulla nella pagina di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="4c7d7-115">Solo i lavori di tipo **Vendite**, **Uscita di trasferimento**, **Prelievo materie prime** oppure **Rifornimento** possono essere annullati utilizzando la funzionalità Annulla lavoro.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="4c7d7-116">La logica di annullamento non verrà eseguita per i lavori di prelievo materie prime bloccati o lavori che possono essere annullati utilizzando la normale funzionalità Annulla (vedere la nota precedente).</span><span class="sxs-lookup"><span data-stu-id="4c7d7-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="4c7d7-117">Per sbloccare il lavoro, il sistema annulla le eventuali righe di lavoro rimanenti e corregge i dati di magazzino associati all'ID lavoro specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="4c7d7-118">Sarà quindi possibile riprendere le normali operazioni di gestione del magazzino che riguardano la quantità dell'articolo interessata.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="4c7d7-119">Per stoccare l'articolo interessato in un'ubicazione specifica dopo che il lavoro è stato annullato, l'utente deve utilizzare un'operazione di movimento scorte o rettifica della quantità su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="4c7d7-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]