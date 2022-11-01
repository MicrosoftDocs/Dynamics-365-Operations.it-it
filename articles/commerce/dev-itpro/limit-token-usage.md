---
title: Limitare l'utilizzo dei token di pagamento
description: Questo articolo descrive la funzionalità che limita il modo in cui vengono utilizzati i token di pagamento in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709656"
---
# <a name="limit-payment-token-usage"></a>Limitare l'utilizzo dei token di pagamento

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Questo articolo descrive la funzionalità che limita il modo in cui vengono utilizzati i token di pagamento in Microsoft Dynamics 365 Commerce. L'utilizzo del token è limitato all'ambito di un ordine cliente o, se viene concesso il consenso del cliente, viene archiviato come carta su file.

## <a name="key-terms"></a>Termini importanti

| Termine | Description |
|---|---|
| Token | Un BLOB XML di riferimento nel sistema Dynamics 365 che archivia i riferimenti di pagamento per scopi transazionali. |
| Carta su file | Un token di riferimento a una carta salvata concordato per un uso futuro nel sistema Dynamics 365 o nel gateway di pagamento e che sia specifico per il conto di un cliente. |

I limiti sull'utilizzo dei token di pagamento si applicano a qualsiasi ambiente che utilizza un servizio di gateway di pagamento in cui vengono impiegati token ricorrenti. Il [connettore di pagamento Dynamics 365 per Adyen](adyen-connector.md) predefinito utilizza i token di pagamento ricorrenti per eseguire le azioni degli ordini successive, come le rettifiche di autorizzazione e le riautorizzazioni.

Per aiutare a controllare come questi token di pagamento ricorrenti vengono utilizzati nel sistema, la funzionalità **Limita l'utilizzo del token di pagamento al contesto dell'ordine** limita l'utilizzo di un token ricorrente all'ambito di un ordine cliente nel sistema. Quando è abilitata, la funzionalità modifica l'interfaccia utente (UI) di Commerce headquarters aggiornando le pagine di input del pagamento e limitando la possibilità di selezionare i riferimenti di pagamento dei clienti passati da utilizzare in nuove istanze di transazione.

Questa funzionalità contribuisce a soddisfare le regole di utilizzo per alcuni istituti emittenti di pagamenti come Visa. Nelle sue [regole principali Visa e Regole sui prodotti e servizi Visa](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf), Visa specifica che l'uso dei token di pagamento dovrebbe essere limitato all'ambito di una transazione, a meno che il titolare della carta non concordi diversamente.

La funzionalità **Limita l'utilizzo del token di pagamento al contesto dell'ordine** è rilevante solo se stai utilizzando un servizio di gateway di pagamento che utilizza riferimenti a token di pagamento ricorrenti.

## <a name="enable-the-feature"></a>Abilitare la funzionalità

Per abilitare la funzionalità **Limita l'utilizzo del token di pagamento al contesto dell'ordine**, in Commerce headquarters per il tuo ambiente, vai a **Aree di lavoro \> Gestione funzionalità**, trova e seleziona **Limita l'utilizzo del token di pagamento al contesto dell'ordine** nell'elenco, quindi seleziona **Abilita ora**.

## <a name="limit-payment-token-usage"></a>Limitare l'utilizzo dei token di pagamento

Quando la funzionalità è abilitata, le pagine di Commerce headquarters utilizzate per l'acquisizione del metodo di pagamento aggiorneranno il modo in cui fanno riferimento ai metodi di pagamento del cliente che sono su file per il cliente. Questo aggiornamento riguarderà principalmente due aree operative:

- Come viene inserita una carta del cliente su file per conto di un cliente
- Modalità di archiviazione delle informazioni di pagamento a carico di un cliente per i movimenti di pagamento degli ordini cliente futuri

Quando un cliente effettua transazioni sui canali Commerce, i dettagli di pagamento vengono archiviati con un contesto dell'ordine cliente. Il contesto dell'ordine cliente limita il token di pagamento in modo che non venga utilizzato come riferimento di pagamento rispetto al record del cliente nelle pagine di pagamento per i pagamenti dell'ordine cliente nuovi o modificati in Commerce headquarters.

### <a name="payment-form-changes"></a>Modifiche al modulo di pagamento

Quando un utente del call center o di Commerce headquarters accetta un pagamento per un cliente a fronte di un ordine cliente, la pagina di pagamento presenta i dettagli di selezione del metodo di pagamento. Quando la funzionalità **Limita l'utilizzo del token di pagamento al contesto dell'ordine** è abilitata, se un utente seleziona il segno più (**+**) nella pagina di pagamento vengono mostrati solo i record "carta su file". Le modifiche richiedono che l'utente del call center o di Commerce headquarters inserisca i dettagli di pagamento completi forniti dal cliente al momento della compilazione nella pagina **Immettere le informazioni sul pagamento cliente** per la nuova transazione dell'ordine cliente.

L'elenco dei valori per il campo **Numero** include solo i riferimenti della carta associati al cliente che ha la carta su file. Filtra tutti i riferimenti di pagamento passati che non rientrano nell'ambito di un ordine cliente.

Il segno più (**+**) sotto il campo **Numero** rimane disponibile e può essere utilizzato per inserire le informazioni di pagamento fornite dal cliente per la transazione associata all'ordine cliente in elaborazione.

### <a name="how-cards-on-file-work"></a>Come funzionano le carte su file

Quando la funzionalità **Limita l'utilizzo del token di pagamento al contesto dell'ordine** è abilitata, una carta su file è un token di pagamento ricorrente che viene salvato in un record del cliente e non è limitato all'ambito di un ordine cliente. Una carta su file consente un rapido riferimento per gli utenti di Commerce headquarters quando compilano la pagina di pagamento per un nuovo pagamento dell'ordine cliente. Questo riferimento al token è applicabile solo all'ambiente Dynamics 365. Per i canali online che utilizzano un servizio di gateway di pagamento che consente agli utenti di salvare un metodo di pagamento per un utilizzo futuro nel modulo iFrame di pagamento, il gateway di pagamento archivia in modo sicuro questi riferimenti come riferimento separato alla carta Dynamics 365 su file.

Ad esempio, se il connettore di pagamento Dynamics 365 Commerce per Adyen viene utilizzato in un canale online, i clienti che inseriscono i dati della propria carta di credito nel modul iFrame di pagamento visualizzano solo i riferimenti delle carte salvate dal servizio gateway per il loro prossimo acquisto online quando sono autenticati. Non vedono la carta archiviata nell'ambiente Dynamics 365 come opzione nel modulo iFrame di pagamento. In modo analogo, quando gli acquirenti effettuano un ordine tramite il call center, i riferimenti delle carte salvate online non vengono presentati come opzioni all'utente del call center. L'utente del call center vede solo la scheda precedente nei riferimenti ai file dal sistema Dynamics 365 (come concordato dal cliente) da salvare per gli ordini futuri.

Gli utenti di Commerce headquarters possono salvare una carta su file per un cliente andando su **Retail e Commerce \> Clienti** e selezionando il record del conto cliente. Nella sezione **Cliente \> Imposta**, gli utenti che dispongono delle autorizzazioni per elaborare le pagine di pagamento possono utilizzare la pagina di immissione **Carte di credito** per inserire una carta di pagamento che verrà archiviata per transazioni future. Questa operazione consente di risparmiare tempo durante l'elaborazione dei futuri pagamenti degli ordini cliente per il cliente. Gli utenti del call center e di Commerce headquarters devono immettere i dettagli della carta su file solo se il cliente accetta di utilizzare il riferimento della carta per transazioni future.

Una casella di controllo **Salva per utilizzo futuro** nella parte inferiore delle pagine di pagamento di Commerce headquarters consente agli utenti di salvare la carta su file per un uso futuro. Questa casella di controllo deve essere utilizzata solo se il cliente accetta di utilizzare la carta su file per transazioni future. Puoi mostrare o limitare la casella di controllo **Salva per uso futuro** utilizzando l'opzione **Consenti carta cliente nel file** nella scheda **Pagamento** della pagina **Parametri del call center** in Commerce headquarters. Quando questa opzione è impostata su **Sì**, gli utenti di Commerce headquarters che dispongono delle autorizzazioni per elaborare le pagine di pagamento possono salvare una carta su file utilizzando la casella di controllo **Salva per uso futuro**. Quando l'opzione è impostata su **No**, la casella di controllo non è disponibile per gli utenti di Commerce headquarters che dispongono delle autorizzazioni per elaborare le pagine di pagamento. L'opzione **Consenti carta cliente nel file** può essere utilizzata se la tua azienda desidera limitare l'utilizzo di token ricorrenti in Commerce headquarters, ma non vuole ancora consentire il salvataggio di una carta su file senza una procedura per garantire che venga concesso il consenso del cliente.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>Le pagine di Commerce headquarters in cui vengono applicate le restrizioni sui token ricorrenti

L'ambito della restrizione del token interessa le seguenti aree di Commerce headquarters quando la funzionalità è abilitata:

- Informazioni sul pagamento del cliente in **Ordine cliente \> Pagamenti \> Pagamenti cliente**
- Ordini di continuità
- Pagamenti rateali
- Pagamenti con la carta di credito nella contabilità clienti

### <a name="manage-payment-tokens-archiving-or-removal"></a>Gestire i token di pagamento (archiviazione o rimozione)

I token di pagamento creati prima che il flag della funzionalità **Limita l'utilizzo del token di pagamento al contesto dell'ordine** fosse abilitato (o mentre la funzionalità era disabilitata) rimarranno "senza ambito" nel sistema e sarà possibile fare riferimento negli elenchi di selezione nella pagina di pagamento di Commerce headquarters. Questi token possono essere rimossi regolarmente in due modi in Commerce headquarters:

- Utilizza la pagina **Archiviare i dati delle transazioni con carta di credito** per configurare un processo che elimina o archivia regolarmente i token di pagamento. Se imposti l'opzione **Elimina dati senza archiviare** su **Sì**, i token che soddisfano l'impostazione **Validità minima transazione (in giorni)** verranno eliminati. Per ulteriori informazioni, vedi [Archiviare i dati delle transazioni con carta di credito](archive-cc-data.md).
- Utilizza la nuova pagina **Elimina token carta di credito** (**Contabilità clienti \> Richieste di informazioni e report \> Pulitura \> Elimina token carta di credito**), che consente di eseguire o configurare un processo batch che elimina i token di pagamento. Impostare i parametri riportati di seguito.

    - Il valore **Validità minima token in giorni** deve essere di 90 giorni o più.
    - Le impostazioni **Esegui in background** possono essere utilizzate per definire le impostazioni **Ricorrenza** o **Avvisi**.
    - È possibile assegnare un gruppo batch per eseguire l'attività per un gruppo specifico.
    - Se l'opzione **Privato** è impostata su **Sì**, solo l'utente che crea il processo può eseguirlo.
    - L'impostazione **Sì** per l'opzione **Processo critico** assicura che il sistema tenga attivamente traccia dello stato del processo.

I token eliminati non possono essere recuperati. Imposta il campo **Validità minima token in giorni** su un intervallo che si adatta alla durata della transazione più lunga per il tuo ambiente (dall'autorizzazione all'acquisizione o al rimborso).

## <a name="additional-resources"></a>Risorse aggiuntive

[Domande frequenti sui pagamenti](payments-retail.md)

[Modulo checkout](../add-checkout-module.md)

[Modulo pagamento](../payment-module.md)
