---
title: Apportare una modifica allo stato dell'inventario per lavoro con quantità parziale
description: Questa pagina spiega come creare una voce di menu con le impostazioni appropriate per consentire ai lavoratori di modificare lo stato dell'inventario per una quantità parziale di un batch.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476718"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Abilitare la modifica dello stato dell'inventario per lavoro con quantità parziale

## <a name="symptoms"></a>Sintomi

È necessario modificare lo stato dell'inventario per una quantità parziale di un batch.

## <a name="resolution"></a>Risoluzione

Per consentire ai lavoratori di apportare questa modifica, è possibile creare una voce di menu per l'app per dispositivi mobili Gestione magazzino. Creare o modificare una voce di menu per una delle seguenti impostazioni nella pagina **Voci di menu del dispositivo mobile**:

- **Modalità:** *Lavoro*
- **Utilizza lavoro esistente:** *No*
- **Processo di creazione lavoro:** *Spostamento*
- **Visualizza stato inventario:** *Sì*

È possibile impostare altri campi nella pagina in base alle proprie esigenze.
