---
title: Impostare un profilo di panoramica arrivo articoli
description: "Questa attività riguarda l'impostazione del profilo della panoramica arrivi."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 5ddc491d73bbb6ac02e37a9c9b9d93545f6f9556
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-an-item-arrival-overview-profile"></a>Impostare un profilo di panoramica arrivo articoli

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa attività riguarda l'impostazione del profilo della panoramica arrivi. Il profilo della panoramica arrivi è una raccolta di regole da applicare alla pagina della panoramica arrivi viene aperta da un utente. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. In genere questa procedura verrebbe eseguita da un addetto al ricevimento.





1. Andare a Gestione articoli > Impostazioni > Distribuzione > Profili panoramica arrivi.
2. Fare clic su Nuovo.
    * Poiché verrà utilizzato quasi sempre lo stesso magazzino in cui vengono scaricati camion carichi, è necessario creare un profilo della panoramica arrivi per semplificare il processo di registrazione degli articoli ricevuti.  
3. Nel campo Nome profilo panoramica arrivi digitare un valore.
4. Selezionare un'opzione nel campo Mostra righe.
    * Selezionare le righe da visualizzare per le entrate. Tutte: indica tutte le righe, indipendentemente dallo stato.   In corso: mostra solo le righe per le entrate con stato di avanzamento Completa o Parzialmente. Ciò significa che, per ogni riga, nel giornale di registrazione arrivi è stata registrata la quantità completa o una quantità parziale.   Non completato: mostra solo le righe per le entrate con stato di avanzamento Nessuno o Parzialmente. Ciò significa che, per ogni riga, nel giornale di registrazione arrivi non è stata registrata alcuna quantità o è stata registrata solo una quantità parziale.  
5. Espandere o comprimere la sezione Opzioni arrivi.
6. Digitare un valore nel campo Giorni successivi.
    * Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento nei prossimi giorni (in base al numero impostato).  
7. Digitare un valore nel campo Giorni precedenti.
    * Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento un numero di giorni prima della data odierna.  
8. Digitare un valore nel campo Magazzini.
    * Viene applicato un filtro su uno o più magazzini.  
9. Selezionare un valore nel campo Modalità di consegna.
    * Viene impostato un filtro per visualizzare solo le righe entrata con questa modalità di consegna.  
10. Selezionare Gestione magazzino nel campo Nome.
11. Nel campo Magazzino selezionare il magazzino 24.
    * Si tratta del magazzino predefinito da utilizzare per le righe entrata registrate che utilizzano il profilo.  
12. Nel campo Ubicazione selezionare Baydoor.
    * Si tratta dell'ubicazione predefinita da utilizzare per le righe entrata registrate che utilizzano il profilo.  
13. Espandere o comprimere la sezione Dettagli query arrivi.
14. Nel campo Limita al sito selezionare il sito 2.
    * Viene impostato un filtro per visualizzare solo le righe entrata con questo sito.  
15. Impostare l'opzione Ordini fornitore su Sì.
    * Consente di selezionare righe entrata dagli ordini fornitore.  
16. Impostare l'opzione Ordini di trasferimento su Sì.
    * Consente di selezionare righe entrata dagli ordini di trasferimento.  
17. Fare clic su Salva.
18. Chiudere la pagina.

