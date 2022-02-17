---
title: Configurare Self-service dipendenti
description: In Microsoft Dynamics 365 Human Resources, è possibile configurare riquadri per la navigazione di livello superiore in Dipendente self-service.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 83718856a864123d7941b21c078bcdb96a62cca8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067581"
---
# <a name="configure-employee-self-service"></a>Configurare il dipendente self-service


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In Microsoft Dynamics 365 Human Resources, è possibile configurare configurare riquadri per la navigazione di livello superiore in **Self service dipendente**. I riquadri Piano benefit indirizzano gli utenti ai piani di benefit per i quali sono idonei.

## <a name="set-up-a-benefit-plans-tile"></a>Impostare un riquadro Piani di benefit

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.

2. Selezionare la scheda **Impostazione riquadro Piani di benefit**, quindi selezionare **Nuovo**.

3. Specifica i valori per i seguenti campi.

   | Campo | Description |
   | --- | --- |
   | **Codice tipo di piano** | Il tipo di piano visualizzato quando si seleziona questo riquadro in **Self-service benefit**. |
   | **ID riquadro** | L'identificatore univoco per il riquadro. |
   | **Testo etichetta riquadro** | Il testo che apparirà per il riquadro in **Self-service benefit**. |
   | **Descrizione** | Una descrizione del riquadro. |
   | **Immagine di sfondo riquadro** | L'URL dell'immagine da utilizzare per il riquadro (facoltativo). |
   | **Traccia iscrizioni aperte** | Seleziona questa opzione per monitorare l'avanzamento delle iscrizioni aperte per questo tipo di piano. Ad esempio, potrebbero essere presenti piani creati in cui **Tipo di piano = Altro**. Questi piani potrebbero essere piani facoltativi per i quali non si desidera monitorare lo stato di avanzamento dell'iscrizione. Se non si seleziona questo tipo di piano, i piani di queste tipologie verranno durante il monitoraggio dello stato di avanzamento o di completamento dell'iscrizione sulla scheda **Iscrizione aperta**. Questa impostazione si applica al tipo di piano selezionato per tutti i periodi e le persone giuridiche. |

4. Seleziona **Salva**.

## <a name="set-up-a-flex-credit-plan-tile"></a>Impostare un riquadro Piano di credito flessibile

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri di Dipendente self-service**.

2. Selezionare la scheda **Impostazione riquadro Piano di credito flessibile**, quindi selezionare **Nuovo**.

3. Specifica i valori per i seguenti campi.

   | Campo | Description |
   | --- | --- |
   | **ID credito benefit** | I piani del programma di credito flessibile visualizzato quando si seleziona questo riquadro in **Self-service benefit**. |
   | **ID riquadro** | L'identificatore univoco per il riquadro. |
   | **Testo etichetta riquadro** | Il testo che apparirà per il riquadro in **Self-service benefit**. |
   | **Descrizione** | Una descrizione del riquadro. |
   | **Immagine di sfondo riquadro** | L'URL dell'immagine da utilizzare per il riquadro (facoltativo). |
   | **Traccia iscrizioni aperte** | Seleziona questa opzione per monitorare l'avanzamento delle iscrizioni aperte per questo tipo di piano. Ad esempio, potrebbero essere presenti piani creati in cui **Tipo di piano = Altro**. Questi piani potrebbero essere piani facoltativi per i quali non si desidera monitorare lo stato di avanzamento dell'iscrizione. Se non si seleziona questo tipo di piano, i piani di queste tipologie verranno durante il monitoraggio dello stato di avanzamento o di completamento dell'iscrizione sulla scheda **Iscrizione aperta**. Questa impostazione si applica al tipo di piano selezionato per tutti i periodi e le persone giuridiche. |

4. Seleziona **Salva**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
