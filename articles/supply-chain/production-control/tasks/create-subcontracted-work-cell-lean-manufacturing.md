---
title: Creare una cella di lavoro in conto lavoro per la lean manufacturing
description: Per modellare un'attività in conto lavoro per la lean manufacturing, è necessario creare una cella di lavoro associata al fornitore che esegue il lavoro.
author: johanhoffmann
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f37a38227ef57e6e66a77e90883bf157792e7f81
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576834"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Creare una cella di lavoro in conto lavoro per la lean manufacturing

[!include [banner](../../includes/banner.md)]

Per modellare un'attività in conto lavoro per la lean manufacturing, è necessario creare una cella di lavoro associata al fornitore che esegue il lavoro. Una cella di lavoro in conto lavoro è collegata al fornitore tramite l'associazione di una risorsa di tipo fornitore. Se si esegue questa registrazione nella società dimostrativa USMF, è possibile selezionare il conto fornitore con ID 1002 e il sito 1.


## <a name="create-a-vendor-resource"></a>Creare una risorsa fornitore
1. Fare clic su Risorse.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Risorsa.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo selezionare "Fornitore".
6. Nel campo Fornitore fare clic sul pulsante a discesa per aprire la ricerca.

## <a name="create-the-resource-group"></a>Creare il gruppo di risorse
1. Fare clic su Gruppo di risorse.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo di risorse.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il sito a cui la cella di lavoro deve essere allocata. In teoria, un sito può rappresentare un singolo sito in cui opera un fornitore. Tuttavia, nella maggior parte dei casi, le risorse in conto lavoro vengono inserite solo nel sito che ordina il conto lavoro. Si noti che i magazzini in ingresso e in uscita delle celle di lavoro in conto lavoro devono essere nello stesso sito.  
6. Digitare un valore nel campo Sito.
7. @SysTaskRecorder:_RequestClose
8. Selezionare o deselezionare la casella di controllo Cella di lavoro.
9. Nel campo Magazzino di input fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il magazzino e l'ubicazione utilizzati per conservare il materiale per la cella di lavoro gestita dal fornitore. In molti casi, il magazzino e l'ubicazione sono modellati utilizzando un magazzino separato per il fornitore e un'ubicazione per la cella di lavoro.  
10. Nel campo Ubicazione di input fare clic sul pulsante a discesa per aprire la ricerca.
11. Nel campo Magazzino di output fare clic sul pulsante a discesa per aprire la ricerca.
    * Definire il magazzino e l'ubicazione in cui il materiale viene registrato quando le attività in conto lavoro della cella di lavoro vengono registrate. Il magazzino e l'ubicazione possono trovarsi nel sito del fornitore se quest'ultimo dichiara il processo kanban. In alternativa, il magazzino e l'ubicazione possono essere l'ubicazione di ricevimento associata al passaggio successivo del flusso di produzione.  
12. Nel campo Ubicazione di output fare clic sul pulsante a discesa per aprire la ricerca.
13. Espandere o comprimere la sezione Calendari.
14. Scegliere Aggiungi.
15. Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.
    * Associare il calendario lavorativo della cella di lavoro al gruppo di risorse. Per le risorse importanti, si consiglia di definire calendari specifici che rappresentano gli orari di lavoro esatti e le funzioni correlate del sito del fornitore o della cella di lavoro.  
16. Espandere o comprimere la sezione Risorse.
17. Scegliere Aggiungi.
    * Un gruppo di risorse in conto lavoro deve disporre di una risorsa associata di tipo fornitore che collega il gruppo di risorse al conto fornitore.  
18. Nel campo Risorsa fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare o immettere la risorsa fornitore creata nella sottoattività precedente.  
19. Espandere o comprimere la sezione Capacità cella di lavoro.
20. Scegliere Aggiungi.
    * Una cella di lavoro deve avere una capacità definita. In questo esempio verrà creata una capacità di produttività di 100 pezzi per giorno lavorativo standard.  
21. Nel campo Modello di flusso di produzione fare clic sul pulsante a discesa per aprire la ricerca.
22. Selezionare un'opzione nel campo Periodo di capacità.
23. Nel campo Quantità di produttività media, immettere un numero.
24. Nel campo Unità fare clic sul pulsante a discesa per aprire la ricerca.
25. ResolveChanges per l'unità.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]