--- 
title: Impostare un modello di lavoro per gli ordini fornitore
description: La procedura si basa sull'impostazione di un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti.
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: aa561d558827e78529ef797b6df6dd3c1dcce34d
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Impostare un modello di lavoro per gli ordini fornitore

[!include[task guide banner](../../includes/task-guide-banner.md)]

La procedura si basa sull'impostazione di un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti. I modelli di lavoro determinano il set di istruzioni presentate all'addetto del magazzino in un dispositivo mobile quando si spostano gli articoli dall'area di ricevimento. È possibile utilizzare questa procedura con i dati indicati nella società di dati dimostrativi USMF. Prima di iniziare questa guida, creare un ID pool di lavoro. In questo esempio, viene utilizzato un ID pool di lavoro denominato Inbound. Questa procedura è destinata al responsabile del magazzino.

1. Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.
2. Nel campo Tipo ordine di lavoro selezionare "Ordini fornitori".

## <a name="create-a-work-template-header"></a>Creare un'intestazione del modello di lavoro
1. Fare clic su Nuovo.
2. Immettere un numero nel campo Numero progressivo.
    * È la sequenza secondo cui vengono valutati i modelli di lavoro. Se necessario, è possibile modificare la sequenza.  
3. Digitare un valore nel campo Modello di lavoro.
    * Identificatore univoco per il modello.  
4. Nel campo Descrizione modello di lavoro, immettere un valore.
    * L'opzione Valido non viene selezionata finché non saranno state completate tutte le informazioni necessarie per il modello e non si sarà fatto clic su Salva.  
    * Un ordine di tipo ordine acquisto non può essere elaborato automaticamente, quindi lasciare l'opzione Elabora automaticamente impostata su no.  
5. Nel campo ID pool lavoro, immettere un valore.
    * Gli ID pool di lavoro consentono di organizzare il lavoro in gruppi. Il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.  
6. Nel campo Priorità lavoro, immettere '1'.
    * Indica il livello di importanza del lavoro e il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.  
7. Fare clic su Salva.
    * È necessario salvare l'intestazione del modello di lavoro per rendere disponibile il pulsante Modifica query.  

## <a name="set-up-the-query-for-the-work-template"></a>Configurare la query per il modello di lavoro
1. Fare clic su Modifica query.
    * Verrà impostato un limite in modo che il modello possa essere utilizzato solo all'interno di un magazzino specifico.  
2. Scegliere Aggiungi.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Campo, digitare 'warehouse'.
5. Digitare un valore nel campo Criteri.
6. Fare clic su OK.
7. Fare clic su Sì.

## <a name="set-work-template-details"></a>Impostare i dettagli del modello di lavoro
1. Fare clic su Nuovo.
2. Nel campo Tipo di lavoro, selezionare 'Preleva'.
3. Nel campo ID classe lavoro, digitare 'acquisto'.
    * La classe di lavoro impostata in questo campo sarà l'impostazione predefinita in tutte le righe di lavoro di tipo prelievo create tramite questo modello. La classe di lavoro non può essere sostituita dalle righe ordine di lavoro. Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile.  
4. Fare clic su Nuovo.
5. Nel campo Tipo di lavoro selezionare "Inserisci".
6. Nel campo ID classe, digitare un valore.
    * Le istruzioni di prelievo e stoccaggio costituiscono un set. Ogni set di prelievo/stoccaggio deve avere la stessa classe di lavoro. Utilizzare la stessa classe di lavoro fornita per l'istruzione di prelievo.  
7. Fare clic su Salva.
    * Si noti che la casella di controllo Valido ora è selezionata.  


