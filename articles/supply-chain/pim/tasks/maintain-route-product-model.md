--- 
title: Gestire un ciclo di lavorazione per un modello di prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2f3df2bd6018d07d65950398e38821cad475752e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-a-route-for-a-product-model"></a>Gestire un ciclo di lavorazione per un modello di prodotto

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente. Questa procedura utilizza il modello High end speaker della società di dati dimostrativi USMF per eseguire il processo.


## <a name="add-a-route-operation"></a>Aggiungere un'operazione del ciclo di lavorazione
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il modello High end speaker per questo esercizio.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione Operazioni ciclo di lavorazione.
6. Scegliere Aggiungi.
7. Digitare un valore nel campo Nome.
8. Nel campo Descrizione digitare un valore.
9. Fare clic su Salva.

## <a name="enter-route-operation-details"></a>Immettere i dettagli operazione ciclo di lavorazione
1. Fare clic su Dettagli operazione ciclo di lavorazione.
2. Nel campo Operazione immettere o selezionare un valore.
3. Nel campo Oper. N. immettere un numero.
    * I numeri di operazione determinano la sequenza del ciclo di lavorazione.  
    * Ogni proprietà di un'operazione del ciclo di lavorazione può ottenere un valore statico o essere sottoposta al mapping a un attributo. Il mapping a un attributo determinerà l'impostazione del valore come parte di configurazione.  
4. Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.
    * Il gruppo di cicli di lavorazione determina il comportamento essenziale di costi, consumo e impostazione.  
5. Fare clic sulla scheda Impostazioni.
6. Fare clic sulla scheda Tempi.
7. Nel campo Qtà lavorazione immettere un numero.
    * Determinare quante elaborazioni verranno eseguite durante un'operazione.  
8. Nel campo Ore/Ora immettere un numero.
    * Inserire il rapporto durata.  
9. Selezionare la casella di controllo Imposta.
10. Nel campo Tempo di esecuzione immettere un numero.
    * Determinare l'ora di elaborazione per la quantità specificata.  
11. Fare clic sulla scheda Requisiti risorsa.
12. Scegliere Aggiungi.
13. Nell'elenco contrassegnare la riga selezionata.
14. Nel campo Tipo di requisito selezionare un'opzione.
    * Decidere se si desidera specificare risorse o funzionalità specifiche di cui si deve disporre.  
15. Nel campo Requisito immettere o selezionare un valore.
16. Fare clic su OK.


