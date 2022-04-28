---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.23 (gennaio 2022)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.23.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 876f5a5f8ebf77a65ba3aa6271a2957b7dc2cb96
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570480"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.23 (gennaio 2022)

[!include [banner](../includes/banner.md)]

Questo argomento elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.23. Questa versione ha il numero di build 10.0.1037 ed è disponibile come segue:

- **Anteprima della versione:** ottobre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** dicembre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** gennaio 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. La colonna *Funzionalità* fornisce collegamenti al [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), dove puoi vedere le date di rilascio ufficiali per ciascuna funzionalità. La colonna *Ulteriori informazioni* fornisce altri dettagli e/o collegamenti alla documentazione correlata. Per determinare come attivare una funzione, vedere la colonna *Abilitato da*. Per ulteriori informazioni su come utilizzare gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Potremmo aggiornare questo argomento per includere le funzionalità che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Rubrica globale | Definire uno stato/provincia predefinito per ogni paese/area geografica nell'impostazione dell'indirizzo | È ora possibile definire uno stato/provincia predefinito per ogni paese/area geografica nell'impostazione dell'indirizzo per la rubrica globale. Quando viene impostato uno stato/provincia predefinito, sarà il valore predefinito inserito nei campi stato/provincia quando crei un nuovo record di regione o città per quel paese/area geografica. Vedi anche [Impostazione dell'indirizzo](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Abilitato per impostazione predefinita. |
| Inventario&nbsp;e&nbsp;logistica | [Sospendi le attività nell'app per dispositivi mobili Warehouse Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Configura le deviazioni per i passaggi nelle voci di menu del dispositivo mobile](../warehousing/warehouse-app-detours.md) | Gestione funzionalità (*Deviazioni dell'app Warehouse Management*) |
| Inventario&nbsp;e&nbsp;logistica | [Campi promossi dell'app di magazzino](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Configura i campi promossi per i passaggi nel dispositivo mobile](../warehousing/warehouse-app-promoted-fields.md)| Gestione funzionalità (*Campi promossi dall'app di magazzino*) |
| Produzione | [Integrazione dei sistemi di esecuzione della produzione](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Eseguire l'integrazione con sistemi di esecuzione della produzione di terze parti](../production-control/mes-integration.md) | Gestione funzionalità: (*Integrazione del sistema di esecuzione della produzione*) |
| Produzione | [Report sui sotto/co-prodotti dall'interfaccia di esecuzione dell'area di produzione](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [Come i lavoratori utilizzano l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-use.md) | Gestione funzionalità (*Report sui sotto/co-prodotti dall'interfaccia di esecuzione dell'area di produzione*) |
| Pianificazione | [Supporto di Ottimizzazione pianificazione per la pianificazione basata sulla priorità](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Pianificazione basata sulle priorità](../master-planning/planning-optimization/priority-based-planning.md) | Gestione funzionalità: (*Supporto MRP basato sulla priorità per Ottimizzazione pianificazione*) |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle nuove funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se vuoi attivare o disattivare una di queste funzioni, devi farlo in [gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), dove sono elencati con i nomi mostrati nella colonna *Nome della funzionalità in gestione funzionalità* della seguente tabella.

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Gestione cespiti | Conti di contropartita per le spese in giornali di registrazione ordini di lavoro | Questa funzionalità consente di specificare un conto di contropartita per ogni spesa elencata in un giornale di registrazione dell'ordine di lavoro. In genere è possibile associare un conto fornitore a ciascuna spesa, ma sono supportati anche altri tipi di conto. Aggiunge due nuove colonne (**Tipo di conto di contropartita** e **Conto di contropartita**) alla scheda dettaglio **Spese** della pagina **Giornale di registrazione ordine di lavoro**.|
| Gestione costi | Crea giustificativi correlati per rivalutazioni di arrotondamento dei costi standard | <p>Quando viene effettuata una registrazione finanziaria di magazzino (come una fattura di un ordine cliente o una transazione di magazzino), questa funzionalità fa sì che il sistema crei un giustificativo separato per qualsiasi rivalutazione di arrotondamento dei costi standard correlata e lo alleghi al giustificativo della registrazione finanziaria come giustificativo correlato.</p><p>Senza questa funzione, il sistema registra le rivalutazioni di arrotondamento dei costi standard sulla stessa registrazione del giustificativo. Tale comportamento può talvolta causare informazioni sulla data in conflitto, poiché le rivalutazioni utilizzano la sessione o la data di sistema, mentre le registrazioni finanziarie utilizzano la data di registrazione.</p> |
| Gestione articoli e magazzino | \[Russia\] Registra le transazioni di magazzino finanziarie di Storno in base al flag di correzione nel giustificativo finanziario per gli ordini cliente | Questa funzione influisce sulla funzionalità di correzione delle note di credito per la Russia. Consente la registrazione delle transazioni di magazzino per le fatture di vendita in conformità con l'opzione di correzione nella contabilità generale. Quando questa funzione è abilitata, non ci sono più discrepanze tra il contrassegno **Correzione** sul giustificativo finanziario della transazione di inventario e il contrassegno **Storno** delle transazioni di inventario. |
| Gestione articoli e magazzino | (Russia) Esegui calcolo report Rotazione saldo scorte in batch | Per le localizzazioni russe di Supply Chain Management, la funzionalità consente di eseguire il report *Rotazione saldo scorte* in modalità batch per archiviarlo e visualizzare i report generati in precedenza. |
| Gestione articoli e magazzino | (Russia) Utilizza le traduzioni nella lingua locale nei moduli primari specifici del paese o dell'area geografica in Gestione inventario | Per le localizzazioni russe di Supply Chain Management, la funzionalità consente di utilizzare le traduzioni russe per nomi di prodotti/articoli e unità di misura negli stampati di inventario specifici per la Russia: elenco di conteggio (INV-3), elenco di conteggio (INV-5) ed elenco di conteggio (INV-6). |
| Pianificazione generale | Servizio Azure Machine Learning per la previsione della domanda | Questa funzionalità consente al servizio Azure Machine Learning di generare previsioni della domanda in base ai dati storici. Per ulteriori informazioni, vedi [Impostazione della previsione della domanda](../master-planning/demand-forecasting-setup.md). |
| Approvvigionamento | Pulisci storico aggiornamento ordini fornitore | Questa funzione consente di ripulire i record storici temporanei relativi agli aggiornamenti degli ordini fornitore. Aggiunge un nuovo pulsante chiamato **Pulisci storico aggiornamento acquisti** al riquadro azioni della pagina **Tutti gli ordini fornitore**. Questo funzionalità è abilitata per impostazione predefinita. |
| Controllo produzione | (Anteprima) Prelievo automatico di materiali pronti per il magazzino per le distinte di prelievo registrate automaticamente | Questa funzionalità consente di prelevare automaticamente e di risolvere le dimensioni inventariali per giornali di distinte di prelievo registrati automaticamente, derivati e di tipo backflush. |
| Controllo produzione | Convalida la scadenza delle materie prime rispetto alla data di consumo pianificata | Questa funzionalità cambia il modo in cui le date di scadenza del batch vengono convalidate quando si prenota un batch di materie prime da utilizzare durante la produzione. Quando questa funzionalità è abilitata, la data di scadenza del batch viene convalidata rispetto alla data di consumo pianificata (la data delle materie prime), come stabilito nella riga DBA di produzione o nella riga della formula dell'ordine batch. Quando questa funzionalità è disabilitata, la data di scadenza del batch viene convalidata rispetto alla data di consegna pianificata dell'ordine di produzione o batch (come in precedenza). |
| Vendite e marketing | Pulisci storico aggiornamento vendite in base alla validità | Questa funzionalità consente di impostare l'età massima dei record da conservare durante l'esecuzione dell'attività periodica **Pulizia dello storico aggiornamenti delle vendite**. I record più vecchi verranno eliminati. Ciò è utile quando si imposta l'attività per l'esecuzione periodica perché l'età viene sempre calcolata rispetto alla data di esecuzione dell'attività. Senza questa funzionalità, puoi solo impostare una data specifica per i record più vecchi da conservare. Per ulteriori informazioni, vedi [Programmare la pulizia dei dati dello storico vendite](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Vendite e marketing | Migliora le prestazioni del report "Primi 100" clienti | Questa funzione migliora le prestazioni del report **I primi 100** clienti eseguendo sempre il report su tutti i clienti (che è l'uso previsto) invece che tramite query personalizzate. Quando questa funzione è abilitata, tutte le impostazioni **Record da includere** sono disabilitate nella finestra del report **I primi 100**. |
| Warehouse Management | Supporto unità di scala per il rilascio al magazzino degli ordini in uscita | Quando questa funzionalità è abilitata, gli ordini in uscita possono essere rilasciati dall'hub direttamente all'unità di scala in cui gli ordini verranno evasi. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti argomenti della guida. Questi argomenti non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Argomenti nuovi o aggiornati |
|---|---|
| Gestione modifiche di progettazione | Per informazioni su come funzionano gli attributi di progettazione, vedi [Attributi di progettazione e ricerca di attributi di progettazione](../engineering-change-management/engineering-attributes-and-search.md). |
| Pianificazione generale | Per maggiori informazioni su come lavorare con le chiavi di riduzione, vedi [Pianificazione generale con previsioni della domanda](../master-planning/planning-optimization/demand-forecast.md) e [Chiavi di riduzione previsioni](../master-planning/reduction-keys.md). |
| Pianificazione generale | Per maggiori informazioni sull'utilizzo delle chiavi minimo/massimo, vedi [Garantire le scorte di sicurezza per gli articoli](../master-planning/safety-stock-replenishment.md). |
| Pianificazione generale | Per maggiori informazioni sull'allocazione delle previsioni, vedi [Previsioni di inventario](../master-planning/inventory-forecast.md). |
| Pianificazione generale | [Programmazione fornitura](../master-planning/supply-schedule.md) |
| Warehouse Management | [Parametri globali del dispositivo mobile](../warehousing/mobile-device-parameters.md) |
| Warehouse Management | [Ancoraggio](../warehousing/anchoring.md) |
| Vendite e marketing | Il commercio interaziendale è ora descritto in dettaglio in [Impostare il commercio interaziendale](../sales-marketing/intercompany-trade-set-up.md) e argomenti correlati. |
| Gestione inventario | La documentazione sulla visibilità inventario è stata ampliata e aggiornata, in [Panoramica del componente aggiuntivo Visibilità inventario](../inventory/inventory-visibility.md) e argomenti correlati. |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.23 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.23 delle app Finance and Operations (novembre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.23, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2021

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2021](/dynamics365-release-plan/2021wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
