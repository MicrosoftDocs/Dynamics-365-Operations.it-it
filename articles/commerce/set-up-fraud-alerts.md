---
title: Impostazione e utilizzo degli avvisi di frode del servizio clienti
description: In questo argomento viene illustrato come impostare le regole per avvisare i rappresentanti dell'assistenza clienti di informazioni potenzialmente fraudolente quando gli ordini vengono elaborati. È possibile definire codici specifici da utilizzare per mettere automaticamente o manualmente gli ordini sospetti in attesa.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 38649e40021d1caaf70f217b3ebae0d488806180
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413535"
---
# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Impostazione e utilizzo degli avvisi di frode del servizio clienti

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come impostare criteri e regole per sospendere ordini cliente potenzialmente fraudolenti da verificare ulteriormente. La funzionalità di verifica frodi viene utilizzata per determinare la validità delle informazioni in un ordine cliente. Se le informazioni nell'ordine cliente vengono considerate sospette in base a criteri e regole antifrode di un'organizzazione, l'ordine può essere sospeso per un'ulteriore verifica. In questo caso, l'ordine non può essere rilasciato al magazzino per continuare elaborazione fino a quando la sospensione non viene cancellata.

> [!NOTE]
> Questa funzionalità può essere utilizzata solo con l'elaborazione di ordini cliente per il canale servizio clienti di Commerce.

## <a name="turning-on-the-fraud-check-feature"></a>Attivazione della funzionalità di verifica frodi

Per utilizzare la funzionalità di verifica frodi, è necessario impostare l'opzione **Attiva completamento ordine** nel canale su **Sì** quando il canale servizio clienti viene [definito](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-order-processing-options). Quando il completamento dell'ordine è attivato, gli utenti del servizio clienti devono selezionare **Completa** nella pagina dell'ordine cliente per tutti gli ordini cliente creati. L'azione Completa Complete determina l'apertura della pagina **Riepilogo ordine cliente**. Dopo che gli utenti immettono la data di pagamento richiesta nella pagina **Riepilogo ordine cliente**, selezionano **Invia** per finalizzare l'ordine. Quando l'ordine viene inviato, la funzionalità di verifica frodi viene attivata e tutte le regole che sono attivate nel sistema vengono convalidate automaticamente.

Gli utenti del servizio clienti possono mettere gli ordini clienti manualmente in attesa di un esame di frode prima di selezionare **Invia**. Per mettere manualmente un ordine cliente in attesa, nella pagina **Riepilogo ordine cliente** selezionare **Pausa** \> **Sospensione manuale per frode**. Verrà quindi chiesto di immettere un commento per spiegare il motivo della sospensione dell'ordine. Questo commento verrà visualizzato nel workbench [Sospensioni ordine](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) per fornire contesto all'utente che esamina gli ordini in attesa per determinare se l'ordine deve essere rilasciato.

Oltre alla configurazione dell'opzione **Attiva completamento ordine** nel canale, è necessario configurare la funzionalità di verifica frodi nei parametri del servizio clienti. Passare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione servizio clienti** \> **Parametri servizio clienti**. Nella pagina **Parametri servizio clienti** nella scheda **Sospensioni** impostare l'opzione **Verifica frodi** su **Sì**.

Nella scheda **Sospensioni** occorre anche definire i [codici sospensione](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) che saranno applicati a un ordine che messo manualmente o automaticamente in attesa di esame per frode. Impostare i codici sospensione nei campi **Codice sospensione manuale per frode** e **Codice sospensione per frode**. Potrebbe essere utile creare due codici sospensione univoci, in modo che gli utenti che lavorano nel workbench delle sospensioni possano facilmente filtrare e distinguere le sospensioni automatiche da quelle manuali.

Perché la funzionalità di verifica frodi funzioni correttamente, è inoltre necessario impostare il campo **Punteggio minimo**. Ogni criterio e regola di frode definita nel sistema ha un punteggio. Quando un ordine cliente viene controllato alla ricerca di corrispondenze con frodi, se vengono rilevate una o più corrispondenze, i punteggi vengono aggiunti insieme per assegnare all'ordine un punteggio totale per frode. Se il punteggio totale di frode per un ordine supera il valore del campo **Punteggio minimo**, l'ordine viene messo automaticamente in attesa. È possibile utilizzare gli altri campi correlati al punteggio nella scheda **Sospensioni** per definire il punteggio di posta elettronica, il punteggio di telefono, il punteggio di codice postale/CAP e il punteggio di codice postale esteso. Se non si specifica un punteggio per questi criteri per frode statici quando li si definisce nella pagina **Dati fraudolenti statici**, il sistema assegna loro un punteggio utilizzando punteggi predefiniti che si specificano nella scheda **Sospensioni** della pagina **Parametri servizio clienti**.

Infine utilizzare il campo **Tipo di commento frode** per specificare il tipo di documento che deve essere utilizzato quando gli utenti immettono commenti quando inseriscono manualmente un ordine in attesa di esame antifrode. In genere, questo campo è impostato **Nota**.

## <a name="defining-fraud-criteria-and-rules"></a>Definizione dei criteri e delle regole per frode

Il sistema fa riferimento a due tipi di criteri di frode per determinare se un ordine deve essere messo in attesa per l'esame antifrode:

- **Dati fraudolenti statici** utilizza un valore specifico, ad esempio un numero di telefono che è stato inserito in un elenco di numeri bloccati o un indirizzo e-mail che è stato contrassegnato perché notoriamente utilizzato per transazioni fraudolente. Per impostare i dati fraudolenti statici, passare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione servizio clienti** \> **Frode** \> **Dati fraudolenti statici**. Nella pagina **Dati fraudolenti statici** è possibile aggiungere criteri di frode manualmente o tramite importazione di dati. I punteggi vengono collegati alle informazioni fraudolente. Se la funzionalità di verifica frodi è attivata, ogni ordine cliente che viene immesso viene confrontato con i dati statici. Se i dati si trovano nell'indirizzo di fatturazione del cliente o nell'indirizzo di consegna che è collegato all'intestazione dell'ordine o se i dati si trovano negli indirizzi di consegna che sono collegati a una o più righe qualsiasi dell'ordine cliente, i punteggi di tutte le corrispondenze univoche vengono aggiunti insieme e confrontati con i valori di **Punteggio minimo** per determinare se l'ordine deve essere messo in attesa.

- Le **regole su frode** consistono in variabili definite dall'utente e in condizioni definite per tali variabili. Per creare le regole, passare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione servizio clienti** \> **Frode** \> **Regole**. Le regole su frode consentono a una società di configurare una regola più complessa che può includere istruzioni **AND** o **OR** per valutare più condizioni. Ad esempio, un utente vuole che tutti gli ordini per i clienti che appartengono a uno specifico gruppo di clienti e che hanno ordinato un prodotto specifico vengano messi in attesa di esame antifrode. In questo caso, le condizioni per convalidare il cliente e i prodotti vengono definite nella pagina **Regole** e viene utilizzare la condizione AND. Un ordine viene quindi messo in attesa solo se entrambe le condizioni sono vere se il valore del punteggio che viene assegnato a questa regole, più il valore di punteggio di qualsiasi altra regola con cui l'ordine trova corrispondenza, il punteggio totale per frode dell'ordine supera il valore di **Punteggio minimo** che è definito nella pagina **Parametri servizio clienti**.

> [!NOTE]
> L'utilizzo di più regole o di regole eccessivamente complesse influirà negativamente sulle prestazioni del sistema quando gli ordini cliente vengono inviati. La funzionalità di verifica frodi non è stata ottimizzata per gestire un grande volume di dati fraudolenti statici e molte regole attive. Tenere presente che ciascuna regola viene valutata quando gli utenti del servizio clienti selezionano **Invia** durante la registrazione dell'ordine cliente. Le regole vengono valutate rispetto all'intestazione dell'ordine cliente e a tutte le righe dell'ordine. Più regole sono presenti e più complesse sono le istruzioni delle regole, più lunga sarà l'elaborazione. Se un ordine presenta molte voci e il numero di regole attive e di immissioni di dati statici è molto elevato, il processo automatico di verifica e convalida di tutti i dati e di calcolo di un punteggio frodi può avere un impatto considerevolmente sulle prestazioni. Le organizzazioni che utilizzano questa funzionalità devono sempre verificare e confermare che il tempo di elaborazione per l'invio dell'ordine è accettabile prima di applicare eventuali modifiche alle regole o ai criteri antifrode statici nell'ambiente di produzione.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Identificazione di ordini in attesa per la revisione antifrode

Quando gli utenti del servizio clienti inviano un ordine cliente, se l'ordine soddisfa i criteri o le regole su frode e se il punteggio supera il limite valore minimo, gli utenti ricevono un messaggio di avviso indicante che l'ordine è stato messo in attesa. Gli utenti possono chiudere il messaggio, poiché ha solo scopo informativo. Gli utenti possono facoltativamente comunicare queste informazioni al cliente. La società deve determinare il protocollo che gli utenti devono seguire questo caso.

L'ordine viene salvato, ma viene impostato il flag **Non elaborare**. Il flag assicura che l'ordine non può essere rilasciato al magazzino. In qualsiasi momento gli utenti possono visualizzare le impostazioni del flag **Non elaborare** per qualsiasi ordine cliente nella pagina **Stato dettagliato**. Questa pagina può essere aperta dalle pagine **Tutti gli ordini cliente** e **Servizio clienti**. Il sistema aggiorna anche il valore del campo **Stato dettagliato** per l'ordine su **Sospensione per frode**.

Per visualizzare e gestire gli ordini in attesa per la revisione antifrode, passare a **Retail e Commerce** \> **Clienti** \> **Sospensioni ordine**. Nella pagina **Sospensioni ordine** selezionare una voce nell'elenco e quindi fare clic su **Ordine sospeso** per avere una visualizzazione più dettagliata che include informazioni sul motivo della sospensione. Nella Scheda dettaglio **Dettagli frode**, è possibile visualizzare i criteri di frode sistematici che sono stati trovati corrispondere per l'ordine e i punteggi che sono stati applicati. Se l'ordine è stato messo in attesa manualmente, è possibile rivedere i commenti che sono stati immessi dall'utente che ha messo l'ordine in attesa guardando la sezione **Note frode** nella Scheda dettaglio **Note**.

Per ulteriori informazioni su come utilizzare gli ordini sospesi, vedere [Sospensioni ordine](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds).
