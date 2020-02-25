---
title: Novità o modifiche in Dynamics 365 Talent (7 gennaio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 615ed3e4260192ba36826e128f1afa1588e94845
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2020
ms.locfileid: "2974432"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="0f891-103">Novità o modifiche in Dynamics 365 Talent (7 gennaio 2020)</span><span class="sxs-lookup"><span data-stu-id="0f891-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="0f891-104">Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="0f891-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="0f891-105">Modifiche in Attract</span><span class="sxs-lookup"><span data-stu-id="0f891-105">Changes in Attract</span></span>

<span data-ttu-id="0f891-106">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="0f891-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="0f891-107">Modifiche in Onboard</span><span class="sxs-lookup"><span data-stu-id="0f891-107">Changes in Onboard</span></span>

<span data-ttu-id="0f891-108">Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="0f891-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="0f891-109">Modifiche di Core HR</span><span class="sxs-lookup"><span data-stu-id="0f891-109">Changes in Core HR</span></span>

<span data-ttu-id="0f891-110">Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2697.</span><span class="sxs-lookup"><span data-stu-id="0f891-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="0f891-111">I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0f891-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="0f891-112">Impossibile eliminare lavoratori che non hanno record di impiego - (386157)</span><span class="sxs-lookup"><span data-stu-id="0f891-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="0f891-113">Questa modifica aggiunge un'opzione di eliminazione nel modulo **Lavoratori con impiego**.</span><span class="sxs-lookup"><span data-stu-id="0f891-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="0f891-114">I lavoratori sono visualizzati in questo modulo quando non esistono impieghi futuri, attivi o storici per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="0f891-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="0f891-115">In questa versione, la funzionalità di eliminazione è abilitata solo per gli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="0f891-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="0f891-116">Tuttavia, nella versione della settimana successiva, la sicurezza verrà aggiornata per consentire a tutti gli utenti con il ruolo di assistente delle risorse umane di rimuovere dipendenti senza impiego.</span><span class="sxs-lookup"><span data-stu-id="0f891-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="0f891-117">È inoltre possibile apportare queste modifiche manualmente procedendo come segue.</span><span class="sxs-lookup"><span data-stu-id="0f891-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="0f891-118">Selezionare **Configurazione sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="0f891-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="0f891-119">Nella scheda **Privilegi**, filtrare l'elenco **Privilegi** in base a **Gestisci lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="0f891-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="0f891-120">Nella colonna **Riferimenti**, selezionare colonna, selezionare **Voci di menu Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="0f891-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="0f891-121">In **Voci di menu Visualizza**, selezionare **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="0f891-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="0f891-122">Impostare l'autorizzazione **Elimina** su Concedi.</span><span class="sxs-lookup"><span data-stu-id="0f891-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="0f891-123">Selezionare la scheda **Oggetti non pubblicati**.</span><span class="sxs-lookup"><span data-stu-id="0f891-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="0f891-124">Selezionare **Pubblica tutto**.</span><span class="sxs-lookup"><span data-stu-id="0f891-124">Select **Publish all**.</span></span>
