---
title: Configurare e utilizzare le sospensioni ordine servizio clienti
description: In questo argomento viene descritto come utilizzare le sospensioni sugli ordini utilizzando Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans, MCROrderEventSetup, MCROrderEventTable
audience: Application User
ms.reviewer: josaw
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 55b794029ec765162ccfca1f39f3816c6772273d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000436"
---
# <a name="configure-and-work-with-call-center-order-holds"></a>Configurare e utilizzare le sospensioni degli ordini del servizio clienti

[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le caratteristiche di sospensione ordine che Dynamics 365 Commerce ha per gli ordini dei servizi clienti.

## <a name="configuring-call-center-order-holds"></a>Configurazione di sospensioni ordine servizio clienti

Per utilizzare le caratteristiche della sospensione ordini del servizio clienti, è necessario definire codici di sospensione. Per creare un set di codici di sospensione definiti dall'utente, basati sui requisiti aziendali, passare a **Vendite e marketing** \> **Impostazioni** \> **Ordini cliente** \> **Codici sospensione ordine**. Facoltativamente è possibile contrassegnare con un flag uno dei codici di sospensione come codice di sospensione predefinito impostandone l'opzione **Impostazioni predefinite per ordine cliente** su **Sì**. Questo codice di sospensione verrà utilizzato ogni volta che un ordine cliente viene messo in attesa. Se un ordine cliente ha prenotato scorte e le prenotazioni devono essere rimosse automaticamente se l'ordine viene messo in attesa per un motivo specifico, impostare l'opzione **Rimuovi prenotazioni inventario** su **Sì** per i codici motivo.

Per specificare il tipo di nota che verrà acquisita quando gli utenti che mettono un ordine cliente in attesa immettono note opzionali, passare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti** e quindi nella Scheda dettaglio di **Impostazione vendite** nella scheda **Generale**, impostare il campo **Tipo di nota**. Utilizzare il campo **Stato ordine cliente "in attesa"** per definire il colore che verrà utilizzato per evidenziare gli ordini cliente che sono in attesa quando vengono visualizzati nella pagina **Servizio clienti**.

Per creare un set facoltativo di codici motivo di sospensione, passare a **Retail e Commerce** \> **Impostazione canale** \> **Codici informativi**. Questi codici informativi possono essere utilizzati come codice motivo secondario per definire ulteriormente il codice di sospensione principale. Selezionare **Nuovo** per creare un set di codici motivo e quindi selezionare **Sottocodici** per definire l'elenco dei motivi aggiuntivi. Per collegare tutti i codici informativi che si definiscono nel canale servizio clienti, passare a **Retail e Commerce** \> **Canali** \> **Servizi clienti** \> **Tutti i servizi clienti**. Nella Scheda dettaglio **Generale** impostare il campo **Codice sospensione**.

## <a name="putting-orders-on-hold"></a>Ordini in attesa

Gli ordini che gli utenti del servizio clienti creano nel programma Commerce di back-office possono essere messi in attesa manualmente o automaticamente in situazioni specifiche.

Durante la registrazione dell'ordine, ma prima che l'ordine venga inviato e confermato, gli utenti del servizio clienti potrebbero voler mettere un ordine in attesa per evitare che venga rilasciato al magazzino per continuare l'elaborazione. Ad esempio, il cliente che inserisce l'ordine potrebbe non essere pronto a procedere al commit oppure potrebbero mancare nell'ordine alcuni dati di importanza critica.

Nella pagina di registrazione dell'ordine, l'utente del servizio clienti può mettere un ordine in attesa utilizzando l'opzione **Sospensioni ordine** nella scheda **Ordine cliente** del menu di registrazione ordini. In alternativa, l'utente può selezionare la voce di menu **Pausa** nella pagina **Riepilogo ordine cliente** che appare quando seleziona **Completato** nell'ordine cliente del servizio clienti.

In entrambi i casi, viene visualizzata la pagina **Sospensioni ordine**. L'utente può quindi selezionare **Nuova** per creare una sospensione per l'ordine. Nel campo **Codice sospensione**, l'utente deve selezionare il codice che meglio descrive il motivo per la sospensione. Nel campo **Codice motivo**, utente può facoltativamente selezionare un codice aggiuntivo per fornire un secondo livello di descrizione della sospensione.

Nella Scheda dettaglio **Note**, nel campo **Note sospensione**, l'utente può immettere altre note a testo libero per fornire informazioni o testo aggiuntivo sulla sospensione. Queste note possono aiutare altri utenti che esaminano o utilizzano l'ordine sospeso in un secondo momento.

Dopo l'immissione e il salvataggio delle informazioni di sospensione, l'utente può chiudere la pagina **Sospensioni ordine**. L'utente torna quindi alla pagina di registrazione dell'ordine cliente. Se non è necessario eseguire altre azioni sull'ordine cliente, l'utente può chiudere la pagina di registrazione dell'ordine cliente.

Se il flag **Attiva completamento ordine** è attivato nel canale servizio clienti, non è necessario che venga applicato il pagamento a un ordine messo in attesa. Di contro, per un ordine cliente che non viene messo in attesa, gli utenti non possono uscire dalla pagina di registrazione dell'ordine cliente senza applicare il pagamento. Naturalmente, il pagamento verrà richiesto prima del rilascio della sospensione dell'ordine.

Inoltre, gli utenti del servizio clienti possono inserire una sospensione manuale per frode su ordini che per qualche motivo ritengono sospetti. Gli ordini possono inoltre essere messi in attesa automaticamente quando soddisfano le regole e i criteri di frode attivi. Per ulteriori informazioni su questo tipo di sospensione ordine, vedere [Impostare avvisi antifrode](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Visualizzazione e gestione di ordini in attesa

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Visualizzazione delle informazioni di sospensione per un singolo ordine cliente

Nella pagina **Servizio clienti**, gli utenti possono identificare visivamente gli ordini in attesa, in quanto le righe ordine vengono evidenziate con un colore specifico. Questo colore viene definito dal campo **Stato ordine cliente "in attesa"** della pagina **Parametri contabilità clienti**.

> [!NOTE]
> Se la riga viene selezionata nella pagina, il colore di evidenziazione non è visibile.

Gli utenti possono inoltre visualizzare informazioni dettagliate sullo stato per un ordine cliente per scoprire se l'ordine è in attesa. Le informazioni di stato dettagliate sono accessibili dalla pagina **Tutti gli ordini cliente** o **Servizio clienti**. Se un ordine è in attesa, il flag **Non elaborare** è impostato e il campo **Stato dettagliato** mostra lo stato **In attesa** o **Sospensione per frode**, a seconda dello scenario.

Per visualizzare i dettagli di un singolo ordine in attesa, gli utenti possono aprire una visualizzazione dettagliata della pagina **Ordine sospeso** dalla pagina **Servizio clienti**, utilizzando il menu **Opzioni** per l'ordine selezionato. Gli utenti possono inoltre accedere a questa visualizzazione dalla pagina **Tutti gli ordini cliente**, selezionando la voce di menu **Sospensioni ordine** nella scheda **Ordine cliente**.

### <a name="viewing-all-orders-that-are-on-hold"></a>Visualizzazione di tutti gli ordini in attesa

Per visualizzare tutti gli ordini che sono stati messi in attesa manualmente o automaticamente, passare a **Retail e Commerce** \> **Clienti** \> **Sospensioni ordine**.

Il workbench **Sospensioni ordine** offre una visualizzazione elenco di tutti gli ordini che sono in attesa a causa di azioni di sospensione manuale o per frode. Usufruendo delle opzioni di filtro e di ordinamento standard presenti nella pagina, gli utenti possono creare visualizzazioni che consentono loro di utilizzare o gestire codici di sospensione specifici che devono esaminare. Il workbench **Sospensioni ordine** indica inoltre il numero di giorni che un ordine rimane in attesa. Queste informazioni consentono agli utenti di assegnare priorità alla coda.

Per ottenere una visualizzazione più dettagliata degli ordini in attesa, gli utenti possono fare clic sull'opzione **Sospensione ordine** nel menu. Questa visualizzazione fornisce informazioni sul cliente, eventuali note applicate all'ordine, al cliente o all'azione di sospensione. La visualizzazione fornisce inoltre i dettagli sul motivo di una sospensione automatica, se l'ordine è stato messo in attesa perché è associato una regola di frode.

Sia nella visualizzazione elenco sia nella visualizzazione dettagliata della pagina **Sospensione ordine**, gli utenti possono visualizzare o modificare informazioni aggiuntive relative agli ordini, ad esempio pagamenti, totali e le note.

Le opzioni nella scheda **Sospendi check out** possono essere utili se più utenti della società utilizzano la coda di sospensione contemporaneamente. Selezionando l'opzione **Estrai**, gli utenti possono indicare che stanno lavorando per esaminare e controllare la sospensione dell'ordine. In questo modo, gli altri utenti non sprecano tempo tentando di effettuare lo stesso lavoro. Nella visualizzazione dettagliata della pagina **Sospensioni ordine**, gli utenti possono visualizzare le informazioni sulla data e all'ora di estrazione e l'utente che ha effettuato l'estrazione del record sospeso.

Dopo l'estrazione del record sospeso, solo l'utente che lo ha estratto può annullare l'estrazione. Tale restrizione viene utilizzata per impedire agli utenti di prendere record a cui altri utenti stanno già lavorando. Per rilasciare un ordine di nuovo alla coda in modo che altri utenti possano utilizzarlo, l'utente che ha estratto il record seleziona l'opzione **Cancella estrazione**.

> [!NOTE]
> La sospensione non viene rilasciata con la cancellazione dell'estrazione.

In alcune situazioni, ad esempio quando un utente è malato o ha lasciato la società, i record estratti da tale utente devono probabilmente essere riassegnati a un altro utente. Un responsabile può riassegnare i record mediante l'opzione **Sostituisci estrazione**.

## <a name="releasing-orders-that-are-on-hold"></a>Rilascio di ordini in attesa

Sia nella visualizzazione elenco sia nella visualizzazione dettagliata della pagina **Sospensioni ordine**, la scheda **Cancella sospensione** contiene le opzioni utilizzate per rilasciare una sospensione di ordine. Utilizzare l'opzione **Cancella sospensioni** per rilasciare un ordine dal codice di sospensione selezionato.

Gli ordini del servizio clienti richiedono il pagamento. Di conseguenza, una sospensione non può essere cancella completamente se non è stato applicato il pagamento all'ordine. Nella pagina **Parametri servizio clienti**, nella scheda **Sospensioni** assicurarsi che il parametro **Invia quando cancellata** venga attivato. Questa impostazione assicura che un ordine di sospensione cancellato segua la logica di inoltro ordine corretta per convalidare e autorizzare i pagamenti. Se mancano i pagamenti, viene visualizzato un errore e il codice sospensione non viene cancellato.

Se il parametro **Invia quando cancellata** non è stato impostato, gli utenti devono selezionare l'opzione **Cancella e invia** del menu **Cancella sospensione** per garantire che l'ordine segua tutte le necessarie convalide di pagamento. Se l'invio dell'ordine ha esito negativo quando il flag **Attiva completamento ordine** è attivato nel canale servizio clienti, l'ordine viene rilasciato dallo stato di sospensione, ma il flag **Non elaborare** rimane impostato. Di conseguenza, l'ordine non viene rilasciato al magazzino fino a quando non vengono applicati e convalidati i pagamenti corretti.

Se gli utenti desiderano rimuovere una sospensione ma apportare altre modifiche all'ordine prima che venga rilasciato per l'elaborazione, possono selezionare l'opzione **Cancella e modifica**. Questa opzione rimuove il codice sospensione e apre i dettagli dell'ordine cliente per consentire agli utenti di apportare ulteriori modifiche all'ordine. Gli utenti possono inoltre applicare il pagamento e inviare l'ordine cliente attraverso la logica di convalida del pagamento quando il flag **Attiva completamento ordine** viene attivato nel canale servizio clienti.

## <a name="reporting-options"></a>Opzioni di creazione report

Passare a **Retail e Commerce** \> **Richieste di informazioni e report** \> **Report servizio clienti** \> **Report sospensioni ordine** per eseguire un report sulle sospensioni degli ordini per intervallo di dati, codice sospensione o altri criteri correlati.
