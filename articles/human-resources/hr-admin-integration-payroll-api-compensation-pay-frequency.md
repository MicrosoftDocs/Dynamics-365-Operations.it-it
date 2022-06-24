---
title: Frequenza della retribuzione
description: Questo articolo fornisce dettagli e una query di esempio per l'entità Frequenza della retribuzione in Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9afe27776797b2355a32226bbd7fa514b5c5d962
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894616"
---
# <a name="compensation-pay-frequency"></a>Frequenza della retribuzione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità Frequenza della retribuzione in Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpayrateconversionentity.

### <a name="description"></a>Descrizione

Questa entità fornisce informazioni sulla conversione della tariffa retributiva per una determinata frequenza della retribuzione.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **Conversione tariffa retributiva annuale**</br>mshr_annualconversionfactor</br>*Decimale* | Sola lettura | Il fattore di conversione annuale per la frequenza di pagamento. |
| **Descrizione**</br>mshr_description</br>*String* | Sola lettura | Descrizione del tasso di conversione. |
| **Conversione tariffa retributiva oraria**</br>mshr_hourlyconversionfactor</br>*Decimale* | Sola lettura | Il fattore di conversione orario per la frequenza di pagamento. |
| **Conversione tariffa retributiva mensile**</br>mshr_monthlyconversionfactor</br>*Decimale* | Sola lettura | Il fattore di conversione mensile per la frequenza di pagamento. |
| **Conversione retribuzione**</br>mshr_payrateconversion</br>*String* | Sola lettura | Una stringa univoca per identificare il tasso di conversione. |
| **Periodo**</br>mshr_period</br>*set di opzioni periodo* | Sola lettura | Il periodo principale per la conversione della tariffa retributiva specificata. |
| **Conversione tariffa retributiva settimanale**</br>mshr_weeklyconversionfactor</br>*Decimale* | Sola lettura | Il fattore di conversione mensile per la frequenza di pagamento. |
| **ID area dati**</br>mshr_dataareaid</br>*String* | Sola lettura | La persona giuridica (società). |
| **ID entità frequenza della retribuzione**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Generato dal sistema | Un valore dell'identificatore univoco globale (GUID) generato dal sistema per identificare il record in modo univoco. |

## <a name="example-query-for-payroll-employee"></a>Query di esempio per Dipendente retribuzioni

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Risposta**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
