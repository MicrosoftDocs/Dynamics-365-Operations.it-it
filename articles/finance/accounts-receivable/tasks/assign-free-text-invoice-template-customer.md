---
title: Assegnare al cliente un modello di fattura a testo libero
description: Questa attività descrive come assegnare un modello di fattura a testo libero a un cliente.
author: ShivamPandey-msft
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb8a683792051a95b443fac47b4670f37c12cc4b4142ee2290b89ee1845662cf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740100"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Assegnare al cliente un modello di fattura a testo libero

[!include [banner](../../includes/banner.md)]

Questa attività descrive come assegnare un modello di fattura a testo libero a un cliente. In questa attività viene utilizzata la società dimostrativa USMF ed è destinata all'utente responsabile della gestione e dell'elaborazione delle fatture di CoCli.

1. Nel **pannello di navigazione**, andare a **Moduli > Contabilità clienti > Clienti > Tutti i clienti**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nel **riquadro azioni** fare clic su **Fattura**.
4. Fare clic su **Fatture ricorrenti**. Utilizzare questa pagina per assegnare ai clienti modelli di fattura a testo libero e specificare con quale frequenza le fatture verranno inviate al cliente.  
5. Fare clic su **Nuovo** per assegnare un nuovo modello al cliente.
6. Nel campo **Modello**, selezionare il modello di fattura a testo libero da assegnare al cliente.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo **Data di inizio fatturazione**, immettere la data alla quale verrà generata la prima fattura.
10. Nella sezione **Termine ricorrenza**, immettere una data di fine ricorrente.  
    * Selezionare una delle opzioni seguenti. Nessuna data di fine: le fatture verranno generate indefinitamente finché il modello non verrà rimosso dal conto cliente.
    * Data di fine fatturazione: selezionare questa opzione e immettere l'ultima data in cui la fattura può essere generata.  
11. Nel campo **Importo cumulativo massimo**, immettere l'importo cumulativo massimo dopo il quale la generazione delle fatture verrà interrotta. Immettere l'importo cumulativo massimo che può essere raggiunto utilizzando il modello selezionato. Se si immette, ad esempio, 1.000,00 e vengono generate fatture mensili per 100,00 ciascuna, la generazione delle fatture verrà interrotta dopo la decima fattura.  
12. nella sezione **Genera fatture ricorrenti tramite il valore predefinito da** selezionare Modello di fattura a testo libero o Conto cliente. Scegliere se utilizzare il modello di fattura a testo libero o il conto cliente per determinare i valori predefiniti per lingua, profilo registrazione, fascia IVA, fascia IVA articoli, codice elenco, paese di consegna, valuta, termini di pagamento, metodo di pagamento, specifica di pagamento, scadenzario pagamenti, sconto di cassa, dimensioni finanziarie e distinta ordine di accredito quando vengono create le fatture.  
13. Nel campo **Criterio di ricorrenza**, selezionare il criterio di ricorrenza.
    + Giornaliero: selezionare questa opzione e immettere il numero di giorni nel campo Per. Se si immette, ad esempio, 15, la fattura verrà generata ogni 15 giorni per il cliente specificato.
    + Settimanale: selezionare questa opzione e immettere il numero di settimane nel campo Per. Se si immette, ad esempio, 2, la fattura verrà generata ogni 2 settimane per il cliente specificato.
    + Mensile: selezionare questa opzione e immettere il numero di mesi nel campo Per. Se si immette, ad esempio, 6, la fattura verrà generata ogni 6 mesi per il cliente specificato.
    + Annuale: selezionare questa opzione e immettere il numero di anni nel campo Per. Se si immette, ad esempio, 2, la fattura verrà generata ogni 2 anni per il cliente specificato.  
14. Nel campo **Per** immettere un numero.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]