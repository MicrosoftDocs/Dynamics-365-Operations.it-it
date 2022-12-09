---
title: Configurare le opzioni di idoneità del contatto personale
description: Questo articolo spiega come configurare le opzioni di idoneità per i contatti personali in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/22/2022
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
ms.openlocfilehash: e3e393002901f31c035a54bd8036ed20ecdf9e00
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803886"
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
   | **Età** |Specifica l'età massima di un contatto personale idoneo per il piano di benefit. Questo campo è attivo solo se si seleziona una relazione. Questa età viene confrontata all'età calcolata del contatto personale. L'età calcolata è: (data di copertura - data di nascita del contatto personale / 365). Questo numero è sempre un numero intero.
Per l'opzione di idoneità al contatto **Personale dipendente in eccedenza**, l'età in questo campo è l'età minima. Ad esempio: se l'età è impostata su 18 anni nell'opzione **Dipendente in eccedenza**, i dipendenti contrassegnati come dipendenti in eccedenza e che hanno almeno 18 anni sarebbero coperti dall'opzione di idoneità.  |

4. Seleziona **Salva**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
