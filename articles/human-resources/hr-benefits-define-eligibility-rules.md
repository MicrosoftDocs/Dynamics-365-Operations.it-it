---
title: Definire regole e criteri di idoneità ai benefit
description: Questo argomento spiega come creare regole di idoneità ai benefici e politiche e poi assegnare le regole ai benefici.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: c2595e40f6f9d1f75a94a3339735cc06bdabd14a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067656"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definire regole e criteri di idoneità ai benefit


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento spiega come creare regole e criteri di idoneità ai benefici e poi assegnare le regole ai benefici.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Creare il tipo di regola dei criteri di idoneità al benefit

1. Andare a **Risorse umane > Benefit > Idoneità > Tipi di regole dei criteri di idoneità al benefit**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome regola** immetti un valore.
4. Nel campo **Descrizione** immettere un valore.
5. Nel campo **Nome query**, seleziona il pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Selezionare **Salva**.
8. Chiudere la pagina.

## <a name="benefit-eligibility-policy"></a>Criteri di idoneità al benefit

1. Vai a **Risorse umane > Benefit > Idoneità > Criteri di idoneità benefit**.
2. Selezionare uno dei criteri di benefit esistenti.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Attivare/disattivare l'espansione delle sezioni **Organizzazioni criteri**. Puoi aggiungere o rimuovere tutte le organizzazioni da includere nei criteri.
5. Espandere o comprimere la sezione **Regole dei criteri**.
6. Nell'elenco individuare la regola dei criteri creata in precedenza.
7. Selezionare **Crea regola dei criteri**.
8. Nel campo **Data di validità** immetti la data in cui si desidera che i criteri diventino effettivi.
    * Se si impostano le date di fine effettive, è possibile apportare modifiche future alle regole dei criteri in modo da eliminare la necessità di tornare ai criteri quando si desidera che le modifiche siano effettive.  
9. Se necessario, aggiungi una clausola al campo **Aggiungi condizione**.
    * Se ad esempio si desidera che la regola venga applicata solo ai responsabili delle vendite, è possibile creare la clausola WHERE nel modo seguente: WHERE descrizione posizione corrisponde al responsabile vendite. Puoi aggiungere più clausole WHERE insieme nella regola.  
10. Selezionare **OK**.
11. Chiudere la pagina.

## <a name="assign-rule-to-benefit"></a>Assegnare la regola al benefit

1. Vai a **Risorse umane > Benefit > Benefit**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Espandere o comprimere la sezione **Regole di idoneità**.
5. Seleziona **Modifica**.
6. Nel campo **Idoneità**, seleziona la regola.
7. Nel campo **Tipo di regola** seleziona la regola creata in precedenza.
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Selezionare **Salva**.
11. Chiudere il modulo.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
