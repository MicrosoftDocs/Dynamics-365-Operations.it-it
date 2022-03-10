---
title: Anteprima di Dynamics 365 Supply Chain Management 10.0.25 (aprile 2022)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.25.
author: kamaybac
ms.date: 02/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 8a9b873b7b4bba43b7b3e6e83c389ac35b4e223e
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102998"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10025-april-2022"></a>Anteprima di Dynamics 365 Supply Chain Management 10.0.25 (aprile 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento elenca le funzionalità nuove o modificate nell'anteprima della versione 10.0.25. di Microsoft Dynamics 365 Supply Chain Management. Questa versione ha il numero di build 10.0.1149 ed è disponibile come segue:

- **Versione di anteprima:** Febbraio 2022
- **Disponibilità generale della versione (aggiornamento automatico):** marzo 2022
- **Disponibilità generale della versione (aggiornamento automatico):** aprile 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Potremmo aggiornare questo argomento per includere le funzionalità che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Inventario&nbsp;e&nbsp;logistica | Miglioramenti dei materiali pericolosi | Questi miglioramenti si basano sulla funzionalità dei materiali pericolosi esistenti per aiutare meglio le aziende a rispettare le normative locali durante il trasporto di materiali pericolosi in aree geografiche diverse. <!-- KFM: Update to 2022w1 link when published -->| Gestione funzionalità:<br>*Miglioramenti dei materiali pericolosi* |
| Inventario&nbsp;e&nbsp;logistica | Lavoro di imballaggio per stazioni di imballaggio | Questa funzionalità migliora notevolmente la flessibilità e l'agilità delle operazioni di imballaggio e spedizione. Durante il processo di imballaggio, i magazzinieri possono ora imballare e spedire singoli pacchi correlati alla stessa spedizione e carico. Le righe ordine che fanno parte della stessa spedizione non devono necessariamente essere spedite insieme se alcuni articoli sono subito pronti per la spedizione. Un singolo ordine può essere imballato e spedito in più pacchi con tempi di spedizione diversi, riducendo così i tempi di attesa e aggiungendo agilità.<!-- KFM: Update to 2022w1 link when published --> | Gestione funzionalità:<br>*Lavoro di imballaggio per stazioni di imballaggio* |
| Inventario&nbsp;e&nbsp;logistica | [Scansiona i codici a barre nel magazzino utilizzando gli standard di formato GS1](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) <!-- KFM: Update to 2022w1 link when published --> | [Codici a barre GS1 e codici QR](../warehousing/gs1-barcodes.md) | Gestione funzionalità:<br>*Esegui scansione codici a barre GS1* |
| Produzione | [Consumo e prenotazioni di materiali nell'interfaccia di esecuzione dell'area di produzione](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [Come i lavoratori utilizzano l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-use.md) | Gestione funzionalità:<br>*(Anteprima) Registra il consumo materiali nell'interfaccia di esecuzione area di produzione (abilitato per WMS)* |
| Produzione | [Registrare consumo di materiali sulle unità di scala](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [Carichi di lavoro di esecuzione della produzione per unità di scala nel cloud e nella rete perimetrale](../cloud-edge/cloud-edge-workload-manufacturing.md) | Gestione funzionalità:<br>*Registra il consumo materiali nell'app per dispositivi mobili in un'unità di scala* |
| Pianificazione | [Suggerimenti di ottimizzazione pianificazione per ottimizzare l'approvvigionamento esistente](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Messaggi d'azione](../master-planning/action-messages.md) | Abilitato per impostazione predefinita |
| Pianificazione | Ordini pianificati semplificati | [Ordini pianificati semplificati](../master-planning/planning-optimization/planned-orders-simplified.md ) | Gestione funzionalità:<br>*Ordini pianificati semplificati* |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Gestione articoli e magazzino | (Polonia) Consentire il collegamento di più fatture DAU a una riga ordine fornitore in un singolo DAU | Questa funzionalità consente di suddividere le righe dell'ordine di acquisto e collegarle a un unico documento amministrativo quando tali righe dell'ordine di acquisto sono state registrate per diverse fatture (ad esempio per spedizioni diverse). |
| Approvvigionamento | Consolida più richieste di acquisto in un singolo ordine fornitore per data contabile | Questa funzionalità consente di consolidare più richieste di acquisto in un unico ordine di acquisto se le diverse richieste di acquisto hanno date contabili diverse. È possibile configurare regole dei criteri di acquisto per la creazione dell'ordine di acquisto e il consolidamento della domanda per automatizzare la decisione di raggruppare le righe della richiesta per data contabile a livello di ordine fornitore. Il consolidamento degli ordini d'acquisto per data contabile non è supportato se il controllo del budget è abilitato perché la data contabile viene utilizzata per le prenotazioni e gli impegni di budget. Pertanto, deve essere conservata durante il passaggio dalla richiesta di acquisto all'ordine fornitore. |
| Approvvigionamento | Visualizza impostazioni predefinite campo di risposta RdO legacy | Questa funzionalità reintroduce le impostazioni del campo di risposta della richiesta di offerta (RdO) predefinita legacy, che erano state precedentemente rimosse dall'interfaccia utente. Queste impostazioni non forniscono alcuna funzionalità predefinita, ma possono essere personalizzate per fornirle secondo necessità. Abilita questa funzione se la tua organizzazione ha già aggiunto funzionalità per le impostazioni del campo di risposta RdO predefinite o se sta pianificando di farlo. Quando questa funzionalità è abilitata, puoi accedere alle impostazioni andando su **Parametri di approvvigionamento**, aprendo la scheda **Richiesta di offerta** e selezionando **Campi di risposta alla richiesta di offerta predefiniti**. |
| Approvvigionamento | Unisci dimensioni finanziarie del fornitore con la dimensione finanziaria del collegamento dimensione attivo nell'ordine fornitore | Questa funzionalità consente di unire dimensioni finanziarie da fornitori con dimensioni finanziarie con collegamento di dimensione attivo dopo l'approvazione della richiesta di acquisto se hai configurato un collegamento tra una dimensione finanziaria e la dimensione dell'inventario del sito. È possibile impostare le regole dei criteri di acquisto per la creazione dell'ordine d'acquisto e il consolidamento della domanda per guidare la decisione di unire le dimensioni finanziarie dei fornitori con la dimensione finanziaria del collegamento alla dimensione attiva a livello di intestazione dell'ordine d'acquisto. |
| Controllo produzione | (Russia) Abilita l'impostazione ubicazione predefinita per formula/DBA di produzione e prenotazione/consumo GTD automatico in produzione | La funzionalità abilita opzioni aggiuntive per la produzione da materie prime importate (solo localizzazione russa):<ul><li>Opzione per impostare l'ubicazione predefinita automatica per le formule di produzione e le distinte base sia nei gruppi di risorse che nei magazzini.</li><li>Prenotazione automatica delle materie prime dalla dimensione *Numero GTD* nei magazzini attivati da WMS secondo l'algoritmo di prenotazione non WMS. Questo vale nei casi in cui esiste un criterio di lavoro per *Prelievo materie prime* con **Metodo di creazione del lavoro** impostato su *Mai* e l'impostazione del magazzino, dell'ubicazione e del numero di articolo corrisponde alle transazioni di magazzino dell'ordine di produzione (batch).</li><li>Consumo automatico di materie prime dalla dimensione *Numero GTD* al momento della registrazione della distinta di prelievo, secondo la prenotazione acquisita descritta in precedenza.</li></ul> |
| Warehouse Management | (Anteprima) Supporto unità di scala per ordini di magazzino in entrata e in uscita | Questa funzionalità fa sì che il sistema crei ordini di magazzino in uscita durante il processo di rilascio in magazzino e crei ordini di magazzino in entrata quando gli ordini di trasferimento vengono registrati come spediti. Il sistema sincronizza quindi ogni ordine di magazzino in entrata o in uscita con l'unità di scala responsabile della spedizione o della ricezione dell'ordine. Tieni presente che dopo aver abilitato questa funzione, i carichi di lavoro di esecuzione del magazzino devono essere aggiornati. Per ulteriori informazioni, vedere [Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Questa funzionalità richiede la funzionalità *Scollega lavoro di stoccaggio da ASN* e abilita la possibilità di ricevere ordini di trasferimento utilizzando il processo di ricezione delle targhe sull'app mobile Warehouse Management. |

## <a name="feature-state-changes-in-this-release"></a>Modifica allo stato della funzionalità in questa versione

Questa tabella elenca le funzionalità diventate obbligatore o attivate per impostazione predefinita a partire dalla versione 10.0.25. Tutte queste funzionalità verranno automaticamente attivate per il tuo sistema non appena esegui l'aggiornamento alla 10.0.25. Le funzionalità obbligatorie non possono essere disattivate, ma le funzionalità attive per impostazione predefinita possono comunque essere disattivate utilizzando [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La tabella elenca anche le funzionalità che erano precedentemente in anteprima pubblica, ma sono state modificate per diventare generalmente disponibili nella versione 10.0.25, il che significa che ora sono consigliate per l'uso negli ambienti di produzione. Queste funzionalità sono disattivate per impostazione predefinita se non diversamente specificato, quindi è necessario utilizzare [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitarle se si desidera utilizzarle.

| Modulo | Nome funzionalità | Stato funzionalità |
| --- | --- | --- |
| Gestione cespiti | [Applica regole per raggruppare ordini di lavoro durante esecuzione piano di manutenzione](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Generalmente disponibile |
| Gestione cespiti | [Gestione basata sul contatore migliorata](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Generalmente disponibile |
| Gestione costi | [Livello di calcolo costi](../cost-management/cost-calculation-level.md) | Generalmente disponibile |
| Gestione costi | Abilita l'impostazione del numero di batch definito dall'utente per lo storno della chiusura dell'inventario | Generalmente disponibile |
| Gestione costi | [Dettagli avanzamento chiusura inventario](whats-new-scm-10-0-21.md) | Generalmente disponibile |
| Gestione costi | [Opzioni per l'impostazione predefinita delle dimensioni finanziarie per la rivalutazione del costo standard di inventario](../cost-management/manage-standard-cost-updates.md) | Generalmente disponibile |
| Gestione costi | Pulizia dati report valori di magazzino | In base all'impostazione predefinita |
| Gestione costi | [Archiviazione report valori di magazzino](../cost-management/inventory-value-report-storage.md) | In base all'impostazione predefinita |
| Gestione costi | Mostra registro chiusura inventario in una griglia | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Abilita gestione modifiche su prodotti esistenti](../engineering-change-management/change-management-existing-products.md) | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Gestione modifiche di progettazione](../engineering-change-management/product-engineering-overview.md) | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Notifiche di progettazione per la produzione](../engineering-change-management/engineering-change-management.md) | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Ereditarietà degli attributi migliorata per la gestione modifiche di progettazione](../engineering-change-management/engineering-attributes-and-search.md) | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Gestisci modifiche a formule e relativi ingredienti](../engineering-change-management/manage-formula-changes.md) | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Controlli di disponibilità prodotto](../engineering-change-management/product-readiness.md) | In base all'impostazione predefinita |
| Gestione modifiche di progettazione | [Generazione di varianti per prodotti di progettazione](../engineering-change-management/engineering-variants.md) | In base all'impostazione predefinita |
| Gestione articoli e magazzino | Passaggio alla versione DBA da righe DBA | Obbligatorio |
| Pianificazione generale | [Stabilizzazione e consolidamento batch per ordini batch in blocco e di imballaggio pianificati](whats-new-scm-10-0-20.md) | Generalmente disponibile |
| Pianificazione generale | Pianificazione delle risorse con manutenzione | Generalmente disponibile |
| Pianificazione generale | Abilitare le funzionalità dell'impostazione guidata del piano generale | Obbligatorio |
| Pianificazione generale | [Selezione modello previsionale in dettagli previsione della domanda](../master-planning/manual-adjustments-baseline-forecast.md) | Obbligatorio |
| Pianificazione generale | [Visualizzazione avanzamento pianificazione generale](../master-planning/tasks/monitor-master-planning-run.md) | Obbligatorio |
| Pianificazione generale | [Stabilizzazione parallela degli ordini pianificati](../master-planning/planning-optimization/planned-order-firming.md) | Obbligatorio |
| Pianificazione generale | [Stabilizzazione pianificata di ordini con filtro](../master-planning/planning-optimization/planned-order-firming.md) | In base all'impostazione predefinita |
| Pianificazione generale | [Visualizzazioni salvate per ordini pianificati](saved-views-scm.md) | In base all'impostazione predefinita |
| Approvvigionamento | Disabilita pulsante Reimposta per distribuzione richiesta di acquisto | Generalmente disponibile |
| Approvvigionamento | [Abilitare la reimpostazione dei flussi di lavoro correlati all'approvvigionamento](whats-new-scm-10-0-20.md) | Generalmente disponibile |
| Approvvigionamento | Possibilità di confermare in batch gli ordini fornitore accettati tramite la collaborazione fornitore | Obbligatorio |
| Approvvigionamento | Stato chiuso contratto di acquisto | Obbligatorio |
| Approvvigionamento | Aggiungi righe a fatture ordine fornitore associate a un contratto di acquisto | In base all'impostazione predefinita |
| Approvvigionamento | Aggiungi campo Quantità ordinata alla pagina Registrazione entrata prodotti | In base all'impostazione predefinita |
| Approvvigionamento | [Consentire ai fornitori di richiedere le categorie di approvvigionamento tramite la collaborazione fornitore](../procurement/category-requests-from-vendors.md) | In base all'impostazione predefinita |
| Approvvigionamento | Spese basate su importi iniziali e finali su ordini fornitore | In base all'impostazione predefinita |
| Approvvigionamento | Impostazione spese con sito e magazzino | In base all'impostazione predefinita |
| Approvvigionamento | Abilita calcolo imposta acquisti in base alla tariffa annuale | In base all'impostazione predefinita |
| Approvvigionamento | [Parte responsabile del contratto di acquisto](../procurement/purchase-agreements.md) | In base all'impostazione predefinita |
| Approvvigionamento | [Visualizzazioni salvate per ordini fornitore](saved-views-scm.md) | In base all'impostazione predefinita |
| Gestione informazioni sul prodotto | [Convalida rigorosa per quantità ordine predefinite](../production-control/default-order-settings.md) | Obbligatorio |
| Gestione informazioni sul prodotto | Pre-elaborazione report distinta base per evitare il timeout | In base all'impostazione predefinita |
| Gestione informazioni sul prodotto | Imposta dimensioni finanziarie predefinite separatamente quando si utilizzano i modelli di articolo | In base all'impostazione predefinita |
| Gestione informazioni sul prodotto | Abilita gruppi di dimensioni prodotto per i modelli di articolo | In base all'impostazione predefinita |
| Gestione informazioni sul prodotto | Rigenera nomi varianti prodotto in base alla nomenclatura | In base all'impostazione predefinita |
| Gestione informazioni sul prodotto | [Miglioramenti della pagina Suggerimenti variante](../pim/tasks/create-predefined-product-variants.md) | In base all'impostazione predefinita |
| Controllo produzione | Prelievo di quantità a peso variabile di produzione migliorata | Generalmente disponibile |
| Controllo produzione | Un nuovo pulsante Interrompi pausa è stato aggiunto alla pagina del terminale della scheda processo | Obbligatorio |
| Controllo produzione | [Abilitare la generazione automatica del numero di identificazione durante la dichiarazione di finito nel dispositivo scheda processo](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Controllo produzione | Abilitare l'entrata parziale di articoli in conto lavoro e correggere un problema con il calcolo dello scarto per le righe DBA di tipo fornitore | Obbligatorio |
| Controllo produzione | [Funzionalità per bloccare il dispositivo scheda processo e il terminale scheda processo di modo che possano essere puliti](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Controllo produzione | Miglioramenti alle finestre di dialogo Approva processi e Processi di trasferimento | Obbligatorio |
| Controllo produzione | [Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Controllo produzione | [Stampa etichetta dal dispositivo scheda processo](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Controllo produzione | [Esecuzione area di produzione](../production-control/production-floor-execution-configure.md) | Obbligatorio |
| Controllo produzione | [Funzionalità di gestione cespiti per l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) | In base all'impostazione predefinita |
| Controllo produzione | [Ricerca del processo per l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) | In base all'impostazione predefinita |
| Controllo produzione | [Sovrascrivi prenotazione di produzione predefinita](../production-control/override-default-reservation-principle.md) | In base all'impostazione predefinita |
| Controllo produzione | [Mostra i numeri di identificazione, serie e batch completi nell'interfaccia di esecuzione area di produzione](whats-new-scm-10-0-21.md) | In base all'impostazione predefinita |
| Vendite e marketing | [Miglioramento prestazioni dettagli ordini cliente](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Generalmente disponibile |
| Vendite e marketing | Miglioramento prestazioni dettagli offerte di vendita | Generalmente disponibile |
| Vendite e marketing | Criteri di esportazione dati a cui fa riferimento l'ordine cliente | Obbligatorio |
| Vendite e marketing | [Criteri di eliminazione della riga ordine cliente nell'ordine fornitore](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Obbligatorio |
| Vendite e marketing | [Criteri di esportazione dati a cui fa riferimento l'offerta di vendita](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Obbligatorio |
| Vendite e marketing | [Ottimizzazione esportazione entità di dati persona di contatto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | In base all'impostazione predefinita |
| Vendite e marketing | Abilita ricerca per i campi chiusura documenti e introduzione documenti di offerta di vendita | In base all'impostazione predefinita |
| Vendite e marketing | [Migliora le prestazioni del report "Primi 100" clienti](whats-new-scm-10-0-23.md) | In base all'impostazione predefinita |
| Vendite e marketing | Ricalcola saldo cliente stimato | In base all'impostazione predefinita |
| Vendite e marketing | [Registrazione riga ordine di reso vendita con precisione decimale con e senza peso variabile](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | In base all'impostazione predefinita |
| Vendite e marketing | [Visualizzazioni salvate per vendite e marketing](saved-views-scm.md) | In base all'impostazione predefinita |
| Vendite e marketing | Conferma dell'ordine cliente con un solo clic | In base all'impostazione predefinita |
| Warehouse Management | [Modelli di cross-docking con direttive di ubicazione](../warehousing/planned-cross-docking.md) | Generalmente disponibile |
| Warehouse Management | [Disabilitare le ricevute previste dagli ordini di controllo qualità che campionano le scorte bloccate](../inventory/inventory-blocking.md) | Generalmente disponibile |
| Warehouse Management | Cronologia ricevimento targa | Generalmente disponibile |
| Warehouse Management | [Interfaccia attrezzatura movimentazione materiali](../warehousing/mhax.md) | Generalmente disponibile |
| Warehouse Management | [Arrotonda quantità per difetto all'unità di vendita più vicina al momento del rilascio nel magazzino](whats-new-scm-10-0-19.md) | Generalmente disponibile |
| Warehouse Management | Supporto unità di scala per elenchi di lavoro per app magazzino | Generalmente disponibile |
| Warehouse Management | Dettagli etichetta ciclo di spedizione | Generalmente disponibile |
| Warehouse Management | [Utilizza API veloce per chiusura/riapertura contenitori in stazione di imballaggio](whats-new-scm-10-0-21.md) | Generalmente disponibile |
| Warehouse Management | [Convalida modelli selezionati per processi di rifornimento](whats-new-scm-10-0-20.md) | Generalmente disponibile |
| Warehouse Management | Consenti al modello di rifornimento di utilizzare il lavoro di rifornimento immediato esistente (tra unità) | Obbligatorio |
| Warehouse Management | Assegnazione automatica dei GUID per creazione dell'utente WHS | Obbligatorio |
| Warehouse Management | Acquisisci varianti prodotto e dimensioni di tracciabilità nell'app del magazzino durante il ricevimento articoli di carico | Obbligatorio |
| Warehouse Management | [Modifica lo stato di magazzino degli articoli controllati dalle dimensioni di tracciabilità](../inventory/inventory-statuses.md) | Obbligatorio |
| Warehouse Management | [Modifica pool di lavoro nel lavoro](../warehousing/change-work-pool-on-work.md) | Obbligatorio |
| Warehouse Management | [Posizione cluster piena](../warehousing/cluster-position-full.md) | Obbligatorio |
| Warehouse Management | [Funzionalità cluster stoccaggio](../warehousing/putaway-clusters.md) | Obbligatorio |
| Warehouse Management | [Conferma e trasferimento](../warehousing/confirm-and-transfer.md) | Obbligatorio |
| Warehouse Management | [Conferma spedizioni in uscita da processi batch](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Obbligatorio |
| Warehouse Management | [Controlla se visualizzare una pagina di riepilogo delle ricezioni sui dispositivi mobili](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obbligatorio |
| Warehouse Management | [Elaborazione differita dell'operazione di movimento inventario manuale](../warehousing/deferred-processing-manual-inventory-movement.md) | Obbligatorio |
| Warehouse Management | Non consentire la creazione di carichi che non soddisfano i requisiti del modello di creazione del carico ondata | Obbligatorio |
| Warehouse Management | [Layout etichette targa avanzata](../warehousing/document-routing-layout-for-license-plates.md) | Obbligatorio |
| Warehouse Management | [Valuta tutte le azioni per direttive di ubicazione multi-SKU](../troubleshooting/warehousing/evaluate-multiple-location-directive-actions.md) | Obbligatorio |
| Warehouse Management | Nascondi il campo valore totale nelle pagine "Tutti i carichi" e "Dettagli carico" | Obbligatorio |
| Warehouse Management | Configurazione di versione etichetta targa | Obbligatorio |
| Warehouse Management | Correzione manuale righe di carico per utenti amministratore o altri utenti attendibili simili | Obbligatorio |
| Warehouse Management | [Posizionamento targa ubicazione](../warehousing/location-license-plate-positioning.md) | Obbligatorio |
| Warehouse Management | [Combinazione dimensioni prodotto ubicazione](../warehousing/location-product-dimension-mixing.md) | Obbligatorio |
| Warehouse Management | Rendi modificabile il campo dello stato inventario del movimento inventario del dispositivo mobile | Obbligatorio |
| Warehouse Management | Servizio di prelievo manuale righe di vendita per amministratori o utenti attendibili simili | Obbligatorio |
| Warehouse Management | [Impedisci l'utilizzo di targhe spedite per l'ordine di trasferimento in altri magazzini diversi dal magazzino di destinazione](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obbligatorio |
| Warehouse Management | Richiedi di risolvere i nomi ambigui per "ubicazione/targa" | Obbligatorio |
| Warehouse Management | [Controllo qualità](../warehousing/quality-check.md) | Obbligatorio |
| Warehouse Management | [Impostazioni utente, icone e titoli di passaggi per la nuova app di magazzino](../warehousing/install-configure-warehouse-management-app.md) | Obbligatorio |
| Warehouse Management | [Zona ubicazione aggiuntiva](../warehousing/additional-location-zones.md) | In base all'impostazione predefinita |
| Warehouse Management | [Creare ed elaborare ordini di trasferimento dall'app di magazzino](../warehousing/create-transfer-order-from-warehouse-app.md) | In base all'impostazione predefinita |
| Warehouse Management | Abilita convalida rapida per i dispositivi mobili del magazzino | In base all'impostazione predefinita |
| Warehouse Management | [Tempo di esecuzione massimo per il processo di pulizia scorte disponibili di gestione magazzino](../warehousing/onhand-cleanup.md) | In base all'impostazione predefinita |
| Warehouse Management | [Visualizzazione del carico di lavoro in uscita](../warehousing/outbound-workload-visualization.md) | In base all'impostazione predefinita |
| Warehouse Management | [Elabora eventi dell'app magazzino](../warehousing/warehouse-app-events.md) | In base all'impostazione predefinita |
| Warehouse Management | [Visualizzazione salvata per il workbench di pianificazione del carico](saved-views-scm.md) | In base all'impostazione predefinita |
| Warehouse Management | [Visualizzazione salvata per la pagina dei dettagli del lavoro](saved-views-scm.md) | In base all'impostazione predefinita |
| Warehouse Management | [Visualizzazione salvata per elaborazione ciclo](saved-views-scm.md) | In base all'impostazione predefinita |
| Warehouse Management | [Visualizzazioni salvate per elaborazione carico](saved-views-scm.md) | In base all'impostazione predefinita |
| Warehouse Management | [Visualizzazioni salvate per elaborazione spedizione](saved-views-scm.md) | In base all'impostazione predefinita |
| Warehouse Management | [Dettagli processo batch ciclo](../warehousing/wave-processing.md) | In base all'impostazione predefinita |
| Warehouse Management | [Notifiche di esecuzione ciclo](../warehousing/wave-execution-notifications.md) | In base all'impostazione predefinita |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.25 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.25 delle app per finanza e operazioni (aprile 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.25, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e cloud di settore: piano del primo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del primo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave1/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
