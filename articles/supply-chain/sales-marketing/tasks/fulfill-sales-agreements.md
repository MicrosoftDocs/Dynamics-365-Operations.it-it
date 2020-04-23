---
title: Adempiere ai contratti di vendita
description: Questa procedura indica come soddisfare un contratto di vendita associando gli ordini cliente.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51ea8afc7c2f683790f697185d6637e0d24462fc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204311"
---
# <a name="fulfill-sales-agreements"></a>Adempiere ai contratti di vendita

[!include [banner](../../includes/banner.md)]

Questa procedura indica come soddisfare un contratto di vendita associando gli ordini cliente. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Prima di iniziare questa guida, assicurarsi di disporre di un contratto di vendita valido di tipo "Impegno valore prodotto". In alternativa, è possibile eseguire la guida attività denominata "Creare contratti di vendita".  




## <a name="release-a-sales-order-from-the-agreement"></a>Rilasciare un ordine cliente dal contratto
1. Passare a Vendite e marketing > Contratti di vendita > Contratti di vendita.
2. Nell'elenco, aprire il contratto con cui si desidera rilasciare l'ordine.
3. Nel riquadro azioni, fare clic su Contratto di vendita.
4. Fare clic su Ordine di rilascio.
    * Come indicato dal testo nella parte superiore della pagina Crea ordine di rilascio, i dettagli richiesti per le righe ordine cliente variano a seconda se il contratto si basa sulla quantità o sul valore.  
    * Il contratto in questa guida è di tipo "Impegno valore prodotto" e pertanto la Righe di questa pagina è vuota. Se l'impegno fosse stato basato sulla quantità, le informazioni sulle righe sarebbero state copiate dal contratto.  
5. Fare clic su Crea.
    * Il messaggio informa che l'ordine cliente è stato creato. Poiché l'ordine non contiene righe, è necessario aggiungere i dettagli riga ordine per completare il processo di rilascio.   
6. Chiudere la pagina.
7. Chiudere la pagina.
8. Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.
9. Nell'elenco, individuare e aprire l'ordine creato come risultato del rilascio dell'ordine dell'attività precedente.
10. Fare clic su Aggiungi riga.
11. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
12. Nel campo Numero articolo, digitare o selezionare l'articolo specificato nel contratto di vendita associato.
13. Nel campo Quantità immettere un numero.
    * Assicurarsi di immettere una quantità tale che l'importo netto sia inferiore al valore del contratto di vendita collegato.  
    * Si noti che poiché l'ordine cliente è collegato al contratto, la percentuale negoziata di sconto viene applicata alla riga ordine.  
14. Fare clic su Aggiorna riga.
15. Fare clic su Collegata.
    * La pagina Contratto allegato mostra l'ID e i termini del contratto da cui la riga viene rilasciata.  
16. Chiudere la pagina.
17. Nel riquadro azioni fare clic su Generale.
18. Fare clic su Contratto di vendita allegato.
19. Espandere la sezione Dettagli riga.
20. Fare clic sulla scheda Evasione.
    * La scheda Evasione mostra un riepilogo di tutte le righe ordine cliente che sono associate a questo impegno e il relativo stato di adempimento nonché l'importo o la quantità che ancora non è stata rilasciata.   
21. Chiudere la pagina.
22. Chiudere la pagina.
23. Chiudere la pagina.

## <a name="apply-sales-agreement-in-the-order-process"></a>Applicare il contratto di vendita nel processo dell'ordine
1. Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco, trovare e selezionare il cliente specificato nel contratto di vendita.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Espandere la sezione Generale.
7. Nel campo ID contratto di vendita fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Fare clic su Sì.
10. Fare clic su OK.
11. Nell'elenco contrassegnare la riga selezionata.
12. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
13. Nel campo Numero articolo, digitare o selezionare l'articolo specificato nel contratto di vendita associato.
14. Nell'elenco fare clic sul collegamento nella riga selezionata.
15. Fare clic su Salva.
16. Nel riquadro azioni fare clic su Preleva e imballa.
17. Fare clic su Registra documento di trasporto.
18. Espandere la sezione Parametri.
19. Selezionare Sì nel campo Registrazione.
20. Fare clic su OK.
21. Fare clic su OK.
22. Nel riquadro azioni fare clic su Generale.
23. Fare clic su Contratto di vendita allegato.
24. Fare clic sulla scheda Evasione.

