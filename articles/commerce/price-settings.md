---
title: Impostazioni dei prezzi
description: Questo articolo descrive le varie impostazioni per la gestione dei prezzi e degli sconti in Microsoft Dynamics 365 Commerce Headquarters.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 4bc8cb16e7960d26adbb9590b4ad83cf46b02838
ms.sourcegitcommit: 6fd44fc6e9a7bad197cab58c36ec25a555724cf1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2022
ms.locfileid: "9410776"
---
# <a name="pricing-settings"></a>Impostazioni dei prezzi

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Questo articolo descrive le varie impostazioni per la gestione dei prezzi e degli sconti in Microsoft Dynamics 365 Commerce Headquarters. Queste impostazioni consentono alle organizzazioni di definire il comportamento dei prezzi nella loro soluzione Commerce per soddisfare esigenze aziendali specifiche.

## <a name="company-level-pricing-settings"></a>Impostazioni dei prezzi a livello di azienda

La maggior parte delle impostazioni dei prezzi sono a livello aziendale e possono essere trovate in **Parametri di commercio \> Prezzi e sconti** in Commerce headquarters.

### <a name="best-price-and-compound-concurrency-control-model"></a>Modello di controllo concorrenza prezzo migliore e combinazione

L'impostazione **Modello di controllo concorrenza prezzo migliore e combinazione** determina il modo in cui il motore di determinazione del prezzo elabora sconti multipli nella modalitò di concorrenza **miglior prezzo** o **composto**. 

Se il parametro è impostato su **Prezzo migliore e composto in priorità, mai composto tra priorità**, tutti gli sconti **composti** che hanno la stessa priorità di prezzo sono cumulati. Il risultato composto compete quindi con qualsiasi sconto di tipo **miglior prezzo** che ha la stessa priorità di prezzo, viene applicato il prezzo migliore e tutti gli sconti con una priorità di prezzo inferiore vengono ignorati.

Se il parametro è impostato su **Prezzo migliore solo in priorità, sempre composto tra priorità**, tutti gli sconti **composti** sono trattati come sconti **miglior prezzo**. All'interno di una priorità di prezzo, vince un solo sconto. Se quel singolo sconto è uno sconto **miglior prezzo** o **composto**, è combinato con tutti gli ulteriori sconti **miglior prezzo** o **composto** che hanno una priorità di prezzo inferiore.

### <a name="discount-compound-behavior"></a>Comportamento combinazione sconti

L'impostazione **Comportamento combinazione sconti** determina il modo in cui il motore di determinazione del prezzo calcola più sconti composti.

Se il parametro è impostato su **Composto**, uno sconto viene applicato sull'altro in maniera cumulativa. Se è impostato su **Composto sul prezzo originale**, tutti gli sconti sono trattati indipendentemente l'uno dall'altro e applicati allo stesso prezzo originario.

Ad esempio, vuoi combinare sconti del 10 percento e del 20 percento per un prodotto il cui prezzo originale è $100. Se imposti il parametro **Comportamento combinazione sconti** su **Composto**, il prezzo finale sarà $72 ($ 100&times; 90%&times; 80%). Se lo imposti su **Composto sul prezzo originale**, il prezzo finale sarà $70 ($ 100 10% 20%).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Abilitare competizione tra soglia esclusiva e altri sconti periodici

Se il parametro **Abilitare competizione tra soglia esclusiva e altri sconti periodici** è impostato su **Sì**, il motore di determinazione del prezzo mette in concorrenza gli sconti di soglia esclusivi con gli sconti non di soglia esclusivi. La priorità di prezzo è ancora valida. Il comportamento degli sconti di soglia **miglior prezzo** e **composto** rimane invariato. In altre parole, non competono con gli sconti fuori soglia.

### <a name="manual-line-discount-and-system-discount"></a>Sconto riga manuale e sconto di sistema

L'impostazione **Sconto riga manuale e sconto di sistema** determina il modo in cui il motore di determinazione del prezzo applica uno sconto di riga manuale e uno sconto di sistema alla stessa riga. Lo sconto riga manuale può essere aggiunto allo sconto di sistema oppure può sostituire lo sconto di sistema. Quando lo sconto riga manuale e lo sconto di sistema sono composti, la logica di calcolo rispetta l'impostazione **Comportamento combinazione sconti**. Uno sconto totale manuale che si applica all'intero ordine non rispetta tale impostazione.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Mantenere gli articoli sulla stessa riga di vendita per l'arrotondamento del prezzo scontato

A volte, l'importo di uno sconto quantità non può essere diviso equamente per la quantità qualificante (ad esempio, se l'importo dello sconto è $10 di sconto per tre unità acquistate). In questi casi, l'impostazione **Mantenere gli articoli sulla stessa riga di vendita per l'arrotondamento del prezzo scontato** determina il modo in cui il motore di determinazione del prezzo applica e distribuisce l'importo dello sconto. Se il parametro è impostato su **Sì**, l'importo dello sconto viene applicato per intero e non viene suddiviso. Se è impostato su **No**, l'importo dello sconto viene diviso per la quantità qualificante e arrotondato. Ad esempio, un importo di sconto di $10 per tre unità è diviso in $3,33 di sconto per un'unità, $3,33 di sconto per la seconda unità e $3,34 di sconto per la terza unità.

### <a name="apply-discounts-to-key-in-price-products"></a>Applicare sconti a prodotti di tipo "digitare il prezzo".

L'impostazione **Applicare sconti a prodotti di tipo "digitare il prezzo"** determina se gli sconti possono essere applicati insieme ai "prezzi digitati" che vengono inseriti nel punto vendita (POS). L'impostazione **Digita il prezzo** nella configurazione del prodotto determina se e come un prodotto supporta il prezzo digitato.

### <a name="apply-discounts-to-price-overrides"></a>Applica sconti a sostituzioni prezzo

L'impostazione **Applica sconti a sostituzioni prezzo** determina se gli sconti possono essere applicati insieme alle sostituzioni dei prezzi.

### <a name="distribute-discounts-for-least-expensive-discounts"></a>Distribuire sconti per sconti meno costosi

Per gli sconti mix and match che utilizzano il tipo di calcolo "meno costoso", l'impostazione **Distribuisci sconto per sconti meno costosi** determina se il motore di determinazione del prezzo distribuisce lo sconto su più righe.

Se il parametro è impostato su **No**, lo sconto si applica solo alle righe meno costose. Ad esempio, per uno sconto mix and match "compra 2 ricevi 1 gratis", l'articolo meno costoso sarà gratuito e gli altri due articoli rimarranno a prezzo pieno. In questo caso, un cliente che restituisce entrambi gli articoli a prezzo pieno riceverà comunque il terzo articolo gratuitamente. Questo scenario potrebbe causare una perdita per il rivenditore.

Se il parametro è impostato su **Sì**, il motore di determinazione del prezzo distribuisce lo sconto su tutte le righe applicabili. Questa impostazione può aiutare a ridurre la perdita sui resi.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Calcola manualmente prezzi e sconti per più righe

L'impostazione **Calcola manualmente prezzi e sconti per più righe** controlla se il motore di determinazione del prezzo utilizza il calcolo ritardato del prezzo e dello sconto per l'applicazione POS e il canale del call center. Se il parametro è impostato su **Sì**, il motore di determinazione del prezzo non calcola immediatamente gli sconti multiriga (come sconti quantità, sconti soglia e sconti mix and match) ogni volta che un ordine cliente viene creato o modificato nell'applicazione POS o nel canale del call center.

> [!NOTE]
> In Commerce versione 10.0.30 e precedenti, l'impostazione **Calcola manualmente prezzi e sconti per più righe** controlla solo il canale del call center. Un'impostazione **Calcola manualmente più sconti articoli** separata nel profilo di funzionalità controlla il comportamento di calcolo del prezzo nell'applicazione POS. In Commerce versione 10.0.31, le due impostazioni sono consolidate in un'unica impostazione a livello aziendale.

### <a name="retention-period-in-days"></a>Periodo di ritenuta in giorni

L'impostazione **Periodo di ritenuta in giorni** indica quanti giorni dopo la data di scadenza (se è impostata una data di scadenza) o la data i disattivazione (se non è impostata una data di scadenza) uno sconto deve essere eliminato sistematicamente. Se il parametro è impostato su **0** (zero), non si verifica alcuna cancellazione automatica.

> [!NOTE]
> In Commerce versione 10.0.30 e precedenti, questa impostazione è denominata **Numero di giorni dopo i quali eliminare gli sconti scaduti**.

### <a name="coupon-bar-code"></a>Codice a barre buono sconto

L'impostazione **Codice a barre buono sconto** determina quale codice a barre specifico viene utilizzato per generare codici a barre buono sconto. Gli utenti possono selezionare uno dei codici a barre predefiniti che sono configurati nella pagina **Impostazione codice a barre**. Per ulteriori informazioni sui codici a barre e le maschere di codici a barre, vedere [Configurare codici a barre](set-up-bar-codes.md) e [Configurare maschere di codici a barre](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>Il codice buono sconto deve essere applicato manualmente alle transazioni di reso

L'impostazione **Il codice buono sconto deve essere applicato manualmente alle transazioni di reso** è applicabile solo alle transazioni di reso per le quali non è prevista alcuna ricevuta di vendita. Impostare il parametro su **No** se i codici buono sconto devono essere applicati automaticamente alla transazione. Impostalo su **Sì** se i codici buono sconto devono essere aggiunti manualmente alla transazione.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>Usa contratti di vendita impostati per l'organizzazione

Per gli ordini business-to-business (B2B), se il parametro **Usa contratti di vendita impostati per l'organizzazione** è impostato su **Sì**, il motore di determinazione del prezzo utilizza i contratti di vendita definiti per l'organizzazione nella gerarchia dei clienti dell'utente per determinare il prezzo basato sul contratto. Se il parametro è impostato su **No** oppure, se la gerarchia dei clienti non è definita, il motore di determinazione del prezzo cerca i contratti di vendita definiti per consentire all'utente di determinare il prezzo basato sul contratto. Per ulteriori informazioni sulle gerarchie dei clienti per l'e-commerce B2B, vedere [Gestire partner commerciali B2B utilizzando gerarchie di clienti](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Impostazioni dei prezzi a livello di canale

Le seguenti impostazioni consentono alle organizzazioni di controllare il comportamento dei prezzi in specifici canali di vendita.

### <a name="enable-order-price-control"></a>Abilita controllo prezzo ordine

Il parametro **Abilita controllo prezzo ordine** si trova nella scheda Dettaglio **Generale** della pagina **Configurazione call center**. L'impostazione determina se il motore di determinazione del prezzo applica una restrizione all'operazione di sostituzione del prezzo nel canale del call center. Funziona in combinazione con l'impostazione a livello di prodotto **Consenti rettifica prezzo**.

Se il controllo del prezzo dell'ordine è disattivato, qualsiasi utente del call center può apportare modifiche ai prezzi sulle righe di vendita nel canale del call center, indipendentemente dal fatto che i prodotti corrispondenti consentano l'adeguamento del prezzo.

Se il controllo del prezzo dell'ordine è attivato, solo i prodotti in cui il parametro **Consenti rettifica prezzo** è impostato su **Sì** consentono la sostituzione del prezzo negli ordini di vendita del canale del call center e un codice motivo deve essere fornito sulle righe di vendita corrispondenti. Un utente del call center può modificare il prezzo di vendita solo fino al valore **Percentuale ricarico costo** definito in **Retail and Commerce \> Configurazione canale \> Configurazione call center \> Sostituisci autorizzazioni**. Se una sostituzione del prezzo supera tale percentuale, l'utente deve inviare una richiesta, che viene quindi elaborata attraverso un flusso di lavoro Commerce predefinito per la revisione e l'approvazione. Per ulteriori informazioni sulla creazione di flussi di lavoro Commerce, vedere [Panoramica del sistema del flusso di lavoro](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Impostazioni dei prezzi a livello di prodotto

Le seguenti impostazioni applicano regole di determinazione dei prezzi a livello di prodotto e possono essere trovate nella pagina **Configurazione prodotto** di un'organizzazione.

### <a name="allow-price-adjust"></a>Consenti rettifica prezzo

Se il parametro **Consenti rettifica prezzo** è impostato su **Sì**, è possibile applicare una sostituzione del prezzo al prodotto negli ordini di vendita del canale del call center.

### <a name="key-in-price"></a>Digitare il prezzo

L'impostazione **Digita il prezzo** determina se un prezzo digitato è obbligatorio quando un prodotto viene aggiunto a una transazione di vendita in POS. Definisce inoltre le restrizioni relative al valore del prezzo.

### <a name="zero-price-valid"></a>Articolo a prezzo zero valido

L'impostazione **Articolo a prezzo zero valido** determina se i prezzi di vendita predefiniti, calcolati dal sistema o regolati manualmente per un prodotto possono essere 0 (zero). Impostare il parametro su **Sì** se è consentito un prezzo pari a zero. Questa impostazione può anche essere specificata a livello di categoria nella gerarchia di prodotti Commerce.

### <a name="prevent-all-discounts"></a>Impedisci tutti gli sconti

Impostando il parametro **Impedisci tutti gli sconti** su **Sì**, impedisci che tutti i tipi di sconti (inclusi quelli manuali) vengano applicati a un prodotto. Questa impostazione può anche essere specificata a livello di categoria nella gerarchia di prodotti Commerce.

> [!NOTE]
> Questa impostazione non limita l'operazione di sostituzione dei prezzi in quanto definisce il prezzo base e non è considerata come sconto.

### <a name="prevent-manual-discounts"></a>Impedisci sconti manuali

Impostando il parametro **Impedisci sconti manuali** su **Sì**, impedisci che gli sconti di transazione o di riga manuali vengano applicati a un prodotto. Tutti gli altri sconti possono comunque essere applicati. Questa impostazione può anche essere specificata a livello di categoria nella gerarchia di prodotti Commerce.

> [!NOTE]
> Questa impostazione non limita l'operazione di sostituzione dei prezzi in quanto definisce il prezzo base e non è considerata come sconto.

### <a name="prevent-retail-discounts"></a>Impedisci sconti vendita al dettaglio

Se il parametro **Impedisci sconti vendita al dettaglio** è impostato su **Sì**, gli sconti **semplice**, **quantità**, **soglia**, **mix and match** e **spedizione** non possono essere applicati a un prodotto. Tutti gli altri sconti (inclusi gli sconti manuali) possono comunque essere applicati.

### <a name="prevent-tender-based-discounts"></a>Impedisci sconti basati su metodi di pagamento

Se il parametro **Impedisci sconti basati su metodi di pagamento** è impostato su **Sì**, uno sconto **basato su metodo di pagamento** non può essere applicato a un prodotto. Tutti gli altri sconti (inclusi gli sconti manuali) possono comunque essere applicati.

I rivenditori al dettaglio spesso scelgono di escludere dagli sconti alcuni prodotti, come gli articoli nuovi o più richiesti dagli sconti basati su articolo (ad esempio sconti semplici o per quantità). Tuttavia, potrebbero comunque voler applicare sconti basati su metodo di pagamento se un cliente paga utilizzando il metodo di pagamento preferito. Per ottenere questo risultato i rivenditori al dettaglio possono impostare le opzioni **Impedisci tutti gli sconti** e **Impedisci sconti basati sul metodo di pagamento** su **No** e impostare i parametri **Impedisci sconti vendita al dettaglio** e **Impedisci sconti manuali** su **Sì**.

## <a name="deprecated-or-removed-settings"></a>Impostazioni rimosse o deprecate

Le seguenti impostazioni dei prezzi sono state rimosse o ne è stata pianificata la rimozione da Dynamics 365 Commerce.

| Impostazione | Motivo della deprecazione o rimozione | Stato di deprecazione o rimozione |
|---------|-----------------------------------|-------------------------------|
| Gestione di sconti sovrapposti | Abbiamo fornito questa impostazione nei parametri Commerce per controllare il modo in cui il motore di determinazione del prezzo cerca e determina la migliore combinazione di sconti da applicare. L'opzione **Migliore sconto** forza tutte le possibili combinazioni di sconti durante il calcolo del prezzo. L'opzione **Prestazioni ottimali** è un'opzione ottimizzata che utilizza un algoritmo euristico avanzato e un metodo di classificazione del valore marginale per stabilire le priorità, valutare e determinare la migliore combinazione di sconti in modo tempestivo. L'opzione **Calcolo bilanciato** nella base di codice corrente funziona esattamente come l'opzione **Prestazioni ottimali**. Pertanto, è essenzialmente un'opzione duplicata. Per aiutare a migliorare le prestazioni, il motore di determinazione del prezzo è stato aggiornato in modo che utilizzi solo **Migliori prestazioni** come opzione standard. Pertanto, questa impostazione non è più applicabile. | Deprecata nella versione 10.0.21 e verrà rimossa a ottobre 2022. |
| Consentire alle rettifiche prezzo di aumentare il prezzo del prodotto | Abbiamo fornito questa impostazione per controllare se la funzione di rettifica del prezzo può aumentare il prezzo del prodotto. Se il parametro è disattivato, le organizzazioni possono utilizzare solo la funzione di rettifica del prezzo per impostare un prezzo unitario di un prodotto in modo che sia inferiore al prezzo base e al prezzo di vendita dell'accordo commerciale. Abbiamo deprecato questa impostazione poiché la funzione di rettifica del prezzo è stata aggiornata per supportare le rettifiche bidirezionali (aumento o diminuzione) pronte all'uso. | Deprecata nella versione 10.0.30 e verrà rimossa a ottobre 2023. |
| Abilita report dei prezzi per punto vendita al dettaglio | Abbiamo fornito questa impostazione per controllare se la funzione **Report sui prezzi** è disponibile per l'uso nella pagina di configurazione del punto vendita. Abbiamo deprecato questa impostazione poiché la pagina di configurazione del punto vendita è stata aggiornata per fornire la funzione **Report sui prezzi** come funzione standard. | Deprecata nella versione 10.0.31 e verrà rimossa a ottobre 2023. |
| Utilizzare la data odierna per calcolare i prezzi | Il motore di determinazione dei prezzi di Dynamics 365 Supply Chain Management supporta il calcolo dei prezzi in base alla data di spedizione richiesta o alla data di ricevimento richiesta, insieme alla data odierna. Il motore di determinazione dei prezzi di Commerce supporta solo il calcolo dei prezzi in base alla data odierna. Per i clienti che utilizzano le funzionalità di Supply Chain Management e di Commerce, abbiamo fornito questa impostazione e consigliato ai clienti di impostarla sempre su **Sì** di modo che i due motori di determinazione dei prezzi possano lavorare insieme. Abbiamo deprecato questa impostazione poiché non cambia essenzialmente il comportamento di calcolo ed è pertanto ridondante. | Deprecata nella versione 10.0.31 e verrà rimossa a ottobre 2023. |
| Prezzo massimo | Abbiamo fornito questa impostazione nel profilo di funzionalità per controllare se solo i prodotti con un prezzo di vendita inferiore al prezzo massimo specificato possono essere venduti tramite POS in negozi specifici. Abbiamo deprecato questa impostazione a causa del basso utilizzo delle funzionalità. | Deprecata nella versione 10.0.31 e verrà rimossa a ottobre 2023. |
| Applica sconti a prezzo unitario | Questa impostazione aveva lo scopo di controllare se i prezzi e gli sconti vengono arrotondati a livello di prezzo unitario o a livello di riga di vendita durante il calcolo del prezzo. L'abbiamo deprecata perché non viene utilizzata da nessuna parte nella base di codice corrente. | Deprecata nella versione 10.0.31 e verrà rimossa a ottobre 2023. |
| Calcola manualmente più sconti articoli | Abbiamo fornito questa impostazione per controllare se il motore di determinazione del prezzo utilizza il calcolo del prezzo ritardato per il canale del punto vendita al dettaglio. Se il parametro è impostato su **Sì**, il motore di determinazione del prezzo non calcola immediatamente gli sconti multiriga (come sconti quantità, sconti soglia e sconti mix and match) ogni volta che un ordine cliente viene creato o modificato nell'applicazione POS. Abbiamo deciso di consolidare questa impostazione con un'impostazione simile nei parametri Commerce per effettuare un controllo multicanale. | Deprecata nella versione 10.0.31 e verrà rimossa a ottobre 2023. |

Per un elenco completo delle funzionalità rimosse o deprecate in Dynamics 365 Commerce, vedere [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
