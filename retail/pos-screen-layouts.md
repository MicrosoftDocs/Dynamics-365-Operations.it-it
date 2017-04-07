---
title: Configurare i layout dello schermo per il POS
description: Di seguito vengono descritti i layout dello schermo per Microsoft Dynamics 365 per le operazioni consente esperienze relative al dettaglio di (POS) del POS.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Configurare i layout dello schermo per il POS

Di seguito vengono descritti i layout dello schermo per Microsoft Dynamics 365 per le operazioni consente esperienze relative al dettaglio di (POS) del POS.

Microsoft Dynamics 365 per le operazioni consente l'interfaccia utente di (POS) del POS può essere configurata utilizzando una combinazione di profili e di layout dello schermo visivi, allocato ai punti vendita, i registri e/o agli utenti.

## <a name="visual-profile"></a>Profilo visivo
I profili visivi vengono assegnati ai registratori di cassa e vengono utilizzati per specificare gli articoli visivi che sono registro- specifici e sono condivisi tra gli utenti. Qualsiasi utente in cui vengono registrate nel registro avrà lo stesso contenuto, colori e immagini. ** Il numero di profilo ** il numero di profilo costituisce l'identificatore univoco per il profilo visivo. ** La descrizione ** la descrizione consente di specificare un nome significativo che contribuirà a identificare il profilo corretto per la specifica situazione. ** Il contenuto ** - utenti può scegliere tra i temi chiaro o scuri dell'applicazione. Queste impostazioni influenzano i colori di sfondo e il carattere nell'app. ** Il colore evidenziatore ** - colore evidenziatore viene utilizzato nel POS per distinguere o visualizzare alcuni elementi visivi ad esempio mattonelle, pulsanti di comando, o collegamenti ipertestuali. Questi elementi sono in genere perseguibili. ** Il colore dell'intestazione ** il colore dell'intestazione consente all'utente configurare il colore dell'intestazione di pagina per soddisfare le esigenze marcanti a caldo del rivenditore. Questa funzionalità è disponibile solo in Dynamics 365 per la versione 1611 delle operazioni. ** Gli ambiti di provenienza di accesso ** - utenti possono specificare un'immagine di sfondo per la schermata di accesso. Dimensione di file di immagine di sfondo deve essere tenuta a quanto possibile, ad esempio carico e archiviazione dei file di grandi dimensioni può avere un impatto sul comportamento e sulle prestazioni dell'applicazione. ** Lo sfondo dell'applicazione ** - L'articolo può inoltre utilizzare un'immagine di sfondo dell'applicazione anziché il colore solido di contenuto. Analogamente agli ambiti di provenienza di accesso, si consiglia di mantenere la dimensione del file minima possibili.

## <a name="screen-layouts"></a>Layout schermo
La configurazione del layout dello schermo determina le azioni, il contenuto e la posizione per i controlli non viene installata nella schermata di benvenuto di Retail POS e schermata di transazione. ** Lo schermo benvenuto ** - della maggior parte dei casi, lo schermo benvenuto la finestra che gli utenti possono momento della registrazione nel POS. Lo schermo benvenuto può essere costituito da marcante un'immagine a caldo e pulsanti nelle griglie consentono di accedere alle operazioni di Retail POS. In genere, le operazioni non specifiche alla transazione corrente vengono disposte in questo campo. ** Verrà visualizzata di transazione ** lo schermo di transazione è lo schermo principale nel POS per elaborare le transazioni di vendita e ordini. Verrà visualizzata di transazione può essere configurato mediante Progettazione layout dello schermo. ** Verrà visualizzata di inizio predefinita ** - alcuni rivenditori preferisce che il cassiere individuare direttamente su schermo delle transazioni dopo il collegamento. L'impostazione della schermata di inizio predefinita consente agli utenti di questo impostino per ogni layout dello schermo.

### <a name="assignment"></a>Assegnazione

I layout dello schermo possono essere assegnati al punto vendita, la registrazione, o a livello degli utenti. L'assegnazione dell'utente ha la priorità sull'assegnazione dei punti vendita e di registro e l'assegnazione di registro sostituisce assegnazione del punto vendita. In uno scenario semplice in cui tutti gli utenti utilizzano lo stesso layout indipendentemente dal registro o il ruolo, il layout dello schermo impostato solo al punto vendita. Nei casi in cui vengono registrati o utenti specifici richiedono i layout specializzati, possono essere assegnati in modo appropriato.

### <a name="layout-sizes"></a>Dimensioni layout

Questa funzionalità viene applicata solo a Dynamics 365 per la versione 1611 delle operazioni. Poiché in molti casi i layout dello schermo possono essere utilizzati nelle dimensioni della schermata e soluzioni diversi, gli utenti possono configurare i propri layout e contenuto per ciascuno di essi. L'applicazione di Retail POS sceglierà automaticamente la dimensione del layout più vicina per l'unità al momento dell'avvio. Un layout dello schermo può inoltre contenere le configurazioni per le unità complete relative a compatte. Questa configurazione consente a un utente venga assegnato a un singolo layout dello schermo supportato nelle diverse dimensioni e fattori in forma del punto vendita. ** Il POS moderno - intera ** - layout completare in genere dalla migliore utilizzato per le visualizzazioni maggiori ad esempio di monitor o di compressione del PC. Gli utenti possono selezionare gli elementi che viene installata da importare, determinano la relativa dimensione e disponibilità e la configurazione delle relative proprietà dettagliate. I layout completare supporto le configurazioni orizzontale di impostare l'orientamento verticale e. ** Il POS moderno - compatto ** - layout compatti in genere dalla migliore utilizzato per telefoni o piccole compressione. Le opzioni di progettazione sono limitate per le unità compatte. Gli utenti possono configurare le colonne e i campi per l'entrata e gli importi nei riquadri.

### <a name="screen-layout-designer"></a>Progettazione layout schermo

Ogni dimensione del layout in un layout dello schermo necessario configurare mediante Progettazione layout dello schermo. In Designer consente agli utenti specifichino e configurare gli elementi non viene installata dello schermo di transazione. In Progettazione layout dello schermo utilizza ClickOnce per scaricare, impostare e avviare ogni volta che l'ultima versione dell'applicazione un utente accedere a. Assicurarsi di verificare i requisiti del browser tramite un browser ClickOnce-, ad esempio Cromato, alle estensioni. ** Il tastierino numerico ** il tastierino numerico è Input utente principale nello schermo di Retail POS. Può essere configurato per visualizzare l'intero tastierino sullo schermo, ovvero ideale per gli attivabili ma al tatto, solo il campo di entrata, che può essere utilizzato con una tastiera fisica. Le impostazioni del tastierino numerico sono disponibili nel layout solo completo. In Dynamics 365 per la versione 1611 delle operazioni, i layout compatti è sempre il tastierino numerico pieno disponibile dallo schermo di transazione. ** Il pannello dei totali ** il pannello dei totali possono essere configurati in qualsiasi una o due colonne per visualizzare i campi ad esempio il numero della riga, sconti l'importo, le spese, il subtotale e l'imposta. In Dynamics 365 per la versione 1611 delle operazioni, i layout compatti supportano solo una singola colonna dei totali. ** Entrata ** - ** ** il pannello di entrata sono contenute righe di vendita, il pagamento e le informazioni di consegna per i prodotti e i servizi elaborati nel POS. È possibile specificare colonne, le larghezze e la posizione. Nei layout compatti in Dynamics 365 per la versione 1611 delle operazioni, è possibile configurare informazioni aggiuntive che verrà visualizzato nella riga nella riga principale. ** La scheda cliente ** la carta cliente vengono visualizzate le informazioni relative al cliente attualmente associato alla transazione. Nella scheda dei clienti può essere configurata per nascondere o visualizzare informazioni aggiuntive. ** Il controllo della scheda ** il controllo della scheda può essere inserito nel layout dello schermo e altri comandi ad esempio il tastierino numerico, la carta cliente, o le griglie dei pulsanti possono essere inseriti nella scheda. Per la scheda è un contenitore che consente agli utenti misurazione più contenuto nello schermo. Per la scheda è disponibile solo per i layout completare. ** Immagine ** il controllo di immagine può essere utilizzato per visualizzare il logo del punto vendita o un'altra immagine marcante a caldo sullo schermo di transazione. Il controllo di l è disponibile solo per i layout completare. ** Prodotti consigliati ** se configurato per l'ambiente, controllo di prodotti consigliato visualizzati i suggerimenti del prodotto in base all'apprendimento automatico. Il controllo di prodotti consigliato è disponibile solo per i layout completare in Dynamics 365 per la versione 1611 delle operazioni. ** Il controllo personalizzato ** il controllo personalizzato agisce come segnaposto nel layout dello schermo consente agli utenti di prenotare lo spazio al contenuto di personalizzato. Il controllo personalizzato è disponibile solo per i layout completare.

<a name="see-also"></a>Vedere anche
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)


