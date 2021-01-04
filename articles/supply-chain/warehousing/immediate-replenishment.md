---
title: Rifornimento immediato
description: In questo argomento viene descritto come utilizzare il rifornimento immediato per il rifornimento del magazzino quando una direttiva ubicazione non riesce ad allocare scorte.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c69a9c9fd595280ba4f05a11409a3e672e4b1691
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431540"
---
# <a name="immediate-replenishment"></a>Rifornimento immediato

[!include [banner](../includes/banner.md)]

Il rifornimento immediato consente di rifornire il magazzino immediatamente dopo che una riga di direttiva ubicazione non è riuscita ad allocare scorte. Il rifornimento si basa su una singola riga nell'impostazione della direttiva ubicazione. Se non sono disponibili scorte nell'unità di misura specificata dalla riga, il rifornimento di tale unità di misura viene eseguito immediatamente.

Il rifornimento immediato rappresenta un'alternativa al metodo in cui l'allocazione delle scorte si base su più righe nella direttiva ubicazione e in cui la domanda viene sommata alla fine dell'allocazione e rifornita nell'unità di misura specificata dall'ultima riga della direttiva ubicazione.

I vantaggi offerti dal rifornimento immediato sono che il rifornimento può essere limitato da unità specifiche e la quantità può essere indirizzata a ubicazioni specifiche.

## <a name="business-scenario"></a>Scenario aziendale

Ad esempio, si dispone di un magazzino che ha aree di prelievo diverse per le unità di misura "scatola" e "singola unità". Si desidera ottimizzare il processo di prelievo selezionando quante più scatole possibili e successivamente selezionando la quantità rimanente che è minore di una scatola dall'area "singola unità".

In questo caso, è possibile utilizzare il rifornimento immediato. Nella direttiva ubicazione, è possibile impostare il rifornimento immediato per le scatole in modo da utilizzare il rifornimento della domanda non appena si verifica una carenza di scatole che possono essere prelevate per la quantità della domanda. In questo modo, si ottimizza il processo di prelievo in modo che il prelievo includa quante più scatole possibili. Il rifornimento immediato genererà il rifornimento delle scatole e la domanda non verrà superata cosicché le quantità verranno prelevate nell'unità di misura "singola unità". In altre parole, solo le quantità che si suppone vengano prelevate nell'unità di misura "singola unità" (vale a dire le quantità che sono minori di una scatola) verranno prelevate dall'area "singola unità". Se nell'area "scatola" si verifica una carenza, è possibile prelevare quante più scatole possibili dalla domanda totale. Le quantità rimanenti verranno prelevate dall'area "singola unità".

## <a name="where-it-applies"></a>Dove si applica

Il rifornimento immediato viene utilizzato durante l'esecuzione dell'ondata se l'allocazione ha esito negativo per una riga di direttiva ubicazione per la quale è impostato un modello di rifornimento.

## <a name="set-up-immediate-replenishment"></a>Impostare il rifornimento immediato

- Passare a **Gestione magazzino** \> **Impostazioni** \> **Direttive ubicazione**, quindi nella scheda **Righe**, nell'elenco **Modello per il rifornimento immediato**, selezionare un modello di rifornimento per la domanda di ondata.

Il modello di rifornimento viene applicato se la riga di direttiva ubicazione non riesce ad allocare un'unità di misura dedicata.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se si seleziona il rifornimento immediato per una riga di direttiva ubicazione, ma non viene generato alcun lavoro di rifornimento quando si utilizzano modelli di rifornimento della domanda per quella riga di direttiva ubicazione, possono esserci due cause:

- Assicurarsi che il modello di rifornimento della domanda applicato sia impostato in modo da utilizzare i modelli di ubicazione corretti e i modelli di lavoro del tipo **Rifornimento**.
- Assicurarsi che ci siano scorte disponibili sufficienti presso le ubicazioni in cui il modello di rifornimento della domanda cerca le scorte disponibili per il rifornimento.
