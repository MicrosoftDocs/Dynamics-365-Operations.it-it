---
title: Rettificare i livelli di scorte in magazzino (immagazzinaggio base)
description: In questa procedura viene descritto dettagliatamente il processo per creare e registrare un giornale di registrazione di rettifica magazzino in modo da rettificare i livelli di scorte dei prodotti in magazzino.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 450e95d8a4d5a216b84a3c944c6c63b4a8ad10c5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838825"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>Rettificare i livelli di scorte in magazzino (immagazzinaggio base)

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene descritto dettagliatamente il processo per creare e registrare un giornale di registrazione di rettifica magazzino in modo da rettificare i livelli di scorte dei prodotti in magazzino. È necessario disporre di un nome del giornale di registrazione magazzino configurato per le rettifiche dell'inventario prima di iniziare la procedura. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. Queste attività verranno in genere svolte da un dipendente del magazzino.


## <a name="create-an-inventory-adjustment-journal"></a>Creare un giornale di registrazione di rettifica magazzino
1. Passare a Gestione articoli > Inserimenti nel giornale di registrazione > Articoli > Rettifica magazzino.
2. Fare clic su Nuovo.
3. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul nome del giornale di registrazione di rettifica magazzino che si desidera utilizzare.
    * Alcuni campi saranno popolati in base all'impostazione del nome del giornale di registrazione di rettifica magazzino selezionato.  
5. Fare clic su OK.

## <a name="create-journal-lines"></a>Creare righe di giornale di registrazione
1. Fare clic su Nuovo.
2. Selezionare il campo del numero di articolo nell'elenco.
3. Nel campo Numero articolo selezionare un articolo. Se si utilizza la società di dati dimostrativi USMF, digitare "D0001".
4. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
5. Selezionare un sito nell'elenco.
6. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
7. Selezionare un magazzino nell'elenco.
    * Se è stato selezionato un articolo con Ubicazione come dimensione obbligatoria, è necessario specificare l'ubicazione in questo campo.  
8. Nel campo Quantità immettere un numero.
    * Nel campo del prezzo di costo viene specificato il costo per unità utilizzato per le entrate in magazzino. Se il costo non viene specificato per il numero articolo o se si desidera modificarlo manualmente, effettuarlo qui.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>Convalidare e registrare il giornale di registrazione di rettifica magazzino
1. Fare clic su Convalida.
2. Fare clic su OK.
3. Fare clic su Registra.
    * Durante la registrazione di questo tipo di giornale di registrazione viene registrata un'entrata o un'uscita dal magazzino, vengono modificati il livello e il valore delle scorte e vengono generate le transazioni contabili.  
4. Fare clic su OK.
5. Chiudere il modulo.
6. Chiudere la pagina.

