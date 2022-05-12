---
title: Parametri di registrazione di Commerce
description: Questo argomento descrive i parametri specifici per la registrazione di transazioni finanziarie e fisiche in Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 1b49c893567d39f05e16cefee47407a424b7e139
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649203"
---
# <a name="commerce-posting-parameters"></a>Parametri di registrazione di Commerce

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento descrive i parametri specifici per la registrazione di transazioni finanziarie e fisiche in Microsoft Dynamics 365 Commerce. I parametri di registrazione di Commerce si trovano in Commerce headquarters in **Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Parametri di commercio \> Registrazione**.

## <a name="periodic-discount-parameters"></a>Parametri di sconto periodico

La tabella seguente elenca i parametri di sconto periodico specifici per la registrazione di transazioni finanziarie e fisiche.

| Parametro | Description |
|-----------|-------------|
| Registra sconto di periodo | Questa opzione controlla se le offerte periodiche vengono registrate nei conti contabili. Gli sconti periodici includono gli sconti gamma, gli sconti quantità e le offerte di sconto. Quando questo parametro è abilitato, è possibile impostare campi aggiuntivi nella sezione **Sconti periodici**. |
| Tipo di conto CoGe | <p>Seleziona il tipo di conto che viene utilizzato per registrare gli sconti periodici:</p><ul><li>**Standard** – Il sistema non utilizza i campi relativi allo sconto in questa pagina. Utilizza invece i conti definiti nella pagina **Registrzione** in Commerce headquarters (**Gestione inventario \> Impostazione \> Registrazione \> Moduli di registrazione**).</li><li>**Periodico** – Il sistema utilizza i conti di sconto di Commerce specificati nei campi relativi agli sconti in questa pagina. Se si seleziona questa opzione, è necessario specificare il conto di contabilità generale (CG) per ogni tipo di offerta (sconto, sconto gamma, quantità e soglia). Quando imposti uno sconto, puoi definire il conto. Quando la funzione di registrazione del conto di sconto viene utilizzata nella pagina di impostazione dello sconto, viene eseguita una registrazione di addebito e di accredito aggiuntiva per riclassificare la registrazione dello sconto dal conto CoGe di sconto di Commerce al conto CoGe di sconto. Per ulteriori informazioni, vedi [Sconti vendita al dettaglio](retail-discounts-overview.md).</li></ul> |
| Registra sconto in base al codice informativo | Questa opzione non è più utilizzata nella soluzione Commerce standard e sarà deprecata. |
| Registra lo sconto periodico per gli ordini | Questa opzione controlla se gli sconti periodici al dettaglio vengono registrati nella contabilità generale per gli ordini cliente e gli ordini servizio clienti. |

## <a name="inventory-update-parameters"></a>Parametri di aggiornamento inventario

La tabella seguente elenca i parametri di aggiornamento inventario specifici per la registrazione di transazioni finanziarie e fisiche.

| Parametro | Description |
|-----------|-------------|
| Utilizza ID batch predefinito se i numeri batch non vengono trovati | Questa opzione controlla se un ID batch predefinito viene utilizzato per gli articoli abilitati al batch se i numeri di batch non vengono trovati ed è consentito l'inventario negativo. |
| ID batch predefinito | Il numero di batch da utilizzare se i numeri di batch per gli articoli non vengono trovati e il parametro **Utilizza ID batch predefinito se i numeri batch non vengono trovati** è abilitato. |

## <a name="aggregation-parameters"></a>Parametri di aggregazione

La tabella seguente elenca i parametri di aggregazione specifici per la registrazione di transazioni finanziarie e fisiche.

| Parametro | Description |
|-----------|-------------|
| Deposito in cassaforte | Abilita questo parametro per aggregare tutte le transazioni durante la registrazione del rendiconto e creare una singola riga nel giornale di registrazione invece di una riga separata per ogni rilascio. |
| Deposito bancario | Abilita questo parametro per aggregare tutte le transazioni durante la registrazione del rendiconto e creare una singola riga nel giornale di registrazione invece di una riga separata per ogni rilascio. |
| Transazioni di vendita | Abilita questo parametro per consolidare le transazioni come parte del processo di registrazione del rendiconto transazioni. Consigliamo di abilitare questo parametro. In precedenza era chiamato **Transazioni giustificativo**. |
| Non aggregare i resi | Se questa opzione è selezionata, ogni transazione di reso verrà registrata come ordine cliente separato durante la registrazione di un rendiconto di vendita al dettaglio. |

## <a name="batch-processing-parameters"></a>Parametri di elaborazione batch

La tabella seguente elenca i parametri di elaborazione batch specifici per la registrazione di transazioni finanziarie e fisiche.

| Parametro | Description |
|-----------|-------------|
| Numero massimo di rendiconti paralleli | Questo campo definisce il numero di attività batch utilizzate per registrare più rendiconto. |
| Thread massimo per elaborazione ordini per rendiconto | Questo campo rappresenta il numero massimo di thread utilizzati dal processo batch di registrazione del rendiconto per creare e fatturare gli ordini di vendita per un singolo rendiconto. Il numero totale di thread che viene utilizzato dal processo di registrazione del rendiconto viene calcolato moltiplicando il valore di questo parametro per il valore del parametro **Numero massimo di registrazioni rendiconti paralleli**. Se il valore di questo parametro è troppo alto può influire negativamente sulle prestazioni del processo di registrazione del rendiconto. |
| Numero massimo di righe transazione incluse in un'aggregazione | Questo campo definisce il numero di righe transazione che vengono incluse in una singola transazione aggregata prima che ne venga creata una nuova. Le transazioni aggregate vengono create in base a diversi criteri di aggregazione come cliente, data del giorno lavorativo o dimensioni finanziarie. Tieni presente che le righe de una singola transazione non vengono suddivise tra diverse transazioni aggregate. Ciò significa che il numero di righe in una transazione aggregata può essere leggermente superiore o inferiore in base a fattori quali il numero di prodotti distinti. |
| Numero massimo di thread per convalidare le transazioni del punto vendita | Questo campo definisce il numero massimo di thread che possono essere utilizzati per convalidare le transazioni. La convalida delle transazioni è un passaggio obbligatorio che deve essere eseguito prima che le transazioni vengano inserite nei rendiconti. Inoltre, è necessario definire un prodotto gift card nella Scheda dettaglio **Gift card** della scheda **Registrazione** della pagina **Parametri di commercio** se l'organizzazione non usa gif card. |

La tabella seguente elenca i valori consigliati per i parametri della tabella precedente. Questi valori devono essere testati e adattati alla configurazione della distribuzione e all'infrastruttura disponibile. Qualsiasi aumento dei valori consigliati può influire negativamente su altre elaborazioni batch e deve essere convalidato.

| Parametro | Valore consigliato | Dettagli |
|-----------|-------------------|---------|
| Numero massimo di registrazioni rendiconti paralleli | <p>Imposta questo parametro sul numero di attività batch disponibili per il gruppo batch che esegue il processo **Dichiarazione**.</p><p>**Regola generale:** moltiplica il numero di server virtuali Application Object Server (AOS) per il numero di attività batch disponibili per ogni server virtuale AOS.</p> | Questo parametro non è applicabile quando la funzionalità **Rendiconti di vendita al dettaglio (inserimento continuo)** è abilitata. |
| Thread massimo per elaborazione ordini per rendiconto | Inizia a testare i valori a **4**. In genere, il valore non deve superare **8**. | Questo parametro definisce il numero di thread utilizzati per creare e registrare ordini cliente. Rappresenta il numero di thread disponibili per la pubblicazione per istruzione. |
| Numero massimo di righe transazione incluse in un'aggregazione | Inizia a testare i valori a **1000**. A seconda della configurazione di Commerce headquarters, ordini più piccoli potrebbero essere più vantaggiosi per le prestazioni. | Questo parametro definisce il numero di righe che vengono incluse in ciascun ordine cliente durante la registrazione della dichiarazione. Una volta raggiunto questo numero, le righe verranno suddivise in un nuovo ordine. Il numero di righe di vendita non sarà esattamente uguale al numero specificato, poiché la suddivisione avviene a livello di ordine cliente. Tuttavia, il numero sarà vicino al numero impostato. Questo parametro viene utilizzato per generare ordini cliente per transazioni al dettaglio che non hanno un cliente denominato. |
| Numero massimo di thread per convalidare le transazioni del punto vendita | Si consiglia di impostare questo parametro su **4** e di aumentarlo solo se non raggiungi prestazioni accettabili. Il numero di thread utilizzati da questo processo non può superare il numero di processori disponibili per il server batch. Se il numero di thread è troppo alto, altre elaborazioni batch potrebbero essere interessate. | Questo parametro controlla il numero di transazioni che possono essere convalidate contemporaneamente per un determinato punto vendita. |

> [!NOTE]
> Tutti i parametri e le impostazioni correlati alle registrazioni dei rendiconti e definiti nei punti vendita e nella pagina **Parametri di commercio** sono applicabili alla funzionalità di registrazione dei rendiconti migliorata.

## <a name="invoice-parameters"></a>Parametri delle fatture

La tabella seguente elenca i parametri di fatture specifici per la registrazione di transazioni finanziarie e fisiche.

| Parametro | Description |
|-----------|-------------|
| Nome giornale di registrazione | Il nome del giornale di registrazione pagamenti utilizzato quando vengono creati i giornali di registrazione pagamenti cliente per i pagamenti degli ordini cliente. Questa impostazione si applica a tutti i pagamenti degli ordini registrati per ordini POS, call center e canali di e-commerce. |
| Nome conto | Nome del conto di pagamento. |
| Assegna priorità a dimensioni da metodo di pagamento | Se il flag è abilitato, il giornale di registrazione pagamenti dispone di dimensioni con priorità del metodo di pagamento anziché del punto vendita. |
| Comportamento calcolo imposta | Questo parametro specifica il comportamento quando gli ordini cliente creati durante la registrazione del rendiconto vengono fatturati:<ul><li>**Ricalcola** – Calcola di nuovo le imposte.</li><li> **Non ricalcolare** – Utilizza gli importi delle imposte calcolati nel POS.</li></ul> |
| Nome giornale di registrazione | Il nome del giornale di registrazione utilizzato quando viene creato un giornale di registrazione pagamenti cliente per i rimborsi. Questa impostazione si applica a tutti i pagamenti degli ordini registrati per ordini POS, call center e canali di e-commerce. |

## <a name="statement-parameters"></a>Parametri di rendiconto

La tabella seguente elenca i parametri di rendiconto specifici per la registrazione di transazioni finanziarie e fisiche.

| Parametro | Description |
|-----------|-------------|
| Prenota scorte durante il calcolo | Quando questo parametro è abilitato, il calcolo del rendiconto riserva temporaneamente le scorte fino alla registrazione del rendiconto. Questo parametro è disabilitato per impostazione predefinita per migliorare le prestazioni del calcolo del rendiconto. Le informazioni aggiornate sull'inventario possono essere calcolate utilizzando il processo batch **Registra magazzino**. Tieni presente che il processo batch **Registra magazzino** non viene più utilizzato quando la creazione degli ordini basata su [inserimento continuo](trickle-feed.md) è abilitata per le transazioni del punto vendita al dettaglio. |
| Disabilita conteggio richiesto | Questo flag disabilita il conteggio durante la registrazione in Commerce headquarters. |
| Ricalcola le dimensioni finanziarie in caso di errore | Quando questo parametro è abilitato, le dimensioni finanziarie possono essere rivalutate in successive registrazioni di rendiconto se la registrazione del rendiconto non riesce. |
| Utilizza dimensioni finanziarie del punto vendita resi | Quando questo parametro è abilitato, è possibile creare ordini di reso-vendita collegati che utilizzano le dimensioni finanziarie del negozio anziché le dimensioni finanziarie della transazione originale. |
| Scollega resi | Quando questo parametro è abilitato, il rendiconto può creare resi di vendite non registrate come resi senza ricevuta. Questo parametro è disabilitato per impostazione predefinita e ti consigliamo di mantenerlo disabilitato. |
| Disabilita la registrazione della differenza di arrotondamento | Questo parametro disabilita la registrazione della differenza di arrotondamento tra il pagamento delle transazioni e l'importo lordo durante l'elaborazione dei pagamenti. |
| Liquida automaticamente i depositi cliente | Quando questo parametro è abilitato, i depositi dei clienti registrati durante la registrazione del rendiconto al dettaglio vengono liquidati in base alle transazioni aperte dei clienti. |
| Abilitare e utilizzare la riconciliazione gestione di cassa da POS | Quando questo parametro è abilitato, la riconciliazione della gestione della cassa viene eseguita nel POS e i valori vengono trasferiti alla registrazione del rendiconto finanziario al dettaglio per creare righe di rendiconto. |
| Livello di dettaglio del giustificativo contabile | Questo parametro definisce il livello di dettaglio incluso nel giustificativo contabile per le transazioni selezionate che hanno origine dal POS. I tipi di transazione includono entrate, spese e sconti. Per gli sconti, questo parametro viene preso in considerazione solo quando il numero di conto per uno sconto periodico e il numero di conto per uno sconto regolare non coincidono. A meno che non siano richiesti dettagli, **Sommario** è il valore consigliato per queste registrazioni. Quando viene definita la registrazione a livello di riepilogo, **TransactionDiscountTrans.RecID** non verrà compilato. Nella versione Commerce 10.0.27, questo flag è stato rinominato e spostato. In precedenza era chiamato **Livello di dettaglio** ed era nella sezione **Aggiorna inventario**. |
