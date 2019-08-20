---
title: Crea cicli di lavorazione (febbraio 2016)
description: Questa attività consente di creare i cicli di lavorazione produzione per un prodotto finito e un prodotto semilavorato.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5aa7db4ed66e7201d8d480d948a4249e43febde7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844563"
---
# <a name="create-routes-february-2016"></a>Crea cicli di lavorazione (febbraio 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa attività consente di creare i cicli di lavorazione produzione per un prodotto finito e un prodotto semilavorato. Corrisponde alla quinta attività della serie di calcoli DBA. La società di dati dimostrativi utilizzata per creare questa attività è USMF.


## <a name="create-a-route-for-a-semi-finished-product"></a>Creare un ciclo di lavorazione per un prodotto semilavorato
1. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare il numero dell'articolo BOM_2.  
3. Nel riquadro azioni fare clic su Progettazione.
4. Fare clic su Ciclo di lavorazione.
5. Fare clic su Nuovo.
6. Fare clic su Ciclo di lavorazione e versione del ciclo di lavorazione.
7. Nel campo Descrizione digitare un valore.
    * Per questo esempio, digitare ROUTE_2.  
8. Nel campo Sito immettere o selezionare un valore.
    * Per questo esempio, immettere o selezionare Site 1.  
9. Fare clic su OK.
10. Fare clic su Nuovo.
11. Nel campo Operazione immettere o selezionare un valore.
    * Per questo esempio, selezionare Assembly.  
12. Nel campo Tempo di esecuzione immettere un numero.
    * Ad esempio, digitare 1. Il tempo di esecuzione spesso fa parte del prezzo calcolato per un articolo.  
13. Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.
    * Per questo esempio, selezionare Std.  
14. Fare clic sulla scheda Impostazioni.
15. Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.
    * Per questo esempio, selezionare Assembly.  
16. Fare clic sulla scheda Tempi.
17. Nel campo Tempo di attrezzaggio immettere un numero.
    * Per questo esempio, digitare 1. Il tempo di impostazione spesso fa parte del prezzo calcolato per un articolo.  
18. Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.
19. Fare clic su Approva.
20. Selezionare Sì nel campo Approvare anche il ciclo di lavorazione? .
21. Fare clic su OK.
22. Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.
23. Fare clic su Attiva.
24. Chiudere la pagina.
25. Chiudere la pagina.

## <a name="create-a-route-for-a-finished-product"></a>Creare un ciclo di lavorazione per un prodotto finito
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare il numero dell'articolo BOM_1.  
2. Nel riquadro azioni fare clic su Progettazione.
3. Fare clic su Ciclo di lavorazione.
4. Fare clic su Nuovo.
5. Fare clic su Ciclo di lavorazione e versione del ciclo di lavorazione.
6. Nel campo Descrizione digitare un valore.
    * Per questo esempio, digitare ROUTE_1.  
7. Nel campo Sito immettere o selezionare un valore.
    * Per questo esempio, immettere o selezionare Site 1.  
8. Fare clic su OK.
9. Fare clic su Nuovo.
10. Nel campo Operazione immettere o selezionare un valore.
    * Per questo esempio, selezionare Imballaggio.  
11. Nel campo Tempo di esecuzione immettere un numero.
    * Per questo esempio, digitare 1.  
12. Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.
    * Per questo esempio, selezionare Std.  
13. Fare clic sulla scheda Impostazioni.
14. Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.
    * Per questo esempio, selezionare Imballaggio.  
15. Fare clic sulla scheda Tempi.
16. Nel campo Tempo di attrezzaggio immettere un numero.
    * Per questo esempio, digitare 1.  
17. Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.
18. Fare clic su Approva.
19. Fare clic su OK.
20. Nel riquadro azioni, fare clic su Versione ciclo di lavorazione.
21. Fare clic su Attiva.
22. Chiudere la pagina.
23. Chiudere la pagina.

## <a name="enable-automatic-consumption-of-setup-time"></a>Abilitare il consumo automatico del tempo di attrezzaggio
1. Passare a Controllo produzione > Impostazioni > Cicli di lavorazione > Gruppi di cicli di lavorazione.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Nell'elenco selezionare Std.  
3. Fare clic su Modifica.
4. Selezionare Sì nel campo Tempo di attrezzaggio.
    * Il tempo di impostazione spesso fa parte del prezzo calcolato per un articolo.  
5. Fare clic su Salva.
6. Chiudere la pagina.

