---
title: Risolvere i problemi relativi a report analitici
description: In questo articolo viene illustrato come procedere se le modifiche ai dati di un cliente non sono visualizzate in alcuna area di lavoro del cliente.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b500d519d61edfd20456355376e3fc81f16517a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794975"
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

![Processi batch](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]