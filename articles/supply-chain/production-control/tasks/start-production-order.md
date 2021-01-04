---
title: Avviare un ordine di produzione
description: Questa procedura mostra come avviare un ordine di produzione in Controllo shop floor.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47915a93151b1adc99ddb4e3facb29bf8db49dd6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431068"
---
# <a name="start-a-production-order"></a>Avviare un ordine di produzione

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come avviare un ordine di produzione in Controllo shop floor. Il consumo di tempo e materiali è dichiarato in questo processo. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Si tratta della quinta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.


## <a name="start-a-production-order"></a>Avviare un ordine di produzione
1. Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.
    * Selezionare un ordine di produzione con stato Rilasciato.  
2. Nel riquadro azioni fare clic su Ordine di produzione.
3. Fare clic su Inizia.
    * In questa pagina, è possibile confermare l'avvio dell'ordine di produzione.  
4. Fare clic sulla scheda Generale.
5. Nel campo Da oper. N. immettere '10'.
6. Nel campo Consumo automatico ciclo di lavorazione selezionare 'Sempre'.
7. Fare clic sulla casella di controllo Registra scheda ciclo di lav. ora.
8. Nel campo Consumo DBA automatico selezionare 'Sempre'.
9. Fare clic sulla casella di controllo Registra distinta di prelievo ora.
10. Fare clic sulla casella di controllo Stampa distinta di prelievo.
11. Fare clic su OK.
    * Si tratta della distinta di prelievo stampata contenente i materiali utilizzati per l'ordine di produzione.  
12. Chiudere la pagina.

## <a name="validate-the-picking-list"></a>Convalidare la distinta di prelievo
1. Nel riquadro azioni fare clic su Visualizza.
2. Fare clic su Distinta di prelievo.
3. Nell'elenco trovare e selezionare il record desiderato.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic su Modifica.
6. Nel campo Consumo immettere un numero.
7. Fare clic su Registra.
8. Fare clic su OK.
    * Nel giornale di registrazione distinte di prelievo, i materiali consumati nell'ordine di produzione vengono registrati. Prima della registrazione del giornale di registrazione, è possibile apportare rettifiche se è presente una differenza tra la quantità stimata e la quantità effettiva.  
9. Fare clic sulla scheda GridPanel.
10. Chiudere la pagina.

## <a name="verify-the-route-card-journal"></a>Verificare il giornale di registrazione delle schede cicli di lavorazione
1. Nel riquadro azioni fare clic su Visualizza.
2. Fare clic su Scheda ciclo di lavorazione.
3. Nell'elenco trovare e selezionare il record desiderato.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic su Modifica.
6. Nel campo Ore immettere un numero.
7. Fare clic su Registra.
8. Fare clic su OK.
    * Nel giornale di registrazione schede cicli di lavorazione, il tempo trascorso sulle singole operazioni viene registrato. È possibile dichiarare anche la quantità idonea e quella difettosa.  
