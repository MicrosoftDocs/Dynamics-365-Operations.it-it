---
title: L'utente può accedere a Core HR ma non a Onboard o Attract
description: In questo argomento viene descritto come risolvere il problema in cui un utente può accedere a Microsoft Dynamics 365 Talent - Core HR ma non ad Attract o Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 80b1f8aeabfd033f393463f4be5a61447377f2d9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009308"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a><span data-ttu-id="5433d-103">L'utente può accedere a Core HR ma non a Onboard o Attract</span><span class="sxs-lookup"><span data-stu-id="5433d-103">User can access Core HR but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5433d-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="5433d-104">**Environment details**</span></span>

- <span data-ttu-id="5433d-105">La distribuzione di Microsoft Dynamics Lifecycle Services (LCS) è stata effettuata dall'utente A.</span><span class="sxs-lookup"><span data-stu-id="5433d-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="5433d-106">L'utente A ha aggiunto l'utente B come utente a Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="5433d-106">User A added user B as a user to Microsoft Dynamics 365 Talent: Core HR.</span></span>

<span data-ttu-id="5433d-107">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5433d-107">**Issue**</span></span>

<span data-ttu-id="5433d-108">L'utente B può accedere a Core HR, ma non può accedere all'app Talent: Attract o Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="5433d-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="5433d-109">Quando l'utente tenta di accedere a **App esperienza**, viene invece visualizzato un ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="5433d-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="5433d-110">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="5433d-110">**Solution**</span></span>

<span data-ttu-id="5433d-111">All'utente B devono essere assegnati i diritti di visualizzare l'ambiente di Microsoft PowerApps creato dall'utente A durante il processo di provisioning.</span><span class="sxs-lookup"><span data-stu-id="5433d-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="5433d-112">Per informazioni, vedere la sezione "Concedere l'accesso all'ambiente" in [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="5433d-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="5433d-113">**Soluzione a lungo termine**</span><span class="sxs-lookup"><span data-stu-id="5433d-113">**Long-term solution**</span></span>

<span data-ttu-id="5433d-114">Microsoft sta considerando l'assegnazione automatica dei diritti appropriati a Onboard e Attract quando un utente viene aggiunto a Core HR.</span><span class="sxs-lookup"><span data-stu-id="5433d-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
