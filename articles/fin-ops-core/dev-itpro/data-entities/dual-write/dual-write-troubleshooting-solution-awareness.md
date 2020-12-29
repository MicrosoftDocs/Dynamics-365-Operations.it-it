---
title: Risoluzione dei problemi relativi alla consapevolezza della soluzione
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 79b2920b80ce4a8b419c2a146e15babc061cf64d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683567"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="df3cf-103">Risoluzione dei problemi relativi alla consapevolezza della soluzione</span><span class="sxs-lookup"><span data-stu-id="df3cf-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="df3cf-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="df3cf-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="df3cf-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.</span><span class="sxs-lookup"><span data-stu-id="df3cf-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df3cf-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="df3cf-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="df3cf-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="df3cf-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="df3cf-108">Errore nella pagina di doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="df3cf-108">Error on the Dual-write page</span></span>

<span data-ttu-id="df3cf-109">Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="df3cf-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="df3cf-110">*L'entità con nome "msdyn\_dualwriteentitymap" con namemapping = "Logico" non è stata trovata in MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="df3cf-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="df3cf-111">Per risolvere il problema, assicurarsi che sia installata la soluzione core doppia scrittura in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="df3cf-111">To fix the issue, make sure that the dual-write core solution is installed in Dataverse.</span></span> <span data-ttu-id="df3cf-112">La soluzione core doppia scrittura è un prerequisito per la consapevolezza della soluzione.</span><span class="sxs-lookup"><span data-stu-id="df3cf-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
