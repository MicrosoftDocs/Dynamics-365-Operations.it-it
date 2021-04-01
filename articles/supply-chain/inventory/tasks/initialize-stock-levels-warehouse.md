---
title: Inizializzare i livelli di scorte in magazzino
description: Questa procedura mostra come aggiornare manualmente l'inventario disponibile tramite un giornale di registrazione movimenti Inventario.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c1e5ca96919acde7e850292a73ebd00185f1f7a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244477"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a>Inizializzare i livelli di scorte in magazzino

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come aggiornare manualmente l'inventario disponibile tramite un giornale di registrazione movimenti Inventario. (È inoltre possibile aggiornare l'inventario disponibile importando le transazioni nelle entità di dati). È possibile eseguire questa guida nella società di dati dimostrativi USMF in cui tutti i prerequisiti come il nome del giornale di registrazione, l'impostazione dell'articolo, i profili di registrazione e i conti sono disponibili. La guida suggerisce valori specifici per l'articolo e le dimensioni utilizzati. Se si sceglie un altro articolo, è possibile che sia necessario immettere valori per le diverse dimensioni.

1. Passare a Gestione articoli > Inserimenti nel giornale di registrazione > Articoli > Movimenti.
2. Fare clic su Nuovo.
3. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare IMov.
    * La procedura consigliata consiste nell'utilizzare diversi modelli di nomi del giornale di registrazione per scopi commerciale differenti.  
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo Conto di contropartita specificare i valori "140200".
    * Si tratta del conto di contropartita che sarà il conto predefinito sulle righe del giornale di registrazione. È possibile ignorare l'impostazione predefinita per assegnare conti di contropartita diversi per riga.  
7. Fare clic su OK.
8. Fare clic su Nuovo.
9. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
10. Selezionare l'articolo A0001.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
12. Fare clic sulla scheda Dimensioni inventariali.
13. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
14. Selezionare sito 1.
15. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
16. Selezionare magazzino 13.
17. Nell'elenco fare clic sul collegamento nella riga selezionata.
18. Nel campo Ubicazione fare clic sul pulsante a discesa per aprire la ricerca.
19. Selezionare ubicazione 13.
20. Nel campo Quantità immettere un numero.
21. Fare clic su Salva.
22. Fare clic su Registra.
23. Selezionare o deselezionare la casella di controllo Trasferisci tutti gli errori di registrazione in un nuovo giornale.
    * Se si abilita l'opzione, tutte le righe che non verranno registrate verranno copiate in un nuovo giornale di registrazione. È possibile utilizzare le informazioni nel registro per correggere i problemi e registrare di nuovo le righe.  
24. Fare clic su OK.
25. Chiudere la pagina.
26. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]