---
title: " Creare ordini del servizio clienti"
description: In questo articolo viene descritta una procedura di esempio in cui un utente del servizio clienti cerca un cliente, crea un nuovo ordine, cerca un prodotto e raccoglie il pagamento del cliente in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2022
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
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228512"
---
# <a name="create-call-center-orders"></a> Creare ordini del servizio clienti

[!include [banner](../includes/banner.md)]

In questo articolo viene descritta una procedura di esempio in cui un utente del servizio clienti cerca un cliente, crea un nuovo ordine, cerca un prodotto e raccoglie il pagamento del cliente in Microsoft Dynamics 365 Commerce. Questa procedura utilizza la società di dati dimostrativi USRT ed è destinata agli addetti degli ordini cliente. 

## <a name="prerequisites"></a>Prerequisiti

L'utente che complete la procedura deve essere impostato come utente del servizio clienti. Facoltativamente, il catalogo semestrale Fabrikam può essere pubblicato con almeno un codice sorgente.

### <a name="add-yourself-as-a-call-center-user"></a>Aggiungere te stesso come utente del servizio clienti

Per aggiungere te stesso come utente del servizio clienti, procedi come segue.

1. In Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Canali \> Servizi clienti \> Tutti i servizi cliente**.
1. Nel campo **Utenti**, seleziona **Utenti canale**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **ID utente**, inserisci il tuo ID utente.
1. Nel campo **Nome** immetti il tuo nome utente. Il nome utente può essere uguale all'ID utente.
1. Nel riquadro azioni selezionare **Salva**.
1. Ritorna a **Vendita al dettaglio e commercio \> Canali \> Servizi clienti \> Tutti i servizi clienti**.
1. Seleziona l'ID canale di vendita al dettaglio del servizio clienti.
1. Verifica l'impostazione dell'opzione **Attiva completamento ordine** su **Sì**. Se l'opzione non è visibile, puoi saltare questo passaggio.

## <a name="complete-the-example-call-center-procedure"></a>Completare la procedura di esempio del servizio clienti

Per completare la procedura di esempio del servizio clienti, procedi come segue.

1. Passare a **Retail e Commerce \> Clienti \> Servizio clienti**.
1. Nella scheda **Ricerca cliente**, immetti i criteri di ricerca per cercare il cliente. Per questa procedura di esempio, immetti **Karen**.
1. Selezionare **Cerca**. Viene visualizzata la finestra di dialogo **Ricerca clienti** in cui sono elencati i risultati della ricerca.
1. Seleziona il record cliente per **Karen Berg** che ha il numero di conto cliente **2001**, quindi seleziona **Seleziona**.
1. Nel riquadro azioni, seleziona **Nuovo ordine cliente**.
1. A destra, seleziona la scheda **Intestazione**.
1. Nella Scheda dettaglio **Consegna**, nel campo **Modalità di consegna**, seleziona **99 standard**.

    ![Seleziona una modalità di consegna.](../media/Select_Mode_of_Delivery.png)

1. A destra, seleziona la scheda **Riga**.
1. Nella sezione **Righe ordine cliente**, nella nuova riga per la nuova riga di vendita, nel campo **Numero articolo**, inserisci il numero dell'articolo da cercare. Per questa procedura di esempio, immetti **81327**, quindi seleziona il prodotto nell'elenco a discesa per aggiungerlo all'ordine cliente.
1. Nel campo **Quantità**, immetti la quantità di vendita.
1. Nel campo **Codice sorgente**, seleziona il codice sorgente per il catalogo. Se non sono presenti codici sorgente attivi, puoi ignorare questo passaggio.
1. Nel riquadro azioni, seleziona **Completa** per acquisire il pagamento del cliente. Questa azione apre la finestra di dialogo **Riepilogo ordine cliente**, che mostra l'importo totale dovuto. L'azione attiva anche il calcolo di eventuali addebiti, come la spedizione e la gestione, e li visualizza nella finestra di dialogo **Riepilogo ordine cliente**.

    ![Il pulsante Completa.](../media/Complete_button.png)

1. Nella finestra di dialogo **Riepilogo ordine cliente**, nella Scheda dettaglio **Pagamenti**, seleziona **Aggiungi** per acquisire i pagamenti.

    ![Finestra di dialogo Riepilogo ordine cliente.](../media/order_summary.png)

1. Nella finestra di dialogo **Immettere le informazioni sul pagamento cliente**, nel campo **Metodo di pagamento**, selezionare il metodo di pagamento. Per questa procedura di esempio, seleziona **Contanti**.
1. Nel campo **Importo pagamento**, immetti l'importo del pagamento. Per questo esempio, immetti **120,00**, che corrisponde al saldo dell'ordine visualizzato nella finestra di dialogo **Riepilogo ordine cliente**. Immettendo questo importo, puoi completare l'ordine come interamente pagato.
1. Seleziona **OK**.
1. Selezionare **Invia**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](../customize-email-delivery-mode.md)

[Modifica modalità di consegna nel POS](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
