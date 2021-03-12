---
title: Diritti di accesso per i controller oggetto di costo
description: Di seguito vengono descritti i diritti di accesso per i controller oggetto di costo.
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 68fc97ed27460ac0a2bee9c10cb9bda67d506e78
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978891"
---
# <a name="access-rights-for-cost-object-controllers"></a>Diritti di accesso per i controller oggetto di costo

[!include [banner](../includes/banner.md)]

L'area di lavoro **Controllo costi** è un punto centrale in cui i responsabili possono visualizzare le prestazioni degli oggetti di costo. Questa area di lavoro consente ai responsabili di utilizzare i dati di contabilità industriale anche se non sono contabili. Per motivi di sicurezza, i responsabili devono poter visualizzare solo i dati della contabilità industriale correlati agli oggetti di costo specifici di cui sono responsabili.

Sono disponibili quattro ruoli specifici nella contabilità industriale.

| Nome ruolo               | Licenza      |
|-------------------------|--------------|
| Responsabile contabilità industriale | Attività     |
| Contabile         | Operations   |
| Addetto contabilità   | Operations   |
| Controller oggetto di costo  | Membri del team |

In questo argomento viene descritto come assegnare il ruolo **Controller oggetto di costo** a un responsabile.

Quando il ruolo **Controller oggetto di costo** viene assegnato a un responsabile, il responsabile può effettuare le seguenti attività:

- Accedere all'area di lavoro **Controllo costi** nel client.

    - Eseguire il drill-through e avere l'accesso in lettura alle pagine che supportano l'esperienza drill-through.

- Accedere all'area di lavoro **Controllo costi** nell'applicazione mobile.

> [!NOTE]
> Il ruolo **Controller oggetto di costo** non verifica per quale oggetti di costo l'utente può accedere e visualizzare i dati. La sicurezza a livello di riga viene fornita tramite le gerarchie di dimensioni e la gerarchia dell'elenco accessi.

## <a name="grant-access-rights"></a>Concedere i diritti di accesso
Nel seguente esempio viene illustrato cosa è una gerarchia di dimensioni.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione    | Nome tipo di gerarchia dimensioni      | Gerarchia elenco accessi |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizzazione             | Centri di costo | Gerarchia classificazioni dimensione | **Sì**               |

È possibile utilizzare la scheda dettaglio **Utenti** nella finestra di progettazione della gerarchia per inserire una o più ID utente in ogni nodo.

|                                   | Utenti            | Intervalli membro di dimensione   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| **Nodi**                         | **ID utente**      | **Membro di dimensione di inizio** | **Membro di dimensione di fine** |
| Organizzazione                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Amministratore                 | aprile            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Dati finanziari   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Risorse umane        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produzione            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Imballaggio | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblaggio  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> I contabili devono essere assegnati al primo livello della gerarchia, in modo che possano visualizzare tutte le voci della contabilità industriale.

Prima che la gerarchia dell'elenco accessi e le impostazioni di sicurezza possano essere applicate, l'opzione **Abilita accesso in visualizzazione per membri di dimensione oggetto di costo** deve essere impostata su **Sì** nella scheda **Generale** della pagina **Parametri di contabilità industriale** (**Contabilità industriale** > **Impostazione** > **Parametri**).

Le impostazioni per la gerarchia dell'elenco accessi vengono utilizzate per controllare i dati visualizzati nelle seguenti aree:

- Area di lavoro **controllo costi** nel client:

    - Dati delle pagine utilizzate per il drill-through

- Area di lavoro **Controllo costi** nell'applicazione mobile:

    - Saldi nelle schede

- Microsoft Power BI:

    - Data visualizzati nelle visualizzazioni di Power BI
    - Le visualizzazioni dei dati di Power BI sono incorporate nel client Dynamics 365 Finance

> [!IMPORTANT]
> - Prima che la gerarchia dell'elenco accessi possa influire sui dati in Power BI, la gerarchia dell'elenco accessi e la sicurezza a livello di riga in Power BI devono essere abbinate. Per ulteriori informazioni, vedere [Impostare la sicurezza del pacchetto di contenuti per la contabilità industriale](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - In questo argomento vengono illustrati i prerequisiti che devono essere definiti prima di poter utilizzare l'area di lavoro **Controllo costi**.

Risorse aggiuntive

- [Area di lavoro controllo costi](cost-control-workspace.md)
- [Gerarchia dimensioni](dimension-hierarchy.md)
- [Impostare la sicurezza per il pacchetto di contenuti della contabilità industriale](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
