---
title: Configurare i layout schermo per POS
description: Di seguito vengono fornite informazioni sui layout dello schermo per le esperienze si Microsoft Dynamics 365 for Retail POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dd2a42ac824dcf55646594b7cb686401214bb3bc
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="configure-screen-layouts-for-pos"></a>Configurare i layout schermo per POS

[!include[banner](includes/banner.md)]


Di seguito vengono fornite informazioni sui layout dello schermo per le esperienze si Microsoft Dynamics 365 for Retail POS.

L'interfaccia utente Microsoft Dynamics 365 for Retail POS può essere configurata utilizzando una combinazione di profili visivi e di layout dello schermo assegnati a punti vendita, registratori di cassa e/o agli utenti.

## <a name="visual-profile"></a>Profilo visivo
I profili visivi vengono assegnati ai registratori di cassa e vengono utilizzati per specificare gli elementi visivi specifici del registratore e condivisi tra gli utenti. Qualsiasi utente che accede al registratore di cassa visualizzerà gli stessi contenuti, colori e immagini. 

**Numero di profilo**: il numero di profilo costituisce l'identificatore univoco per il profilo visivo. 

**Descrizione**: la descrizione consente di specificare un nome significativo che contribuirà a identificare il profilo corretto per la specifica situazione.

**Contenuto**: gli utenti possono scegliere tra i temi chiari o scuri dell'applicazione. Queste impostazioni influenzano i colori di sfondo e il carattere nell'app.

**Colore accento**: il colore accento viene utilizzato nel POS per distinguere o evidenziare alcuni elementi visivi ad esempio riquadri, pulsanti di comando o collegamenti ipertestuali. Questi elementi sono in genere elementi su cui è possibile eseguire azioni.

**Colore intestazione**: il colore dell'intestazione consente all'utente di configurare il colore dell'intestazione di pagina per soddisfare le esigenze di marchio del rivenditore. Questa funzionalità è disponibile solo nella versione 1611 di Dynamics 365 for Retail.

**Sfondi di accesso**: gli utenti possono specificare un'immagine di sfondo per la schermata di accesso. Le dimensioni dei file di immagine di sfondo devono essere mantenute il più ridotte possibile in quanto la memorizzazione e il caricamento di file di grandi dimensioni può avere un impatto sul comportamento e sulle prestazioni dell'applicazione.

**Sfondo dell'applicazione**: il POS può inoltre utilizzare un'immagine di sfondo nell'applicazione anziché il colore pieno del tema. Analogamente per gli sfondi di accesso, si consiglia di mantenere le dimensioni il più ridotte possibile.

## <a name="screen-layouts"></a>Layout schermo
La configurazione del layout dello schermo determina le azioni, il contenuto e la posizione dei controlli dell'interfaccia utente nella schermata di benvenuto del POS e nella schermata della transazione. 

**Schermata di benvenuto**: nella maggior parte dei casi, la schermata di benvenuto corrisponde alla pagina che gli utenti visualizzano al momento dell'accesso al POS. La schermata di benvenuto può essere costituita da un'immagine del marchio e da griglie dei pulsanti che consentono di accedere alle operazioni del POS. In genere, le operazioni non specifiche alla transazione corrente vengono posizionate in questa schermata. 

**Schermata transazione**: la schermata transazione è lo schermo principale nel POS per l'elaborazione di transazioni di vendita e ordini. La schermata transazione può essere configurata mediante Progettazione layout schermo. 

**Schermata di avvio predefinita**: alcuni rivenditori preferiscono che il cassiere passi direttamente alla schermata delle transazioni dopo l'accesso. L'impostazione della schermata di avvio predefinita consente agli utenti di impostare questa schermata per ogni layout dello schermo.

### <a name="assignment"></a>Assegnazione

I layout dello schermo possono essere assegnati a livello di punto vendita, registratore di cassa o utente. L'assegnazione dell'utente ha la priorità sull'assegnazione dei punti vendita e del registratore di cassa e l'assegnazione del registratore ha la priorità sull'assegnazione del punto vendita. In uno scenario semplice in cui tutti gli utenti utilizzano lo stesso layout indipendentemente dal registratore o dal ruolo, il layout dello schermo può essere impostato solo al punto vendita. Nei casi in cui determinati registratori di cassa o utenti specifici richiedono i layout specializzati, questi possono essere assegnati in modo appropriato.

### <a name="layout-sizes"></a>Dimensioni layout

Questa funzionalità si applica solo alla versione 1611 di Dynamics 365 for Retail. Poiché in molti casi i layout dello schermo possono essere utilizzati con dimensioni e risoluzioni dello schermo diversi, gli utenti possono configurare i propri layout e contenuti per ciascuno di essi. L'applicazione POS sceglierà automaticamente la dimensione del layout più vicina per l'unità al momento dell'avvio. Un layout dello schermo può inoltre contenere le configurazioni per dispositivi compatti e completi. Questa configurazione consente di assegnare un utente a un singolo layout dello schermo supportato per diverse dimensioni e fattori in forma del punto vendita. 

**POS moderno - Completo**: il layout completo in genere è più adatto per schermi di maggiori dimensioni, ad esempio di monitor di PC o tablet. Gli utenti possono selezionare gli elementi dell'interfaccia utente da includere, determinarne la relativa dimensione e posizione e configurare le proprietà dettagliate. Il layout completo supporta entrambe le configurazioni orizzontale e verticale. 

**POS moderno - Compatto**: il layout compatto in genere è migliore per telefoni o tablet di piccole dimensioni. Le opzioni di progettazione sono limitate per i dispositivi compatti. Gli utenti possono configurare le colonne e i campi per il riquadro ricevuta e il pannello totali.

### <a name="screen-layout-designer"></a>Progettazione layout schermo

Ogni dimensione del layout in un layout dello schermo deve essere configurata mediante Progettazione layout dello schermo. Questa funzione consente agli utenti di specificare e configurare gli elementi dell'interfaccia utente della Schermata transazione. Progettazione layout dello schermo utilizza ClickOnce per scaricare, installare e avviare l'ultima versione dell'applicazione ogni volta che un utente accede. Assicurarsi di verificare i requisiti del browser per l'utilizzo di ClickOnce, alcuni browser, come Chrome, richiedono delle estensioni. 

**Tastierino numerico**: è l'input utente principale nella Schermata transazione del POS. Può essere configurato per visualizzare l'intero tastierino sullo schermo, ideale per touchscreen o solo il campo di input, che può essere utilizzato con una tastiera fisica. Le impostazioni del tastierino numerico sono disponibili solo nel layout completo. Nella versione 1611 di Dynamics 365 for Retail, i layout compatti hanno sempre il tastierino numerico completo disponibile nella Schermata transazione.

**Pannello totali**: può essere configurato in una o due colonne per visualizzare i campi come ad esempio conteggio righe, importo di sconto, addebiti, subtotale e imposta. Nella versione 1611 di Dynamics 365 for Retail, i layout compatti supportano solo una singola colonna dei totali. 

**Ricevuta**: il riquadro ricevuta contiene righe di vendita, pagamento e le informazioni di consegna per i prodotti e i servizi elaborati nel POS. È possibile specificare colonne, larghezze e posizione. Nei layout compatti in Dynamics 365 for Retail versione 1611, è possibile configurare informazioni aggiuntive che verranno visualizzate nella riga sotto la riga principale. 

**Scheda cliente**: vengono visualizzate le informazioni relative al cliente attualmente associato alla transazione. La scheda cliente può essere configurata per nascondere o visualizzare informazioni aggiuntive. 

**Controllo scheda**: può essere inserito nel layout dello schermo, altri comandi ad esempio il tastierino numerico, la carta cliente o le griglie dei pulsanti possono essere inseriti nella scheda. Controllo scheda è un contenitore che consente agli utenti di inserire ulteriore contenuto nello schermo. Controllo scheda è disponibile solo per i layout completi. 

**Immagine**: il controllo immagine può essere utilizzato per visualizzare il logo del punto vendita o un'altra immagine del marchio nello schermo di transazione. Controllo immagine è disponibile solo per i layout completi. 

**Prodotti consigliati**: se configurato per l'ambiente, il controllo prodotti consigliati visualizza suggerimenti sul prodotto basati su Machine Learning. Il controllo prodotti consigliati è disponibile solo per i layout completi Dynamics 365 for Retail versione 1611. **Controllo personalizzato** il controllo personalizzato agisce come segnaposto nel layout dello schermo e consente agli utenti di prenotare lo spazio per contenuto personalizzato. Controllo personalizzato è disponibile solo per i layout completi.

<a name="see-also"></a>Vedere anche
--------

[Installare lo strumento di progettazione layout di Retail POS](install-pos-layout-designer.md)




