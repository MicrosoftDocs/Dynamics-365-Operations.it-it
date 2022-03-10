---
title: Tipo di congedo
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Tipo di congedo in Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dced58e6e9f6c20578e4582e4cf39162622713e7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069909"
---
# <a name="leave-type"></a>Tipo di congedo


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Tipo di congedo per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni per un determinato tipo di congedo.

Nome fisico: mshr_essleavetypeentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID tipo di congedo**</br>mshr_leavetypeid</br>*String* | Sola lettura | ID tipo di congedo. |
| **Descrizione**</br>mshr_description</br>*String* | Sola lettura | Descrizione di un tipo di congedo. |
| **Categoria**</br>mshr_category</br>*Set di opzioni mshr_LeaveTypeCategory* | Sola lettura | Categoria tipo di congedo. |
| **Codice motivo obbligatorio**</br>mshr_isreasoncoderequired</br>*Set di opzioni mshr_NoYes* | Sola lettura | Definisce se è richiesto un codice motivo per il tipo di congedo. |
| **Unità congedo**</br>mshr_leaveamountunit</br>*Set di opzioni mshr_LeaveAmountUnit* | Sola lettura | Unità di questo tipo di congedo. |
| **Abilita mezza giornata**</br>mshr_enablehalfdaydefinition</br>*Set di opzioni mshr_NoYes* | Definisce se è abilitata la mezza giornata per il tipo di congedo. |
| **ID area dati**</br>mshr_dataareaid_id</br>*String* | Sola lettura | Specifica la persona giuridica (società). |
| **Entità tipo di congedo**</br>mshr_essleavetypeentityid</br>*GUID* | Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il tipo di congedo. |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Risposta**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
