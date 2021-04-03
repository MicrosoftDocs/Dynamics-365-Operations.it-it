---
title: Progettare l'interfaccia di esecuzione dell'area di produzione
description: Questo argomento descrive come progettare il contenuto dell'interfaccia utente per ciascuna configurazione.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 282785799b6d61a00a356fcc2ae86ff0e3b7b39f
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501032"
---
# <a name="design-the-production-floor-execution-interface"></a>Progettare l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

È possibile progettare il contenuto dell'interfaccia utente per ciascuna configurazione utilizzata dall'interfaccia di esecuzione dell'area di produzione. Ad esempio, i lavoratori di una cella di lavoro potrebbero dover essere in grado di aprire le istruzioni di lavoro nell'area di produzione, mentre in un'altra cella di lavoro le istruzioni non sono necessarie. In tal caso, è necessario creare due configurazioni, una con un pulsante per l'apertura degli allegati dei documenti e una senza questo pulsante.

## <a name="design-a-tab"></a>Progettare una scheda

Nella pagina **Configura esecuzione area di produzione** è possibile creare e configurare le schede selezionando **Progettazione schede** nel riquadro azioni.

Ciascuna scheda è suddivisa in quattro sezioni, come mostrato nell'illustrazione seguente.

![Layout della schede](media/pfe-tab-layout.png "Layout della schede")

I seguenti elementi sono mostrati nell'illustrazione:

1. Barra degli strumenti principale
1. Barra degli strumenti secondaria
1. Visualizzazione principale
1. Visualizzazione dettagliata

Per creare e configurare una nuova scheda, effettuare le seguenti operazioni:

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.

1. Selezionare **Progettazione schede** nel riquadro azioni per aprire la pagina **Progettazione schede**.

    ![La pagina Progettazione schede](media/pfe-design-tabs.png "La pagina Progettazione schede")

1. Nel Riquadro azioni seleziona **Nuovo**.

1. Effettuare le seguenti impostazioni nell'intestazione della pagina:

    - **Nome scheda** - Specificare un nome per la scheda.
    - **Visualizzazione principale** - Selezionare tra i due elenchi di processi predefiniti (*Processi attivi*, *Tutti i processi* o *Macchina personale*).
    - **Visualizzazione dei dettagli** - Selezionare tra un valore vuoto o **Dettagli processo**. Se si seleziona il valore vuoto, non ci sarà una visualizzazione dettagliata nella scheda. Se si seleziona **Dettagli processo**, la visualizzazione dettagliata conterrà una descrizione dettagliata del processo selezionato nell'elenco dei processi nella visualizzazione principale.

1. Nella sezione **Barra degli strumenti principale** scegliere quali pulsanti devono essere disponibili nella barra degli strumenti principale. La colonna **Azioni disponibili** mostra un elenco di tutti i pulsanti che possono essere aggiunti. Le colonne **Azioni selezionate** mostrano un elenco di tutti i pulsanti inclusi nella configurazione corrente. Utilizzare i pulsanti tra le colonne per spostare gli elementi selezionati tra le colonne secondo necessità. Utilizzare i pulsanti su e giù accanto alla colonna **Azioni selezionate** per controllare l'ordine in cui i pulsanti vengono presentati nell'interfaccia utente.

1. Nella sezione **Barra degli strumenti** **secondaria** scegliere quali pulsanti devono essere disponibili nella barra degli strumenti secondaria. La colonna **Azioni disponibili** mostra un elenco di tutti i pulsanti che possono essere aggiunti. Le colonne **Azioni selezionate** mostrano un elenco di tutti i pulsanti inclusi nella configurazione corrente. Utilizzare i pulsanti tra le colonne per spostare gli elementi selezionati tra le colonne secondo necessità. Utilizzare i pulsanti su e giù accanto alla colonna **Azioni selezionate** per controllare l'ordine in cui i pulsanti vengono presentati nell'interfaccia utente.

## <a name="associate-a-tab-with-a-configuration"></a>Associare una scheda a una configurazione

Dopo aver progettato tutte le schede necessarie, è possibile associarle a una configurazione.

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.

    ![Configura esecuzione area di produzione](media/pfe-config-prod-floor-execution.png "Configura esecuzione area di produzione")

1. Nella Scheda dettaglio **Selezione scheda** selezionare **Aggiungi**.

1. Una nuova riga viene aggiunta alla griglia. Per questa nuova riga, selezionare il nome di una scheda che si desidera aggiungere alla configurazione.

1. Continuare ad aggiungere altre schede secondo necessità.

1. Utilizzare i pulsanti **Sposta su** e **Sposta giù** sulla barra degli strumenti per disporre le schede secondo necessità. Le schede verranno visualizzate da sinistra a destra nell'ordine mostrato nella schermata sopra (la scheda in alto è mostrata a sinistra).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]