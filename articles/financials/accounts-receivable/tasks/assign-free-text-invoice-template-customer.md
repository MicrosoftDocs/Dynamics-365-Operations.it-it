--- 
title: Assegnare al cliente un modello di fattura a testo libero
description: "Questa attività descrive come assegnare un modello di fattura a testo libero a un cliente."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3bcb59c6edd04877dc2a052002be513205ae840a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Assegnare al cliente un modello di fattura a testo libero

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa attività descrive come assegnare un modello di fattura a testo libero a un cliente. In questa attività viene utilizzata la società dimostrativa USMF ed è destinata all'utente responsabile della gestione e dell'elaborazione delle fatture di CoCli.

1. Andare a Contabilità clienti > Clienti > Tutti i clienti.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nel riquadro azioni fare clic su Fattura.
4. Fare clic su Fatture ricorrenti.
    * Utilizzare questa pagina per assegnare ai clienti modelli di fattura a testo libero e specificare con quale frequenza le fatture verranno inviate al cliente.  
5. Fare clic su Nuovo per assegnare un nuovo modello al cliente.
6. Selezionare il modello di fattura a testo libero da assegnare al cliente.
7. Trovare e selezionare il record desiderato nell'elenco.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Immettere la data in cui verrà generata la prima fattura.
    * Immettere una data di fine ricorrente.  
    * Selezionare una delle opzioni seguenti. Nessuna data di fine: le fatture verranno generate indefinitamente finché il modello non verrà rimosso dal conto cliente.  Data di fine fatturazione: selezionare questa opzione e immettere l'ultima data in cui la fattura può essere generata.  
    * Importo cumulativo massimo dopo il quale la generazione della fattura verrà interrotta.  
    * Immettere l'importo cumulativo massimo che può essere raggiunto utilizzando il modello selezionato. Se si immette, ad esempio, 1.000,00 e vengono generate fatture mensili per 100,00 ciascuna, la generazione delle fatture verrà interrotta dopo la decima fattura.  
    * Genera fatture ricorrenti utilizzando i valori predefiniti dal modello di fattura a testo libero o dal conto cliente.  
    * Scegliere se utilizzare il modello di fattura a testo libero o il conto cliente per determinare i valori predefiniti per lingua, profilo registrazione, fascia IVA, fascia IVA articoli, codice elenco, paese di consegna, valuta, termini di pagamento, metodo di pagamento, specifica di pagamento, scadenzario pagamenti, sconto di cassa, dimensioni finanziarie e distinta ordine di accredito quando vengono create le fatture.  
10. Selezionare il criterio di ricorrenza.
    * Giornaliero: selezionare questa opzione e immettere il numero di giorni nel campo Per. Se si immette, ad esempio, 15, la fattura verrà generata ogni 15 giorni per il cliente specificato.  Settimanale: selezionare questa opzione e immettere il numero di settimane nel campo Per. Se si immette, ad esempio, 2, la fattura verrà generata ogni 2 settimane per il cliente specificato.  Mensile: selezionare questa opzione e immettere il numero di mesi nel campo Per. Se si immette, ad esempio, 6, la fattura verrà generata ogni 6 mesi per il cliente specificato.  Annuale: selezionare questa opzione e immettere il numero di anni nel campo Per. Se si immette, ad esempio, 2, la fattura verrà generata ogni 2 anni per il cliente specificato.  
11. Nel campo Per immettere un numero.


