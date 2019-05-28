---
title: Registrare le provvigioni di vendita
description: Questa procedura mostra come le provvigioni di vendita vengono calcolate e registrate.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c39b2fcf521106dfb58466bc45a316c0b506345
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560714"
---
# <a name="register-sales-commissions"></a>Registrare le provvigioni di vendita

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come le provvigioni di vendita vengono calcolate e registrate. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Prima di iniziare questa guida, eseguire la guida chiamata “Impostare regole per la provvigione vendite" per assicurarsi che tutto il necessario per il calcolo della provvigione sia impostato.

Prendere nota dei numeri cliente e articolo scelti per il processo di provvigione e usarli quando chiesto per creare un ordine cliente nella guida.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Fatturare un ordine cliente che qualifica un venditore per una provvigione
1. Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su OK.
7. Nel riquadro azioni fare clic su Opzioni.
8. Fare clic su Cambia visualizzazione.
9. Fare clic su Visualizzazione intestazione.
10. Espandere la sezione Impostazione.
    * Il valore nel campo Gruppo vendite rappresenta un gruppo a cui sono assegnati uno o più rappresentanti. Le persone nel gruppo sono quelle che ricevono le provvigioni quando l'ordine viene fatturato, secondo le percentuali e la distribuzione predefinite.   Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.  Il gruppo vendite verrà copiato anche nella riga ordine cliente. È possibile modificarlo in modo che sia diverso da quello nell'intestazione e/o tra le righe.  
    * Il valore nel campo Gruppo provvigioni rappresenta un gruppo creato per uno o più clienti a scopo di tracciabilità delle provvigioni.   Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.   
11. Nel riquadro azioni fare clic su Opzioni.
12. Fare clic su Cambia visualizzazione.
13. Fare clic su Visualizzazione riga.
14. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
15. Nell'elenco, selezionare l'articolo impostato per le provvigioni. 
16. Nel campo Quantità immettere un numero.
    * Prendere nota dell'importo netto della riga. Rappresenta i ricavi di vendita, che in questo esempio costituiscono la base per il calcolo della provvigione.  
17. Fare clic su Salva.
18. Nel riquadro azioni fare clic su Fattura.
19. Fare clic su Fattura.
20. Espandere la sezione Parametri.
21. Nel campo Quantità selezionare "Tutto".
22. Selezionare Sì nel campo Registrazione.
23. Fare clic su OK.
24. Fare clic su OK.
    * Può richiedere qualche minuto registrare la transazione. Attendere il completamento dell'elaborazione e non chiudere la pagina.  

## <a name="review-the-registered-sales-commissions"></a>Verificare le provvigioni vendite registrate
1. Nel riquadro azioni fare clic su Fattura.
2. Fare clic su Fattura.
3. Nel riquadro azioni fare clic su Fattura.
4. Fare clic su Transazioni provvigione.
    * La scheda Panoramica visualizza le righe che rappresentano gli importi di provvigione dovuti ai rappresentanti associati all'ordine cliente fatturato. Esaminiamo i dettagli.     
    * Se è stata utilizzata la guida "Impostare regole per la provvigione vendite" per impostare il gruppo vendite con provvigione, sono presenti due venditori per ricevere le provvigioni di vendita e la provvigione è divisa equamente tra loro.  
    * In questo esempio, l'importo totale delle provvigioni viene calcolato come percentuale di ricavi da vendite (l'importo netto della riga ordine).   
5. Chiudere la pagina.
6. Fare clic su Giustificativo.
    * È possibile esaminare le transazioni giustificativo per gli importi della provvigione registrati nei conti predefiniti Commissioni e Importo a debito provvigioni.  

