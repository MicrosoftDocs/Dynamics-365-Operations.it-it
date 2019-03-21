---
title: Novità o modifiche in Dynamics 365 for Talent (14 febbraio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5f96dd60652705de820e0661d417dcaee8143561
ms.sourcegitcommit: 5384200c3e33510c5b3ac31f2b22443e1076251f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "390668"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-14-2019"></a><span data-ttu-id="27a5c-103">Novità o modifiche in Dynamics 365 for Talent (14 febbraio 2019)</span><span class="sxs-lookup"><span data-stu-id="27a5c-103">What's new or changed in Dynamics 365 for Talent (February 14, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="27a5c-104">Questo argomento descrive le funzionalità nuove o modificate di Talent.</span><span class="sxs-lookup"><span data-stu-id="27a5c-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="27a5c-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="27a5c-105">Changes in Attract</span></span>
<span data-ttu-id="27a5c-106">Questa versione include correzioni di bug minori.</span><span class="sxs-lookup"><span data-stu-id="27a5c-106">There are minor bug fixes included with this release.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="27a5c-107">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="27a5c-107">Changes in Onboarding</span></span>
<span data-ttu-id="27a5c-108">Questa versione include correzioni di bug minori.</span><span class="sxs-lookup"><span data-stu-id="27a5c-108">There are minor bug fixes included with this release.</span></span>
 
## <a name="changes-in-core-hr"></a><span data-ttu-id="27a5c-109">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="27a5c-109">Changes in Core HR</span></span> 
<span data-ttu-id="27a5c-110">**Build 8.1.2146**</span><span class="sxs-lookup"><span data-stu-id="27a5c-110">**Build 8.1.2146**</span></span>

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a><span data-ttu-id="27a5c-111">L'entità Retribuzione fissa dipendente non esporta tutti i record</span><span class="sxs-lookup"><span data-stu-id="27a5c-111">Employee fixed compensation entity doesn't export all records</span></span>
<span data-ttu-id="27a5c-112">Con questa modifica, l'entità **Retribuzione fissa dipendente** ora esporterà tutti i record.</span><span class="sxs-lookup"><span data-stu-id="27a5c-112">With this change, the **Employee fixed compensation** entity will now export all records.</span></span> <span data-ttu-id="27a5c-113">L'entità può essere utilizzata per creare e aggiornare record di retribuzione fissa esistenti per i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="27a5c-113">The entity can be used to create and update existing fixed compensation records for employees.</span></span> 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a><span data-ttu-id="27a5c-114">La data di fine impiego non è conforme alle impostazioni di fuso orario preferite del dipendente</span><span class="sxs-lookup"><span data-stu-id="27a5c-114">Employment end date doesn't honor employee preferred time zone settings</span></span>
<span data-ttu-id="27a5c-115">Le date di fine impiego ora sono conformi al fuso orario preferito dell'utente quando si crea o si termina un impiego con una società.</span><span class="sxs-lookup"><span data-stu-id="27a5c-115">Employment end dates are now honoring the user-preferred time zone when creating or ending employment with a company.</span></span>
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a><span data-ttu-id="27a5c-116">Indirizzi del Regno Unito visualizzati in Analisi come indirizzi della Svizzera orientale</span><span class="sxs-lookup"><span data-stu-id="27a5c-116">UK addresses display in Analytics as Eastern Switzerland addresses</span></span>
<span data-ttu-id="27a5c-117">In questa versione, è stata apportata una modifica per correggere l'errato allineamento degli indirizzi in **Gestione personale** nel report "Numero dipendenti per ubicazione".</span><span class="sxs-lookup"><span data-stu-id="27a5c-117">In this release, a change has been made to correct misalignment in addresses in the **Personnel Management** "Headcount by location" report.</span></span>
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a><span data-ttu-id="27a5c-118">Il codice di fine rapporto non viene popolato nel record dell'assegnazione posizione lavoratore quando si termina la posizione</span><span class="sxs-lookup"><span data-stu-id="27a5c-118">Termination code is not populated on the worker position assignment record when ending the position</span></span>
<span data-ttu-id="27a5c-119">È stata effettuata una modifica al codice "Motivo fine rapporto" predefinito quando si termina l'assegnazione della posizione dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="27a5c-119">A change has been made to default the "Termination reason" code when ending the employees position assignment.</span></span>

### <a name="new-entity-created-for-job-compensation-levels"></a><span data-ttu-id="27a5c-120">Nuova entità creata per i livelli di retribuzione delle mansioni</span><span class="sxs-lookup"><span data-stu-id="27a5c-120">New entity created for job compensation levels</span></span>
<span data-ttu-id="27a5c-121">È stata creata una nuova entità DMF (Data Management Framework).</span><span class="sxs-lookup"><span data-stu-id="27a5c-121">A new data management framework (DMF) entity was created.</span></span> <span data-ttu-id="27a5c-122">Questa entità consente la creazione e l'aggiornamento di livelli retributivi, valori di mercato e informazioni per ogni mansione definita nel sistema.</span><span class="sxs-lookup"><span data-stu-id="27a5c-122">The entity provides for creation and updates to compensation levels, market values, and survey information for each job defined in the system.</span></span>
