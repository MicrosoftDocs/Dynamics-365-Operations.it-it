---
title: " Creare ordini del servizio clienti"
description: In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8dc9e19ecd6b835569ba80563bce33134895cb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791657"
---
# <a name="create-call-center-orders"></a> Creare ordini del servizio clienti

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per individuare un cliente, creare un nuovo ordine, cercare un prodotto e raccogliere il pagamento del cliente. Questa procedura utilizza la società di dati dimostrativi USRT ed è destinata all'addetto degli ordini cliente. Prerequisiti: l'utente che completa la procedura viene impostato come utente del servizio clienti e il catalogo semestrale di Fabrikam è pubblicato con almeno un codice sorgente.

1. Passare a **Retail e Commerce \> Clienti \> Servizio clienti**.
2. Nel campo **Cerca testo**, immettere i criteri di ricerca per cercare il cliente.
    * Per questa procedura di esempio, digitare "Karen" e premere **TAB**.  
3. Selezionare Cerca.
    * Poiché è presente un solo cliente di nome "Karen" nei dati dimostrativi, il risultato viene automaticamente selezionato.  
4. Selezionare **Nuovo ordine cliente**.
5. Espandere o comprimere la sezione **intestazione ordine cliente**.
6. Selezionare il codice sorgente per il catalogo.
    * Se non sono presenti codici sorgente attivi è possibile ignorare questo passaggio.  
7. Selezionare **Aggiungi riga**.
8. Nel campo **Numero articolo**, immettere il termine di ricerca per l'articolo.
    * Per questa procedura di esempio impostare un numero di articolo parziale "8111" e premere TAB. Viene visualizzata la finestra pop-up per la ricerca dell'articolo.  
9. Selezionare il prodotto da aggiungere all'ordine cliente.
10. Immettere la quantità di vendita.
11. Selezionare **Crea**.
12. Selezionare **Completa** per acquisire il pagamento del cliente.
13. Selezionare **Aggiungi**.
    * Il collegamento Aggiungi è presente nella scheda Pagamenti. Espandere la scheda Pagamenti se è compressa.  
14. Selezionare il metodo di pagamento.
    * Selezionare il metodo di pagamento in contanti per questa procedura.  
15. Chiudere la pagina.
16. Immettere l'importo.
    * Per questa procedura immettere un importo uguale al saldo ordine che può essere presente nella pagina di riepilogo Ordine cliente a sinistra del campo dell'importo. L'azione consente di completare l'ordine come interamente pagato.  
17. Selezionare **OK**.
18. Selezionare **Invia**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](../customize-email-delivery-mode.md)

[Modifica modalità di consegna nel POS](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]