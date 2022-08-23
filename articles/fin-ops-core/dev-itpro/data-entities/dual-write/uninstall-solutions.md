---
title: Disinstallare le soluzioni di orchestrazione dell'applicazione a doppia scrittura
description: Questo articolo descrive come disinstallare le soluzioni di orchestrazione dell'applicazione a doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: fd9dc98ec1323a2ef262a330a400a6bd3833e554
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288732"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Disinstallare le soluzioni di orchestrazione dell'applicazione a doppia scrittura

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come disinstallare le soluzioni di orchestrazione dell'applicazione a doppia scrittura.

Alcuni clienti installano involontariamente il pacchetto di orchestrazione dell'applicazione a doppia scrittura che installa più soluzioni nel loro ambiente Microsoft Dataverse. L'installazione di soluzioni estranee nel pacchetto possono causare problemi indesiderati o imprevisti.

Per risolvere i problemi che sono relativi all'installazione del pacchetto di orchestrazione dell'applicazione a doppia scrittura, disinstallare le soluzioni a doppia scrittura nel seguente ordine:

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (se presente)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (per disinstallare questa soluzione devi aprire un ticket di supporto a Microsoft).
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Se le soluzioni parte e rubrica globale sono state installate, disinstallarle nel seguente ordine:

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Parte
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
