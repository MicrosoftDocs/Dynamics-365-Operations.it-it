---
title: " Definire schemi di programma fedeltà"
description: In questa procedura vengono descritti i passaggi per definire uno schema del programma fedeltà.
author: jashanno
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3909213aaefa3a63fedfc90e6c02ef89b893b16ff5841bf10249867d406c894c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738650"
---
# <a name="define-loyalty-schemes"></a> Definire schemi di programma fedeltà

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per definire uno schema del programma fedeltà. Gli schemi del programma fedeltà sono regole di acquisizione e riscatto premi di un programma di fedeltà. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Retail e Commerce > Clienti > Fedeltà > Schemi programma fedeltà.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo ID schema.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
    * È possibile avere schemi del programma fedeltà per un programma fedeltà. Gli schemi del programma fedeltà possono essere per tutti i canali o solo per un sottoinsieme di canali.  
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Fare clic su Salva.
9. Fare clic su Aggiungi riga.
10. Nel campo Tipo di attività selezionare un'opzione.
    * Selezionare Acquista prodotti per importo se si desidera che i clienti acquisiscano punti in base a quanto spendono. Selezionare Acquista prodotti per quantità se si desidera che i clienti acquisiscano punti in base a quanti prodotti acquistano.  Selezionare Conteggio transazioni di vendita se si desidera che i clienti acquisiscano punti per ciascuna transazione di vendita, indipendentemente dal tipo o dalla quantità di articoli acquistati.  
    * Consente di selezionare una categoria. La categoria limiterà i prodotti a cui si applica questa regola di acquisizione.  
    * Lasciare vuoto il campo se si desidera che la regola di acquisizione venga applicata a tutti i prodotti.  
11. Nel campo Importo/Quantità attività immettere un numero.
    *  Per il tipo di attività Conteggio transazioni di vendita, utilizzare sempre un valore "1.0". Per i tipi di attività di acquisto in base all'importo o di acquisto in base alla quantità, qualsiasi transazione inferiore al valore immesso non attiva la regola di acquisizione. Ad esempio, se il tipo di attività è Acquista per importo e si immette "10,00 ", una transazione di vendita per "9,00" non acquisirà punti per la regola di acquisizione.  
12. Digitare un valore nel campo Valuta attività.
13. Nel campo ID punto premio fare clic sul pulsante a discesa per aprire la ricerca.
14. Nell'elenco fare clic sul collegamento nella riga selezionata.
15. Immettere un numero nel campo Punti premio.
    * I punti premio di tipo Importo registreranno gli importi acquisiti con i decimali. Ad esempio, se la regola indica che si acquisisce 1 punto premio per ogni dollaro canadese speso e il cliente spende 1,25 dollari canadesi, il cliente acquisirà 1,25 punti premio. I punti premio di tipo Quantità registreranno gli importi acquisiti in valori interi. Se si utilizza l'esempio in cui la regola indica che si acquisisce 1 punto premio per ogni dollaro canadese speso, e il cliente spende 1,25 dollari canadesi, il cliente acquisirà 1,0 punti premio.  
16. Fare clic su Salva.
17. Fare clic su Aggiungi riga.
    * Le regole di rimborso vengono utilizzate se si impiega il metodo di pagamento del programma fedeltà.  
18. Nel campo ID punto premio fare clic sul pulsante a discesa per aprire la ricerca.
    * Solo i punti premio riscattabili vengono visualizzati.  
19. Nell'elenco fare clic sul collegamento nella riga selezionata.
20. Immettere un numero nel campo Punti premio.
21. Nel campo Tipo di rimborso selezionare un'opzione.
    * Se si seleziona Pagamento in base a importo, il campo Importo o quantità viene trattato come valore di valuta. In questo caso, l'importo dei punti premio utilizzati per ogni unità di valuta di pagamento è un rapporto fisso. Se si seleziona Pagamento in base a quantità, il campo Importo o quantità viene trattato come valore di quantità. In questo caso, l'importo dei punti premio usati per ogni quantità di articolo è un rapporto fisso, tuttavia, l'importo in valuta può variare se il prezzo pagato per gli articoli con i punti premio fedeltà varia per la stessa quantità. Il tipo di riscatto Sconto punti fedeltà è valido solo quando è abilitata la chiave di configurazione specifica del paese 'Russia' e i profili di funzionalità POS hanno il codice ISO "RU".  
    * Consente di selezionare una categoria. La categoria limiterà i prodotti a cui si applica questa regola di riscatto.  
    * Lasciare vuoto il campo se si desidera che la regola di riscatto venga applicata a tutti i prodotti.  
22. Nel campo Importo o quantità immettere un numero.
23. Digitare un valore nel campo Valuta.
24. Fare clic su Salva.
25. Fare clic su Aggiungi riga.
    * Selezionare uno o più nodi dall'elenco Nodi organizzazione disponibili e spostarli nell'elenco Nodi organizzazione selezionati facendo clic sulla freccia tra i due elenchi.  
26. Fare clic su OK.
27. Fare clic su Salva.
    * Se si modificano i canali per uno schema del programma fedeltà, è necessario eseguire Elabora programmi fedeltà. In tal modo, i canali riceveranno gli schemi del programma fedeltà aggiornati.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]