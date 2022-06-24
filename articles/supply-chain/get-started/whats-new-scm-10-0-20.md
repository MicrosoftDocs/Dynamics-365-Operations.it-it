---
title: Novità e modifiche in Dynamics 365 Supply Chain Management 10.0.20 (agosto 2021)
description: Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Supply Chain Management 10.0.20.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3eadc447d8c0c443fa9d3eab220300e3eedf051d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888645"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Novità e modifiche in Dynamics 365 Supply Chain Management 10.0.20 (agosto 2021)

[!include [banner](../includes/banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.20. Questa versione ha il numero di build 10.0.886 ed è disponibile come segue:

- **Anteprima della versione:** maggio 2021
- **Disponibilità generale della versione (aggiornamento automatico):** luglio 2021
- **Disponibilità generale della versione (aggiornamento automatico):** agosto 2021

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. La colonna *Funzionalità* fornisce collegamenti al [piano di rilascio](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), dove puoi vedere le date di rilascio ufficiali per ciascuna funzionalità. La colonna *Ulteriori informazioni* fornisce altri dettagli e/o collegamenti alla documentazione correlata.

La maggior parte di queste funzionalità deve essere abilitata tramite [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) prima di poter essere utilizzate.

| Area funzionale | Funzionalità | Ulteriori informazioni |
|---|---|---|
| Inventario&nbsp;e&nbsp;logistica | [Miglioramento prestazioni dettagli ordini cliente](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Questa funzionalità rende l'interfaccia utente più reattiva quando si aprono ordini di vendita, in particolare ordini che includono molte righe. |
| Produzione | [Richiamare i flussi di automazione dei processi per creare ordini di controllo qualità](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Richiamare i flussi di automazione dei processi per creare ordini di controllo qualità](../production-control/process-automation-quality-orders.md ) |
| Produzione | [Interfaccia di esecuzione dell'area di produzione migliorata per la produzione](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [Configurare l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md) |
| Pianificazione | [Programmazione capacità infinita per Ottimizzazione pianificazione](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [Programmazione con capacità infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Gestione informazioni sul prodotto | [Gestisci le modifiche nelle formule e negli ingredienti](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Gestisci le modifiche nelle formule e nei loro ingredienti](../engineering-change-management/manage-formula-changes.md) |
| Gestione informazioni sul prodotto | [Controlli di preparazione prodotto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Idoneità prodotto](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato). Se desideri utilizzare una di queste funzionalità, devi abilitarle esplicitamente in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della&nbsp;funzionalità&nbsp;nella gestione&nbsp;delle funzionalità | Ulteriori informazioni |
|---|---|---|
| Pianificazione generale | Autorizzazione parallela della previsione della domanda modificata | Questa funzionalità consente l'autorizzazione parallela della previsione della domanda rettificata dalla pagina **Previsione della domanda modificata**. Lo scopo di questa funzione è aumentare le prestazioni quando viene autorizzato un numero elevato di previsioni. Al momento dell'autorizzazione, l'utente può specificare il **Numero di thread** nella finestra di dialogo di autorizzazione. |
| Pianificazione generale | (Anteprima) Stabilizzazione e consolidamento batch per ordini batch in blocco e di imballaggio pianificati | Questa funzionalità consente di utilizzare i processi batch per stabilizzare e consolidare gli ordini in blocco e di imballaggio pianificati. |
| Controllo produzione | Copia cicli di lavorazione generici | Questa funzionalità migliora la funzione di copia del percorso per consentire agli utenti di copiare percorsi che non sono specifici dell'elemento. Consente al sistema di aggiornare tutte le informazioni rilevanti (come il sito, il gruppo di percorsi, i requisiti delle risorse e varie volte) dopo che la funzione di copia del percorso è stata utilizzata per sovrascrivere un percorso non ancora assegnato a un elemento. |
| Controllo produzione | Aggiorna requisiti delle risorse correlate quando viene modificata un'operazione di ciclo di lavorazione | Questa funzionalità consente al sistema di aggiornare i requisiti delle risorse correlate dopo che un utente ha modificato il funzionamento di un passaggio del ciclo di lavorazione esistente. |
| Gestione informazioni sul prodotto | Pre-elaborazione del report della distinta base per evitare il timeout | Questa funzionalità fa sì che il report della distinta base venga pre-elaborato. Ciò eviterà problemi di timeout quando si ha un grande carico di dati per il rapporto. |
| Approvvigionamento | Abilitare la reimpostazione dei flussi di lavoro correlati all'approvvigionamento | Questa funzionalità di anteprima consente di reimpostare i seguenti flussi di lavoro allo stato di bozza: ordine di acquisto, modifica del fornitore e richieste di acquisto. |
| Gestione trasporto | Abilitare la creazione di un giornale di registrazione fatture fornitore quando si rimuove una fattura di trasporto | Quando questa funzionalità è abilitata, un giornale di registrazione fatture fornitore corrispondente verrà creato solo per motivi di riconciliazione quando si utilizza l'opzione pagamento fornitore. In caso contrario, verrà sempre creato il giornale di registrazione fatture. |
| Gestione magazzino | Convalida modelli selezionati per processi di rifornimento | Questa funzionalità aiuta a garantire che gli utenti selezionino modelli di rifornimento validi durante l'impostazione di un lavoro di rifornimento. Impedisce agli utenti di creare un lavoro di rifornimento senza un modello e di selezionare modelli di tipo *Domanda ondata*, che non creerà alcun lavoro di rifornimento e potrebbe richiedere molto tempo per l'elaborazione. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti articoli della guida. Non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente, ma possono aiutare a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Articoli nuovi o aggiornati |
|---|---|
| Gestione modifiche di progettazione | [Transazioni e stati del ciclo di vita del prodotto](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Gestione inventario | [Componente aggiuntivo Visibilità magazzino](../inventory/inventory-visibility.md)<br><br>[Panoramica sulla gestione della qualità e delle non conformità](../inventory/quality-management-processes.md) (più tutti gli articoli relativi alla gestione della qualità) |
| Approvvigionamento | [Mantenere la certificazione del fornitore](../../finance/public-sector/manage-vendor-certification.md) |
| Controllo produzione | [Progettare l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-styles.md) |
| Gestione magazzino | [Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management](../warehousing/step-icons-titles.md)<br><br>[Elaborazione differita del movimento manuale delle scorte](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.20 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.20 delle app per finanza e operazioni (luglio 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.20, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Piano del primo ciclo di rilascio del 2021 di Dynamics 365

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Consultare il [piano del primo ciclo di rilascio del 2021 di Dynamics 365](/dynamics365-release-plan/2021wave1/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
