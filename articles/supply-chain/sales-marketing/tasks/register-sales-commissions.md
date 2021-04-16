---
title: Registrare le provvigioni di vendita
description: In questo argomento viene descritto come vengono calcolate e registrate le provvigioni di vendita.
author: omulvad
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee75f3a0c9dea7a7c4a4f927651aaab1d6bdb5c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836376"
---
# <a name="register-sales-commissions"></a>Registrare le provvigioni di vendita

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come vengono calcolate e registrate le provvigioni di vendita. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Prima di iniziare questa guida, eseguire la guida chiamata “Impostare regole per la provvigione vendite" per assicurarsi che tutto il necessario per il calcolo della provvigione sia impostato.

Prendere nota dei numeri cliente e articolo scelti per il processo di provvigione e usarli quando chiesto per creare un ordine cliente nella guida.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Fatturare un ordine cliente che qualifica un venditore per una provvigione
1. Nel pannello di navigazione, andare a **Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente** selezionare il record desiderato nel menu a discesa.
4. Selezionare **OK**.
5. Nel riquadro azioni selezionare **Opzioni**.
6. Selezionare **Cambia visualizzazione**.
7. Selezionare **Visualizzazione intestazione**.
8. Espandere la sezione **Impostazione**.

    - Il valore nel campo **Gruppo vendite** rappresenta un gruppo a cui sono assegnati uno o più rappresentanti. Le persone nel gruppo sono quelle che ricevono le provvigioni quando l'ordine viene fatturato, secondo le percentuali e la distribuzione predefinite.   
    - Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.  
    - Il gruppo vendite verrà copiato anche nella riga ordine cliente. È possibile modificarlo in modo che sia diverso da quello nell'intestazione e/o tra le righe.  
    - Il valore nel campo **Gruppo provvigioni** rappresenta un gruppo creato per uno o più clienti a scopo di tracciabilità delle provvigioni.   
    - Il valore viene copiato dalla scheda Cliente, ma è possibile modificarlo se si desidera.   

9. Nel riquadro azioni selezionare **Opzioni**.
10. Selezionare **Cambia visualizzazione**.
11. Seleziona **Visualizzazione riga**.
12. Nel menu a discesa del campo **Numero articolo**, selezionare l'articolo impostato per le provvigioni. 
13. Nel campo **Quantità** immettere un numero. Prendere nota dell'importo netto della riga. Rappresenta i ricavi di vendita, che in questo esempio costituiscono la base per il calcolo della provvigione.  
14. Selezionare **Salva**.
15. Nel riquadro azioni selezionare **Fattura**.
16. Selezionare **Fattura**.
17. Espandere la sezione **Parametri**.
18. Nel campo **Quantità** selezionare **Tutto**.
19. Selezionare **Sì** nel campo **Registrazione**.
20. Selezionare **OK**, quindi selezionare **OK** nel riquadro successivo. Può richiedere qualche minuto registrare la transazione. Attendere il completamento dell'elaborazione e non chiudere la pagina.  

## <a name="review-the-registered-sales-commissions"></a>Verificare le provvigioni vendite registrate
1. Nel riquadro azioni selezionare **Fattura**, quindi selezionare di nuovo **Fattura**.
2. Nel riquadro azioni selezionare **Fattura**, quindi selezionare **Transazioni provvigione**.

    - La scheda **Panoramica** visualizza le righe che rappresentano gli importi di provvigione dovuti ai rappresentanti associati all'ordine cliente fatturato. Esaminiamo i dettagli.  
    - Se è stata utilizzata la guida "Impostare regole per la provvigione vendite" per impostare il gruppo **vendite con provvigione**, sono presenti due venditori per ricevere le provvigioni di vendita e la provvigione è divisa equamente tra loro.  
    - In questo esempio, l'importo totale delle provvigioni viene calcolato come percentuale di ricavi da vendite (l'importo netto della riga ordine).  
3. Chiudere la pagina.
4. Seleziona **Giustificativo**. È possibile esaminare le transazioni giustificativo per gli importi della provvigione registrati nei conti predefiniti Commissioni e Importo a debito provvigioni.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]