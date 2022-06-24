---
title: Integrare Dynamics 365 Supply Chain Management (gestione cespiti) con Dynamics 365 Guides
description: Questo articolo spiega come integrare il modulo Gestione cespiti in Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides per trarre vantaggio dalle guide alla realtà mista nei flussi di lavoro quotidiani di assistenza e manutenzione.
author: johanhoffmann
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: d06978bcbd6205111384f5c7cefdf34fdbdbfbf5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875686"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Integrare Dynamics 365 Supply Chain Management (gestione cespiti) con Dynamics 365 Guides

[!include [banner](../includes/banner.md)]

È possibile integrare il modulo **Gestione cespiti** in Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides per trarre vantaggio dalle guide alla realtà mista nei flussi di lavoro quotidiani di assistenza e manutenzione. Se una guida è associata a un ordine di lavoro Gestione cespiti, un lavoratore che apre l'elenco di controllo di manutenzione dell'ordine di lavoro nell'app mobile Supply Chain Management (Dynamics 365) vede che è disponibile una guida. Il lavoratore può quindi trovare e aprire la guida nell'app Dynamics 365 Guides HoloLens.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter allegare guide agli ordini di lavoro di Gestione cespiti, è necessario completare questi prerequisiti:

- [Configurare Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) versione 10.0.9 o successiva.
- [Attivare la doppia scrittura per le app Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Attivare l'anterprima](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) per la funzionalità **MRGuidesFeature**. Per gli ambienti di produzione, è prima necessario inviare un ticket di supporto affinché un tenant possa essere aggiunto al gruppo di versioni di anteprima.
- [Attivare le seguenti chiavi di configurazione](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) nella pagina **Configurazione licenza**:

    - Gestione cespiti \> Realtà mista gestione cespiti
    - Realtà mista \> Guida alla realtà mista

- [Configurare Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versione 200.0.0.96 o successiva.

## <a name="use-dynamics-365-guides-with-asset-management"></a>Utilizzare Dynamics 365 Guides con Gestione cespiti

Per associare una guida, utilizzare una riga dell'elenco di controllo di manutenzione in Gestione cespiti. È possibile creare l'associazione tramite un modello di elenco di controllo di manutenzione, un tipo di processo di manutenzione o un ordine di lavoro, poiché tutti e tre contengono righe dell'elenco di controllo di manutenzione. È possibile risparmiare tempo utilizzando un modello, in quanto può essere associato a tutti i tipi di processi di manutenzione che lo utilizzano. Ad esempio, una guida associata a un tipo di processo di manutenzione viene automaticamente associata a tutti gli ordini di lavoro che specificano quel tipo di processo. D'altra parte, una guida associata direttamente a un ordine di lavoro esiste solo per tale ordine di lavoro.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Associare una guida a un modello di elenco di controllo di manutenzione

Per associare una guida a un modello di elenco di controllo di manutenzione, attenersi alla seguente procedura.

1. Creare una guida usando le app per PC Dynamics 365 Guides e HoloLens. Per informazioni sulla creazione di una guida, vedere gli articoli seguenti:

    - [Utilizzare l'app per PC per creare una guida](/dynamics365/mixed-reality/guides/pc-app-overview)
    - [Utilizzare l'app HoloLens per posizionare gli ologrammi](/dynamics365/mixed-reality/guides/hololens-app-overview)

1. In Supply Chain Management [creare un modello di elenco di controllo di manutenzione](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. Associare la guida creata con una riga dell'elenco di controllo di manutenzione nel nuovo modello di elenco di controllo di manutenzione:

    1. Nella Scheda dettaglio **Righe elenco di controllo di manutenzione** selezionare la riga a cui si desidera associare la guida.
    1. Nella scheda dettaglio **Guide associate** selezionare **Aggiungi guida**.

        ![Associare una guida a una riga di elenco di controllo di manutenzione.](media/am-guides-integration-add-guide.png "Associare una guida a una riga di elenco di controllo di manutenzione")

    1. Nel campo **Nome** selezionare una guida, quindi selezionare **Salva**.

        ![Selezionare una guida nel campo Nome.](media/am-guides-integration-select-guide.png "Selezionare una guida nel campo Nome")

1. Associare il modello di elenco di controllo di manutenzione a un tipo di processo:

    1. [Creare un tipo di processo di manutenzione](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) o selezionare un tipo di processo di manutenzione esistente.
    1. Nel riquadro azioni selezionare **Valori predefiniti tipo di processo di manutenzione**.

        ![Pulsante Valori predefiniti tipo di processo di manutenzione.](media/am-guides-integration-job-defaults.png "Pulsante Valori predefiniti tipo di processo di manutenzione")

    1. Creare una riga, quindi selezionare **Salva**.

        ![Crea una riga.](media/am-guides-integration-add-line.png "Creare una riga")

    1. Nel riquadro azioni selezionare **Elenco di controllo di manutenzione**.

        ![Pulsante Elenco di controllo di manutenzione.](media/am-guides-integration-maintenance-checklist.png "Pulsante Elenco di controllo di manutenzione")

    1. Nella Scheda dettaglio **Righe elenco di controllo di manutenzione** aggiungere una riga e quindi modificare il valore del campo **Tipo** in **Modello**.

        ![Modificare il valore Tipo.](media/am-guides-integration-checklist-lines.png "Modificare il valore Tipo")

    1. Nella Scheda dettaglio **Dettagli riga** selezionare nel campo **Modello** il modello a cui è stata associata la guida, quindi selezionare **Salva**.

        ![Selezionare il modello.](media/am-guides-integration-checklist-line-details.png "Selezionare il modello")

1. [Creare un ordine di lavoro](work-orders/manually-created-workorders.md#create-work-order), quindi selezionare il tipo di processo di manutenzione che utilizza il modello di elenco di controllo di manutenzione a cui è stata associata la guida. La guida viene automaticamente associata all'ordine di lavoro.

    ![Selezionare un tipo di processo di manutenzione.](media/am-guides-integration-create-work-order.png "Selezionare un tipo di processo di manutenzione")

1. Visualizzare la guida associata all'ordine di lavoro e ai lavoratori.

    1. Aprire [Area di lavoro mobile di gestione cespiti](asset-management-mobile-workspace.md) per accedere all'ordine di lavoro.
    1. [Aprire l'elenco di controllo di manutenzione](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) per l'ordine di lavoro.
    1. Selezionare una riga dell'elenco di controllo per visualizzare la guida associata.

        ![Guida associata a una riga dell'elenco di controllo.](media/am-guides-integration-show-guide.png "Guida associata a una riga dell'elenco di controllo")

    1. Aprire la guida in HoloLens.

        ![Aprire la guida in HoloLens.](media/am-guides-integration-hololens-select.png "Aprire la guida in HoloLens")

> [!NOTE]
> È inoltre possibile associare una guida direttamente all'elenco di controllo di manutenzione di un ordine di lavoro o di un tipo di processo.

> [!IMPORTANT]
> Esiste un problema noto a causa del quale quando si associa un modello di elenco di controllo di manutenzione a un tipo di processo di manutenzione predefinito, la guida collegata al modello non viene visualizzata nella Scheda dettaglio **Guide associate** della pagina **Valori predefiniti per il tipo di processo di manutenzione**. La guida verrà tuttavia visualizzata dopo l'applicazione del tipo di processo a un ordine di lavoro nella Scheda dettaglio **Guide associate**.

## <a name="see-also"></a>Vedere anche

- [Panoramica della doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Panoramica della gestione cespiti](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]