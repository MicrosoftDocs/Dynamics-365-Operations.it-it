---
title: Tipi di inventario combinati quando si utilizza il profilo di gestione banchine
description: Affinché un profilo di gestione banchine gestisca efficacemente la combinazione dell'inventario, è necessario innanzitutto impostare una suddivisione dell'intestazione del lavoro. Questa pagina spiega come eseguire tale operazione.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476752"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>I tipi di inventario vengono combinati quando si utilizza un profilo di gestione banchine

## <a name="symptoms"></a>Sintomi

Si stanno utilizzando *criteri di consolidamento della spedizione*. Si configura un *profilo di gestione banchine* per un *profilo di ubicazione*, ma quando viene creato il lavoro, i tipi di inventario vengono combinati nell'ubicazione finale.

## <a name="resolution"></a>Risoluzione

I profili di gestione banchine richiedono che il lavoro venga suddiviso in anticipo. In altre parole, il profilo di gestione banchine prevede che un'intestazione di lavoro non abbia più ubicazioni di stoccaggio.

Affinché il profilo di gestione banchine gestisca efficacemente la combinazione dell'inventario, è necessario impostare una suddivisione dell'intestazione del lavoro.

In questo esempio, il nostro profilo di gestione banchine è configurato in modo tale che il campo **Tipi di inventario che non devono essere combinati** sia impostato su *ID spedizione* e imposteremo una suddivisione dell'intestazione del lavoro:

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Selezionare **Tipo di ordine di lavoro** per modificare (ad esempio, *Ordine fornitore*).
1. Selezionare il modello di lavoro da modificare.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Aprire la scheda **Ordinamento** e aggiungere una riga con le seguenti impostazioni:
    - **Tabella** - *Transazioni lavoro temporanee*
    - **Tabella derivata** - *Transazioni lavoro temporanee*
    - **Campo** - *ID spedizione*
1. Selezionare **OK**.
1. Viene visualizzata di nuovo la pagina **Modelli di lavoro**. Nel riquadro azioni, selezionare **Suddivisioni intestazione lavoro**.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Selezionare la casella di controllo associata a **Nome campo** *ID spedizione*.
1. Nel riquadro azioni selezionare **Salva**.
