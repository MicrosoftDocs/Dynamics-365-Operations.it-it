---
title: Definire regole e criteri di idoneità ai benefit
description: In questo articolo viene descritto come è possibile creare regole e criteri di idoneità di benefit e come assegnare le regole ai benefit.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: f46437fef342ab1a4e368063d8b74205ca8e8c05
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430879"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definire regole e criteri di idoneità ai benefit

In questo articolo viene descritto come è possibile creare regole e criteri di idoneità di benefit e come assegnare le regole ai benefit.  

La società di dati dimostrativi utilizzata per creare questa registrazione è USMF.


## <a name="create-benefit-eligibility-policy-rule-type"></a>Creare il tipo di regola dei criteri di idoneità al benefit
1. Andare a Risorse umane > Benefit > Idoneità > Tipi di regole dei criteri di idoneità al benefit.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Regola.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Nome query fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Fare clic su Salva.
8. Chiudere la pagina.

## <a name="benefit-eligibility-policy"></a>Criteri di idoneità al benefit
1. Andare a Risorse umane > Benefit > Idoneità > Criteri di idoneità benefit.
2. Selezionare uno dei criteri di benefit esistenti.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Attivare/disattivare l'espansione delle sezioni Organizzazioni criteri.  In questo punto è possibile aggiungere o rimuovere tutte le organizzazioni da includere nei criteri.
5. Espandere o comprimere la sezione Regole dei criteri.
6. Nell'elenco individuare la regola dei criteri creata in precedenza.
7. Fare clic su Crea regola dei criteri.
8. Nel campo Data di validità immettere la data in cui si desidera che i criteri diventino effettivi.
    * Se si impostano le date di validità e di fine, è possibile apportare modifiche future alle regole dei criteri ed eliminare la necessità di tornare ai criteri quando si desidera che le modifiche siano effettive.  
9. 
    * Se ad esempio si desidera che la regola venga applicata solo ai responsabili delle vendite, è possibile creare la clausola WHERE nel modo seguente: WHERE descrizione posizione corrisponde al responsabile vendite.  È possibile utilizzare l'operatore And oppure Or in più istruzioni WHERE nella regola.  
10. Fare clic su OK.
11. Chiudere la pagina.
12. Chiudere la pagina.

## <a name="assign-rule-to-benefit"></a>Assegnare la regola al benefit
1. Andare a Risorse umane > Benefit > Benefit.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Espandere o comprimere la sezione Regole di idoneità.
5. Fare clic su Modifica.
6. Nel campo Idoneità selezionare Basato su regole.
7. Nel campo Tipo di regola fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco individuare e selezionare la regola creata in precedenza.
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Fare clic su Salva.
11. Chiudere il modulo.

