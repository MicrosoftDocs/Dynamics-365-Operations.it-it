---
title: Impostare un modello di lavoro per gli ordini fornitore
description: In questo argomento viene descritto come impostare un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9acf6db9138a009527c6662f1cbb7e5fedc8778
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976865"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Impostare un modello di lavoro per gli ordini fornitore

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come impostare un modello di lavoro semplice da utilizzare quando si stoccano gli articoli ricevuti. I modelli di lavoro determinano il set di istruzioni presentate all'addetto del magazzino in un dispositivo mobile quando si spostano gli articoli dall'area di ricevimento. È possibile utilizzare questa procedura con i dati indicati nella società di dati dimostrativi USMF. Prima di iniziare questa guida, creare un ID pool di lavoro. In questo esempio, viene utilizzato un ID pool di lavoro denominato Inbound. Questa procedura è destinata al responsabile del magazzino.

1. Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro**.
2. Nel campo **Tipo ordine di lavoro** selezionare **Ordini fornitori**.

## <a name="create-a-work-template-header"></a>Creare un'intestazione del modello di lavoro
1. Selezionare **Nuovo**.
2. Immettere un numero nel campo **Numero progressivo**. È la sequenza secondo cui vengono valutati i modelli di lavoro. Se necessario, è possibile modificare la sequenza.  
3. Digitare un valore nel campo **Modello di lavoro**. Identificatore univoco per il modello.  
4. Nel campo **Descrizione modello di lavoro**, immettere un valore.
    - L'opzione **Valido** non viene selezionata finché non saranno state completate tutte le informazioni necessarie per il modello e non si sarà selezionato **Salva**.  
    - Un ordine di lavoro di tipo **Ordine fornitore** non può essere elaborato automaticamente, quindi lasciare l'opzione **Elabora automaticamente** impostata su **No**.  
5. Nel campo **ID pool lavoro**, immettere un valore. Gli ID pool di lavoro consentono di organizzare il lavoro in gruppi. Il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.  
6. Nel campo **Priorità lavoro**, immettere `1`. Indica il livello di importanza del lavoro e il valore impostato in questo campo sarà l'impostazione predefinita per qualsiasi lavoro creato tramite questo modello.  
7. Selezionare **Salva**. È necessario salvare l'intestazione del modello di lavoro per rendere disponibile il pulsante **Modifica query**.  

## <a name="set-up-the-query-for-the-work-template"></a>Configurare la query per il modello di lavoro
1. Selezionare **Modifica query**. Verrà impostato un limite in modo che il modello possa essere utilizzato solo all'interno di un magazzino specifico.  
2. Selezionare **Aggiungi**.
3. Nel campo **Campo** della nuova riga, digitare `warehouse`.
4. Digitare un valore nel campo **Criteri**.
5. Selezionare **OK**.
6. Selezionare **Sì**.

## <a name="set-work-template-details"></a>Impostare i dettagli del modello di lavoro
1. Selezionare **Nuovo**.
2. Nel campo **Tipo di lavoro**, selezionare **Preleva**.
3. Nel campo **ID classe lavoro**, digitare `purchase`. La classe di lavoro impostata in questo campo sarà l'impostazione predefinita in tutte le righe di lavoro di tipo prelievo create tramite questo modello. La classe di lavoro non può essere sostituita dalle righe ordine di lavoro. Le classi di lavoro vengono utilizzate per indirizzare e/o limitare il tipo di righe ordine di lavoro che un addetto al magazzino può elaborare in un dispositivo mobile.  
4. Selezionare **Nuovo**.
5. Nel campo **Tipo di lavoro** selezionare **Inserisci**.
6. Nel campo **ID classe lavoro**, digitare un valore. Le istruzioni di prelievo e stoccaggio costituiscono un set. Ogni set di prelievo/stoccaggio deve avere la stessa classe di lavoro. Utilizzare la stessa classe di lavoro fornita per l'istruzione di prelievo.  
7. Selezionare **Salva**. Si noti che la casella di controllo **Valido** ora è selezionata.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]