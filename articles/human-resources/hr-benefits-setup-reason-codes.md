---
title: Imposta i codici causale
description: Dynamics 365 Human Resources utilizza codici motivo per spiegare perché i benefit di un dipendente stanno cambiando.
author: twheeloc
ms.date: 08/25/2021
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
ms.openlocfilehash: 692bd5acd574492526644849fb555e5856b4463f
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323421"
---
# <a name="set-up-reason-codes"></a>Imposta i codici causale

Dynamics 365 Human Resources utilizza codici motivo per spiegare perché i benefit di un dipendente stanno cambiando.

> [!NOTE]
> A partire da gennaio 2021, i codici motivo sono stati migrati all'area di lavoro **Gestione personale** invece dell'area di lavoro **Gestione benefit**. Per ulteriori informazioni, vedi [Migrare manualmente i codici motivo alla gestione del personale](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Creare codici motivo

1. Nell'area di lavoro **Gestione personale** (o nell'area di lavoro **Gestione benefit** se i codici motivo non sono stati migrati), selezionare **Collegamenti** e quindi selezionare **Codici motivo**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Codice motivo** | Un nome univoco per identificare il motivo per cui un dipendente cambierebbe l'iscrizione a un piano di benefit. |
   | **Descrizione** | Descrizione del codice motivo. |

4. In **Scenario applicabile**, imposta **Gestione benefit** su **Sì**. Non applicabile se i codici motivo non sono stati migrati all'area di lavoro **Gestione personale**.

5. Selezionare **Salva**.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Migrare manualmente i codici motivo alla gestione del personale

A gennaio 2021, i codici motivo sono stati migrati all'area di lavoro **Gestione personale** invece dell'area di lavoro **Gestione benefit**. La maggior parte dei dati del codice motivo verrà migrata automaticamente nel tuo ambiente. Alcuni dati del codice motivo potrebbero non essere migrati. Ad esempio, i codici motivo ora hanno un massimo di 15 caratteri, quindi qualsiasi codice motivo più lungo di 15 caratteri non verrà migrato automaticamente.

Vedrai un banner nella pagina **Collegamenti** dell'area di lavoro **Gestione benefit** che ti informa sulla migrazione e se i codici motivo non sono stati migrati.

1. Seleziona **Codici motivo** per i dettagli sullo stato della migrazione.

   [![Codici motivo.](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Seleziona un codice motivo di cui la migrazione non è riuscita.

   [![Stato della migrazione del codice motivo.](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Seleziona **Migra codice motivo**.

   [![Esegui migrazione codice motivo.](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. Nel riquadro **Migrazione del codice motivo benefit**, sono disponibili due opzioni per la mappatura a un codice motivo della gestione del personale:

   - Per utilizzare un codice motivo esistente in Gestione personale, scegline uno dal menu a discesa **Utilizza codice motivo esistente**.
     > [!NOTE]
     > Puoi utilizzare un codice motivo esistente in Gestione personale solo se un altro codice motivo della gestione dei vantaggi non è già stato migrato su di esso.
   - Per creare un nuovo codice motivo in Gestione personale, immettine uno nuovo in **Nuovo codice motivo**, quindi inserisci una descrizione in **Nuova descrizione**.

   [![Associare a un codice motivo Gestione personale.](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Dopo la migrazione dei codici motivo a Gestione personale, l'opzione per utilizzarli in Gestione benefit viene automaticamente impostata su **Sì**.

[![Usa codice motivo in Gestione benefit.](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
