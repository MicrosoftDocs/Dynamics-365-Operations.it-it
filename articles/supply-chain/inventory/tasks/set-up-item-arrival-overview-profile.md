---
title: Impostare un profilo di panoramica arrivo articoli
description: In questo articolo viene descritta l'impostazione del profilo della panoramica arrivi.
author: yufeihuang
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8517710f5d0be1859f86449152712d950281769a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872009"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>Impostare un profilo di panoramica arrivo articoli

[!include [banner](../../includes/banner.md)]

In questo articolo viene descritta l'impostazione del profilo della panoramica arrivi. Il profilo della panoramica arrivi è una raccolta di regole da applicare alla pagina della panoramica arrivi viene aperta da un utente. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. In genere questa procedura verrebbe eseguita da un addetto al ricevimento.

1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazione > Distribuzione > Profili panoramica arrivi**.
2. Selezionare **Nuovo**. Poiché verrà utilizzato quasi sempre lo stesso magazzino in cui vengono scaricati camion carichi, è necessario creare un profilo della panoramica arrivi per semplificare il processo di registrazione degli articoli ricevuti.  
3. Nel campo **Nome profilo panoramica arrivi** digitare un valore.
4. Selezionare un'opzione nel campo **Mostra righe**. Selezionare le righe da visualizzare per le entrate:  

    - **Tutto**: mostra tutte le righe, indipendentemente dal loro stato.   
    - **In corso**: mostra solo le righe per le entrate con stato di avanzamento Completa o Parzialmente. Ciò significa che, per ogni riga, nel giornale di registrazione arrivi è stata registrata la quantità completa o una quantità parziale.   
    - **Non completato**: mostra solo le righe per le entrate con stato di avanzamento Nessuno o Parzialmente. Ciò significa che, per ogni riga, nel giornale di registrazione arrivi non è stata registrata alcuna quantità o è stata registrata solo una quantità parziale.  

5. Espandere o comprimere la sezione **Opzioni arrivi**.
6. Digitare un valore nel campo **Giorni successivi**. Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento nei prossimi giorni (in base al numero impostato).  
7. Digitare un valore nel campo **Giorni precedenti**. Viene impostato un filtro per visualizzare le righe di entrata previste per il ricevimento un numero di giorni prima della data odierna.  
8. Digitare un valore nel campo **Magazzini**. Viene applicato un filtro su uno o più magazzini.  
9. Selezionare un valore nel campo **Modalità di consegna**. Viene impostato un filtro per visualizzare solo le righe entrata con questa modalità di consegna.  
10. Selezionare Gestione magazzino nel campo **Nome**.
11. Nel campo **Magazzino** selezionare il magazzino 24. Si tratta del magazzino predefinito da utilizzare per le righe entrata registrate che utilizzano il profilo.  
12. Nel campo **Ubicazione** selezionare **Baydoor**. Si tratta dell'ubicazione predefinita da utilizzare per le righe entrata registrate che utilizzano il profilo.  
13. Espandere o comprimere la sezione **Dettagli query arrivi**.
14. Nel campo **Limita al sito** selezionare il sito 2. Viene impostato un filtro per visualizzare solo le righe entrata con questo sito.  
15. Impostare l'opzione **Ordini fornitore** su **Sì**. Consente di selezionare righe entrata dagli ordini fornitore.  
16. Impostare l'opzione **Ordini di trasferimento** su **Sì**. Consente di selezionare righe entrata dagli ordini di trasferimento.  
17. Selezionare **Salva**.
18. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
