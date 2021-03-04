---
title: Stati del ciclo di vita delle unità funzionali
description: In questo argomento viene descritto come impostare gli stati delle unità funzionali e i modelli del ciclo di vita Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationLifecycleModel, EntAssetFunctionalLocationLifecycleState
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eedc21dde32671b4f5539ac4e798a8e1329c191
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431447"
---
# <a name="functional-location-lifecycle-states"></a>Stati del ciclo di vita delle unità funzionali

[!include [banner](../../includes/banner.md)]

 

In questo argomento viene descritto come impostare gli stati del ciclo di vita delle unità funzionali e i modelli del ciclo di vita Gestione cespiti. Gli stati funzionali del ciclo di vita delle unità funzionali definiscono gli stati che può avere una unità funzionale, ad esempio, creata, attiva e terminata. È possibile visualizzare tutte le unità funzionali, indipendentemente dallo stato del ciclo di vita, nella pagina elenco **Tutte le unità funzionali**. È possibile modificare lo stato di una unità funzionale selezionandola nella pagina elenco **Tutte le unità funzionali** e **Aggiorna stato dell'unità funzionale**.

## <a name="set-up-functional-location-lifecycle-states"></a>Imposta gli stati del ciclo di vita dell'unità funzionale

1. Selezionare **Gestione cespiti** > **Impostazione** > **Unità funzionali** > **Stati del ciclo di vita**.
2. Selezionare **Nuovo** per creare un nuovo stato di unità funzionale.
3. Immettere l'ID dello stato nel campo **Stato del ciclo di vita** e un nome per lo stato dell'unità funzionale nel campo **Nome**. Nel campo **Modelli del ciclo di vita**, è possibile visualizzare il numero di modelli del ciclo di vita delle unità funzionali che utilizzano lo stato dell'unità funzionale.
4. Nella Scheda dettaglio **Generale**, scegliere "Sì" sull'interruttore **Attivo** se l'unità funzionale deve essere attiva in questo stato.
5. Selezionare "Sì" sull'interruttore **Crea cespiti** se deve essere possibile creare automaticamente un cespite con lo stesso nome dell'unità funzionale e installarlo nell'unità funzionale a questo stato.  
>[!NOTE]
>Questo interruttore si riferisce al campo **Tipo di cespite** nella Scheda dettaglio **Generale** del modulo **Tipi di unità funzionali** (**Gestione cespiti** > **Impostazione** > **Unità funzionali** > **Tipi di unità funzionali**).
6. Selezionare "Sì" sull'interruttore **Rinomina ubicazione** se deve essere possibile modificare il nome dell'unità funzionale a questo stato.
7. Selezionare "Sì" sull'interruttore **Nuove ubicazioni secondarie** se deve essere possibile aggiungere nuove ubicazioi secondarie all'unità funzionale a questo stato.
8. Selezionare "Sì" sull'interruttore **Installa cespiti** se deve essere possibile installare cespiti nell'unità funzionale a questo stato.
9. Selezionare "Sì" sull'interruttore **Elimina unità funzionale** se deve essere possibile eliminare l'unità funzionale a questo stato.
10. Selezionare uno stato cespite nel campo **Stato del ciclo di vita** se si desidera che lo stato del ciclo di vita del cespite per tutti i cespiti installati nell'unità funzionale sia aggiornato automaticamente in questo stato. Esempio: Se si chiude una unità funzionale e imposta lo stato del ciclo di vita dell'unità funzionale su "Finito", può essere opportuno modificare automaticamente lo stato del ciclo di vita dei cespiti installati in tale unità funzionale su "Non in uso".


>[!NOTE]
>Gli stati del ciclo di vita, i modelli del ciclo di vita e i tipi di unità funzionali sono correlati e utilizzati nello stesso modo come stati di ciclo di vita dell'ordine di lavoro, modelli del ciclo di vita dell'ordine di lavoro e tipi di ordine di lavoro. 

## <a name="set-up-functional-location-lifecycle-models"></a>Imposta i modelli del ciclo di vita dell'unità funzionale

Una volta creati gli stati di ciclo di vita necessari per le unità funzionali, possono essere divisi in gruppi. Effettuare questa operazione per creare il flusso di modelli del ciclo di vita che può essere utilizzato per i diversi tipi di unità funzionali. Come minimo, un modello standard del ciclo di vita delle unità funzionali deve essere creato.

1. Selezionare **Gestione cespiti** > **Impostazione** > **Unità funzionali** > **Modelli del ciclo di vita**.
2. Selezionare **Nuovo** per creare un nuovo modello del ciclo di vita.
3. Immettere l'ID dello modello del ciclo di vita nel campo **Modello del ciclo di vita** e un nome per il modello del ciclo di vita nel campo **Nome**. Nei campi **Tipi di unità funzionali** e **Stati del ciclo di vita**, sarà possibile visualizzare il numero di tipi di unità funzionali che utilizza il modello del ciclo di vita e il numero degli stati selezionati nel modello del ciclo di vita.
4. Nella Scheda dettaglio **Stati del ciclo di vita**, selezionare gli stati  che devono essere inclusi nel modello. Questa operazione può essere effettuata facendo clic su uno stato nella sezione **Stati del ciclo di vita rimanenti** e facendo clic sul pulsante ![freccia in avanti](media/02-setup-for-functional-locations.png).
5. Se si desidera selezionare tutti gli stati disponibili per un modello, fare clic sul pulsante ![Seleziona tutte le fasi disponibili](media/03-setup-for-functional-locations.png). Tutti gli stati verranno trasferiti nella sezione **Stati del ciclo di vita selezionati**.
6. Se si desidera rimuovere uno stato selezionato dal modello, selezionare lo stato nella sezione **Stati del ciclo di vita selezionati** e quindi fare clic sul pulsante ![freccia Indietro](media/04-setup-for-functional-locations.png).
7. Selezionare **Aggiornamenti stati del ciclo di vita** per definire quali stati del ciclo di vita possono seguire uno stato selezionato.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]