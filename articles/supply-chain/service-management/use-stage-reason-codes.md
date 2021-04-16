---
title: Utilizzare i codici motivo fase
description: I codici motivo vengono utilizzati per indicare il motivo dell'annullamento di un accordo sui livelli di servizio (SLA, Service Level Agreement) o il motivo del superamento del limite di tempo definito nell'accordo stesso.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 307e6b3e67de702135662e047aef00fd181d4749
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824248"
---
# <a name="use-stage-reason-codes"></a>Utilizzare i codici motivo fase 

[!include [banner](../includes/banner.md)]


I codici motivo vengono utilizzati per indicare il motivo dell'annullamento di un accordo sui livelli di servizio (SLA, Service Level Agreement) o il motivo del superamento del limite di tempo definito nell'accordo stesso.

È inoltre possibile specificare che è necessario un codice motivo quando viene risolto un contratto di servizio, o se il limite di tempo supera il tempo specificato nel contratto di servizio per l'ordine di assistenza.

Se è stato specificato che è necessario specificare un codice motivo, è necessario immettere un codice motivo nelle seguenti situazioni:

  - Quando un ordine di assistenza viene spostato in una fase durante la quale viene interrotta la registrazione delle ore a fronte dell'accordo sui livelli di servizio per l'ordine stesso.

  - Quando l'ordine di assistenza viene eliminato.

  - Quando la registrazione delle ore viene interrotta manualmente.

## <a name="set-up-reason-codes"></a>Imposta i codici causale

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Ordini di assistenza** \> **Codici motivo fase**.

2.  Nel modulo **Codici motivo fase** fare clic su **Nuovo** per creare un nuovo codice motivo fase.

3.  Nel campo **Codici motivo fase** immettere un codice motivo fase univoco.

4.  Nel campo **Descrizione** immettere una descrizione del codice motivo fase.

5.  Chiudere il modulo per salvare le modifiche.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Richiedere l'indicazione di codici motivo in caso di annullamento di un accordo sui livelli di servizio

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Parametri di gestione assistenza**.

2.  Nel modulo **Parametri di gestione assistenza**, fare clic sul collegamento **Generale** e selezionare la casella di controllo **Codice motivo per annullamento**.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Richiedere i codici motivo quando un ordine di assistenza supera il limite di tempo stabilito dall'accordo sui livelli di servizio

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Parametri di gestione assistenza**.

2.  Nel modulo **Parametri di gestione assistenza**, fare clic sul collegamento **Generale** e selezionare la casella di controllo **Codice motivo per superamento tempo massimo**.

## <a name="see-also"></a>Vedere anche

[Avviare e interrompere la registrazione dell'ora per un ordine di assistenza](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]