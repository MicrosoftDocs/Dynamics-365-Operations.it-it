---
title: "L'utente può accedere a Core HR ma non all'app Onboard o Attract"
description: "In questo argomento viene descritto come risolvere il problema in cui un utente può accedere a Microsoft Dynamics 365 for Talent Core HR ma non all'app Attract o Onboard."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---

# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="e1c5d-103">L'utente può accedere a Core HR ma non all'app Onboard o Attract</span><span class="sxs-lookup"><span data-stu-id="e1c5d-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e1c5d-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="e1c5d-104">**Environment details**</span></span>

- <span data-ttu-id="e1c5d-105">La distribuzione di Microsoft Dynamics Lifecycle Services (LCS) è stata effettuata dall'utente A.</span><span class="sxs-lookup"><span data-stu-id="e1c5d-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="e1c5d-106">L'utente A ha aggiunto l'utente B come utente a Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="e1c5d-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="e1c5d-107">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="e1c5d-107">**Issue**</span></span>

<span data-ttu-id="e1c5d-108">L'utente B può accedere a Core HR, ma non può accedere all'app Talent: Attract o Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="e1c5d-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="e1c5d-109">Quando l'utente tenta di accedere a **App esperienza**, viene invece visualizzato un ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="e1c5d-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="e1c5d-110">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="e1c5d-110">**Solution**</span></span>

<span data-ttu-id="e1c5d-111">All'utente B devono essere assegnati i diritti di visualizzare l'ambiente di Microsoft PowerApps creato dall'utente A durante il processo di provisioning.</span><span class="sxs-lookup"><span data-stu-id="e1c5d-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="e1c5d-112">Per informazioni, vedere la sezione "Concedere l'accesso all'ambiente" in [Eseguire il provisioning di Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="e1c5d-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="e1c5d-113">**Soluzione a lungo termine**</span><span class="sxs-lookup"><span data-stu-id="e1c5d-113">**Long-term solution**</span></span>

<span data-ttu-id="e1c5d-114">Microsoft sta considerando l'assegnazione automatica dei diritti appropriati a Onboard e Attract quando un utente viene aggiunto a Core HR.</span><span class="sxs-lookup"><span data-stu-id="e1c5d-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>

