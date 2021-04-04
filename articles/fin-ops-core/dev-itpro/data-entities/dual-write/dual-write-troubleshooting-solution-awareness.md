---
title: Risoluzione dei problemi relativi alla consapevolezza della soluzione
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f9e02a6a5afe965a1707f0b04e1b4daedd4ec1df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566791"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="a65fc-103">Risoluzione dei problemi relativi alla consapevolezza della soluzione</span><span class="sxs-lookup"><span data-stu-id="a65fc-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="a65fc-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a65fc-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="a65fc-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi alla consapevolezza della soluzione.</span><span class="sxs-lookup"><span data-stu-id="a65fc-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a65fc-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a65fc-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="a65fc-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="a65fc-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="a65fc-108">Errore nella pagina di doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="a65fc-108">Error on the Dual-write page</span></span>

<span data-ttu-id="a65fc-109">Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="a65fc-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="a65fc-110">*L'entità con nome "msdyn\_dualwriteentitymap" con namemapping = "Logico" non è stata trovata in MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="a65fc-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="a65fc-111">Per risolvere il problema, assicurarsi che sia installata la soluzione core doppia scrittura in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a65fc-111">To fix the issue, make sure that the dual-write core solution is installed in Dataverse.</span></span> <span data-ttu-id="a65fc-112">La soluzione core doppia scrittura è un prerequisito per la consapevolezza della soluzione.</span><span class="sxs-lookup"><span data-stu-id="a65fc-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]