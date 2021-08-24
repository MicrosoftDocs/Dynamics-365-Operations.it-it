---
title: Risolvere i problemi relativi a report analitici
description: In questo articolo viene illustrato come procedere se le modifiche ai dati di un cliente non sono visualizzate in alcuna area di lavoro del cliente.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d4e76f3b6231b6f307173fa176360daf775c8a7950bc4ab2f2162c768102c369
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717416"
---
# <a name="troubleshoot-analytic-reports"></a>Risolvere i problemi relativi a report analitici

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

Le modifiche ai dati di un cliente non sono visualizzate nelle schede **Analisi** di alcuna area di lavoro del cliente.

**Causa**

Per impostazione predefinita, i report di Microsoft Power BI sono aggiornati ogni quattro ore, in base alla programmazione del processo batch Distribuire misura.

**Risoluzione**

Il problema potrebbe essere semplicemente una questione di tempistiche. Seguire la procedura seguente per avviare il processo batch e aggiornare le aree di lavoro di analisi.

1. Aprire la pagina **Processi batch** in **Amministrazione sistema \> Collegamenti \> Processi batch \> Processi batch**. In alternativa, utilizzare Cerca e immettere **Processi batch**.
1. Individuare il processo **Distribuire misura** nell'elenco.
1. Selezionare **Modifica** nella parte superiore della pagina e impostare la data/ora di avvio pianificata su un valore che aggiorna l'analisi più prossima all'ora corrente.

![Processi batch.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]