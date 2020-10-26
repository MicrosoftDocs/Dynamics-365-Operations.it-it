---
title: Configurare un esperimento
description: In questo argomento viene descritto come configurare un esperimento in un servizio di terze parti.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0f7db0ce009f6ee7603952891aacfdc16fcde016
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930228"
---
# <a name="set-up-an-experiment"></a>Configurare un esperimento

Dopo che hai [definito un'ipotesi e determinato quali metriche desideri utilizzare](experimentation-identify.md), dovrai configurare l'esperimento nel servizio di terze parti. Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati.

[ ![Percorso utente per sperimentazione - Configurazione](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configurare l'esperimento nel servizio di terze parti
A questo punto dovresti aver scelto il servizio di terze parti per eseguire e monitorare l'esperimento e configurare il connettore di sperimentazione. Questi prerequisiti sono elencati in [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md).

Segui i passaggi necessari per creare l'esperimento nel servizio di terze parti. Se il connettore è configurato correttamente, l'elenco completo degli esperimenti che hai configurato nel servizio di terze parti sarà visualizzato in Creazione di siti Web nel giro di 5 minuti.

## <a name="set-up-your-success-metrics"></a>Configurare le metriche
Per ogni esperimento sono necessarie metriche per misurare l'impatto delle varianti e per convalidare l'ipotesi. Segui i passaggi seguenti per abilitare il calcolo delle metriche nel servizio di terze parti utilizzando eventi di telemetria in tempo reale di Dynamics 365 Commerce.

1. In Creazione di siti Web, seleziona la scheda **Pagine** nel riquadro di spostamento a sinistra e quindi seleziona la pagina per la quale desideri raccogliere metriche. 
1. Vai alla sezione **ID evento da monitorare** nel riquadro delle proprietà a destra della pagina o del modulo che desideri monitorare.
1. Seleziona **Visualizza**. Viene visualizzato un elenco di tutti gli ID evento. Copia l'evento che desideri monitorare e incolla la chiave dell'evento nella posizione designata nel servizio di terze parti. Se hai bisogno di più eventi, copia le chiavi una alla volta. 
    - Per informazioni su come visualizzare tutti gli eventi e gli attributi disponibili, comprese le visualizzazioni delle pagine e il monitoraggio delle entrate, vedi [Eventi dei componenti Commerce per diagnostica e risoluzione dei problemi](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Esegui altri passaggi per il monitoraggio delle metriche come richiesto nel servizio di terze parti.

## <a name="previous-step"></a>Passaggio precedente
[Identificare un'ipotesi e determina le metriche per un esperimento](experimentation-identify.md) 


## <a name="next-step"></a>Passaggio successivo
[Collegare e modificare un esperimento](experimentation-connect-edit.md)
