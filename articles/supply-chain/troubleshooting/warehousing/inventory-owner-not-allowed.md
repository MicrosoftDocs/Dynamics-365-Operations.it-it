---
title: Proprietario dell'inventario non autorizzato durante l'elaborazione di movimenti
description: Potrebbe venire visualizzato l'errore "Il proprietario dell'inventario %1 non è autorizzato." I processi di gestione del magazzino supportano solo l'inventario di proprietà della persona giuridica.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476744"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>Proprietario dell'inventario non autorizzato durante l'elaborazione di movimenti nell'app magazzino

## <a name="symptoms"></a>Sintomi

Durante l'elaborazione di movimenti nell'app per dispositivi mobili Warehouse Management, è possibile che venga visualizzato il seguente messaggio di errore:

> Il proprietario dell'inventario %1 non è autorizzato in questo processo.

## <a name="cause"></a>Causa

Ciò si verifica perché la dimensione di tracciabilità **Proprietario** non è presente quando l'app per dispositivi mobili Warehouse Management viene utilizzata per effettuare gli spostamenti. Un regolare giornale di registrazione trasferimento magazzino dal client Supply Chain Management sembra funzionare come previsto e può essere registrato solo se la dimensione **Proprietario** è compilata.

## <a name="resolution"></a>Risoluzione

Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. Attualmente, i processi di gestione del magazzino supportano solo l'inventario di proprietà della persona giuridica.
