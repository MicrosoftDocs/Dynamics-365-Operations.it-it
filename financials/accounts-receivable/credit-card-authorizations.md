---
title: Impostazione, autorizzazione e acquisizione della carta di credito
description: Questo articolo fornisce una panoramica dell&quot;autorizzazione della carta di credito in Microsoft Dynamics AX. Sono riportate informazioni sull&quot;impostazione di un servizio di pagamento, sull&quot;aggiunta di una carta di credito a un ordine cliente e sull&quot;annullamento di un&quot;autorizzazione.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40d950b04511e85d05106c274d1580a3daac7af7
ms.lasthandoff: 03/31/2017


---

# <a name="credit-card-setup-authorization-and-capture"></a>Impostazione, autorizzazione e acquisizione della carta di credito

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica dell'autorizzazione della carta di credito in Microsoft Dynamics AX. Sono riportate informazioni sull'impostazione di un servizio di pagamento, sull'aggiunta di una carta di credito a un ordine cliente e sull'annullamento di un'autorizzazione.

<a name="setting-up-the-credit-card-payment-service"></a>Impostazione del servizio di pagamento con carta di credito
------------------------------------------

Per utilizzare le carte di credito, è necessario impostare e attivare un servizio di pagamento nella pagina Servizi di pagamento. Un servizio di pagamento funge da tramite tra la persona giuridica e la banca che elabora gli addebiti su carta di credito del cliente. È necessario utilizzare un fornitore della carta di credito che viene elencato nel campo Connettore pagamenti e configurare un conto per tale fornitore. È quindi necessario impostare le altre opzioni nella pagina Servizi di pagamento, impostare i tipi di carta di credito per American Express, Discover, MasterCard e Discover nella pagina dei tipi di carta di credito e attivare il fornitore come fornitore predefinito. Per completare la configurazione, è necessario inoltre attenersi alla procedura seguente:
-   Nella pagina dei parametri di contabilità clienti specificare i parametri per l'utilizzo delle autorizzazioni della carta di credito.
-   Nella pagina termini di pagamento configurare i termini di pagamento per le carte di credito. Nel campo Tipo di pagamento selezionare Carta di credito.
-   Nella pagina Carte di credito cliente immettere le informazioni della carta di credito per i clienti.

## <a name="adding-a-new-credit-card"></a>Aggiunta di una nuova carta di credito
È possibile creare nuovi record della carta di credito nella pagina Clienti tramite le opzioni Cliente, Impostazioni, Carta di credito. È inoltre possibile creare record della carta di credito quando si immettono gli ordini cliente nella pagina Ordine cliente, utilizzando le opzioni Gestisci, Cliente, Carta di credito, Registra.
Aggiunta di una carta di credito a un ordine cliente
-------------------------------------

È possibile aggiungere una carta di credito per un ordine cliente selezionandola nell'area di ricerca relativa nella scheda dettaglio Prezzo e sconti nella pagina Ordine cliente. Per avviare il processo di autorizzazione, nel riquadro azioni, nella scheda Gestisci selezionare Carta di credito, quindi Autorizza.
Autorizzazione di una carta di credito
-------------------------

Quando una carta di credito viene autorizzata, il numero della carta e il nome del titolare della carta vengono verificati e il saldo in Avere disponibile viene confermato. Facoltativamente, vengono verificati il numero di verifica della carta di credito e l'indirizzo del titolare della carta. Il saldo in Avere disponibile del cliente viene quindi ridotto dell'importo della fattura. Il servizio di pagamento invia le informazioni per segnalare se la carta di credito è stata accettata o rifiutata. L'importo della fattura viene addebitato (acquisito) sulla carta di credito una volta fatturato l'ordine cliente.

### <a name="card-verification-value"></a>Valore di verifica carta

È possibile richiedere il valore di verifica della carta, talvolta definito codice di sicurezza. Per la carta American Express si tratta di un valore a quattro cifre. Per le carte Discover, MasterCard e Visa si tratta di un valore a tre cifre.

### <a name="address-verification"></a>Verifica indirizzo

Le informazioni sulla verifica dell'indirizzo vengono inviate sempre al fornitore dei servizi di pagamento. È possibile stabilire la quantità di informazioni necessaria per accettare una transazione. Assicurarsi di controllare con il fornitore se accetta queste informazioni. Di seguito sono le opzioni per la verifica dell'indirizzo:
-   **Accetta sempre transazione**: consente di accettare la transazione indipendentemente dai risultati della verifica dell'indirizzo.
-   **Titolare conto**: confrontare il nome del titolare della carta per la transazione con le informazioni del gestore della carta di credito.
-   **Indirizzo di fatturazione**: confrontare il nome del titolare della carta e l'indirizzo di fatturazione per la transazione con le informazioni del gestore della carta di credito.
-   **CAP fatturazione**: confrontare il nome del titolare della carta, l'indirizzo di fatturazione e il codice di avviamento postale per la transazione con le informazioni del gestore della carta di credito.

## <a name="data-support"></a>Supporto dati
Per ogni tipo di carta di credito supportato, è possibile specificare il livello di supporto dati. Il livello controlla quante informazioni relative a una transazione vengono trasferite al servizio di pagamento. Assicurarsi di controllare con il fornitore se è possibile fornire queste informazioni. Di seguito sono indicate le opzioni per il livello del supporto di dati:
-   **Livello 1**: trasferire la data della transazione, l'importo della transazione e la descrizione.
-   **Livello 2**: per trasferire le informazioni di livello 1, più gli indirizzi di spedizione e dell'esercente e le informazioni fiscali.
-   **Livello 3**: trasferire le informazioni di livello 2, più le informazioni sulla riga ordine.

## <a name="partial-payments"></a>Pagamenti parziali
Se si spedisce parte di un ordine, l'importo dell'ordine parziale viene acquisito e l'autorizzazione, che si riferiva all'importo dell'intero ordine, viene chiusa. Quindi, una nuova autorizzazione viene inviata per l'importo rimanente dell'ordine non spedito.

## <a name="voiding-an-authorization"></a>Annullamento di un'autorizzazione 
Per annullare un'autorizzazione della carta di credito, è possibile modificare il metodo di pagamento per sceglierne uno non correlato a una carta di credito.






