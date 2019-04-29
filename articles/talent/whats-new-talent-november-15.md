---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (15 novembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "857317"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="e9b4d-103">Novità o modifiche in Dynamics 365 for Talent Core HR (15 novembre 2018)</span><span class="sxs-lookup"><span data-stu-id="e9b4d-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e9b4d-104">**Build 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="e9b4d-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="e9b4d-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="e9b4d-106">Altre modifiche/correzioni</span><span class="sxs-lookup"><span data-stu-id="e9b4d-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="e9b4d-107">Impossibile modificare la posizione corrente del dipendente in una posizione aperta futura</span><span class="sxs-lookup"><span data-stu-id="e9b4d-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="e9b4d-108">È stata effettuata una modifica per abilitare i trasferimenti di posizioni quando la posizione è disponibile solo in futuro.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="e9b4d-109">La posizione non viene visualizzata quando si crea un nuovo dipendente</span><span class="sxs-lookup"><span data-stu-id="e9b4d-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="e9b4d-110">È stata effettuata una modifica per visualizzare tutte le posizioni aperte disponibili per l'assegnazione quando si assumono nuovi dipendenti in Talent.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="e9b4d-111">Sono incluse le posizioni storiche o le posizioni future.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="e9b4d-112">Le posizioni sono ora visualizzate correttamente in base alla data di inizio impiego.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="e9b4d-113">La data di fine rapporto viene visualizzata in base alle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="e9b4d-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="e9b4d-114">È stata effettuata una modifica all'elenco dei dipendenti passati per prendere in considerazione eventuali differenze di fuso orario per il fuso orario preferito dei dipendenti quando si visualizza la data di fine rapporto.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="e9b4d-115">I collegamenti di Elementi di lavoro assegnati all'utente non visualizzano le informazioni corrette</span><span class="sxs-lookup"><span data-stu-id="e9b4d-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="e9b4d-116">Con questa modifica, il percorso ai dettagli dei singoli elementi di lavoro nell'elenco visualizza le informazioni corrette per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="e9b4d-117">Questo problema si è verificato solo con opzioni di sicurezza avanzate.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="e9b4d-118">Problema noto</span><span class="sxs-lookup"><span data-stu-id="e9b4d-118">Known issue</span></span>

- <span data-ttu-id="e9b4d-119">**Problema**: quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="e9b4d-120">**Soluzione alternativa:** prima di aprire la pagina dell'allegato, verificare che le schede dettaglio della pagina **Lavoratore** siano chiuse.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="e9b4d-121">Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="e9b4d-122">Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e9b4d-122">(This issue will be fixed in the next platform update.)</span></span>
