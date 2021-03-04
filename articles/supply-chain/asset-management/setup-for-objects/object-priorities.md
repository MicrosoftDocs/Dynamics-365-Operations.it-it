---
title: Livelli di servizio cespiti
description: In questo argomento vengono descritti i livelli di servizio cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431056"
---
# <a name="asset-service-levels"></a>Livelli di servizio cespiti

[!include [banner](../../includes/banner.md)]

 

In questo argomento vengono descritti i livelli di servizio cespiti in Gestione cespiti. I livelli di servizio cespiti sono correlati ai cespiti e trasferiti alle richieste di intervento di manutenzione e ordini di lavoro. Vengono utilizzati per calcolare la priorità degli ordini di lavoro durante la programmazione degli ordini di lavoro. I livelli di servizio cespiti possono essere modificati, se le modifiche sono necessarie.

Per ulteriori informazioni sull'impostazione relativa al calcolo dei punteggi di valutazione per la programmazione degli ordini di lavoro, vedere [Parametri di Gestione cespiti](../setup-for-objects/enterprise-asset-management-parameters.md). È necessario impostare almeno un record predefinito per il livello di servizio cespiti. Questo record predefinito viene utilizzato se non sono presenti altre corrispondenze durante la programmazione degli ordini di lavoro.

**Esempio 1:** Il livello di servizio predefinito utilizzato se non sono presenti altre corrispondenze. In questo record, si seleziona solo un livello di servizio.

**Esempio 2:** un livello di servizio elevato utilizzato per la programmazione dei processi per un camion Volvo. In questo record, si selezionare un tipo di cespite pertinente (ad esempio **Camion**), un produttore (**Volvo**) e un livello di servizio.

## <a name="set-up-asset-service-levels"></a>Impostare i livelli di servizio cespiti

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Livelli di servizio cespiti**.
2. Selezionare **Nuovo** per creare un record.
3. A seconda del livello di dettaglio necessario per il livello di servizio cespiti, selezionare opzioni appropriate nei campi **Unità funzionale**, **Tipo di cespite**, **Produttore**, **Modello**, **Cespite**, **Tipo di ordine di lavoro** e **Livello servizio**.

    > [!NOTE]
    > Quando il livello di servizio cespiti viene utilizzato per le richieste di intervento di manutenzione e gli ordini di lavoro, Gestione cespiti analizza tutti i record di livello di servizio cespiti per verificare la presenza di una corrispondenza possibile. Controlla sempre la combinazione più specifica per prima. In altre parole, Gestione cespiti controlla prima **Tipo di ordine di lavoro** per trovare una corrispondenza. Se non trova corrispondenza, controlla **Cespite** e così via. Come si vede nel layout della pagina **Livelli di servizio cespiti**, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza. Se non viene trovata alcuna corrispondenza, il record predefinito senza selezioni in quei campi viene utilizzato.

4. Nel campo **Livello servizio**, selezionare un numero che indica il livello di servizio (priorità).


> [!NOTE]
> Se si modifica un record di livello di servizio cespiti nella pagina **Livelli di servizio cespiti** dopo che è stato già utilizzato in un ordine di lavoro, il livello di servizio per le richieste di intervento di manutenzione e ordini di lavoro non verrà aggiornato di conseguenza.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]