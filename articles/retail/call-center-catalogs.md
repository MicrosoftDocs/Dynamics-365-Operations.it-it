---
title: Cataloghi del servizio clienti
description: Questo argomento descrive le funzionalità specifiche del servizio clienti per i cataloghi in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 65c1c3070aa48bf7a2016534071693716fabe831
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562743"
---
# <a name="call-center-catalogs"></a>Cataloghi del servizio clienti

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità specifiche del servizio clienti collegate alle funzionalità di catalogo in Microsoft Dynamics 365 for Retail.

Le funzionalità del catalogo disponibili in Dynamics 365 for Retail possono essere utilizzate per più scopi. Inizialmente le funzionalità del catalogo sono state create per supportare le integrazioni di e-commerce di terze parti. L'impostazione di un catalogo ha consentito alle società di creare un raggruppamento di prodotti e attributi che potessero essere pubblicati esternamente a uso e consumo di una soluzione di e-commerce di terze parti.

Con l'aggiunta del supporto di canale di servizio clienti a Dynamics 365 for Retail, il concetto di catalogo è stato esteso per includere funzionalità di supporto e di gestione correlate ai tradizionali cataloghi di marketing diretto a consumatori. Un società che si rivolge direttamente ai consumatori produce spesso cataloghi stampati, che vengono spediti per posta a uno o più segmenti di consumatori. Questi cataloghi contengono in genere promozioni o offerte specifiche che vengono onorate solo se il cliente fornisce un codice di identificazione del catalogo al momento della creazione dell'ordine.

Le società di marketing che si rivolgono direttamente ai consumatori sono concentrate sul tracciamento della risposta a questi cataloghi per verificare che i costi di produzione e spedizione di tali cataloghi siano giustificati. Per tenere traccia della risposta, sul retro del catalogo è presente un codice stampato che viene richiesto e applicato quando il destinatario del catalogo chiama per effettuare un ordine telefonicamente (o, come avviene più frequentemente in questi anni, viene inserito dal cliente quando effettua un ordine online). Sebbene esistano diversi termini standard per identificare questo codice di tracciamento del catalogo (tra cui codice chiave, codice promo, codice catalogo, codice di origine), in Dynamics 365 for Retail viene chiamato **ID codice di origine**.

## <a name="basic-catalog-setup"></a>Impostare il catalogo di base

Passare a **Retail** \> **Cataloghi e assortimenti** \> **Tutti i cataloghi** per configurare un catalogo.

Quando si crea un nuovo catalogo, è necessario prima di tutto collegarlo a uno o più canali di vendita al dettaglio. Questa operazione viene eseguita nella Scheda dettaglio **Canali di vendita al dettaglio** del modulo di **impostazione del catalogo**. Fare clic su **Aggiungi** e selezionare uno o più canali di vendita al dettaglio. Per la creazione del catalogo possono essere utilizzati solo gli articoli collegati al canale selezionato [assortimenti](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments).

Per aggiungere prodotti a un catalogo, è necessario selezionare una gerarchia di navigazione. La gerarchia di navigazione supporta la struttura di categorie del catalogo. È necessario selezionare una delle gerarchie di navigazione collegate ai canali di vendita al dettaglio selezionati nella Scheda dettaglio **Canali di vendita al dettaglio** della pagina **Catalogo**. Se un canale di navigazione non viene collegato prima a un canale, passare a **Retail** \> **Impostazione canale** \> **Categorie canale e attributi del prodotto** per collegare l'impostazione predefinita della gerarchia di navigazione a ognuno dei canali di vendita al dettaglio.

Nella scheda di menu **Cataloghi**, nella pagina **Impostazione catalogo**, fare clic su **Aggiungi prodotti** per configurare i prodotti da aggiungere al catalogo oppure selezionare un nodo nella gerarchia di navigazione (quando si seleziona un nodo, la schermata cambia consentendo di aggiungere i prodotti direttamente a una categoria nel catalogo).

Fare clic su nodo principale della gerarchia del catalogo per tornare alla visualizzazione principale dell'intestazione del catalogo. Configurare le dati di scadenza e di validità in base alle esigenze nella Scheda dettaglio **Generale**.

Prima che il catalogo sia disponibile all'utilizzo, deve essere pubblicato. Fare clic su **Convalida catalogo** nel menu **Cataloghi** per elaborare una convalida. Si tratta di un'azione obbligatoria che convalida la precisione dell'impostazione necessaria. Fare clic su **Visualizza risultati** per vedere i dettagli della convalida. Se vengono rilevati errori, è necessario correggere i dati ed eseguire nuovamente la convalida finché la convalida non sia stata superata.

Dopo la conferma della convalida, fare clic su **Flusso di lavoro** nel menu per avviare il flusso di lavoro di approvazione. Fare clic su **Invia** nel menu **Flusso di lavoro** per eseguire il processo. Configurare i passaggi e gli utenti autorizzati per il flusso di lavoro da **Retail** \> **Impostazione sedi centrali** \> **Flussi di lavoro per la vendita al dettaglio**. Il flusso di lavoro definisce i passaggi necessari per impostare il catalogo sullo stato **Approvato**. Quando il catalogo è nello stato **Approvato**, è possibile fare clic sull'opzione **Pubblica** nel menu **Cataloghi** per completare il processo. Dopo che il catalogo si trova nello stato **Pubblicato**, può essere utilizzato nell'ordine registrazione del servizio clienti ed è possibile inviare i processi del catalogo.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Utilizzare i cataloghi per determinare i prezzi e le promozioni di ordini cliente

Un motivo fondamentale per la definizione del catalogo da utilizzare con un servizio clienti è quello di poter configurare prezzi e promozioni specifici per il catalogo. I clienti che ordinano dal catalogo riceveranno questi prezzi e queste promozioni nell'ordine di registrazione del servizio clienti se l'**ID codice di origine** del catalogo viene applicato all'intestazione o alle righe.

Per configurare prezzi specifici per il catalogo, selezionare l'opzione **Gruppi prezzi** nella scheda **Cataloghi** per collegare uno o più gruppi di prezzi al catalogo. Tutti gli accordi commerciali, i giornali di registrazione rettifiche prezzo e gli sconti avanzati per la vendita al dettaglio (soglia, quantità, unità e corrispondenza) che sono stati collegati allo stesso gruppo di prezzi verranno applicati quando i clienti ordinano dal catalogo.

Nella Scheda dettaglio **Codici di origine**, fare clic su **Aggiungi** per aggiungere uno o più identificatori **ID codice di origine** al catalogo. Questo è il codice che verrà applicato durante l'ordine di registrazione del servizio clienti all'intestazione (e alle righe) dell'ordine cliente. Questo codice viene utilizzato per collegare l'ordine cliente al catalogo e in ultima analisi ai gruppi di prezzi e a tutti i prezzi speciali e le promozioni che sono stati configurati.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>Utilizzare l'ID di origine per tenere traccia dei costi e delle velocità di risposta

Quando si definisce l'**ID codice di origine**, è possibile facoltativamente collegarlo a un **ID mercato di destinazione**. L'**ID mercato di destinazione** può essere definito in **Retail** \> **Clienti** \> **Mercato di destinazione**. Il mercato di destinazione è un elenco di clienti e/o prospect che appartengono a un segmento definito dall'utente. Il collegamento dei dati del prospect o del cliente all'ID codice sorgente consente una migliore visibilità sui destinatari del catalogo. Se un cliente è collegato a un mercato di destinazione e questo è collegato a un catalogo/ID codice di origine attivo, gli utenti del servizio clienti saranno in grado di vedere quali cataloghi sono stati ricevuti da un cliente selezionando l'opzione di menu **Codici di origine** nella scheda di menu **Clienti** della pagina **Servizio clienti**. Durante un ordine di registrazione, gli utenti del servizio clienti possono inoltre vedere i cataloghi specifici inviati a un cliente dall'elenco a discesa **Origine** nell'intestazione dell'ordine cliente. Se si modifica il filtro da **Tutti** a **Di destinazione**, l'utente potrà vedere gli specifici cataloghi attivi inviati al cliente. Questa opzione di filtro è utile nei casi in cui il cliente ha dimenticato il catalogo o non riesce a individuare o a leggere il codice del catalogo quando chiama per creare un ordine cliente.

È possibile collegare più ID codice di origine a un catalogo. Questa operazione viene spesso utilizzata quando una società vuole tenere traccia della velocità di risposta di segmenti diversi. Lo società fornisce lo stesso codice di catalogo a segmenti di clienti diversi, per poter tenere traccia della velocità di risposta, fino al livello di segmento, all'interno di un determinato evento di catalogo.

Se si seleziona un record di **ID codice di origine** specifico e si fa clic sull'opzione **Dettagli** nella Scheda dettaglio **Codici di origine**, vengono visualizzati campi aggiuntivi i cui vengono acquisiti i dati sulle proiezioni di vendita, i costi di spedizione per posta e le dati di spedizione per posta. Questi dati sono utili per eseguire l'analisi dettagliata dell'efficacia del catalogo. Gli utenti possono tornare nel tempo in questa pagina e utilizzare i pulsanti **Analisi codice sorgente** e **Confronta promozioni** per attivare i report analitici basati sui dati di vendita correnti e per confrontare costi e budget rispetto alle cifre effettive.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Configurare gli script di articolo e di ordine specifici del catalogo

Quando un utente del servizio clienti crea un ordine cliente, può utilizzare gli script a video. Questi script basati su testo possono fornire informazioni supplementari che l'utente dove dire al cliente. Possono inoltre essere promemoria/note interne che l'utente del servizio clienti deve esaminare e utilizzare durante la creazione dell'ordine cliente.

È spesso utile disporre di set diversi di script per cataloghi diversi. Nella Scheda dettaglio **Script**, sono disponibili script predefiniti che possono essere collegati a un catalogo. Utilizzare il campo **Tempo** per determinare se lo script apparirà all'inizio dell'ordine (non appena viene inserito l'ID codice di origine nell'intestazione dell'ordine) o alla fine dell'ordine (nel modulo riepilogativo dell'ordine cliente).

Quando si seleziona un nodo nella gerarchia del catalogo e si utilizzano i dati nella Scheda dettaglio **Prodotti**, gli utenti possono inoltre collegare gli script specifici a cataloghi o articoli mediante l'azione **Script**.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Configurare articoli di up-selling e cross-selling specifici del catalogo

È possibile collegare suggerimenti di up-selling/cross-selling a un articolo dall'impostazione di prodotti, ma in alcuni casi, è possibile che una società voglia promuovere articoli di up-selling/cross-selling speciali presso i clienti che ordinano un prodotto specifico da un catalogo specifico. Nella Scheda dettaglio **Prodotti**, selezionare un articolo e fare clic su **Up-selling/cross-selling articoli** per configurare i prodotti da vendere in up-selling o cross-selling a clienti che acquistano l'articolo selezionato dal catalogo. Durante la registrazione dell'ordine del servizio clienti, gli articoli in up-selling/cross-selling specifici del catalogo appariranno sullo schermo al poto dei prodotti di up-selling/cross-selling standard che potrebbero essere stati configurati per quell'articolo tramite la solita configurazione di prodotto.

Gli articoli in up-selling/cross-selling possono trarre vantaggio anche delle funzionalità di script per mostrare messaggi specifici che verranno visualizzati all'utente quando l'articolo in up-selling/cross-selling viene visualizzato durante la registrazione dell'ordine. Gli script correlati a prodotti in up-selling/cross-selling configurati in modo specifico per un prodotto di catalogo appariranno solo quando il codice di origine di quel catalogo viene applicato nella registrazione dell'ordine del servizio clienti.

## <a name="catalog-page-analysis"></a>Analisi della pagina Catalogo

Nella scheda **Cataloghi**, sono disponibili opzioni per configurare **Pagine catalogo**. Questa funzionalità consente di definire pagine e tipi di pagina specifici per il catalogo stampato e i costi associati.

Quando si configurazione i prodotti nel catalogo, utilizzare l'azione **Layout pagina prodotti** per definire le pagine specifiche, la percentuale di pagina e la posizione dei dettagli di pagina per l'articolo. La configurazione di questi dati consente agli utenti di usufruire del **Report analisi area catalogo**. Questo report è disponibile passando a **Retail** \> **Report servizio clienti** \> **Report analisi area catalogo**. Questo report analizza le vendite piazzate con il catalogo (ordini cliente in cui l'ID di origine per il catalogo è stato precedentemente associato all'intestazione o riga dell'ordine) e la percentuale di pagina e i costi associati per offrire un tradizionale report di marketing diretto **Analisi pollice quadrato**.

## <a name="catalog-requests"></a>Richieste catalogo

Poiché i cataloghi sono configurati e pubblicati in Dynamics 365 for Retail, è possibile utilizzare la funzionalità **Invia catalogo**. Questa funzionalità è disponibile nelle pagine **Ricerca cliente** e **Servizio clienti**. Dopo avere selezionato un record di cliente tramite **Ricerca cliente** o mentre si visualizza un account di clienti selezionati da **Servizio clienti**, gli utenti possono selezionare l'opzione **Invia catalogo** che visualizza una finestra di dialogo in cui l'utente può scegliere da un elenco di cataloghi attivi e pubblicati. Un utente può selezionare un catalogo e una quantità, nonché un ID codice di origine specifico da inviare. Quando l'utente fa clic su **Invia**, viene memorizzata una richiesta che può successivamente essere gestita stampando il report **Richieste catalogo**. Questo report è disponibile passando a **Retail** \> **Report servizio clienti** \> **Report richieste catalogo**. Questo report elenca tutte le richieste di catalogo, inclusi i dettagli del nome e dell'indirizzo del cliente che ha richiesto il catalogo. Questo report può essere utilizzato internamente oppure è possibile trasmettere i dati a terze parti che si occupano di inviare fisicamente il catalogo al cliente.

## <a name="additional-features"></a>Funzionalità aggiuntive

Nella scheda **Cataloghi** sono inoltre disponibili le opzioni di configurazione **Scadenzario pagamenti** e **Prodotti gratuiti**. Se l'ID codice di origine collegato al catalogo viene applicato durante la registrazione dell'ordine del servizio clienti, il cliente è idoneo a ricevere prodotti gratuiti o a utilizzare scadenziari di pagamento del catalogo specifici, in base a quanto definito. Se è necessario limitare la selezione del cliente ai soli scadenziari di pagamento collegati al catalogo e non a tutti gli scadenziari attivi nel sistema, è possibile selezionare la casella di controllo **Consenti solo piani catalogo** per uno o più ID codice di origine definiti per rafforzare tale limitazione.

## <a name="additional-notes"></a>Note aggiuntive

Attualmente, quando un ID codice di origine viene applicato a un ordine cliente nel servizio clienti, viene utilizzato per determinare prezzi, promozioni, script up-selling e cross-selling specifici del catalogo. Il sistema non impedirà l'ordine nell'ordine cliente di un prodotto che non è presente nel catalogo. Se un articolo ordinato non è presente nel catalogo, il sistema utilizza prima di tutto il **Gruppo di prezzi** che è definito nel canale del servizio clienti (**Retail** \> **Canali** \> **Servizi clienti** \> **Tutti i servizi clienti**) per il prezzo dell'articolo o le promozioni. Se non viene trovato alcun prezzo di canale, viene utilizzato il prezzo di vendita di base dell'articolo.
