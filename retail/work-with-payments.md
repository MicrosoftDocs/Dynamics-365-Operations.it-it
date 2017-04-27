---
title: Metodi di pagamento in un servizio clienti
description: "In questo argomento vengono descritti i vari metodi di pagamento che è possibile utilizzare in un servizio clienti di Vendita al dettaglio e commercio."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 636d83ecc7732a164924352853603588cded0db4
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods-in-a-call-center"></a>Metodi di pagamento in un servizio clienti

[!include[banner](includes/banner.md)]


In questo argomento vengono descritti i vari metodi di pagamento che è possibile utilizzare in un servizio clienti di Vendita al dettaglio e commercio.

I metodi di pagamento utilizzati in altri canali in Vendita al dettaglio e commercio in Microsoft Dynamics AX, ad esempio contanti, assegni, carte di credito e gift card, possono essere utilizzati anche nei servizi clienti. Dopo aver impostato un metodo di pagamento per un servizio clienti, viene visualizzato come una delle opzioni nella sezione **Pagamenti** della pagina ** Ordine cliente ** per gli utenti del servizio clienti. È possibile inoltre impostare dei buoni sconto per offrire degli sconti ai clienti che effettuano un ordine presso il servizio clienti di un'organizzazione. I buoni sconto possono indicare un importo di sconto fisso o una percentuale sul prezzo dell'articolo o sul totale dell'ordine. Ad esempio, un buono basato su importo può offrire uno sconto di 75 euro quando il cliente spende 750 euro o oltre. Potete creare diversi tipi di buoni sconto, impostare buoni sconto padre/figlio e copiare o annullare un buono sconto. Utilizzare le opzioni nella tabella seguente per creare i buoni sconto.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Attributo**             | Nel campo **Tasso di rimborso** immettere sotto forma di percentuale il valore del tasso di rimborso atteso per il buono sconto e selezionare se il buono può essere usato una sola volta, se sarà emesso nuovamente in automatico o se è specifico per un cliente.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Valida**                 | Nei campi **Data di inizio** e **Data di fine** immettere le date del primo e dell'ultimo giorno in cui il buono sconto sarà valido.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Regole di inclusione/esclusione** | Nei campi **Cataloghi** e **Articoli** selezionare se vi sono dei cataloghi o degli articoli inclusi o esclusi dal buono sconto. Se si seleziona **Includi** o **Escluderi**, fare clic su **Imposta**, selezionare **Includi/escludi cataloghi** o **Includi/escludi prodotti**e immettere le informazioni sul catalogo o articolo. Se si seleziona **Nessuno** in questi campi, tutti i cataloghi o gli articoli saranno inclusi nel buono sconto.                                                                                                                                                                                                                          |
| **Varie**         | Se questo buono sconto non può essere utilizzato con altri sconti, selezionare la casella di controllo **Esclusivo**. Quindi, nel campo **Origine**, selezionare dove può essere utilizzato il buono sconto. Se si tratta di un buono sconto del produttore, selezionare la casella di controllo **Buono sconto produttore**.                                                                                                                                                                                                                                                                                                                                                                |
| **Buono sconto futuro**         | Se il buono verrà associato come padre ad altri buoni sconto, selezionare la casella di controllo **Buono sconto padre**. Se questo buono è associato come buono sconto figlio a un buono esistente, selezionare il buono padre nel campo **ID buono sconto padre**. Ad esempio, è possibile creare un buono sconto per il nuovo catalogo primavera. Tutti gli altri buoni sconto che si creano per il catalogo primavera saranno buoni figlio del buono sconto per il catalogo. I buoni figlio possono includere uno sconto del 20% per i nuovi ordini cliente, uno sconto del 10% su un articolo nuovissimo o uno sconto di 95,00 per gli ordini con importi di 1.000 o superiori. |

Se si invia un pagamento con carta di credito dalla pagina **Ordine cliente** e si riceve un messaggio indicante che la carta non è stata autorizzata, è possibile gestire l'autorizzazione manualmente. È possibile autorizzare, rifiutare o inviare nuovamente una transazione con carta di credito utilizzando la pagina **Gestione autorizzazioni**. Utilizzare la pagina parametri servizio clienti per configurare ulteriori opzioni di elaborazione dei pagamenti:

-   Le sopensioni assegno consentono al personale finanziario di elaborare gli ordini che sono stati sospesi perché è stato utilizzato un assegno come metodo di pagamento e l'importo di soglia di sospensione dell'assegno è stato superato. La sospensione può essere rilasciata manualmente o scade automaticamente alla fine del periodo configurato.
-   È possibile impostare soglie superiori alle quali i rimborsi che vengono emessi tramite assegno e carta di credito devono essere manualmente approvati. Qualsiasi rimborso che supera l'importo di soglia viene aggiunto alla coda di approvazione. Dopo l'approvazione del rimborso, l'ordine cliente reso può essere fatturato.





