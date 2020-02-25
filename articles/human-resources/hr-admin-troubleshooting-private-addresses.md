---
title: Accedere a indirizzi privati per ruolo di sicurezza
description: In questo articolo viene descritto come risolvere il problema in cui un cliente non può accedere a indirizzi privati.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: facfd17f007b2c9e6f068d0ec4c5ce45b85a1b78
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009566"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="d033b-103">Accesso a indirizzi privati per ruolo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d033b-103">Access to private addresses by security role</span></span>

<span data-ttu-id="d033b-104">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="d033b-104">**Issue**</span></span>

<span data-ttu-id="d033b-105">Dopo che un cliente duplica un ruolo di sicurezza e accede con quel nuovo ruolo, il cliente non può visualizzare indirizzi contrassegnati come privati.</span><span class="sxs-lookup"><span data-stu-id="d033b-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="d033b-106">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="d033b-106">**Resolution**</span></span>

<span data-ttu-id="d033b-107">Per risolvere il problema, il cliente deve completare i passaggi seguenti per il ruolo di sicurezza duplicato.</span><span class="sxs-lookup"><span data-stu-id="d033b-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="d033b-108">Accedere a **Amministrazione organizzazione \> Rubrica globale \> Parametri Rubrica globale**.</span><span class="sxs-lookup"><span data-stu-id="d033b-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="d033b-109">Nella scheda **Sicurezza ubicazione privata**, spostare il nuovo ruolo di sicurezza dall'elenco **Ruoli disponibili** all'elenco **Ruoli selezionati**.</span><span class="sxs-lookup"><span data-stu-id="d033b-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="d033b-110">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d033b-110">Select **Save**.</span></span>

![Pagina dei parametri della rubrica globale](media/GAD-parameters.png)
