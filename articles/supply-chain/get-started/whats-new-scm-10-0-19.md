---
title: Novità o modifiche introdotte in Dynamics 365 Supply Chain Management versione 10.0.19 (giugno 2021)
description: Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 74720e387d5db7de841228e6573fb40c5d22588b
ms.sourcegitcommit: 2b04b5a5c883d216072bb91123f9c7709a41f69a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "7384661"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Novità o modifiche introdotte in Dynamics 365 Supply Chain Management versione 10.0.19 (giugno 2021)

[!include [banner](../includes/banner.md)]

Questo argomento elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.19. Questa versione ha il numero di build 10.0.837 ed è disponibile come segue:

- **Anteprima della versione:** aprile 2021
- **Disponibilità generale della versione (aggiornamento automatico):** giugno 2021
- **Disponibilità generale della versione (aggiornamento automatico):** giugno 2021

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. La colonna *Funzionalità* fornisce collegamenti al [piano di rilascio](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), dove puoi vedere le date di rilascio ufficiali per ciascuna funzionalità. La colonna *Ulteriori informazioni* fornisce altri dettagli e/o collegamenti alla documentazione correlata.

La maggior parte di queste funzionalità deve essere abilitata tramite [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) prima di poter essere utilizzate.

| Area funzionale | Funzionalità | Ulteriori informazioni |
|---|---|---|
| Inventario&nbsp;e&nbsp;logistica | [Approvare e salvare i dati bancari inviati dal fornitore](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [Conservare le informazioni sul conto corrente del fornitore](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| Inventario e logistica | [Ottimizzazione esportazione entità di dati persona di contatto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | Quando questa funzionalità è abilitata, le modifiche ai dati di riferimento non determineranno l'inclusione dei contatti correlati nella successiva esportazione incrementale. Quando questa funzionalità è disabilitata, le modifiche ai dati di riferimento determineranno l'inclusione dei contatti correlati nella successiva esportazione incrementale. |
| Inventario e logistica | [Miglioramenti incrementali per le funzionalità di esecuzione del magazzino con unità di scala](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Messaggi dell'elaboratore messaggi](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Rettifica scorte magazzino](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Inventario e logistica | [Funzionalità di ricerca per i campi Introduzioni documento e Testo di chiusura documento nella pagina Offerta di vendita](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Questa funzionalità aggiunge la funzionalità di ricerca per i campi **Introduzioni documento** e **Testo di chiusura documento** nella pagina **Offerta di vendita**.<br><br>Questo funzionalità è abilitata per impostazione predefinita. |
| Inventario e logistica | [Esecuzione di magazzino con unità di scala nella rete perimetrale sul tuo hardware personalizzato](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Distribuzione di unità di scala nella rete perimetrale su hardware personalizzato utilizzando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Produzione | [Esecuzione di produzione con unità di scala nella rete perimetrale sul tuo hardware personalizzato](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Distribuire unità di scala nella rete perimetrale su hardware personalizzato utilizzando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Pianificazione | [Programmazione capacità infinita per Ottimizzazione pianificazione](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [Programmazione con capacità infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Pianificazione | Stabilizzazione di ordini pianificati basata su query | [Stabilizzare ordini pianificati](../master-planning/planning-optimization/planned-order-firming.md) |
| Gestione informazioni sul prodotto | [Miglioramenti della pagina Suggerimenti variante](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Creare varianti prodotto predefinite](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato). Se desideri utilizzare una di queste funzionalità, devi abilitarle esplicitamente in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Area funzionale | Nome della&nbsp;funzionalità&nbsp;nella gestione&nbsp;delle funzionalità | Ulteriori informazioni |
|---|---|---|
| Vendite e marketing | Miglioramenti delle prestazioni di pulizia della cronologia delle vendite | La pulizia della cronologia delle vendite può richiedere molto tempo se eseguita raramente in ambienti con un volume elevato di aggiornamenti delle vendite. Per ridurre la durata e migliorare l'affidabilità, questa funzionalità suddivide la pulizia in batch che vengono eseguiti per una durata limitata. Ove possibile, le funzionalità del database verranno sfruttate per ridurre al minimo il blocco ed evitare di unire tabelle transazionali durante la pulizia. |
| Vendite e marketing | Aggiorna data di ricevimento richiesta con data confermata per ordini interaziendali | Questa funzionalità consente di controllare cosa accadrà ai valori dei campi della data di acquisto e di vendita quando si utilizza la consegna diretta interaziendale. Puoi scegliere se il sistema aggiornerà le date richieste o ignorerà l'aggiornamento. Se ignori l'aggiornamento, le date richieste rappresenteranno ciò che il cliente ha richiesto. Se abiliti l'aggiornamento, le date richieste (quando si utilizza il controllo della data di consegna) rappresentano inizialmente solo ciò che il cliente ha richiesto. Controllo della data di consegna, se diversa da *Nessuna*, annullerà quanto inizialmente richiesto. È possibile impostare questa opzione utilizzando la nuova impostazione **Aggiorna data di ricevimento richiesta con data confermata** nelle impostazioni del fornitore o del cliente interaziendale.<br><br>Se la funzionalità è disabilitata, il sistema sovrascriverà la data di ricezione richiesta sugli ordini di vendita originali in base alla regola di controllo della data di consegna, ma la data di spedizione richiesta rimarrà invariata. |
| Gestione magazzino | Arrotonda quantità per difetto all'unità di vendita più vicina al momento del rilascio nel magazzino | Questa funzionalità aggiunge un'opzione che può limitare le quantità dell'ordine al rilascio in magazzino. Quando è abilitata, le quantità dell'ordine verranno arrotondate per difetto all'unità di vendita intera più vicina e gli ordini che includono quantità per meno di un'unità di vendita verranno rifiutati per il rilascio. |
| Gestione magazzino | Metodo di ciclo "Programma creazione lavoro" a livello di organizzazione | Quando viene abilitata questa funzionalità, il metodo ciclo *Programma creazione lavoro* verrà configurato per essere eseguito in parallelo tra tutte le persone giuridiche. Saranno interessate anche diverse impostazioni aggiuntive. Per i dettagli completi, vedi [Pianificare la creazione del lavoro nel corso del ciclo](../warehousing/configure-wave-schedule-work-creation.md). |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti argomenti della guida. Non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente, ma possono aiutare a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Argomenti nuovi o aggiornati |
|---|---|
| Gestione modifiche di progettazione | [Gestione modifiche di progettazione - Domande frequenti](../engineering-change-management/change-management-faq.md) |
| Approvvigionamento | [Richieste di categorie da parte dei fornitori](../procurement/category-requests-from-vendors.md) |
| Gestione informazioni sul prodotto | [Gestire unità di misura](../pim/tasks/manage-unit-measure.md)<br><br>[Calcoli per il modello di configurazione prodotto](../pim/config-model-calculations.md) |
| Controllo produzione | [Sequenza numerica unificata per gli ID processo](../production-control/unified-job-ids.md) |
| Gestione trasporto | [Classi LTL](../transportation/ltl-class.md)<br><br>[Codici NMFC](../transportation/nmfc-codes.md) |
| Gestione magazzino | [Risolvere i problemi relativi a gerarchie di prenotazione seriale e batch di magazzino](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Gestione del magazzino, creazione ed elaborazione dei cicli | [Creazione ed elaborazione del ciclo](../warehousing/wave-processing.md)<br><br>[Parametri di magazzino per l'elaborazione del ciclo](../warehousing/wave-warehouse-parameters.md)<br><br>[Modelli di ciclo](../warehousing/wave-templates.md)<br><br>[Allocazione ciclo](../warehousing/wave-allocation-method.md)<br><br>[Programmare la creazione del lavoro durante il ciclo](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Containerizzazione](../warehousing/wave-containerization.md)<br><br>[Notifiche di esecuzione ciclo](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per le app Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.19 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.19 delle app Finance and Operations (giugno 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.19, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Piano del primo ciclo di rilascio del 2021 di Dynamics 365

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Consultare il [piano del primo ciclo di rilascio del 2021 di Dynamics 365](/dynamics365-release-plan/2021wave1/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
