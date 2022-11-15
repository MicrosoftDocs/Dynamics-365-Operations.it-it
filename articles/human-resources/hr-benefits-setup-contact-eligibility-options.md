---
title: Configurare le opzioni di idoneità del contatto personale
description: Questo articolo spiega come configurare le opzioni di idoneità per i contatti personali in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 251a12b0da364744f1d8c84324099708a2f816a1
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749284"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurare le opzioni di idoneità del contatto personale


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In questo articolo viene illustrato come configurare i tipi di contatti personali da utilizzare nei benefit in Microsoft Dynamics 365 Human Resources. I contatti personali sono le persone che saranno coperte dai tuoi piani (persone a carico) o che beneficeranno dei tuoi piani (beneficiari). Le persone a carico sono in genere coniugi o figli. I beneficiari possono essere coniugi, figli, trust o genitori.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Opzioni di idoneità per contatti personali**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Opzione di idoneità** | Un nome o codice di opzione di idoneità univoco per identificare l'opzione di idoneità. |
   | **Descrizione** | Una breve descrizione dell'opzione di idoneità. |
   | **Codice di idoneità contatto** | Codice di sistema che descrive meglio l'opzione di idoneità personale. È possibile scegliere tra: <ul><li>Rapporto</li><li>Studente</li><li>Parte dipendente troppo anziana</li><li>Parte dipendente disabilitata troppo anziana</li></ul> |
   | **Stato** | Lo stato dell'opzione di idoneità. Se lo stato di un'opzione di idoneità è impostato su inattivo, non è possibile selezionare quell'opzione di idoneità per contatti personali. |
   | **Rapporto** | Specifica la relazione tra il contatto personale e il dipendente. Questo campo è attivo solo se il codice di idoneità del contatto è impostato su Relazione. |
   | **Età** | L'età minima di un contatto personale idoneo per il piano di benefit. Questo campo è attivo solo se si seleziona una relazione. Questa età viene confrontata all'età calcolata del contatto personale. L'età calcolata è: (data di copertura - data di nascita del contatto personale / 365). Questo numero è sempre un numero intero. |

4. Selezionare **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
