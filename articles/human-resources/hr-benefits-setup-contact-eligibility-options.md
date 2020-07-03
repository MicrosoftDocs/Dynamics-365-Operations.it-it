---
title: Configurare opzioni di idoneità per contatti personali
description: Configurare opzioni di idoneità per contatti personali in Microsoft Dynamics 365 Human Resources. I contatti personali possono essere beneficiari o persone a carico.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 68364b0cc1c579a3ee9813474c9d3f6e4df1c05d
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430764"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurare opzioni di idoneità per contatti personali

In questo articolo viene illustrato come configurare i tipi di contatti personali da utilizzare nei benefit in Microsoft Dynamics 365 Human Resources. I contatti personali possono essere beneficiari o persone a carico. 

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di idoneità per contatti personali**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Opzione di idoneità** | Un nome o codice di opzione di idoneità univoco per identificare l'opzione di idoneità. |
   | **Descrizione** | Una breve Descrizione dell'opzione di idoneità. |
   | **Codice di idoneità contatto** | Codice di sistema che descrive meglio l'opzione di idoneità personale. È possibile scegliere tra: <ul><li>Rapporto</li><li>Studente</li><li>Parte dipendente troppo anziana</li><li>Parte dipendente disabilitata troppo anziana</li></ul> |
   | **Stato** | Lo stato dell'opzione di idoneità. Se lo stato di un'opzione di idoneità è impostato su inattivo, non è possibile selezionare quell'opzione di idoneità per contatti personali. |
   | **Rapporto** | Specifica la relazione tra il contatto personale e il dipendente. Questo campo è attivo solo se il codice di idoneità del contatto è impostato su Relazione. |
   | **Età** | L'età massima di un contatto personale idoneo per il piano di benefit. Questo campo è attivo solo se si seleziona una relazione. Questa età viene confrontata all'età calcolata del contatto personale. L'età calcolata è: (data di copertura - data di nascita del contatto personale / 365). Questo numero è sempre un numero intero. |

4. Selezionare **Salva**. 
