---
title: " Creare ordini del servizio clienti"
description: In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4867ad67dc570ab42420ba12fc7dc2da6b5ba503
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "334314"
---
# <a name="create-call-center-orders"></a> Creare ordini del servizio clienti

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente. Questa procedura utilizza la società di dati dimostrativi USRT ed è destinata all'addetto degli ordini cliente. Prerequisiti: l'utente che completa la procedura viene impostato come utente del servizio clienti e il catalogo semestrale di Fabrikam è pubblicato con almeno un codice sorgente.

1. Passare a Vendita al dettaglio e commercio > Clienti > Servizio clienti.
2. Nel campo Cerca testo, immettere i criteri di ricerca per cercare il cliente.
    * Per questa procedura di esempio, digitare 'karen' e premere TAB.  
3. Fare clic su Cerca.
    * Poiché è presente un solo cliente di nome Karen, i dati dimostrativi verranno automaticamente selezionati.  
4. Fare clic su Nuovo ordine cliente.
5. Espandere o comprimere la sezione Intestazione ordine cliente.
6. Selezionare il codice sorgente per il catalogo.
    * Se non sono presenti codici sorgente attivi è possibile chiudere il campo Origine e ignorare questo passaggio.  
7. Fare clic su Aggiungi riga.
8. Nel campo Numero articolo, immettere il termine di ricerca per l'articolo.
    * Per questa procedura di esempio impostare un numero di articolo parziale "8111"e premere TAB. Verrà visualizzata la finestra pop-up per la ricerca dell'articolo.  
9. Selezionare il prodotto da aggiungere all'ordine cliente
10. Immettere la quantità di vendita.
11. Fare clic su Crea.
12. Fare clic su Completa per acquisire il pagamento del cliente.
13. Scegliere Aggiungi.
    * Il collegamento Aggiungi è presente nella scheda Pagamenti. Espandere la scheda Pagamenti se è compressa.  
14. Selezionare il metodo di pagamento.
    * Selezionare il metodo di pagamento in contanti per questa procedura.  
15. Chiudere la pagina.
16. Immettere l'importo.
    * Per questa procedura immettere un importo uguale al saldo ordine che può essere presente nella pagina di riepilogo Ordine cliente a sinistra del campo dell'importo. In tal modo sarà possibile completare l'ordine come interamente pagato.  
17. Fare clic su OK.
18. Fare clic su Invia.

