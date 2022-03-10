---
title: Impostare un sito di e-commerce B2B
description: Questo argomento descrive come impostare un sito di e-commerce business-to-business (B2B) in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e012b88465e98e788f65697d95fc141d453888e3
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983319"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>Creare un sito di e-commerce B2B

[!include [banner](../../includes/banner.md)]

I siti di e-commerce business-to-business (B2B) forniscono alcune funzionalità chiave che ottimizzano il flusso di lavoro per un utente B2B. Questo argomento descrive come impostare un sito di e-commerce B2B in Microsoft Dynamics 365 Commerce. Passa attraverso i moduli e le impostazioni del sito che devono essere configurati per abilitare scenari specifici B2B.

## <a name="prerequisites"></a>Prerequisiti

- Per impostare un sito di e-commerce B2B, è necessario abilitare e configurare funzionalità specifiche nella sede di Commerce, come descritto in questo argomento.
- Le esperienze principali, come la scoperta del prodotto, le pagine dei dettagli del prodotto, il carrello e il checkout, sono alimentate dagli stessi moduli utilizzati per i siti di e-commerce business-to-consumer (B2C). Gli autori del sito dovrebbero avere familiarità con tutti i moduli supportati da Dynamics 365 Commerce. Per ulteriori informazioni, vedi [Panoramica Libreria moduli](../starter-kit-overview.md).
- In questo argomento si presume che gli autori del sito comprendano le basi del generatore di siti di Commerce, dei modelli, dei frammenti e delle pagine, in modo che possano abilitare le funzionalità B2B per i siti di e-commerce.

## <a name="site-level-settings"></a>Impostazioni a livello di sito

Puoi accedere alle impostazioni a livello di sito in Creazione di siti Web, in **Impostazioni sito \> Estensioni**. Le due impostazioni a livello di sito seguenti si applicano agli scenari B2B:

- **Abilita i pagamenti dell'account cliente**: questa proprietà consente agli utenti di pagare gli ordini utilizzando gli account dei clienti. I valori disponibili sono **Abilitato per i clienti B2B**, **Abilitato per i clienti B2C**, **Abilitato per tutti i clienti** e **Disabilitato per tutti i clienti**. Se il tuo sito B2B supporta gli account dei clienti, devi selezionare **Abilitato per i clienti B2B**.
- **Abilita i limiti di quantità dell'ordine**: questa proprietà consente di impostare dei limiti sul numero di articoli che possono essere ordinati per ogni prodotto o categoria. I valori disponibili sono **Abilitato per i clienti B2B**, **Abilitato per i clienti B2C**, **Abilitato per tutti i clienti** e **Disabilitato per tutti i clienti**.

> [!NOTE]
> Quando si aggiorna alla versione più recente della libreria dei moduli, è necessario seguire passaggi aggiuntivi per assicurarsi che le impostazioni del sito descritte in precedenza siano disponibili nel proprio ambiente. Per ulteriori informazioni, vedi [Aggiorna il file app.settings.json](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Crea pagine di registrazione dei partner commerciali

Per diventare un business partner, gli utenti devono prima inviare una richiesta di partner commerciali. Un collegamento alla pagina di richiesta del partner commerciale sarà disponibile sulla home page del B2B, in modo che gli utenti possano avviare il processo. Dopo che gli utenti hanno inviato una richiesta per diventare partner commerciali, riceveranno la conferma che la richiesta è stata inviata. 

### <a name="create-a-business-partner-request-page"></a>Crea una pagina di richiesta del partner commerciale

Il modulo **Iscrizione partner** su una pagina di richiesta del partner commerciale viene utilizzato per avviare le richieste degli utenti per diventare partner commerciali. Questo modulo ti consente di raccogliere le informazioni sull'utente necessarie per il processo di registrazione. Inoltre, il modulo **Indirizzo dell'account aziendale** viene utilizzato per acquisire l'indirizzo dell'utente.

Per impostare e configurare la pagina di richiesta del partner commerciale in Creazione di siti Web, attenersi alla seguente procedura.

1. Crea un modello denominato **Iscriviti**. Questo modello dovrebbe includere i seguenti moduli:

    - Iscrizione partner
    - Percorso di navigazione
    - Intestazione
    - Piè di pagina
    - Blocco contenuto
    - Blocco di testo
    - Raccolta prodotti

1. Usa il modello **Iscriviti** per creare una pagina denominata **Richiesta di partner commerciale**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla home page e inserisci **Home** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **Iscrizione partner** sotto il modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Intestazione**, accedi **Diventa un partner commerciale**.
1. Nello slot **Iscrizione partner**, aggiungi un modulo **Indirizzo dell'account aziendale**.
1. Nello slot **Contenitore**, aggiungi un modulo **Blocco di testo** sotto il modulo **Iscrizione partner**. Qui puoi definire alcuni termini e condizioni per il processo di registrazione.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.

### <a name="create-a-business-partner-request-confirmation-page"></a>Crea una pagina di conferma del partner commerciale

Dopo che una richiesta del business partner è stata inviata, dovrebbe essere mostrata all'utente una pagina di conferma per confermare l'invio. 

Per impostare e configurare la pagina di conferma di richiesta in Creazione di siti Web, attenersi alla seguente procedura.

1. Usa il modello **Iscriviti** creato in precedenza per creare una pagina denominata **Conferma richiesta partner**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Blocco contenuto**. Nel riquadro delle proprietà del modulo, in **Intestazione**, accedi a **Richiesta inviata**. Nel campo **RTF**, immetti **La richiesta è stata inoltrata**. In **Collegamenti**, configura un collegamento alla home page e immetti **Continua gli acquisti** come testo del collegamento.
1. Aggiungi un altro modulo **Contenitore** e aggiungi ad esso un modulo **Raccolta prodotti**.
1. Configura il modulo **Raccolta prodotti** con il consiglio o l'elenco delle categorie che desideri mostrare nella pagina.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.

Per aggiungere un collegamento a una pagina di conferma di richiesta in Creazione di siti Web, attenersi alla seguente procedura.

1. Vai alla pagina **Richiesta di partner commerciale** che hai creato in precedenza e seleziona **Modifica**. 
1. Seleziona lo slot del modulo **Iscrizione partner**. Nel riquadro delle proprietà, in **Collegamento alla pagina di conferma della registrazione**, configura il collegamento alla pagina di richiesta del partner commerciale creata in precedenza. 
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Aggiungere un collegamento alla richiesta del partner commerciale alla home page

Dopo aver creato le pagine di registrazione e conferma della richiesta del partner commerciale, è necessario rendere la pagina di registrazione accessibile tramite un collegamento nella home page. Puoi completare questa attività aggiungendo il collegamento a qualsiasi modulo **Blocco dei contenuti** nella home page.

Per aggiungere un collegamento a una richiesta di partner commerciale in Creazione di siti Web, attenersi alla seguente procedura.

1. Vai alla home page per il tuo sito e seleziona **Modifica**.
1. Seleziona uno slot del modulo **Blocco di contenuto**. Nel riquadro delle proprietà del modulo, in **Collegamenti**, configura un collegamento alla pagina di richiesta del partner commerciale creata in precedenza e immetti **Iscriviti per diventare un partner commerciale** o un testo simile al testo del collegamento. Aggiungi un'immagine come appropriato.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="account-management-landing-page"></a>Pagina di destinazione di gestione account

La pagina di destinazione della gestione dell'account include tutte le informazioni sulla gestione dell'account necessarie per i siti di e-commerce B2B e B2C. Solo gli utenti registrati possono visualizzare questa pagina.

Per creare e configurare una pagina di destinazione per la gestione dell'account B2B in Creazione di siti Web, segui questi passaggi.

1. Crea un modello denominato **Gestione conto**. Questo modello dovrebbe includere i seguenti moduli:

    - Intestazione
    - Piè di pagina
    - Percorso di navigazione
    - Riquadro di benvenuto conto
    - Riquadro generico conto
    - Riquadro indirizzo conto
    - Riquadro lista dei desideri conto
    - Riquadro indirizzo conto
    - Riquadro fedeltà conto
    - Riquadro saldo cliente conto
    - Riquadro modelli ordine conto
    - Utenti organizzazione
    - Elenco organizzazioni aziendale
    - Saldo del conto cliente
    - Righe modello ordine
    - Elenco modello ordine
    - Riquadro fattura conto
    - Elenco fatture
    - Dettagli fattura

1. Usa il modello **Gestione conti** per creare una pagina denominata **Account personale**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**. 
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla home page e inserisci **Home** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **Messaggio di benvenuto**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Benvenuto**.
1. Nello slot **Principale**, aggiungi un altro modulo **Contenitore** (**Contenitore 2**). Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**. Impostare il valore **Figli visualizzati** su **Due**. 
1. Nello slot **Contenitore 2**, aggiungi un modulo **Riquadro generico account**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Mio profilo**. In **Collegamenti**, configura un collegamento alla pagina **Mio profilo**. 
1. Nello slot **Contenitore 2**, aggiungi un altro modulo **Riquadro generico account**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Storico ordini**. In **Collegamenti**, configura un collegamento alla pagina Storico ordini.
1. Nello slot **Principale**, aggiungi un altro modulo **Contenitore** (**Contenitore 3**). Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**. Impostare il valore **Figli visualizzati** su **Due**. 
1. Nello slot **Contenitore 3**, aggiungi un modulo **Riquadro indirizzo account**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Il mio indirizzo**. In **Collegamenti**, configura un collegamento alla pagina **Il mio indirizzo**. 
1. Nello slot **Contenitore 3**, aggiungi un modulo **Riquadro elenco preferenze account**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Il mio elenco preferenze**. In **Collegamenti**, configura un collegamento alla pagina **Il mio elenco preferenze**.
1. Nello slot **Principale**, aggiungi un altro modulo **Contenitore** (**Contenitore 4**). Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**. Impostare il valore **Figli visualizzati** su **Due**. 
1. Nello slot **Contenitore 4**, aggiungi un modulo **Utenti organizzazione**. Nel riquadro delle proprietà del modulo, in **Intestazione**, accedi a **Utenti organizzazione**. 
1. Nello slot **Contenitore 4**, aggiungi un modulo **Riquadro saldo cliente conto**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Credito conto**. 
1. Nello slot **Principale**, aggiungi un altro modulo **Contenitore** (**Contenitore 5**). Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**. Impostare il valore **Figli visualizzati** su **Due**. 
1. Nel modulo **Contenitore 5**, aggiungi un modulo **Riquadro moduli ordini conto**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Modelli ordini**. 
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

> [!NOTE] 
> Alcune delle sezioni che hai aggiunto nei passaggi da 13 a 18 non verranno visualizzate nella canvas WYSIWYG in Creazione di siti Web, perché richiedono un account B2B registrato.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Crea e configura pagine e moduli del saldo cliente 

Gli account dei clienti possono essere utilizzati per pagare gli ordini. Il saldo disponibile in un conto cliente può essere visualizzato dalla pagina di gestione del conto di un utente.

### <a name="create-a-customer-balance-page"></a>Creare una pagina di saldo cliente 

Prima che gli utenti B2B registrati possano visualizzare il proprio saldo clienti, è necessario creare una pagina del saldo clienti. 

Per creare una pagina del saldo cliente in Creazione di siti Web segui questi passaggi.

1. Utilizza il modello **Gestione conti** creato in precedenza per creare una pagina denominata **Saldo cliente**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un altro modulo **Contenitore** (**Contenitore 3**). Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**. Impostare il valore **Figli visualizzati** su **Due**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla pagina di destinazione di gestione dei conti e immetti **Account personale** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **Saldo cliente conto**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Saldo conto**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.
1. Vai alla pagina di destinazione della gestione dell'account (**Account personale**) che hai creato in precedenza.
1. Nel riquadro delle proprietà per il modulo **Riquadro saldo cliente conto**, aggiungi un collegamento alla pagina di destinazione del cliente. 
1. Salva e pubblica la pagina.

La pagina del saldo del cliente è stata ora creata e gli utenti possono accedervi dalla pagina di destinazione della gestione dell'account.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Configura una pagina di checkout in modo che il saldo del cliente possa essere utilizzato come forma di pagamento

Il modulo **Pagamento conto cliente** è necessario per abilitare il saldo del cliente da utilizzare come forma di pagamento. Questo modulo dovrebbe essere aggiunto alla pagina di checkout come forma di pagamento. Per informazioni su come configurare una pagina di checkout e i moduli necessari per il pagamento, inclusi tutti i dettagli di pagamento, vedi [Modulo di checkout](../add-checkout-module.md).

Dopo aver configurato una pagina di checkout, devi aggiungere il modulo **Pagamento conto cliente** nella sezione pagamenti, quindi salva e pubblica la pagina. Gli utenti B2B potranno quindi accedere al sito di e-commerce e applicare il saldo cliente disponibile agli ordini durante il checkout.

Inoltre, in **Creazione di siti Web \> Estensioni**, devi assicurarti che la proprietà **Abilita i pagamenti dell'account cliente** è impostata su **Abilitato per i clienti B2B**.

## <a name="create-order-template-pages"></a>Crea pagine modello ordini

Puoi impostare due pagine di modelli degli ordini per un sito di e-commerce B2B: una pagina di elenco dei modelli degli ordini e una pagina di righe di modello degli ordini.

Una pagina di elenco dei modelli degli ordini mostra un elenco di tutti i modelli degli ordini disponibili. È impostato utilizzando il modulo **Elenco dei modelli degli ordini**. La pagina dell'elenco dei modelli degli ordini consente di creare o eliminare un modello e di aggiungere gli articoli in un modello al carrello.

Una pagina delle righe del modello degli ordini mostra i dettagli del modello degli ordini selezionato in una pagina di elenco dei modelli degli ordini. È impostato utilizzando il modulo **Righe dei modelli degli ordini**. Quando un utente seleziona il nome di un modello in una pagina di elenco dei modelli degli ordini, viene visualizzata la pagina delle righe del modello degli ordini che mostra i dettagli del modello. L'utente può quindi visualizzare e modificare gli elementi nel modello.

### <a name="create-an-order-templates-list-page"></a>Crea una pagina con l'elenco dei modelli degli ordini

Per creare una pagina dell'elenco dei modelli degli ordini in Creazione di siti Web, segui questi passaggi.

1. Utilizza il modello **Gestione conti** creato in precedenza per creare una pagina denominata **Modelli ordini**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla pagina di destinazione di gestione dei conti e immetti **Account personale** come testo del collegamento.
1. Nel modulo **Contenitore**, aggiungi un modulo **Elenco dei modelli degli ordini**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.
1. Vai alla pagina di destinazione della gestione dell'account (**Account personale**) che hai creato in precedenza.
1. Nel riquadro delle proprietà per il modulo **Riquadro moduli ordini conto**, in **Collegamenti**, configura un collegamento alla pagina dell'elenco dei modelli di ordine appena creata.
1. Salva e pubblica la pagina.

La pagina dell'elenco dei modelli degli ordini è stata ora creata e gli utenti possono accedervi dalla pagina di destinazione della gestione dell'account.

### <a name="create-an-order-template-lines-page"></a>Crea una pagina con le righe dei modelli degli ordini

Per creare una pagina delle righe dei modelli degli ordini in Creazione di siti Web, segui questi passaggi.

1. Utilizza il modello **Gestione conti** creato in precedenza per creare una pagina denominata **Righe modelli ordini**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla pagina di destinazione di gestione dei conti e immetti **Account personale** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **Righe dei modelli degli ordini**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.

## <a name="onboard-business-partner-users"></a>Eseguire l'onboarding degli utenti dei partner commerciali

La pagina degli utenti dell'organizzazione consente all'amministratore di un'organizzazione di partner commerciali di caricare altri utenti di tale organizzazione sul sito di e-commerce B2B. È impostato utilizzando il modulo **Elenco organizzazioni commerciali**. Dalla pagina degli utenti dell'organizzazione, un amministratore può aggiungere o rimuovere utenti, definire i saldi dei conti e richiedere istruzioni per un utente.

Per creare una pagina degli utenti dell'organizzazione in Creazione di siti Web, segui questi passaggi.

1. Utilizza il modello **Gestione conti** creato in precedenza per creare una pagina denominata **Utenti organizzazione**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla pagina di destinazione di gestione dei conti e immetti **Account personale** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **Elenco organizzazione aziendale**. Nel riquadro delle proprietà del modulo, in **Intestazione**, accedi a **Utenti organizzazione**.
1. Nel riquadro delle proprietà del modulo **Elenco organizzazione aziendale**, abilita le proprietà **Ordina tabella** e **Impaginazione tabella**. Imposta il conteggio dell'impaginazione su **5**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.
1. Vai alla pagina di destinazione della gestione dell'account (**Account personale**) che hai creato in precedenza.
1. Nel riquadro delle proprietà per il modulo **Riquadro utenti organizzazione**, in **Collegamenti**, configura un collegamento alla pagina degli utenti dell'organizzazione appena creata. 
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="create-invoice-pages"></a>Crea pagine fatture

Una pagina contenente elenchi di fatture mostra un elenco di tutte le fatture disponibili. È impostato utilizzando il modulo **InvoicesList**. Dalla pagina dell'elenco delle fatture, gli utenti possono pagare o richiedere fatture. 

Una pagina dei dettagli della fattura mostra i dettagli della fattura selezionata in una pagina di elenco delle fatture. È impostato utilizzando il modulo **Dettagli fatture**. Quando un utente seleziona un ID fattura in una pagina di elenco fatture, viene visualizzata la pagina dei dettagli della fattura che mostra i dettagli della fattura.

### <a name="create-an-invoices-list-page"></a>Crea una pagina con l'elenco delle fatture

Per creare una pagina con l'elenco delle fatture in Creazione di siti Web, segui questi passaggi.

1. Utilizza il modello **Gestione conti** creato in precedenza per creare una pagina denominata **Elenco fatture**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla pagina di destinazione di gestione dei conti e immetti **Account personale** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **InvoicesList**. Nel riquadro delle proprietà del modulo, in **Intestazione**, immetti **Fatture**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.
1. Vai alla pagina di destinazione della gestione dell'account (**Account personale**) che hai creato in precedenza.
1. Nel riquadro delle proprietà per il modulo **Riquadro fatture conto**, in **Collegamenti**, configura un collegamento alla pagina dell'elenco delle fatture appena creata. 
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="create-an-invoice-details-page"></a>Crea una pagina dei dettagli della fattura

Per creare una pagina con l'elenco dei dettagli delle fatture in Creazione di siti Web, segui questi passaggi.

1. Utilizza il modello **Gestione conti** creato in precedenza per creare una pagina denominata **Dettagli fatture**.
1. Nello slot **Intestazione**, aggiungi il frammento di intestazione preconfigurato con l'intestazione del sito.
1. Nello slot **Piè di pagina**, aggiungi il piè di pagina preconfigurato con l'intestazione del piè di pagina.
1. Nello slot **Principale**, aggiungi un modulo **Contenitore**. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore**, aggiungi un modulo **Percorso di navigazione**. Nel riquadro delle proprietà del modulo, sotto **Collegamenti**, configura un collegamento alla pagina di destinazione di gestione dei conti e immetti **Account personale** come testo del collegamento. Quindi configura un collegamento alla pagina dell'elenco delle fatture e immetti **Elenchi fatture** come testo del collegamento.
1. Nello slot **Contenitore**, aggiungi un modulo **Dettagli fatture**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Pubblica l'URL della pagina.

## <a name="add-a-quick-add-module-to-the-cart-page"></a>Aggiungere un modulo di aggiunta rapida alla pagina del carrello

Il modulo di aggiunta rapida fornisce un modo per aggiungere rapidamente più articoli al carrello utilizzando gli ID articolo (noti anche come ID unità di stockkeeping \[SKU\] ). Il modulo di aggiunta rapida viene aggiunto alla pagina del carrello di un sito.

Per aggiungere un modulo di aggiunta rapida alla pagina carrello in Creazione di siti di Commerce, effettua le seguenti operazioni.

1. Vai a **Modelli** e seleziona il modello di pagina del carrello del tuo sito.
1. Seleziona **Modifica**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Aggiungi rapido** e quindi **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Vai a **Pagine** e seleziona la pagina del carrello del tuo sito.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo **Contenitore**, in **Larghezza** seleziona **Riempi contenitore**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Aggiungi rapido** e quindi **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

> [!NOTE] 
> Il modulo di aggiunta rapida è disponibile a partire dalla versione Commerce 10.0.17. Se stai aggiornando da una versione precedente di Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="add-a-bulk-purchase-module-to-a-product-details-page"></a>Aggiungere un modulo Acquisti in blocco a una pagina dettagli del prodotto

Il modulo di acquisti in blocco in una pagina dei dettagli del prodotto fornisce un'esperienza basata su matrice che consente a un acquirente di aggiungere rapidamente più varianti di un prodotto al carrello. Quando un utente del sito deve ordinare più varianti dello stesso prodotto, questa esperienza elimina la necessità di selezionare la combinazione di dimensioni del prodotto, definire la quantità, aggiungere la variante al carrello e quindi ripetere il processo per altre combinazioni di dimensioni del prodotto.

Per aggiungere un modulo di acquisti in blocco a una pagina dei dettagli del prodotto in Creazione di siti Web di Commerce, segui questi passaggi.

1. Vai a **Modelli** e seleziona il modello di pagina dei dettagli del prodotto del tuo sito.
1. Seleziona **Modifica**.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Acquisti in blocco** e quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Vai a **Pagine** e seleziona la pagina dei dettagli del prodotto del tuo sito.
1. Nello slot **Principale** del modulo **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo **Contenitore**, in **Larghezza** seleziona **Riempi contenitore**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Acquisti in blocco** e quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

> [!NOTE] 
> Il modulo di acquisti in blocco è disponibile a partire dalla versione Commerce 10.0.24. Se stai aggiornando da una versione precedente di Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](../starter-kit-overview.md)

[SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file)

[Panoramica della pagina di creazione](../authoring-home-overview.md)

[Panoramica modelli e layout](../templates-layouts-overview.md)

[Utilizzare i frammenti](../work-with-fragments.md)

[Aggiungere una nuova pagina del sito](../add-new-page.md)

[Modulo checkout](../add-checkout-module.md)

[Modulo blocco contenuto](../add-hero-module.md)

[Modulo Raccolta prodotti](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
