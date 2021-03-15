---
title: Esecuzione programmata
description: In questo argomento viene descritta l'esecuzione programmata in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a6d1761202697f62421bbf288c7e22efe559a986
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022409"
---
# <a name="scheduled-execution"></a>Esecuzione programmata

[!include [banner](../../includes/banner.md)]

 

È possibile utilizzare i livelli di servizio di ordine di lavoro per impostare l'esecuzione programmata (per ulteriori informazioni sui livelli di servizio di ordine di lavoro, vedere [Descrizione e livello del servizio](service-level-and-description.md)). L'esecuzione programmata fornisce flessibilità nella pianificazione del lavoro degli addetti della manutenzione, poiché è possibile impostare requisiti più dettagliati o meno dettagliati per l'intervallo durante il quale un ordine di lavoro deve essere completato. Ad esempio, un addetto alla manutenzione che completa un processo prima del previsto in un impianto di produzione potrebbe essere in grado di passare a un altro processo pianificato per la settimana corrente ma non necessariamente per il giorno corrente. Questo approccio consente l'ottimizzazione della pianificazione del lavoratore e del completamento del processo.

La configurazione dell'esecuzione programmata, correlata agli ordini di lavoro, può essere generica o specifica. È possibile impostare righe generiche che non sono limitate a specifici tipi di ordini di lavoro, tipi di cespite e così via. In alternativa, è possibile creare righe di esecuzione programmata applicabili a uno specifico tipo di ordine di lavoro, tipo di cespite, tipo di processo di manutenzione e così via.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Esecuzione programmata**.
2. Selezionare **Nuovo** per creare una riga di esecuzione programmata.
3. Nei campi **Unità funzionale**, **Tipo di ordine di lavoro**, **Tipo di cespite**, **Produttore**, **Modello**, **Categoria tipi di processo di manutenzione**, **Tipo di processo di manutenzione**, **Variante tipi di processo di manutenzione** e **Settore**, selezionare i valori necessari.
4. Nel campo **Livello servizio**, selezionare un livello di servizio di ordine di lavoro. Se si lascia vuoto questo campo, si crea il tipo di riga di esecuzione programmata. Per un esempio di riga generica, vedere il primo record nell'illustrazione seguente. Tale riga consente la programmazione di tutti gli ordini di lavoro che non hanno alcun livello di servizio di ordine di lavoro a una data e un'ora specifiche.
5. Nel campo **Esecuzione programmata**, selezionare l'intervallo di tempo.
6. Selezionare **Salva**.

![Esecuzione programmata](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]