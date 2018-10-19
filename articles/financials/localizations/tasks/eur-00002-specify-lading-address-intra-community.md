--- 
title: EUR-00002 Specifica di un indirizzo di carico per una transazione intracomunitaria
description: In questa procedura viene illustrato come specificare un indirizzo di carico per una transazione per il commercio intracomunitario.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid,  VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 4db22444bee1590770a47ca5946941b530ae85ce
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a>EUR-00002 Specifica di un indirizzo di carico per una transazione intracomunitaria

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come specificare un indirizzo di carico per una transazione per il commercio intracomunitario. Ad esempio, una società in Germania ordina articoli da un fornitore con un indirizzo commerciale tedesco. Tale fornitore ha un magazzino in Italia e spedisce gli articoli da lì. Questa consegna deve essere dichiarata in Intrastat. Lo stesso comportamento è valido per i resi dei clienti.
Questa procedura si applica a tutti i paesi europei. L'attività è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Germania. Prima di poter completare questa procedura, è necessario configurare la dichiarazione Intrastat. Questa procedura è destinata ai contabili. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

1. Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Immettere o selezionare un valore
    * Selezionare, ad esempio, DE-001. Tale fornitore dispone di un indirizzo commerciale tedesco.  
4. Fare clic su OK.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo Numero articolo immettere o selezionare il valore D0001.
7. Fare clic su Salva.
8. Nel riquadro azioni fare clic su Ricevi.
9. Fare clic su Dettagli trasporto.
10. Nel campo Data/ora carico immettere una data e un'ora.
11. Fare clic su Aggiungi indirizzo.
12. Fare clic su Nuovo quindi creare il nuovo indirizzo con scopo Carico.
13. Digitare 'Italiano' nel campo Nome o Descrizione.
14. Selezionare il valore Carico.
    * Tenere presente che lo scopo dell'indirizzo deve esse Carico.  
15. Nel campo Paese immettere o selezionare un valore ITA.
16. Fare clic su Salva.
17. Chiudere la pagina.
18. Fare clic su Salva.
    * Verificare che l'indirizzo di carico sia corretto.  
19. Chiudere la pagina.
20. Nel riquadro azioni fare clic su Acquisti.
21. Fare clic su Conferma.
22. Nel riquadro azioni fare clic su Fattura.
23. Fare clic su Fattura.
24. Digitare un valore nel campo Numero.
25. Immettere una data nel campo Data fattura.
26. Fare clic su Predefinito da: Quantità entrata prodotti per aprire la finestra di dialogo a discesa.
27. Nel campo Quantità predefinita per le righe, selezionare 'Quantità ordinata'.
28. Fare clic su OK.
29. Fare clic su Dettagli trasporto.
    * Verificare che le merci siano state spedite dall'Italia. Se necessario, è possibile modificare i dettagli di carico.  
30. Chiudere la pagina.
31. Fare clic su Registra.
32. Chiudere la pagina.
33. Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.
34. Fare clic su Trasferisci.
35. Selezionare Sì nel campo Fattura fornitore.
36. Fare clic su OK.
37. Fare clic sulla scheda Generale.
    * Individuare una riga creata di recente e verificare che il mittente abbia spedito le merci dall'Italia.  


