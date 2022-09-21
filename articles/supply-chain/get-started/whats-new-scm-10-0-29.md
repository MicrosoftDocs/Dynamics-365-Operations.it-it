---
title: Anteprima di Dynamics 365 Supply Chain Management 10.0.29 (ottobre 2022)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.29.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 316650de19d3275f2c60c79c10d6ac8a8c79e1aa
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427876"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10029-october-2022"></a>Anteprima di Dynamics 365 Supply Chain Management 10.0.29 (ottobre 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione di anteprima 10.0.29. Questa versione ha il numero di build 10.0.1326 ed è disponibile con il seguente programma:

- **Anteprima della versione:** agosto 2022
- **Disponibilità generale della versione (aggiornamento automatico):** settembre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo articolo per includere le funzionalità che sono state aggiunte nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Inventario e logistica | [Alloca e prenota articoli WMS in Visibilità inventario](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | Presto disponibili | Abilitato per impostazione predefinita |
| Inventario e logistica | [Precarica elenchi di scorte disponibili ottimizzati](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | Presto disponibili | Abilitato per impostazione predefinita |
| Automazione dell'offerta Produzione su ordine | [Automazione dell'offerta Produzione su ordine](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Automazione dell'offerta Produzione su ordine](../master-planning/make-to-order-supply-automation.md) | Gestione funzionalità:<br>*Automazione dell'offerta Produzione su ordine* |
| Pianificazione | [Visualizza e applica informazioni dettagliati per DDMRP](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Panoramica della pianificazione del fabbisogno di materiale basato sulla domanda](../master-planning/planning-optimization/ddmrp-overview.md) | Gestione funzionalità:<br>*(Anteprima) DDMRP per Ottimizzazione pianificazione* |
| Controllo produzione | [Rendi fisicamente disponibili i prodotti finiti prima della registrazione nei giornali](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Rendi fisicamente disponibili i prodotti finiti prima della registrazione nei giornali](../production-control/deferred-posting.md) | Gestione funzionalità:<br>*(Anteprima) Rendi fisicamente disponibili i prodotti finiti prima della registrazione nei giornali* |
| Warehouse Management | [Cerca dati pertinenti in Warehouse mobile app](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Esegui query sui dati usando le deviazioni dell'app per dispositivi mobili Warehouse Management](../warehousing/warehouse-app-data-inquiry.md) | Gestione funzionalità:<br>*Flusso di richiesta di dati dell'app Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Gestione costi | Ottimizzazione del calcolo del prezzo in sospeso di co-prodotto | Questa funzionalità risolve un conflitto che a volte può verificarsi quando i prezzi di co-prodotti vengono calcolati utilizzando più thread. Induce il sistema a verificare che ogni prezzo di co-prodotto venga calcolato una sola volta. Il risultato di tale calcolo viene quindi utilizzato come input per tutti gli altri calcoli. Se esiste già un prezzo in sospeso, viene utilizzato quel prezzo. |
| Pianificazione generale | Raggruppa transazioni in Ottimizzazione pianificazione | Questa funzionalità aiuta a ridurre il numero di ordini pianificati generati per fornire una singola riga di ordine cliente quando si utilizza Ottimizzazione pianificazione. Quando questa funzionalità è attivata, Ottimizzazione pianificazione raggrupperà tutte le transazioni di magazzino per una riga ordine in un unico fabbisogno per l'intera quantità (questo comportamento corrisponde al comportamento del motore di pianificazione integrato). Offerta e domanda sono raggruppate separatamente. Pertanto, la funzionalità aiuta a ridurre il volume delle transazioni quando si hanno transazioni divise e quando si utilizzano dimensioni (come numeri di lotto o numeri di serie) che non sono dimensioni di copertura. |
| Approvvigionamento | Metti in attesa fornitore per ordini fornitore | Questa funzionalità ti consente di mettere in attesa un fornitore per gli ordini fornitore. Aggiunge un nuovo tipo di messa in attesa *Ordine fornitore* che contrassegna un fornitore come in attesa per gli ordini fornitore. Non potrai creare nuovi ordini fornitore per i fornitori in attesa, ma potrai comunque procedere con eventuali fatture o pagamenti aperti per tali fornitori. |
| Vendite e marketing | Calcola importo netto riga all'importazione | Questa funzionalità ti consente di determinare se il sistema deve ricalcolare i totali di riga quando si importano dati tramite l'entità *Righe ordine cliente*, *Righe offerta di vendita* o *Righe ordine di reso* mediante OData o la doppia scrittura. Ha effetto solo quando sono presenti anche criteri di valutazione di accordi commerciali che limitano le modifiche al campo **Importo netto** per righe di ordine cliente, di offerta di vendita e/o di ordine di reso. Aggiunge un'impostazione denominata **Calcola importo netto riga** alla pagina **Contabilità clienti > Impostazioni > Parametri contabilità clienti**. Quando questa impostazione è impostata su *Sì*, il sistema ricalcolerà sempre gli importi delle righe quando necessario (ignorando quindi eventuali criteri di valutazione di accordi commerciali per l'importo netto delle righe). Quando l'impostazione è impostata su *No*, il sistema non calcolerà mai automaticamente l'importo netto delle righe, anche quando le modifiche in entrata al prezzo, alla quantità e/o allo sconto delle righe implicherebbero il ricalcolo dell'importo netto delle righe. Questa funzione è abilitata per impostazione predefinita e imposta inizialmente **Calcola importo netto riga** su *Sì*. L'impostazione *No* corrisponde al comportamento del sistema prima della versione 10.0.23 e viene fornita principalmente per supportare gli scenari di integrazione legacy.<br><br>Per ulteriori informazioni, vedi [Ricalcolare gli importi netti di riga durante l'importazione di ordini cliente, offerte e resi](../sales-marketing/calc-line-net-amounts-import.md). |
| Vendite e marketing | Calcola totali vendite tramite più thread | Questa funzionalità consente di migliorare le prestazioni consentendo al sistema di usare l'elaborazione parallela per i calcoli dei totali delle vendite in un batch. La funzionalità aggiunge un nuovo campo **Numero di thread** alla finestra di dialogo **Calcola totali vendite**. Se scegli di eseguire il calcolo in un batch, puoi utilizzare questo campo per impostare il numero massimo di thread. Se imposti il valore su *0* (zero) o *1*, verrà utilizzato un singolo thread. I valori superiori a 1 abilitano il multithreading. |
| Vendite e marketing | Aggiorna prezzi e sconti immessi manualmente per sistema interaziendale | Questa funzionalità aggiunge supporto per criteri di modifica manuale per ordini interaziendali. Include supporto per il trasferimento di criteri di modifica manuale tra ordini cliente e fornitore interaziendali. In precedenza, i criteri di modifica manuale erano supportati solo per ordini non interaziendali. Quando questa funzionalità è abilitata, il sistema offre la possibilità di aggiornare i prezzi e gli sconti dopo aver salvato le modifiche a un ordine interaziendale. Questa opzione ti consente di scegliere se applicare i dettagli di nuovi prezzi e sconti all'ordine interaziendale o lasciare l'ordine invariato. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti articoli della guida. Questi articoli non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nelle sezioni precedenti. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Articoli nuovi o aggiornati |
|---|---|
| Pianificazione generale, CTP | [Calcolare le date di consegna di ordini cliente utilizzando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Pianificazione generale, DDMRP | [Panoramica della pianificazione del fabbisogno di materiale basato sulla domanda](../master-planning/planning-optimization/ddmrp-overview.md)<br>[Attivare la funzionalità DDMRP per il sistema](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Posizionamento delle scorte](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Profilo e livelli di buffer](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Pianificazione basata sulla domanda](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Esecuzione collaborativa e visiva](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Warehouse Management | [Imballare contenitori per la spedizione](../warehousing/packing-containers.md)<br>[Lavoro di imballaggio per l'imballaggio di contenitori in uscita e l'elaborazione di spedizioni](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Modifica allo stato della funzionalità in questa versione

Questa tabella elenca le funzionalità diventate obbligatore o attivate per impostazione predefinita nella versione 10.0.29. Tutte queste funzionalità verranno automaticamente attivate per il tuo sistema non appena esegui l'aggiornamento alla versione 10.0.29. Le funzionalità obbligatorie non possono essere disattivate, ma le funzionalità che sono attivate per impostazione predefinita possono comunque essere disattivate utilizzando [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La tabella elenca anche le funzionalità che in precedenza erano in anteprima pubblica, ma che sono state modificate per diventare generalmente disponibili nella versione 10.0.29. Questa modifica indica che le funzionalità sono ora consigliate per l'uso in ambienti di produzione. Queste funzionalità sono disattivate per impostazione predefinita, salvo diversa indicazione. Di conseguenza, devi utilizzare [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitarle e utilizzarle.

| Modulo | Nome funzionalità | Nuovo stato funzionalità |
| --- | --- | --- |
| Gestione cespiti | [Funzionalità di gestione cespiti per l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Gestione costi | [Modifica l'etichetta di Annullamento in Chiusura e rettifica su Storno](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Obbligatorio |
| Gestione costi | Pulisci versioni di determinazione costi calcolo DBA | Obbligatorio |
| Gestione costi | [Archiviazione confronto prezzi articoli](../cost-management/compare-item-price.md) | Obbligatorio |
| Gestione costi | [Livello di calcolo costi](../cost-management/cost-calculation-level.md) | In base all'impostazione predefinita |
| Gestione costi | Abilita l'impostazione del numero di batch definito dall'utente per lo storno della chiusura dell'inventario | In base all'impostazione predefinita |
| Gestione costi | [Dettagli avanzamento chiusura inventario](whats-new-scm-10-0-21.md) | In base all'impostazione predefinita |
| Gestione costi | [Archiviazione report valori di magazzino](../cost-management/inventory-value-report-storage.md) | Obbligatorio |
| Gestione costi | Pulizia dati report valori di magazzino | Obbligatorio |
| Gestione costi | Sequenza costi di fallback di media mobile | Obbligatorio |
| Gestione costi | Mostra registro chiusura inventario in una griglia | Obbligatorio |
| Gestione costi | Mostra gli articoli con transazioni non completamente liquidate in formato riepilogativo | Obbligatorio |
| Gestione articoli e magazzino | Consenti valori di attributi batch vuoti | Obbligatorio |
| Gestione articoli e magazzino | Incremento automatico dei numeri di riga delle righe ordine di trasferimento scorte | Obbligatorio |
| Gestione articoli e magazzino | Crea ordine di trasferimento da riga di vendita. | Obbligatorio |
| Gestione articoli e magazzino | Disabilita campo riga giornale di registrazione magazzino nel flusso di lavoro | Obbligatorio |
| Gestione articoli e magazzino | Abilita funzionalità di avviso parametri di gestione qualità scorte | Obbligatorio |
| Gestione articoli e magazzino | (Cina) Escludere i costi di entrata e uscita fisiche dal costo medio mensile | In base all'impostazione predefinita |
| Gestione articoli e magazzino | [Flusso di lavoro per approvazione giornale di registrazione magazzino](../inventory/inventory-journal-workflow.md) | Obbligatorio |
| Gestione articoli e magazzino | [Archiviazione report scorte disponibili](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Obbligatorio |
| Gestione articoli e magazzino | [Visualizzazioni salvate per gestione inventario](saved-views-scm.md) | Obbligatorio |
| Gestione articoli e magazzino | Annullamento ordine di trasferimento | Obbligatorio |
| Gestione articoli e magazzino | Utilizzo dell'unità di misura e della quantità unitaria nei giornali di registrazione magazzino | Obbligatorio |
| Gestione articoli e magazzino | Sblocca giornale di registrazione magazzino | Obbligatorio |
| Produzione | [Prelievo automatico di materiali pronti per il magazzino per le distinte di prelievo registrate automaticamente](whats-new-scm-10-0-23.md) | Generalmente disponibile |
| Produzione | Abilita la visualizzazione delle dimensioni inventariali nell'elenco dei materiali per le operazioni cicli di lavorazione produzione | Obbligatorio |
| Produzione | [Abilitare per immettere numeri di serie e batch durante la dichiarazione di finito dal dispositivo scheda processo](../production-control/report-finished-job-device.md) | In base all'impostazione predefinita |
| Produzione | Prelievo di quantità a peso variabile di produzione migliorata | In base all'impostazione predefinita |
| Produzione | [Ricerca del processo per l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Produzione | [Integrazione di sistemi di esecuzione della produzione](../production-control/mes-integration.md) | In base all'impostazione predefinita |
| Produzione | [Visualizzazione "Registrazioni quotidiane" per l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) | In base all'impostazione predefinita |
| Produzione | [Controllo disponibilità materiali su richiesta per ordini di produzione](whats-new-scm-10-0-24.md) | In base all'impostazione predefinita |
| Produzione | [Sovrascrivi prenotazione di produzione predefinita](../production-control/override-default-reservation-principle.md) | Obbligatorio |
| Produzione | [Registra il consumo di materiali nell'interfaccia di esecuzione dell'area di produzione (non WMS)](../production-control/production-floor-execution-configure.md) | Generalmente disponibile |
| Produzione | [Report sugli articoli a peso variabile dall'interfaccia di esecuzione area di produzione](../production-control/production-floor-execution-configure.md) | Generalmente disponibile |
| Produzione | [Report sui sotto/co-prodotti dall'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) | In base all'impostazione predefinita |
| Produzione | [Report sugli articoli pianificazione nell'interfaccia di esecuzione dell'area di produzione](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | In base all'impostazione predefinita |
| Produzione | [Visualizzazioni salvate per il controllo della produzione](saved-views-scm.md) | Obbligatorio |
| Produzione | [Mostra i numeri di identificazione, serie e batch completi nell'interfaccia di esecuzione area di produzione](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Produzione | [Convalida la scadenza delle materie prime rispetto alla data di consumo pianificata](whats-new-scm-10-0-23.md) | In base all'impostazione predefinita |
| Pianificazione generale | [Stabilizzazione automatica per l'ottimizzazione della pianificazione](../master-planning/planning-optimization/planned-order-firming.md) | Obbligatorio |
| Pianificazione generale | [Stabilizzazione e consolidamento batch per ordini batch in blocco e di imballaggio pianificati](whats-new-scm-10-0-20.md) | In base all'impostazione predefinita |
| Pianificazione generale | [Includi articoli con disponibilità se sono abilitati filtri di pre-elaborazione](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | In base all'impostazione predefinita |
| Pianificazione generale | [Programmazione capacità infinita per Ottimizzazione pianificazione](../master-planning/planning-optimization/infinite-capacity-planning.md) | In base all'impostazione predefinita |
| Pianificazione generale | [Margini per Ottimizzazione pianificazione](../master-planning/planning-optimization/safety-margins.md) | Obbligatorio |
| Pianificazione generale | [Giorni negativi per l'ottimizzazione della pianificazione](../master-planning/planning-optimization/delay-tolerance.md) | Obbligatorio |
| Pianificazione generale | [Autorizzazione parallela della previsione della domanda modificata](whats-new-scm-10-0-20.md) | Obbligatorio |
| Pianificazione generale | [Stabilizzazione pianificata di ordini con filtro](../master-planning/planning-optimization/planned-order-firming.md) | Obbligatorio |
| Pianificazione generale | [Ordini di produzione pianificati per Ottimizzazione pianificazione](../master-planning/planning-optimization/production-planning.md) | Obbligatorio |
| Pianificazione generale | [Accordi commerciali di acquisto per Ottimizzazione pianificazione](../master-planning/planning-optimization/purchase-trade-agreement.md) | Obbligatorio |
| Pianificazione generale | [Visualizzazioni salvate per ordini pianificati](saved-views-scm.md) | Obbligatorio |
| Approvvigionamento | Spese basate su importi iniziali e finali su ordini fornitore | Obbligatorio |
| Approvvigionamento | Disabilita pulsante Reimposta per distribuzione richiesta di acquisto | In base all'impostazione predefinita |
| Approvvigionamento | [Abilitare la reimpostazione dei flussi di lavoro correlati all'approvvigionamento](whats-new-scm-10-0-20.md) | In base all'impostazione predefinita |
| Approvvigionamento | [Limita il numero di righe ordine fornitore per attività batch](whats-new-scm-10-0-27.md) | In base all'impostazione predefinita |
| Approvvigionamento | [Unisci dimensioni finanziarie del fornitore con la dimensione finanziaria del collegamento dimensione attivo nell'ordine fornitore](whats-new-scm-10-0-25.md) | Obbligatorio |
| Approvvigionamento | [Registra quantità registrate di prodotti stoccati e rimanenze di prodotti non stoccati per entrate e fatture fornitore](whats-new-scm-10-0-26.md) | Generalmente disponibile |
| Approvvigionamento | [Impedisci utilizzo eccessivo di prenotazioni di budget generale quando più richieste di acquisto sono presenti nel flusso di lavoro](whats-new-scm-10-0-21.md) | In base all'impostazione predefinita |
| Approvvigionamento | [Parte responsabile del contratto di acquisto](../procurement/purchase-agreements.md) | Obbligatorio |
| Approvvigionamento | [Visualizzazioni salvate per ordini fornitore](saved-views-scm.md) | Obbligatorio |
| Gestione informazioni sul prodotto | Pre-elaborazione report distinta base per evitare il timeout | Obbligatorio |
| Gestione informazioni sul prodotto | Imposta dimensioni finanziarie predefinite separatamente quando si utilizzano i modelli di articolo | Obbligatorio |
| Gestione informazioni sul prodotto | Abilita gruppi di dimensioni prodotto per i modelli di articolo | Obbligatorio |
| Gestione informazioni sul prodotto | Entità articolo - codice a barre migliorata | Obbligatorio |
| Gestione informazioni sul prodotto | Rigenera nomi varianti prodotto in base alla nomenclatura | Obbligatorio |
| Gestione informazioni sul prodotto | [Visualizzazioni salvate per prodotti rilasciati](saved-views-scm.md) | Obbligatorio |
| Gestione informazioni sul prodotto | [Miglioramenti della pagina Suggerimenti variante](../pim/tasks/create-predefined-product-variants.md) | Obbligatorio |
| Vendite e marketing | [Allocazione spese in un ordine cliente](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Obbligatorio |
| Vendite e marketing | Pulisci storico aggiornamento ordini cliente | Obbligatorio |
| Vendite e marketing | [Pulisci storico aggiornamento vendite in base alla validità](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Obbligatorio |
| Vendite e marketing | [Ottimizzazione esportazione entità di dati persona di contatto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Obbligatorio |
| Vendite e marketing | Copia gruppo di sconti totali per nota di accredito di vendita | Obbligatorio |
| Vendite e marketing | [Abilita ricerca per i campi chiusura documenti e introduzione documenti di offerta di vendita](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Obbligatorio |
| Vendite e marketing | [Migliora le prestazioni del report "Primi 100" clienti](whats-new-scm-10-0-23.md) | Obbligatorio |
| Vendite e marketing | Includi record in attesa nelle attività di pulizia storico | Obbligatorio |
| Vendite e marketing | Limita il numero di righe ordine cliente per attività batch | In base all'impostazione predefinita |
| Vendite e marketing | [Limita il numero di ordini cliente che è possibile selezionare per la registrazione](whats-new-scm-10-0-21.md) | Obbligatorio |
| Vendite e marketing | Ricalcola saldo cliente stimato | Obbligatorio |
| Vendite e marketing | [Registrazione riga ordine di reso vendita con precisione decimale con e senza peso variabile](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Obbligatorio |
| Vendite e marketing | [Visualizzazioni salvate per vendite e marketing](saved-views-scm.md) | Obbligatorio |
| Vendite e marketing | [Conferma dell'ordine cliente con un solo clic](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Obbligatorio |
| Gestione trasporto | Consenti la mancata corrispondenza delle fatture di trasporto con le righe fattura di trasporto senza un giornale di registrazione fatture fornitore registrato | In base all'impostazione predefinita |
| Gestione trasporto | [Abilitare la creazione di un giornale di registrazione fatture fornitore quando si rimuove una fattura di trasporto](whats-new-scm-10-0-20.md) | In base all'impostazione predefinita |
| Gestione trasporto | [Spedizione pacchi di piccole dimensioni](../warehousing/small-parcel-shipping.md) | Obbligatorio |
| Gestione trasporto | [Documento del certificato di origine USMCA](../transportation/usmca-certification-of-origin.md) | In base all'impostazione predefinita |
| Warehouse Management | [Zona ubicazione aggiuntiva](../warehousing/additional-location-zones.md) | Obbligatorio |
| Warehouse Management | [Annulla lavoro](../warehousing/cancel-warehouse-work.md) | Obbligatorio |
| Warehouse Management | [Consolida spedizione](../warehousing/configure-shipment-consolidation-policies.md) | Obbligatorio |
| Warehouse Management | [Creare ed elaborare ordini di trasferimento dall'app di magazzino](../warehousing/create-transfer-order-from-warehouse-app.md) | Obbligatorio |
| Warehouse Management | Modelli di cross-docking con direttive di ubicazione | In base all'impostazione predefinita |
| Warehouse Management | [Scollega lavoro di stoccaggio da ASN](whats-new-scm-10-0-21.md) | Obbligatorio |
| Warehouse Management | [Operazioni Put differite](../warehousing/deferred-processing-manual-inventory-movement.md) | Obbligatorio |
| Warehouse Management | Contenitore - Inserimento differito | In base all'impostazione predefinita |
| Warehouse Management | Elaborazione operazione put differita - Abilita la funzionalità modello di controllo con evento di attivazione impostato su Precedente | Obbligatorio |
| Warehouse Management | [Disabilitare le ricevute previste dagli ordini di controllo qualità che campionano le scorte bloccate](../inventory/inventory-blocking.md) | In base all'impostazione predefinita |
| Warehouse Management | Abilita convalida rapida per i dispositivi mobili del magazzino | Obbligatorio |
| Warehouse Management | [Parser avanzato per codici a barre GS1](../warehousing/gs1-barcodes.md) | Generalmente disponibile |
| Warehouse Management | [Prenotazione targa impegnata dell'ordine flessibile](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obbligatorio |
| Warehouse Management | [Prenotazione flessibile di dimensioni a livello di magazzino](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obbligatorio |
| Warehouse Management | [Utilizzo ubicazione consolidamento articolo](../warehousing/item-consolidation-location-utilization.md) | In base all'impostazione predefinita |
| Warehouse Management | Cronologia ricevimento targa | In base all'impostazione predefinita |
| Warehouse Management | [Consolidamento spedizioni manuale](../warehousing/consolidate-shipments-manual-workbench.md) | In base all'impostazione predefinita |
| Warehouse Management | [Servizio di prelievo manuale righe di trasferimento per amministratori o utenti attendibili simili](whats-new-scm-10-0-28.md) | Generalmente disponibile |
| Warehouse Management | [Interfaccia attrezzatura movimentazione materiali](../warehousing/mhax.md) | Obbligatorio |
| Warehouse Management | [Nuove pagine del workbench di pianificazione del carico](whats-new-scm-10-0-24.md) | Generalmente disponibile |
| Warehouse Management | [Visualizzazione del carico di lavoro in uscita](../warehousing/outbound-workload-visualization.md) | Obbligatorio |
| Warehouse Management | [Cross-docking pianificato](../warehousing/planned-cross-docking.md) | Obbligatorio |
| Warehouse Management | [Elabora eventi dell'app magazzino](../warehousing/warehouse-app-events.md) | Obbligatorio |
| Warehouse Management | Query migliorata per il modello di lavoro stoccaggio del co-prodotto e del sottoprodotto | Obbligatorio |
| Warehouse Management | [Arrotonda quantità per difetto all'unità di vendita più vicina al momento del rilascio nel magazzino](whats-new-scm-10-0-19.md) | Obbligatorio |
| Warehouse Management | [Visualizzazione salvata per il workbench di pianificazione del carico](saved-views-scm.md) | Obbligatorio |
| Warehouse Management | [Visualizzazione salvata per la pagina dei dettagli del lavoro](saved-views-scm.md) | Obbligatorio |
| Warehouse Management | [Visualizzazione salvata per elaborazione ciclo](saved-views-scm.md) | Obbligatorio |
| Warehouse Management | [Visualizzazioni salvate per elaborazione carico](saved-views-scm.md) | Obbligatorio |
| Warehouse Management | [Visualizzazioni salvate per elaborazione spedizione](saved-views-scm.md) | Obbligatorio |
| Warehouse Management | [Esegui scansione codici a barre GS1](../warehousing/gs1-barcodes.md) | Generalmente disponibile |
| Warehouse Management | Dettagli etichetta ciclo di spedizione | Obbligatorio |
| Warehouse Management | [Assegna in unità miste](whats-new-scm-10-0-21.md) | Obbligatorio |
| Warehouse Management | [Utilizza API veloce per chiusura/riapertura contenitori in stazione di imballaggio](whats-new-scm-10-0-21.md) | In base all'impostazione predefinita |
| Warehouse Management | [Convalida modelli selezionati per processi di rifornimento](whats-new-scm-10-0-20.md) | In base all'impostazione predefinita |
| Warehouse Management | [Campi promossi dell'app di magazzino](../warehousing/warehouse-app-promoted-fields.md) | Obbligatorio |
| Warehouse Management | [Istruzioni per i passaggi dell'app di magazzino](../warehousing/mobile-app-titles-instructions.md) | Obbligatorio |
| Warehouse Management | [Stato ubicazione magazzino](../warehousing/warehouse-location-status.md) | Obbligatorio |
| Warehouse Management | [Deviazioni app Warehouse Management](../warehousing/warehouse-app-detours.md) | In base all'impostazione predefinita |
| Warehouse Management | [Dettagli processo batch ciclo](../warehousing/wave-processing.md) | Obbligatorio |
| Warehouse Management | [Notifiche di esecuzione ciclo](../warehousing/wave-execution-notifications.md) | Obbligatorio |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.29 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.29 delle app per finanza e operazioni (ottobre 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ognuno degli aggiornamenti che fanno parte della versione 10.0.29, accedi a Lifecycle Services (LCS) e visualizza l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e cloud di settore: piano del primo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
