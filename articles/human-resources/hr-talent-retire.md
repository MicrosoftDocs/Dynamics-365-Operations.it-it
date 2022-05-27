---
title: Ritiro di Dynamics 365 Talent - App Attract e Onboard
description: Questo argomento descrive il ritiro di Dynamics 365 Talent - App Attract e Onboard.
author: twheeloc
ms.date: 01/27/2022
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
ms.openlocfilehash: e17b92621f05ad8483a7c578bfaece58a530df2d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692004"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Ritiro delle app Dynamics 365 Talent: Attract e Onboard


A dicembre 2019 abbiamo annunciato il ritiro dal 1 febbraio 2022 di Dynamics 365 Talent - App Attract e Onboard, offrendo ai nostri clienti due anni per pianificare.

Per ulteriori informazioni sul ritiro di queste app, vedi:
 - [Ritiro delle app Dynamics 365 Talent - Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Creazione di una forza lavoro di maggior successo con Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Continueremo a supportare Dynamics 365 Human Resources, che aiuterà i nostri clienti a ottenere le informazioni dettagliate sulla forza lavoro necessarie per creare esperienze dei dipendenti basate sui dati in più aree, come ad esempio:

- Retribuzione
- Benefit
- Congedo e assenza
- Conformità
- Payroll
- Riscontro prestazioni
- Formazione e certificazione
- Programmi self-service

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Domande sul ritiro delle app Dynamics 365 Talent

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Qual è l'esperienza utente per entrambe le app Dynamics 365 Talent - Attract e Onboard a partire dal 1° febbraio 2022?

Gli utenti non potranno utilizzare le applicazioni e vengono reindirizzati a una pagina di ritiro.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>I clienti possono continuare a esportare i dati per entrambe le app Dynamics 365 Talent - Attract e Onboard dopo il 1° febbraio 2022?
  
No, il ritiro è stato annunciato a dicembre 2019 e le funzionalità di esportazione richieste sono state fornite fino al 1° febbraio 2022. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>I dati del cliente relativi ad entrambe le app Dynamics 365 Talent - Attract e Onboard in Dataverse saranno eliminati dopo il 1 febbraio 2022?

No, le entità Dataverse rimarranno nell'ambiente Microsoft Dataverse del cliente anche dopo il ritiro, a meno che la soluzione Human Capital Management Talent non venga eliminata o disinstallata.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Conosco il nome dell'ambiente Talent. Come posso vedere i dati Attract e Onboard in Dataverse?

1.  Accedi a Power Apps: https://make.powerapps.com
2.  Seleziona l'ambiente in cui desideri visualizzare i dati Attract e Onboard.
3.  Vai a **Dataverse > Tabelle**. 
4.  Digita "msdyn_" in **Cerca**. Se vedi l'elenco delle tabelle che iniziano con "msdyn_" + nomi di tabelle (esempio: msdyn_candidate), allora hai trovato l'ambiente con i dati Attract e Onboard.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Non conosco il nome dell'ambiente Talent. Come posso trovare l'ambiente che contiene i dati per le applicazioni Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard?

1)  Accedi all'interfaccia di amministrazione di Power Platform:https://admin.powerplatform.microsoft.com/
2)  Selezionare **Ambienti**.
3)  Seleziona un ambiente specifico da valutare.
4)  Seleziona **Risorse > App Dynamics 365**.
5)  Se vedi la soluzione **HCM Talent** installata, in questo ambiente dovrebbero essere archiviati i dati Attract e Onboard. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> La soluzione **HCM Talent** viene utilizzata anche in Dynamics 365 Human Resources.
