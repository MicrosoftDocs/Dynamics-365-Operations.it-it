---
title: Impostare canali servizio clienti
description: In questo argomento sono riportate informazioni su come elaborare gli ordini per i servizi clienti utilizzando Dynamics 365 Commerce.
author: josaw1
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters, MCRSalesTableOrderHistory, SalesOrderProcessingWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 64669c5bf71a4f1673f5ad2c46db7d3a2eaf2a97
ms.sourcegitcommit: 39f1455215e0363cd1449bbc6bdff489097f9ded
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092434"
---
# <a name="set-up-call-center-channels"></a>Impostare canali servizio clienti

[!include [banner](includes/banner.md)]

Una società può definire più canali servizio clienti in Dynamics 365 Commerce. I canali servizio clienti vengono configurati in **Retail e Commerce** \> **Canali** \> **Servizi clienti** \> **Tutti i servizi clienti** e sono specifici di una persona giuridica.

Quando si crea un nuovo canale servizio clienti, viene assegnato in modo sistematico un numero di unità operativa. Poiché i servizi clienti vengono creati come unità operative, gli utenti possono collegare il canale servizio clienti a varie funzionalità di Commerce, come assortimenti, cataloghi e modalità di consegna specifiche.

Un magazzino predefinito può essere configurato sul canale servizio clienti. Quindi, quando vengono creati ordini clienti in quel canale, il magazzino predefinito viene automaticamente inserito nell'intestazione dell'ordine cliente, a meno che non sia stato definito un altro magazzino per il cliente selezionato per l'ordine cliente. In tal caso, il magazzino del cliente viene inserito per impostazione predefinita.

Gli utenti devono essere collegati a un canale servizio clienti per utilizzare le funzionalità del servizio clienti. Qualsiasi ordine cliente creato da un utente viene automaticamente collegato al canale servizio clienti dell'utente. Attualmente, un singolo utente non può essere collegato a più canali servizio clienti contemporaneamente.

È anche possibile configurare un profilo di notifica e-mail sul canale servizio clienti. Il profilo definisce l'insieme di modelli di posta elettronica che viene utilizzato quando il messaggio viene inviato ai clienti che effettuano ordini tramite il canale servizio clienti. I trigger di posta elettronica possono essere configurati in base agli eventi di sistema, come l'invio dell'ordine o la spedizione dell'ordine.

Prima che le vendite possano essere elaborate correttamente attraverso un canale servizio clienti, per il canale devono essere definiti i [metodi di pagamento](/dynamics365/unified-operations/retail/work-with-payments) e le modalità di consegna corretti.

A livello del canale servizio clienti, è possibile definire altri valori predefiniti correlati alle dimensioni finanziarie che saranno collegate agli ordini creati da quel canale.

## <a name="options-for-order-processing-behavior"></a>Opzioni per il comportamento di elaborazione dell'ordine

Tre impostazioni nella configurazione di un servizio clienti hanno un effetto importante sulle funzionalità e funzioni disponibili per gli ordini cliente creati rispetto a tale servizio clienti: **Attiva completamento ordine**, **Attiva vendita diretta** e **Abilita controllo prezzo ordine**.

### <a name="enable-order-completion"></a>Attiva completamento ordine

L'impostazione **Attiva completamento ordine** sul canale servizio clienti ha un effetto importante sul flusso di ordini di ordini cliente immessi per quel canale. Quando questa impostazione è attivata, tutti gli ordini cliente devono superare una serie di regole di convalida prima che possano essere confermati. È possibile eseguire queste regole scegliendo il pulsante **Completa** che viene aggiunto nel riquadro azioni della pagina di ordine cliente. Tutti gli ordini cliente creati quando è attiva l'impostazione **Attiva completamento ordine** devono superare il processo di completamento dell'ordine. Questo processo applica l'acquisizione della logica di pagamento e di convalida dei pagamenti. Oltre all'applicazione dei pagamenti, la procedura di invio dell'ordine può attivare le [verifiche frodi](/dynamics365/unified-operations/retail/set-up-fraud-alerts) configurate nel sistema. Gli ordini che non superano la convalida antifrode e la convalida del pagamento vengono messi in attesa e non possono essere rilasciati per ulteriori elaborazioni (come il prelievo o la spedizione) finché il problema che ha causato la sospensione non viene risolto.

Quando l'impostazione **Attiva completamento ordine** è attivata per il canale servizio clienti, se le voci vengono registrate in un ordine cliente e l'utente del canale tenta di chiudere o accedere dal modulo di ordine cliente senza prima selezionare **Completa**, il sistema impone il completamento dell'ordine da elaborare aprendo la pagina di riepilogo dell'ordine cliente e richiedendo che l'utente invii correttamente l'ordine cliente. Se l'ordine non può essere inviato correttamente insieme al pagamento, l'utente può utilizzare la funzionalità [sospensioni ordine](/dynamics365/unified-operations/retail/work-with-order-holds) per mettere in attesa l'ordine. Se l'utente sta tentando di annullare l'ordine, deve annullarlo correttamente utilizzando la funzione Annulla o Elimina, a seconda della funzione consentita dalle impostazioni di sicurezza dell'utente.

Se l'impostazione **Attiva completamento ordine** è attivata per il canale servizio clienti, il campo **Stato pagamento** verrà tracciato nell'ordine. Il sistema calcola lo **Stato pagamento** quando l'ordine cliente viene inviato. Solo gli ordini che hanno uno stato di pagamento approvato possono venire spostati nel sistema per ulteriori passaggi di elaborazione degli ordini, come il prelievo e la spedizione. Se i pagamenti vengono rifiutati, il flag **Non elaborare** verrà abilitato nello stato dettagliato dell'ordine e questo metterà in attesa l'ordine fino alla risoluzione del problema di pagamento.

Inoltre, se l'opzione **Attiva completamento ordine** è attivata, quando gli utenti creano ordini cliente e sono in modalità di immissione voci, il campo **Origine** sarà disponibile nell'intestazione dell'ordine cliente principale. Il campo **Origine** viene utilizzato per acquisire un [codice sorgente del catalogo](/dynamics365/unified-operations/retail/call-center-catalogs) in uno scenario di vendita di direct marketing. Questo codice può quindi determinare prezzi speciali e promozioni.

Anche se l'impostazione **Attiva completamento ordine** è disattivata, gli utenti possono comunque applicare un codice sorgente a un ordine cliente. Tuttavia, devono prima aprire i dettagli dell'intestazione dell'ordine cliente per accedere al campo **Origine**. In altre parole, sono necessari alcuni clic aggiuntivi. Lo stesso comportamento si applica a funzioni come ordini completati e urgenti. Queste funzioni sono disponibili per tutti gli ordini creati nel servizio clienti. Tuttavia, quando l'impostazione **Abilita completamento ordine** è attivata, gli utenti possono visualizzare la configurazione di queste funzionalità nell'intestazione vendite mentre si trovano nella vista di immissione righe. Non è necessario eseguire il drill-in nei dettagli dell'intestazione dell'ordine clienti per trovare le impostazioni e i campi appropriati.

> [!NOTE]
> Quando la funzionalità **Pagamenti ordini Commerce multicanale** è abilitata, il pulsante **Attiva completamento ordine** del call center sarà nascosto nella sede centrale sulla Scheda dettaglio **Generale** del tuo canale su **Retail e Commerce \> Canali \> Call Center**.

### <a name="enable-direct-selling"></a>Attiva vendita diretta

Se l'impostazione **Attiva vendita diretta** è attivata per il canale servizio clienti, gli utenti possono usufruire delle funzionalità di upsell e cross-sell di Commerce. In questo caso, le finestre popup vengono visualizzate durante la registrazione ordine e suggeriscono altri prodotti che l'utente del servizio clienti può offrire al cliente. I prodotti suggeriti si basano sul prodotto che è stato appena ordinato nella riga dell'ordine cliente. Attualmente, i suggerimenti di upsell e cross-sell sono configurati a livello di articolo su prodotti o cataloghi. Se l'impostazione **Attiva vendita diretta** è disattivata per il canale servizio clienti, le finestre popup non vengono visualizzate durante l'immissione degli ordini, anche se per un articolo ordinato viene indicato un suggerimento di upsell o cross-sell valido.

Se l'impostazione **Attiva vendita diretta** è attivata, vengono attivati anche gli script e le immagini della pagina di registrazione dell'ordine cliente. In questo caso, un riquadro informativo è disponibile sul lato destro della pagina durante l'inserimento dell'ordine. Questo riquadro può mostrare script relativi al processo di registrazione ordine generico, al codice sorgente del catalogo applicato o agli script correlati agli articoli ordinati. Inoltre, il riquadro immagini può mostrare un'immagine del prodotto per gli articoli ordinati, se è stata definita un'immagine per l'articolo nella configurazione del prodotto

### <a name="enable-order-price-control"></a>Abilita controllo prezzo ordine

Se l'impostazione **Abilita controllo prezzo ordine** è attivata, solo gli utenti autorizzati possono modificare il prezzo di vendita di un articolo durante la registrazione ordine. Le modifiche devono essere comprese entro tolleranze definite. Gli utenti che non dispongono dell'autorizzazione appropriata devono invece inviare una richiesta di modifica del prezzo. La richiesta verrà quindi elaborata tramite i flussi di lavoro del sistema per la revisione e l'approvazione.

## <a name="channel-users"></a>Utenti canale

Quando si definisce il canale servizio clienti, è necessario collegare gli utenti del canale al servizio clienti. In caso contrario, il servizio clienti non può essere utilizzato nel sistema. Quando gli utenti eseguono l'accesso a Commerce e immettono ordini cliente o ordini di reso in una pagina relativa alla registrazione ordine, il loro ID utente viene convalidato rispetto alla configurazione del canale servizio clienti. Se un utente è collegato a un canale servizio clienti specifico, gli ordini creati dall'utente ereditano le caratteristiche e i valori predefiniti di quel canale.

Per impostazione predefinita, il flag **Vendita** nell'intestazione ordine cliente è attivato per tutti gli ordini creati dagli utenti del servizio clienti. Gli ordini possono quindi sfruttare le funzionalità di prezzo e promozioni specifiche del sistema Commerce.


Gli utenti che non sono collegati a un canale servizio clienti utilizzano le funzionalità di registrazione ordine standard di Microsoft Dynamics 365 Finance. Gli ordini che questi utenti registrano attraverso il modulo di registrazione ordine cliente non verranno sistematicamente identificati come ordini Commerce. Inoltre, questi ordini registrati da questi utenti non saranno soggetti a nessuna delle regole di elaborazione del completamento dell'ordine, della logica dei prezzi o di altre convalide degli ordini che possono essere definite nella configurazione del canale servizio clienti o nei parametri del sistema del servizio clienti.

Dopo aver completato la configurazione del canale servizio clienti e la definizione degli utenti del canale, per garantire il comportamento del sistema desiderato, assicurarsi che tutti i parametri necessari del servizio clienti siano definiti in **Retail e Commerce** \> **Impostazione canale** \> **Impostazione servizio clienti** \> **Parametri servizio clienti**. Assicurarsi che anche le sequenze numeriche correlate vengano definite.

> [!NOTE]
> Per utilizzare la funzionalità di servizio clienti, la chiave di configurazione per **Indirizzi di spedizione multipli** deve essere abilitata. Questa chiave di configurazione è disponibile nelle chiavi **Configurazione commercio** sotto **Amministrazione di sistema**\>**Impostazioni**\>**Configurazione licenza**. Ciò è necessario a causa della funzionalità di servizio clienti che esegue varie convalide in base all'indirizzo di consegna configurato a livello di riga ordine cliente. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
