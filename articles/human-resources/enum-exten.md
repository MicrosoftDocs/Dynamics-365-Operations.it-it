---
title: Estendibilità dell'enumerazione di base del sesso
description: In questo articolo viene fornita una panoramica dell'estendibilità dell'enumerazione di base del sesso (enum).
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749315"
---
# <a name="gender-base-enum-extensibility"></a>Estendibilità dell'enumerazione di base del sesso

L'enumerazione di **Sesso** (enum) è ora estendibile. In questo articolo vengono descritte le modifiche che è necessario apportare alla base di codice se prevedi di estendere l'enumerazione **Sesso**.

## <a name="gender-vs-hcmpersongender"></a>Sesso rispetto a HcmPersonGender

Esistono due enumerazioni per i valori di sesso:

- **Sesso** (piattaforma dell'applicazione)
- **HcmPersonGender** (PersonnelManagement)

L'enumerazione **Sesso** è utilizzata in tutto Microsoft Dynamics 365 Finance, mentre **HcmPersonGender** è specifica della funzionalità di gestione del capitale umano (HCM). Se stai utilizzando la funzionalità HCM e apporti modifiche all'enumerazione **Sesso**, è cosnigliabile considerare di apportare le stesse modifiche a **HcmPersonGender**. Ad esempio, se aggiungi **Transgender** all'enumerazione **Sesso**, aggiungi **Transgender** anche all'enumerazione **HcmPersonGender**.

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (Classe)

Una nuova classe **HcmPersonGenderTranformUtil** è stata creata per consentire la conversione tra i due enumeratori di base. In questa classe ci sono due metodi: **convertGenderToHcmPersonGender** e **convertHcmPersonGenderToGender**. È consigliabile creare un'estensione usando la classe **Catena di comando** classe o **gestori evento** ed estendere entrambi i metodi per eseguire il mapping dei nuovi valori che vengono aggiunti a una delle enumerazioni di base.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (Classe)

**PayrollStateWageTaxPrepDP** è la classe del provider di dati per il report di SQL Server Reporting Services (SSRS) **Preparazione dell'imposta sul salario statale sui salari** . Per gli Stati Uniti sono disponibili tre valori: **Maschio**, **Femmina** e **Non specificato**. Nel metodo **populatePayrollStateWageTaxPrepTmp**, c'è un'istruzione switch che viene utilizzata per eseguire il mapping del valore dell'enumerazione **HcmPersonGender** in uno dei tre campi: **IsMale**, **IsFemale** o **IsUnspecifiedGender**. Il valore predefinito per l'istruzione switch è **IsUnspecifiedGender**. Se aggiungi dei valori all'enumerazione **HcmPersonGender** per eseguire il mapping in modo diverso, è necessario creare un'estensione utilizzando la classe **Catena di comando** sopra il metodo **populatePayrollStateWageTaxPrepTmp** per modificare il valore in base alle esigenze.

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (Class)

La classe di integrazione **smmOutlookSync_Contact** collega i valori da e verso **Outlook** e **Contatti**. **Outlook** supporta tre valori: **Maschio**, **Femmina** e **Non specificato**. La classe ha due metodi per aiutarti a eseguire il mapping di **Sessi** a **OutlookGenders**. Il metodo predefinito **NonSpecific/UnSpecified**. Se crei altri valori per l'enumerazione **Sesso**, è consigliabile creare un'estensione utilizzando la classe **Catena di comando** su entrambi i metodi ed eseguire il mapping in base alle esigenze.
