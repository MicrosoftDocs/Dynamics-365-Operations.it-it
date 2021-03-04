---
title: Impostare regole per la provvigione vendite
description: Questa procedura mostra come impostare e abilitare il calcolo e la verifica della provvigione di vendita.
author: omulvad
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended, CommissionEmplSalesGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b1ea016817462269a13e450c8c7576546c7f0eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431073"
---
# <a name="set-up-sales-commission-rules"></a>Impostare regole per la provvigione vendite

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come impostare e abilitare il calcolo e la verifica della provvigione di vendita. Le procedura mostra come creare i gruppi di provvigioni per clienti e per articoli e quindi come collegare un cliente e un prodotto selezionati ai rispettivi gruppi. Tali gruppi vengono utilizzati nell'impostazione di calcolo della provvigione per creare una combinazione di cliente, articolo e rappresentante che deve corrispondere all'ordine cliente per autorizzare i venditori a una provvigione. Creare i gruppi di provvigioni per clienti e articoli è facoltativo, poiché il calcolo della provvigione può anche essere eseguito per un cliente e/o articolo individuale. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.


## <a name="set-up-commission-groups-and-commission-rates"></a>Impostare i gruppi di provvigioni e le percentuali di provvigione
1. Passare a **Pannello di navigazione > Moduli > Vendite e marketing > Provvigioni > Gruppi di clienti per la provvigione**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Gruppo**.
4. Digitare un valore nel campo **Nome**.
5. Selezionare **Salva**.
6. Chiudere la pagina.
7. Passare a **Pannello di navigazione > Moduli > Vendite e marketing > Provvigioni > Gruppi di articoli**.
8. Selezionare **Nuovo**.
9. Digitare un valore nel campo **Gruppo**.
10. Digitare un valore nel campo **Nome**.
11. Selezionare **Salva**.
12. Chiudere la pagina.
13. Andare a **Vendite e marketing > Provvigioni > Gruppi vendite**.
    - Un gruppo vendite con provvigione specifica i dipendenti con ruoli di rappresentante idonei a ricevere una provvigione quando un cliente associato al gruppo vendite competente compra determinati articoli.  
    - Nella società di dati dimostrativi USMF, è presente un gruppo vendite denominato "Sales reps US".  
14. Nel **riquadro azioni** fare clic su **Generale**.
15. Fare clic su **Rappres.**. La pagina Rappres. mostra un elenco dei venditori della società associati a un gruppo di provvigioni specifico. È possibile assegnare più rappresentanti allo stesso gruppo e definire la rispettiva quota delle commissioni di provvigione totali come valore percentuale. La somma delle quote di provvigione di tutti i dipendenti non deve superare 100. 
16. Nell'elenco contrassegnare la riga selezionata.
17. Selezionare **Modifica**.
18. Impostare **Quota provvigione** su '50'.
19. Fare clic su **Nuovo**.
20. Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.
21. Utilizzare il **filtro rapido** per trovare i record. Ad esempio, filtrare il campo Nome con il valore 'Susan Burk'.
22. Fare clic su **Seleziona**.
23. Impostare **Quota provvigione** su '50'.
24. Fare clic su **Salva**.
25. Andare a **Vendite e marketing > Provvigioni > Calcolo della provvigione**. Nella pagina **Calcolo della provvigione** viene definita la percentuale di provvigione che il dipendente deve ricevere per una transazione di vendita quando contiene la combinazione prestabilita di cliente e di prodotto. Nella impostazione della percentuale della provvigione, è necessario specificare la base di calcolo della provvigione e se deve includere oppure escludere gli sconti. È inoltre possibile immettere un periodo di validità nel quale la percentuale di provvigione è attiva.  
26. Fare clic su **Nuovo**.
27. Selezionare 'Gruppo' nel campo **Codice articolo**.
28. Nel campo **Relazione articolo** fare clic sul pulsante a discesa per aprire la ricerca.
29. Nell'elenco, trovare e selezionare il gruppo creato in precedenza.
30. Selezionare 'Gruppo' nel campo **Codice cliente**.
31. Nel campo **Relazione cliente** fare clic sul pulsante a discesa per aprire la ricerca.
32. Nell'elenco, selezionare il gruppo impostato in precedenza.
33. Nel campo **Relazione rappr.** fare clic sul pulsante a discesa per aprire la ricerca.
34. Nell'elenco trovare e selezionare il record desiderato.
    - Mantenere l'opzione "Prima dello sconto riga".  
    - Mantenere l'opzione "Ricavi" come base per il calcolo del valore della provvigione.    
35. Immettere un numero nel campo Percentuale provvigione.
36. Fare clic su **Salva**.

## <a name="setting-up-commission-posting"></a>Impostazione della registrazione della provvigione
1. Passare a **Pannello di navigazione > Vendite e marketing > Provvigioni > Registrazione provvigione**. Le commissioni di provvigione sono un debito a dipendenti e devono pertanto essere impostate in modo da garantire la registrazione finanziaria corretta nei conti appropriati nella **contabilità generale**. Ciò viene effettuato nella pagina **Registrazione provvigione**. Esaminare l'impostazione disponibile per la società corrente. In genere, gli importi della provvigione vengono registrati in un conto spese dedicato e vengono compensati in contropartita in un conto a debito dedicato. Se non sono impostate regole di registrazione delle provvigioni, il sistema non riuscirà a completare la fatturazione di un ordine cliente con provvigioni idonee.  
2. Chiudere la pagina.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Assegnare un gruppo di provvigioni a un cliente e un prodotto
1. Passare a **Pannello di navigazione > Moduli > Vendite e marketing > Clienti > Tutti i clienti**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su **Modifica**.
5. Espandere la sezione **Impostazioni predefinite ordine cliente**.
6. Nel campo **Gruppo provvigioni** fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco, selezionare il gruppo creato in precedenza.
8. Nel campo **Gruppo vendite** fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Fare clic su **Salva**.
11. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.
12. Utilizzare il **filtro** per trovare i record. Ad esempio, filtrare il campo Numero articolo con un valore 'T0020'.
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Fare clic su **Modifica**.
15. Espandere la sezione **Vendi**.
16. Nel campo **Gruppo provvigioni** fare clic sul pulsante a discesa per aprire la ricerca.
17. Nell'elenco, selezionare il gruppo di provvigioni creato in precedenza.
18. Selezionare **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]