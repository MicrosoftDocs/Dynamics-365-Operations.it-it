---
title: Definire una data di scadenza per una versione del flusso di produzione
description: Per terminare la validità e l'elaborazione di una versione del flusso di produzione in una data specifica o per pianificare la sostituzione di una versione attiva con una nuova versione, è necessario impostare una data di scadenza della versione.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa0bde90273f9392a36732ed79afdad2eea8bf86
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573213"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Definire una data di scadenza per una versione del flusso di produzione

[!include [task guide banner](../../includes/task-guide-banner.md)]

Per terminare la validità e l'elaborazione di una versione del flusso di produzione in una data specifica o per pianificare la sostituzione di una versione attiva con una nuova versione, è necessario impostare una data di scadenza della versione. Non è necessario disattivare la versione.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Impostare una data di scadenza per terminare una versione del flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare un flusso di produzione con una versione che è già definita.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Modifica.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo Data di scadenza immettere una data e un'ora.
    * Per la data di scadenza, una nuova versione non inizierà o verrà attivata. E non sarà più possibile creare o avviare processi per questo flusso di produzione. È comunque possibile completare i processi avviati dopo la data di scadenza.  

