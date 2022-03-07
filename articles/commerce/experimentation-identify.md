---
title: Identificare un'ipotesi e determinare le metriche per un esperimento
description: In questo argomento viene descritto come identificare l'ipotesi e le metriche per un esperimento che eseguirai in un sito Web di e-commerce in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91614cda804cae4574fce4c9cfb31c63d876f19b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238632"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Identificare un'ipotesi e determinare le metriche per un esperimento
La prima fase del ciclo di vita della sperimentazione include l'identificazione dell'ipotesi per l'esperimento e la determinazione delle metriche da monitorare per valutare l'esito positivo dell'esperimento. Il diagramma seguente mostra tutti i passaggi relativi alla [configurazione e all'esecuzione di un esperimento](experimentation-overview.md) su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati. 

[ ![Percorso utente per sperimentazione - Identificazione](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

Un'ipotesi è un'asserzione in cui prevedi il risultato dell'esperimento. Molti fattori contribuiscono alla definizione di un'ipotesi, ad esempio la ricerca sul comportamento degli utenti e sui dati del sito Web raccolti. Con l'ipotesi, definirai l'assunto o la teoria che vuoi convalidare con l'esperimento. Un esempio di ipotesi per l'esperimento potrebbe essere "*un'immagine di una t-shirt bianca sulla mia home page genererà una percentuale di clic più alta rispetto a un maglione blu scuro durante i mesi estivi poiché le persone vogliono indossare qualcosa di leggero e di colore chiaro in estate.*" In tal caso, creerai varianti che includono una t-shirt bianca e un maglione blu scuro e pubblicherai entrambi contemporaneamente.

Per convalidare un'ipotesi, l'esito positivo o negativo di un esperimento dovrebbe essere direttamente associato alle azioni dell'utente; ad esempio, se l'utente del sito web fa clic su un collegamento o un pulsante. Queste azioni devono corrispondere agli eventi che verranno segnalati al servizio di terze parti che monitora l'esperimento. Nel tempo, la percentuale di utenti che intraprendono l'azione verrà conteggiata come metrica che puoi utilizzare per generare rapporti e condurre analisi. Per esaminare tutti gli eventi e gli attributi disponibili vedere [Eventi dei componenti Commerce per la diagnostica e la risoluzione dei problemi](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).

## <a name="previous-step"></a>Passaggio precedente
[Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md)


## <a name="next-step"></a>Passaggio successivo
[Configurare un esperimento](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]