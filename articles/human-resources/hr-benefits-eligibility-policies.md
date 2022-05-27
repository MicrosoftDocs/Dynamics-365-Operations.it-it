---
title: Criteri di idoneità benefit
description: Questo argomento fornisce informazioni sulle politiche di idoneità ai benefici, che definiscono chi ha diritto a specifici benefici.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e36235e089fef70bc0d33815cd855628836f58db
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689552"
---
# <a name="benefit-eligibility-policies"></a>Criteri di idoneità benefit


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento fornisce informazioni sulle politiche di idoneità ai benefici, che definiscono chi ha diritto a specifici benefici.

Quando si creano benefit, si decide quali benefit saranno disponibili per determinati dipendenti. Nella seguente tabella vengono visualizzati gli esempi di benefit che è possibile rendere disponibili per dipendenti specifici.

| Benefit          | Per chi è disponibile il benefit |
|------------------|---------------------------------|
| Assicurazione sanitaria | Tutti i dipendenti                   |
| Cellulare     | Venditori, dirigenti         |
| Pass di parcheggio   | Dirigenti                      |

I seguenti componenti vengono utilizzati per creare i criteri di idoneità:

-   Tipi di regola dei criteri
-   Criteri di idoneità benefit

I tipi di regola dei criteri consentono di definire i parametri relativi a query utilizzati quando si sviluppano regole dei criteri specifiche. Dopo aver creato i tipi di regola dei criteri, è possibile creare i criteri di idoneità al benefit. I criteri consentono di creare una raccolta di regole applicabili a una o più persone giuridiche. All'interno di ciascun criterio, è possibile visualizzare qualsiasi tipo di regola dei criteri di idoneità al benefit creata in precedenza. 

Definire l'ambito della regola all'interno del criterio. Ad esempio, se si crea un tipo di regola dei criteri di idoneità al benefit denominata **Dirigente**, è possibile specificare come deve essere considerata la regola all'interno di tale criterio. In questo esempio, la regola può prevedere che qualsiasi posizione contenente la parola "dirigente" debba essere inclusa nella regola. Dopo aver definito i parametri della regola o delle regole incluse nel criterio, è possibile assegnare una regola specifica al benefit.






[!INCLUDE[footer-include](../includes/footer-banner.md)]
