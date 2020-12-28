---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (24 settembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
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
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e0c1a3bf7613db4887e0943a70ad6262a70997f0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461629"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-24-2018"></a><span data-ttu-id="c0178-103">Novità o modifiche in Dynamics 365 Talent - Core HR (24 settembre 2018)</span><span class="sxs-lookup"><span data-stu-id="c0178-103">What's new or changed in Dynamics 365 Talent - Core HR (September 24, 2018)</span></span>

<span data-ttu-id="c0178-104">**Build 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="c0178-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="c0178-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="c0178-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="c0178-106">Valuta aggiunta ai benefit</span><span class="sxs-lookup"><span data-stu-id="c0178-106">Currency added to Benefits</span></span>

<span data-ttu-id="c0178-107">I piani di benefit sono stati aggiornati per includere la valuta del benefit.</span><span class="sxs-lookup"><span data-stu-id="c0178-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="c0178-108">Questo nuovo campo è disponibile anche per i benefit a cui è iscritto il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="c0178-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="c0178-109">Questo nuovo campo fa parte del privilegio di sicurezza Gestisci benefit e Visualizza un elenco di benefit.</span><span class="sxs-lookup"><span data-stu-id="c0178-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="c0178-110">Aggiornamento del processo di ripartizione - Congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="c0178-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="c0178-111">Le organizzazioni attribuiscono permessi in modo diverso in base a quando i dipendenti entrano e lasciano la società.</span><span class="sxs-lookup"><span data-stu-id="c0178-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="c0178-112">Per i dipendenti che lasciano l'organizzazione, può essere necessario che alcuni usufruiscano interamente del riconoscimento alla data di fine rapporto, mentre altri si affidano all'ultimo giorno lavorato per interrompere il processo di attribuzione.</span><span class="sxs-lookup"><span data-stu-id="c0178-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="c0178-113">Queste modifiche offrono alle organizzazioni la possibilità di scegliere quando terminare la registrazione durante il processo di fine rapporto.</span><span class="sxs-lookup"><span data-stu-id="c0178-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="c0178-114">Queste nuove opzioni fanno parte dei privilegi per Termina rapporto con lavoratore e Richiesta di terminare il rapporto con un lavoratore da un responsabile self-service.</span><span class="sxs-lookup"><span data-stu-id="c0178-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="c0178-115">Altre modifiche</span><span class="sxs-lookup"><span data-stu-id="c0178-115">Other changes</span></span>

<span data-ttu-id="c0178-116">In questa versione sono incluse altre correzioni di bug.</span><span class="sxs-lookup"><span data-stu-id="c0178-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="c0178-117">Problema noto</span><span class="sxs-lookup"><span data-stu-id="c0178-117">Known Issue</span></span>

-   <span data-ttu-id="c0178-118">**Problema:** quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** appaiono disattivati. **Soluzione alternativa:** prima di aprire la pagina degli allegati, assicurarsi che i riquadri Dettaglio informazioni nella pagina **Lavoratore** siano chiusi.</span><span class="sxs-lookup"><span data-stu-id="c0178-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="c0178-119">Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli Allegati saranno abilitati.</span><span class="sxs-lookup"><span data-stu-id="c0178-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="c0178-120">Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c0178-120">(This issue will be fixed in the next platform update.)</span></span>
