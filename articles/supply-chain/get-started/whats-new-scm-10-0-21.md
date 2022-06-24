---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.21 (ottobre 2021)
description: Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a78b4c37bfca9fedbd46cd8a16b47bd4444fbfee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849534"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.21 (ottobre 2021)

[!include [banner](../includes/banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.21. Questa versione ha il numero di build 10.0.960 ed è disponibile come segue:

- **Anteprima della versione:** agosto 2021
- **Disponibilità generale della versione (aggiornamento automatico):** settembre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2021

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. La colonna *Funzionalità* fornisce collegamenti al [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), dove puoi vedere le date di rilascio ufficiali per ciascuna funzionalità. La colonna *Ulteriori informazioni* fornisce altri dettagli e/o collegamenti alla documentazione correlata.

La maggior parte di queste funzionalità deve essere abilitata tramite [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) prima di poter essere utilizzate.

| Area funzionale | Funzionalità | Ulteriori informazioni |
|---|---|---|
| Inventario&nbsp;e&nbsp;logistica | [Componente aggiuntivo Contabilità inventario globale per Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Home page di Contabilità inventario globale](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Inventario&nbsp;e&nbsp;logistica | [Registrare le rettifiche delle scorte disponibili utilizzando codici collegati ai conti di contropartita](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Codici motivo per il conteggio scorte](../warehousing/reason-codes-for-counting-journals.md) |
| Inventario&nbsp;e&nbsp;logistica | [Criteri di esportazione dati a cui fa riferimento l'offerta di vendita](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Scegli se le modifiche ai dati di riferimento per offerta non determineranno l'inclusione delle offerte (o delle righe) nella successiva esportazione incrementale. Le tue esportazioni incrementali verranno eseguite più rapidamente se scegli di non includere tali offerte o righe.<br><br>Questa funzionalità aggiunge un'impostazione chiamata **Ignora i dati di riferimento delle offerte di vendita durante il rilevamento delle modifiche** alla pagina **Parametri contabilità clienti**. |
| Inventario&nbsp;e&nbsp;logistica | [Offerta nascosta](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [Offerta nascosta per RdO](../procurement/sealed-bidding.md) |
| Inventario&nbsp;e&nbsp;logistica | [Prenotazione soft per l'add-in di visibilità dell'inventario](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Prenotazioni di visibilità dell'inventario](../inventory/inventory-visibility-reservations.md) |
| Inventario&nbsp;e&nbsp;logistica | [Detrazioni e miglioramenti peso variabile per la gestione degli sconti](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Gestire le detrazioni usando il workbench detrazioni](../rebate-management/deduction-workbench.md )<br><br>[Elaborazione, revisione e registrazione degli sconti](../rebate-management/process-review-post.md)<br><br>[Transazioni di gestione degli sconti](../rebate-management/rebate-management-deals.md) |
| Inventario&nbsp;e&nbsp;logistica | [Istruzioni del passaggio dell'app di magazzino](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Personalizzare i titoli dei passi e le istruzioni per l'applicazione mobile Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Inventario&nbsp;e&nbsp;logistica | [Pause di lavoro e aggiornamenti di tracciabilità per i costi di spedizione](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Aggiorna tracciabilità per stoccaggio](../landed-cost/update-tracking-putaway.md )<br><br>[Elaborazione merci in transito](../landed-cost/in-transit-processing.md) |
| Pianificazione generale | [Giorni negativi per l'ottimizzazione della pianificazione](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolleranza di ritardo (giorni negativi)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato). Se desideri utilizzare una di queste funzionalità, devi abilitarle esplicitamente in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della&nbsp;funzionalità&nbsp;nella gestione&nbsp;delle funzionalità | Ulteriori informazioni |
|---|---|---|
| Gestione costi | Dettagli avanzamento chiusura inventario | Questa funzione di anteprima consente una visualizzazione dettagliata dell'avanzamento della chiusura dell'inventario. |
| Approvvigionamento | Impedisci utilizzo eccessivo di prenotazioni di budget generale quando più richieste di acquisto sono presenti nel flusso di lavoro | Questa funzionalità di anteprima migliora il controllo degli errori quando gli utenti inviano e approvano le richieste di acquisto che superano il saldo rimanente di una riga di prenotazione del budget generale. Ciò aiuta a prevenire il consumo in eccesso di prenotazioni di budget generali quando più richieste di acquisto sono nel flusso di lavoro. |
| Controllo produzione | Mostra i numeri di identificazione, serie e batch completi nell'interfaccia di esecuzione area di produzione | Questa funzionalità offre un'esperienza migliorata per la visualizzazione di elenchi di numeri di serie, batch e targa nell'interfaccia di esecuzione dell'area di produzione. La visualizzazione cambia da una visualizzazione scheda con un numero limitato di caratteri a una visualizzazione elenco che fornisce spazio sufficiente per mostrare i valori completi. L'elenco offre anche la possibilità di cercare numeri specifici. |
| Vendite e marketing | Limita il numero di ordini cliente che è possibile selezionare per la registrazione | Questa funzione permette di definire il numero massimo di ordini di vendita che possono essere selezionati quando si pubblicano conferme, liste di prelievo, bolle di accompagnamento e fatture dalla pagina della lista degli ordini di vendita. Si attiva automaticamente. La funzione aggiunge un'impostazione chiamata **Numero massimo di ordini di vendita per la registrazione** alla pagina dei **parametri dei crediti** . La nuova impostazione predefinita è un valore di *100*. La funzione aiuta a migliorare le prestazioni della pagina dell'elenco degli ordini di vendita quando viene selezionato un numero considerevole di ordini di vendita. Non ha alcun impatto sul numero di ordini di vendita che possono essere elaborati da un compito periodico. |
| Warehouse Management | Scollega lavoro di stoccaggio da ASN | Questa funzionalità è necessaria per inviare e ricevere avvisi di spedizione anticipata quando si esegue un carico di lavoro di gestione del magazzino su un'unità di scala (come parte di una topologia ibrida distribuita). Aggiunge una nuova tabella di database dedicata alla memorizzazione di informazioni sul lavoro di stoccaggio. In precedenza, queste informazioni venivano archiviate in tabelle utilizzate anche per gli avvisi di spedizione anticipata. |
| Warehouse Management | Assegna in unità miste | Consente al sistema di inserire gli articoli in ubicazioni che includono unità miste (come scatole e casse). Per ogni riga del modello di assegnazione, questa funzione consente di scegliere se la riga deve inserire gli articoli in ubicazioni di unità miste o singole. |
| Warehouse Management | Utilizza API veloce per chiusura/riapertura contenitori in stazione di imballaggio | Quando questa funzionalità di anteprima è abilitata, le transazioni di inventario relative ai contenitori vengono create utilizzando un nuovo processo semplice che migliora le prestazioni di chiusura o riapertura dei contenitori durante l'elaborazione manuale della stazione di imballaggio. |

## <a name="features-turned-on-by-default-in-this-release"></a>Funzionalità attivate per impostazione predefinita in questa versione

Questa tabella elenca le funzionalità attivate per impostazione predefinita in 10.0.21. La maggior parte delle funzioni che sono state attivate atomicamente possono essere disattivate in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Nome funzionalità | Abilita data | Aggiunta funzionalità | Stato funzionalità | Modulo |
| :--- | :--- | :--- | :--- | :--- |
| Archiviazione report scorte disponibili | 1/9/2021 | 1/4/2020 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Annullamento ordine di trasferimento | 1/9/2021 | 13/7/2020 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Sblocca giornale di registrazione magazzino | 1/9/2021 | 17/8/2020 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Visualizzazioni salvate per gestione inventario | 1/9/2021 | 30/9/2020 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Passaggio alla versione DBA da righe DBA | 1/9/2021 | 11/11/2019 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Utilizzo dell'unità di misura e della quantità unitaria nei giornali di registrazione magazzino | 1/9/2021 | 11/11/2019 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Consenti valori di attributi batch vuoti | 1/9/2021 | 11/11/2019 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Incremento automatico dei numeri di riga delle righe ordine di trasferimento scorte | 1/9/2021 | 11/10/2019 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Flusso di lavoro per approvazione giornale di registrazione magazzino | 1/9/2021 | 6/1/2020 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Abilita funzionalità di avviso parametri di gestione qualità scorte | 1/9/2021 | 7/10/2019 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Crea ordine di trasferimento da riga di vendita. | 1/9/2021 | 31/8/2019 | In base all'impostazione predefinita | Gestione articoli e magazzino |
| Selezione modello previsionale in dettagli previsione della domanda | 1/9/2021 | 11/10/2019 | In base all'impostazione predefinita | Pianificazione generale |
| Visualizzazione avanzamento pianificazione generale | 1/9/2021 | 7/10/2019 | In base all'impostazione predefinita | Pianificazione generale |
| Stabilizzazione automatica per l'ottimizzazione della pianificazione | 1/9/2021 | 11/10/2019 | In base all'impostazione predefinita | Pianificazione generale |
| Stabilizzazione parallela degli ordini pianificati | 1/9/2021 | 31/8/2019 | In base all'impostazione predefinita | Pianificazione generale |
| Messaggio per l'invio dell'offerta riuscito | 1/9/2021 | 15/5/2019 | In base all'impostazione predefinita | Approvvigionamento |
| Collegamento di riferimento RdO aggiunto all'ordine fornitore | 1/9/2021 | 31/8/2019 | In base all'impostazione predefinita | Approvvigionamento |
| Possibilità di confermare in batch gli ordini fornitore accettati tramite la collaborazione fornitore | 1/9/2021 | 10/9/2019 | In base all'impostazione predefinita | Approvvigionamento |
| Miglioramenti cXML per gli acquisti | 1/9/2021 | 11/11/2019 | In base all'impostazione predefinita | Approvvigionamento |
| Visualizza il collegamento &quot;Richieste di offerta pubblicate aperte&quot; come riquadro | 1/9/2021 | 30/9/2020 | In base all'impostazione predefinita | Approvvigionamento |
| Domande e risposte RdO | 1/9/2021 | 19/2/2020 | In base all'impostazione predefinita | Approvvigionamento |
| Informazioni e documentazione di spedizione relative ai prodotti materiali pericolosi | 1/9/2021 | 14/6/2020 | In base all'impostazione predefinita | Gestione informazioni sul prodotto |
| Convalida rigorosa per quantità ordine predefinite | 1/9/2021 | 24/6/2020 | In base all'impostazione predefinita | Gestione informazioni sul prodotto |
| Funzionalità di gestione del paese di origine | 1/9/2021 | 13/7/2020 | In base all'impostazione predefinita | Gestione informazioni sul prodotto |
| Visualizzazioni salvate per prodotti rilasciati | 1/9/2021 | 30/9/2020 | In base all'impostazione predefinita | Gestione informazioni sul prodotto |
| Miglioramenti alle finestre di dialogo Approva processi e Processi di trasferimento | 1/9/2021 | 11/10/2019 | In base all'impostazione predefinita | Controllo produzione |
| Targa per la dichiarazione di finito aggiunta al dispositivo della scheda processo | 1/9/2021 | 31/8/2019 | In base all'impostazione predefinita | Controllo produzione |
| Un nuovo pulsante Interrompi pausa è stato aggiunto alla pagina del terminale della scheda processo | 1/9/2021 | 19/2/2020 | In base all'impostazione predefinita | Controllo produzione |
| Abilitare l'entrata parziale di articoli in conto lavoro e correggere un problema con il calcolo dello scarto per le righe DBA di tipo fornitore. | 1/9/2021 | 11/11/2019 | In base all'impostazione predefinita | Controllo produzione |
| Visualizzazioni salvate per controllo di produzione | 1/9/2021 | 17/8/2020 | In base all'impostazione predefinita | Controllo produzione |
| Dynamics 365 Guides per produzione | 1/9/2021 | 13/7/2020 | In base all'impostazione predefinita | Controllo produzione |
| Esecuzione area di produzione | 1/9/2021 | 30/9/2020 | In base all'impostazione predefinita | Controllo produzione |
| Funzionalità per bloccare il dispositivo scheda processo e il terminale scheda processo di modo che possano essere puliti | 1/9/2021 | 10/5/2020 | In base all'impostazione predefinita | Controllo produzione |
| Allocazione spese in un ordine cliente | 1/9/2021 | 30/9/2020 | In base all'impostazione predefinita | Vendite e marketing |
| Limita il numero di ordini cliente che è possibile selezionare per la registrazione | 1/9/2021 | 1/9/2021 | In base all'impostazione predefinita | Vendite e marketing |
| Pulisci storico aggiornamento ordini cliente | 1/9/2021 | 1/9/2021 | In base all'impostazione predefinita | Vendite e marketing |
| Modifica la sequenza numerica per il lavoro conteggio ciclo | 1/9/2021 | 7/10/2019 | In base all'impostazione predefinita | Warehouse Management |
| Rifornimento basato sulla domanda ondata basata su attività | 1/9/2021 | 7/10/2019 | Obbligatorio | Warehouse Management |
| Nascondi il campo valore totale nelle pagine &quot;Tutti i carichi&quot; e &quot;Dettagli carico&quot; | 1/9/2021 | 7/10/2019 | In base all'impostazione predefinita | Warehouse Management |
| Stampa di etichette ciclo | 1/9/2021 | 19/2/2020 | Obbligatorio | Warehouse Management |
| Associa operazioni di magazzino ordine fornitore con carico | 1/9/2021 | 6/1/2020 | Obbligatorio | Warehouse Management |
| Layout etichette targa avanzata | 1/9/2021 | 19/2/2020 | In base all'impostazione predefinita | Warehouse Management |
| Blocco lavoro a livello di organizzazione | 1/9/2021 | 19/2/2020 | Obbligatorio | Warehouse Management |
| Dettagli riga di lavoro | 1/9/2021 | 11/10/2019 | In base all'impostazione predefinita | Warehouse Management |
| Rendi modificabile il campo dello stato inventario del movimento inventario del dispositivo mobile | 1/9/2021 | 16/10/2019 | In base all'impostazione predefinita | Warehouse Management |
| Conferma spedizioni in uscita da processi batch | 1/9/2021 | 13/7/2020 | In base all'impostazione predefinita | Warehouse Management |
| Controlla se visualizzare una pagina di riepilogo delle ricezioni sui dispositivi mobili | 1/9/2021 | 1/4/2020 | In base all'impostazione predefinita | Warehouse Management |
| Richiedi di risolvere i nomi ambigui per &#39;ubicazione/targa&#39; | 1/9/2021 | 1/4/2020 | In base all'impostazione predefinita | Warehouse Management |
| Acquisisci varianti prodotto e dimensioni di tracciabilità nell'app del magazzino durante il ricevimento articoli di carico | 1/9/2021 | 10/5/2020 | In base all'impostazione predefinita | Warehouse Management |
| Non consentire la creazione di carichi che non soddisfano i requisiti del modello di creazione del carico ondata. | 1/9/2021 | 17/8/2020 | In base all'impostazione predefinita | Warehouse Management |
| Valuta tutte le azioni per direttive di ubicazione multi-SKU | 1/9/2021 | 30/9/2020 | In base all'impostazione predefinita | Warehouse Management |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti articoli della guida. Non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente, ma possono aiutare a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Articoli nuovi o aggiornati |
|---|---|
| Pianificazione generale | [Previsioni di inventario](../master-planning/inventory-forecast.md) |
| Pianificazione generale | [Parametri non utilizzati da Ottimizzazione pianificazione](../master-planning/planning-optimization/not-used-parameters.md) |
| Pianificazione generale | [Metodi di rifornimento e modifica della quantità](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Pianificazione generale | [Programmazione con capacità infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Pianificazione generale | [Visualizzare i registri di pianificazione e dello storico del piano](../master-planning/planning-optimization/plan-history-logs.md) |
| Warehouse Management | [Strategie di imballaggio dei contenitori](../warehousing/container-packing-strategy-overview.md) |
| Warehouse Management | [Scenari di esempio di conteggio ciclo](../warehousing/cycle-counting-scenarios.md) |
| Warehouse Management | [Importare gli ASN in entrata tramite l'entità di dati V3](../warehousing/import-asn-data-entity.md) |
| Warehouse Management | [Prelievo in eccesso per ordini cliente e di trasferimento](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Warehouse Management | [Programmare la stampa di etichette ciclo durante il ciclo](../warehousing/configure-task-based-wave-label-printing.md) |
| Warehouse Management | [Novità o modifiche nell'app per dispositivi mobili Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.21 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.21 delle app per finanza e operazioni (ottobre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.21, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2021

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2021](/dynamics365-release-plan/2021wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
