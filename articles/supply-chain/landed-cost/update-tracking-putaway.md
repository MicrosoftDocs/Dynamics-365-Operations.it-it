---
title: Aggiorna tracciabilità per stoccaggio
description: Questo argomento descrive come impostare ed eseguire l'attività periodica Aggiorna tracciabilità per stoccaggio.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d2e1e4596a6052ea80d6e578dccf2564269d97444cd5b302acb5968cca2c884f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782589"
---
# <a name="update-tracking-for-put-away"></a>Aggiorna tracciabilità per stoccaggio

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

L'attività periodica *Aggiorna tracciabilità per stoccaggio* è progettata per essere eseguita come batch ricorrente notturno. Identifica quali percorsi hanno ricevuto tutte le transazioni di inventario e quali percorsi non hanno un valore per la data di fine effettiva. Quindi imposta la data di fine effettiva sulla data corrente come richiesto.

*Attività contenitore* sono create per ciascuno *scalo* di un percorso per ciascun *contenitore di spedizione*. Questi valori sono definiti dal modello di percorso selezionato quando viene creato un percorso. Per ogni record di attività del contenitore, è possibile impostare valori per i campi **Data di inizio**, **Data di fine prevista**, e **Data di fine effettiva**. Questi campi possono essere aggiornati quando si riceve la conferma che uno scalo è iniziato o è stato completato.

In genere, le informazioni relative alle date confermate vengono fornite da una terza parte, ad esempio uno spedizioniere, perché queste azioni vengono gestite al di fuori di Microsoft Dynamics 365 Supply Chain Management. Tuttavia, le informazioni di terzi non sono necessarie per tracciare l'arrivo di merci da uno scalo di percorso al magazzino (come indicato dallo stoccaggio delle merci). Pertanto, il monitoraggio può essere determinato in base alle informazioni in Dynamics 365 Supply Chain Management.

Per impostare ed eseguire l'attività periodica *Aggiorna tracciabilità per stoccaggio* segui questi passaggi:

1. Vai a **Costo di spedizione \> Attività periodiche \> Aggiorna tracciabilità per stoccaggio**.
1. Nella finestra di dialogo **Aggiorna tracciabilità per stoccaggio** nella sezione **Parametri** imposta i seguenti campi:

    - **Scalo** – Seleziona il nome/numero di identificazione univoco per la parte di un percorso per cui vuoi aggiornare la tracciabilità. Il valore selezionato deve rappresentare l'arrivo del percorso al magazzino.
    - **Attività** – Seleziona l'attività che è stata intrapresa durante lo scalo selezionato. Questi valori vengono assegnati per riga del modello di percorso nel centro di controllo tracciabilità.

1. Per limitere il set di record che devono essere inclusi nell'aggiornamento, seleziona il pulsante **Filtro** nella scheda dettaglio **Record da includere**. Viene visualizzata una finestra di dialogo di query standard, in cui puoi definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come funzionano per altri tipi di query in Supply Chain Management. I campi qui sono di sola lettura e mostrano i valori correlati alla tua query.
1. Nella Scheda dettaglio **Esegui in background**, configura le opzioni batch e di pianificazione in base alle tue esigenze, proprio come faresti per altri tipi di processi in Supply Chain Management.
1. Seleziona **OK** per applicare le impostazioni ed eseguire o pianificare l'aggiornamento.
