---
title: Uso di Programma di continuità
description: Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b8e3903aac99d32bbf4d065e6db1c3f3aab998c04d052d08338eb3f54ccc96f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761540"
---
# <a name="using-continuity-program"></a>Uso di Programma di continuità

[!include [banner](../includes/banner.md)]

Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati. Per eseguire questa procedura, l'utente deve essere impostato come utente di servizio clienti. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Retail e Commerce > Clienti > Servizio clienti.
2. Nel campo Cerca testo, digitare 'Karen' quindi premere il tasto TAB.
    * La finestra di dialogo di ricerca avanzata dovrebbe apparire. In caso contrario, fare clic su Cerca a destra del campo.  
3. Nell'elenco contrassegnare la riga selezionata.
    * Deve essere presente un'unica riga che mostra Karen Berg. Selezionare la riga facendo clic su nella colonna di segno di spunta all'estrema sinistra della griglia.  
4. Fare clic su Seleziona.
5. Fare clic su Nuovo ordine cliente.
    * È consigliabile prendere nota del numero di ordine cliente. Sarà necessario più avanti in questa procedura.  
6. Nel campo Numero articolo, digitare '88000' quindi premere il tasto TAB.
    * Si tratta di un articolo continuità nei dati dimostrativi USRT.  
7. Fare clic su Completa.
8. Nel campo Metodo di pagamento, immettere 'Visa'.
9. Fare clic su Aggiungi carta di credito.
    * Immettere le informazioni necessarie su carta di credito in questa pagina.  
10. Fare clic su OK.
11. Espandere la sezione Pagamento.
    * Per inviare un ordine servizio clienti, i pagamenti devono essere immessi per l'ordine.  
12. Fare clic su OK.
13. Fare clic su Invia.
    * È terminata la creazione di un nuovo ordine di continuità. A questo punto, eseguirete due processi batch utilizzati per elaborare gli ordini di continuità.  
14. Chiudere la pagina.
15. Passare a Retail e Commerce > Continuità > Elabora pagamenti di continuità.
16. Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.
17. Fare clic su OK.
18. Passare a Retail e Commerce > Continuità > Crea ordini di continuità figlio.
    * Questo processo consente di creare nuovi ordini cliente in base alle impostazioni dei programmi di continuità.  
19. Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.
    * Articolo '88000' è un articolo di continuità nei dati dimostrativi USRT.  
20. Nel campo Ordine cliente immettere o selezionare un valore.
    * Immettere il numero di ordine cliente annotato in precedenza nella procedura. Questo terrà il tempo di elaborazione a un minimo per questa procedura. Il campo Ordine cliente è facoltativo: si potrebbero elaborare tutti gli ordini per qualsiasi dato programma.  
21. Fare clic su OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]