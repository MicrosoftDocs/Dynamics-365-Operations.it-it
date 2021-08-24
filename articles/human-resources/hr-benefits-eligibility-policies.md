---
title: Criteri di idoneità benefit
description: Questo articolo fornisce le informazioni sui criteri di idoneità ai benefit, che consentono di definire chi è idoneo per ottenere i benefit specifici.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 8f0f51bc701af3f5dec2d393a87f589729af147bf44a56c4995991631f0d6379
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727163"
---
# <a name="benefit-eligibility-policies"></a>Criteri di idoneità benefit

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo fornisce le informazioni sui criteri di idoneità ai benefit, che consentono di definire chi è idoneo per ottenere i benefit specifici.

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