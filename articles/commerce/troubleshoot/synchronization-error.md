---
title: Problemi di sincronizzazione degli ordini asincroni
description: Questo articolo descrive i motivi comuni dell'errore di creazione dell'ordine asincrono in Microsoft Dynamics 365 Commerce e fornisce i passaggi per la risoluzione dei problemi per aiutare gli utenti e i partner del sistema a capire cosa è andato storto.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815758"
---
# <a name="asynchronous-order-synchronization-issues"></a>Problemi di sincronizzazione degli ordini asincroni

[!include [banner](../../includes/banner.md)]

Questo articolo descrive i motivi comuni dell'errore di creazione dell'ordine asincrono in Microsoft Dynamics 365 Commerce e fornisce i passaggi per la risoluzione dei problemi per aiutare gli utenti e i partner del sistema a capire cosa è andato storto.

## <a name="symptom"></a>Sintomo

Gli ordini asincroni creati dall'e-commerce Dynamics 365 Commerce o dal POS non si riflettono in Commerce headquarters.

## <a name="troubleshooting"></a>Risoluzione dei problemi

La creazione dell'ordine può fallire in Commerce headquarters per diversi motivi, a seconda della fase in cui il processo di creazione dell'ordine non va a buon fine. I seguenti passaggi per la risoluzione dei problemi esaminano le possibili cause principali.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Verificare che la transazione relativa all'ordine asincrono abbia raggiunto Commerce headquarters

Per gli ordini e-commerce, in Commerce headquarters, vai a **Retail e Commerce \> Richieste di informazioni e report \> Transazioni punto vendita online**. Se disponi di un numero di conferma per l'ordine, filtra le transazioni inserendo il numero di conferma nel campo **ID riferimento canale**. Se non disponi del numero di conferma, filtra le transazioni inserendo il numero di conto cliente.

Per gli ordini POS, apri la pagina **Transazioni punto vendita** e filtra i record in base al numero di ricevuta o al numero di conto cliente. Se la transazione non viene trovata, esegui il processo delle transazioni del canale **P-0001**, che sincronizza le transazioni dai canali in Commerce headquarters. Se il processo **P-0001** non riesce, apri un ticket di supporto per il lavoro non riuscito. Se il processo **P-0001** viene completato, ma le transazioni non vengono ancora visualizzate in headquarters, apri un ticket di supporto che includa le relative informazioni.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>Verifica lo stato della sincronizzazione se la transazione è presente in headquarters ma non è collegata a un ordine cliente

Se la transazione è presente in headquarters, ma l'ordine cliente non è stato creato, apri la pagina **Transazioni punto vendita online** e seleziona la Scheda dettaglio **Stato sincronizzazione**. Se il processo **Sincronizza ordini** ha tentato di sincronizzare questa transazione, il campo **Stato ordine in sospeso** dovrebbe mostrare uno stato **Riuscito** o **Non riuscito**. Se lo stato è **Riuscito**, il campo ordine cliente deve essere presente in questa transazione. Se lo stato è **Non riuscito**, puoi visualizzare i dettagli dell'errore nel campo **Dettagli errori ordini** nella scheda Dettagli **Stato sincronizzazione**. Se non viene visualizzato nessuno di questi stati, non è stato effettuato alcun tentativo di elaborazione della transazione. In questo caso, puoi selezionare **Sincronizza ordine** nella parte superiore della pagina per eseguire il processo di sincronizzazione.

Assicurati che il processo **Sincronizza ordini** sia programmato per essere eseguito periodicamente, in modo che le transazioni asincrone possano essere create come ordini in headquarters.

Le seguenti sezioni forniscono informazioni su alcuni errori comuni e le risoluzioni proposte.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>Il campo Dettagli errore ordine mostra il seguente messaggio di errore: "La sequenza numerica è stata superata"

Le sequenze numeriche vengono utilizzate per creare ordini cliente in headquarters. Se tutti i numeri consentiti per una sequenza numerica sono esauriti, il sistema genera questo messaggio di errore. La sequenza numerica utilizzata per creare ordini cliente è disponibile in **Parametri effetti attivi di conto \> Sequenze numeriche \> Ordine cliente**. Per risolvere questo errore, correggi la sequenza numerica esistente o sostituiscila con una nuova sequenza numerica.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>Il campo Dettagli errori ordini mostra il seguente messaggio di errore: "Deve essere presente un servizio di pagamento predefinito per elaborare le transazioni con carta di credito"

Per correggere questo errore, conferma che è definito un pagamento predefinito in headquarters. Se non è definito alcun pagamento predefinito, è necessario definirne uno. Vai a **Contabilità clienti \> Impostazione pagamenti \> Servizi di pagamento** e verifica che l'opzione **Elaboratore predefinito nuove carte di credito** sia impostata su **Sì** per un servizio di pagamento.
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>Il campo Dettagli errore ordine mostra un messaggio di errore relativo alla struttura del conto

Il testo del messaggio di errore relativo alla struttura del conto può variare, come mostrano gli esempi seguenti. Tuttavia, gli errori condividono una causa principale comune correlata alla configurazione della struttura dei conti.

- "La registrazione dei risultati per il numero batch del giornale di registrazione 0009656328 Buono ARP-000959899 1,00 per il buono ARP-000959899 nell'azienda usrt verrà registrato come pagamento in eccesso o in difetto"
- "La registrazione dei risultati per il numero batch del giornale di registrazione 0009656328 Buono ARP-000959899 della struttura dei conti buono ARP-000959901 per la combinazione 618160, non è valida per la contabilità generale del conto principale aziendale condiviso"
- "La registrazione dei risultati per il numero batch del giornale di registrazione 0009656328 Buono ARP-000959899 Buono ARP-000959901 dichiarato dagli account società usrt"
- "La registrazione dei risultati per il numero batch 0009656328 Buono ARP-000959899 La registrazione è stata annullata"
    
Per correggere questi errori, verifica la precisione delle strutture dei conti. Per ulteriori informazioni, vedi [Configurare le strutture dei conti](/dynamics365/finance/general-ledger/configure-account-structures).
    
Dopo che l'errore è stato corretto, seleziona la transazione non riuscita, quindi **Sincronizza ordine** nella parte superiore della pagina per eseguire il processo di sincronizzazione.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Altri tipi di errori che potrebbero richiedere la correzione dei dati della transazione

Per correggere altri tipi di errori che potrebbero richiedere la correzione dei dati della transazione, puoi utilizzare la funzionalità "modifica e verifica transazioni". Per ulteriori informazioni, vedi [Modificare e controllare le transazioni](../edit-order-trans.md).
