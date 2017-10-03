--- 
title: Creare una previsione di base
description: "Un responsabile di pianificazione della produzione può creare una previsione di base utilizzando i modelli previsionali delle serie temporali o copiando la domanda storica."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c94a9766319531bd8285cca04003225709ce2113
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-baseline-forecast"></a>Creare una previsione di base

[!include[task guide banner](../../includes/task-guide-banner.md)]

Un responsabile di pianificazione della produzione può creare una previsione di base utilizzando i modelli previsionali delle serie temporali o copiando la domanda storica. Questa procedura illustra come copiare la domanda storica per creare una previsione di base per tutti i prodotti utilizzando una chiave di allocazione articolo. 


## <a name="set-up-an-item-allocation-key"></a>Impostare una chiave di allocazione articolo
1. Andare a Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro nel campo Nome con un valore "10".
    * La previsione della domanda viene eseguita tra le persone giuridiche. Per questo motivo è necessario impostare tutte le società per cui si desidera generare previsioni in un gruppo di pianificazione interaziendale.  
3. Nell'elenco trovare e selezionare il record desiderato.
4. Fare clic su Chiavi di allocazione articoli.
    * Selezionare tutte le chiavi di allocazione articolo per il quale si desidera creare previsioni.  
5. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare la chiave di allocazione articolo D_Aloc.  
6. Fare clic su >.
7. Chiudere la pagina.
8. Chiudere la pagina.

## <a name="set-up-the-demand-forecasting-paramters"></a>Impostare i parametri della previsione della domanda
1. Andare a Pianificazione generale > Impostazioni > Previsione della domanda > Parametri di previsione della domanda.
2. Espandere la sezione Parametri dell'algoritmo di previsione.
3. Nel campo Strategia di generazione previsione selezionare "Copia domanda storica".
4. Fare clic su Salva.

## <a name="create-a-baseline-forecast"></a>Creare una previsione di base
1. Andare a Pianificazione generale > Previsioni > Previsione della domanda > Genera previsione di base statistica.
2. Immettere una data nel campo Dal.
    * Se sono presenti ordini cliente a partire dal 1° gennaio 2015, inserire questa data. In caso negativo, immettere la prima data degli ordini cliente.  
3. Nel campo Data finale immettere una data.
    * Immettere l'ultima data degli ordini cliente, ad esempio "31-03-2015".  
4. Immettere una data nel campo Dal.
    * Immettere "01-04-2015". Questa data verrà calcolata automaticamente come data di inizio dell'intervallo di tempo di previsione.  
5. Espandere la sezione Record da includere.
6. Fare clic su Filtro.
7. Nell'elenco contrassegnare la riga selezionata.
    * Contrassegnare la riga in cui Campo = Gruppo di pianificazione interaziendale.  
8. Digitare un valore nel campo Criteri.
    * Immettere il gruppo di pianificazione interaziendale, ad esempio 10, utilizzato nella prima attività.  
9. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la riga in cui Campo = Chiave di allocazione articolo.  
10. Digitare un valore nel campo Criteri.
11. Fare clic su OK.
12. Espandere la sezione Parametri avanzati.
13. Nel campo Intervallo di tempo previsioni selezionare "Mese".
14. Nel campo Orizzonte previsione immettere "3".
15. Nel campo Intervallo temporale blocco immettere "1".
16. Fare clic su OK.

## <a name="visualize-the-demand-forecast"></a>Visualizzare la previsione della domanda
1. Andare a Pianificazione generale > Previsioni > Previsione della domanda > Previsione della domanda modificata.
2. Nella tabella della visualizzazione aggregata, selezionare la cella nella riga 1, colonna 2. È il secondo mese per il quale è stata creata la previsione.
3. Impostare QtyCell su "400".
    * Nella cella immettere un numero diverso da quello previsto, ad esempio 400.  
4. È stata effettuata una rettifica manuale alla previsione. Si noti l'indicazione grafica al passaggio successivo.
5. Fare clic su Dettagli riga previsione.
    * In questa pagina è possibile visualizzare i valori di precisione, la domanda storica e la previsione. È inoltre possibile modificare la previsione.  


