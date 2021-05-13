---
title: Abilitare la gestione della qualità e della non conformità
description: Questo argomento fornisce una panoramica del processo per l'impostazione e la configurazione delle funzionalità di gestione della qualità e della non conformità in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956256"
---
# <a name="enable-quality-and-nonconformance-management"></a>Abilitare la gestione della qualità e della non conformità

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica del processo per l'impostazione e la configurazione delle funzionalità di gestione della qualità e della non conformità in Microsoft Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>Abilitare la gestione della qualità e della non conformità

Segui questi passaggi per abilitare la gestione della qualità sul tuo sistema.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione articoli e magazzino**.
1. Nella scheda **Gestione qualità**, impostare l'opzione **Usa Gestione qualità** su *Sì*.
1. Nel campo **Tariffa oraria**, immettere una tariffa oraria per la manodopera nella valuta locale. La tariffa oraria viene utilizzata per calcolare i costi delle operazioni correlate a una non conformità. La tariffa oraria e i costi calcolati forniscono informazioni di riferimento per una non conformità. Non interagiscono con altre funzionalità.
1. Seleziona **Impostazione report**.
1. Aggiungere nuove righe per i vari tipi di report e selezionare il tipo di documento da utilizzare per ogni report.
1. Chiudere la pagina.
1. Chiudere la pagina.

## <a name="quality-management-configuration-process"></a>Processo di configurazione della gestione qualità

Prima di poter iniziare a utilizzare le funzionalità di gestione della qualità e generare ordini di controllo qualità, è necessario configurare il sistema e i prerequisiti. Di seguito è riportato un elenco dei passaggi necessari per configurare la gestione della qualità.

1. [Abilitare la gestione della qualità e della non conformità](#enable-qm).
1. Facoltativo: [Configurare gli strumenti di test](quality-test-instruments.md).
1. [Configurare i test](quality-tests.md).
1. [Configurare le variabili e i risultati dei test](quality-test-variables.md).
1. [Configurare i gruppi di test](quality-test-groups.md).
1. Facoltativo: [Configurare i gruppi di controllo qualità e collegarli ai prodotti](quality-groups.md).
1. Facoltativo: [Configurare le associazioni di controllo qualità](quality-associations.md).

Una volta completata la configurazione, è possibile iniziare a creare ed elaborare gli ordini di controllo qualità. Per ulteriori informazioni su come creare e utilizzare gli ordini di controllo qualità, vedere [Ordini di controllo qualità](quality-orders.md).

## <a name="nonconformance-management-configuration-process"></a>Processo di configurazione della gestione delle non conformità

Prima di poter iniziare a utilizzare le funzionalità di gestione delle non conformità e generare non conformità, è necessario configurare il sistema e i prerequisiti. Di seguito è riportato un elenco dei passaggi necessari per configurare la gestione della non conformità.

1. [Abilitare la gestione della qualità e della non conformità](#enable-qm).
1. [Configurare i lavoratori responsabili dell'approvazione delle non conformità](quality-responsible-workers.md)
1. [Configurare i tipi di problemi](quality-problem-types.md).
1. [Configurare le aree di quarantena](quality-quarantine-zones.md).
1. [Configurare i tipi di diagnostica](quality-diagnostic-types.md).
1. [Configurare le operazioni](quality-operations.md).
1. Facoltativo: [Configurare le spese di gestione qualità](quality-charges.md).

Una volta completata la configurazione, è possibile iniziare a creare ed elaborare le non conformità. Per ulteriori informazioni su come creare e utilizzare le non conformità, vedere [Creare ed elaborare le non conformità](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
