---
title: Parametri di integrazione retribuzioni
description: Questo articolo descrive i parametri di integrazione retribuzioni di Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d784909fc8c5fa05557566b62b19802cd2acece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896100"
---
# <a name="payroll-integration-parameters"></a>Parametri di integrazione retribuzioni


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Prima di utilizzare l'integrazione retribuzioni di Dynamics 365 Human Resources, è necessario impostare i parametri descritti in questo articolo.

## <a name="enable-payroll-address"></a>Abilitare l'indirizzo retribuzioni

Per poter utilizzare l'indirizzo retribuzioni, è necessario abilitarlo dal [modulo parametri condivisi](hr-setup-shared-parameters.md) nella scheda Integrazione retribuzioni.

## <a name="define-the-identification-type"></a>Definisce il tipo di identificazione

Per esporre l'ID del tipo di identificazione nell'[entità dipendente retribuzioni](hr-admin-integration-payroll-api-payroll-employee.md), è necessario [configurare i parametri di Human resources](hr-setup-shared-parameters.md) per ogni azienda.

1. Nell'area di lavoro **Gestione retribuzioni**, in collegamenti, selezionare **Parametri Risorse umane**. 
2. Nella scheda **Integrazione retribuzioni** specificare il valore dei seguenti campi.

| Campo | descrizione |
| --- | --- |
| Usa i tipi di identificazione nell'elaborazione delle retribuzioni | Quando questa opzione è selezionata, l'ID tipo selezionato verrà esposto nell'entità dipendente retribuzioni. |
| Tipo di identificazione | Il tipo di identificazione da esporre nel campo **mshr_payrollemployeeentityid** dell'[entità dipendente retribuzioni](hr-admin-integration-payroll-api-payroll-employee.md). |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
