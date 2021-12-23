---
title: Anteprima di Dynamics 365 Supply Chain Management 10.0.24 (febbraio 2022)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.24.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 1b5742ddf7e5e2c5c32c446a0bde08f4964d6b95
ms.sourcegitcommit: 96515ddbe2f65905140b16088ba62e9b258863fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2021
ms.locfileid: "7891878"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10024-february-2022"></a>Anteprima di Dynamics 365 Supply Chain Management 10.0.24 (febbraio 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento elenca le funzionalità nuove o modificate nell'anteprima della versione 10.0.24. di Microsoft Dynamics 365 Supply Chain Management. Questa versione ha il numero di build 10.0.1084 ed è disponibile come segue:

- **Versione di anteprima:** Dicembre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** gennaio 2022
- **Disponibilità generale della versione (aggiornamento automatico):** febbraio 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Potremmo aggiornare questo argomento per includere le funzionalità che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Topologia ibrida distribuita | [Carichi di lavoro di esecuzione del magazzino ottimizzati su unità di scala](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale](../cloud-edge/cloud-edge-workload-warehousing.md) | Abilitato per impostazione predefinita. |
| Pianificazione | [Supporto Ottimizzazione pianificazione per il margine di riordino e il margine di emissione](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Margini di sicurezza](../master-planning/planning-optimization/safety-margins.md) | Abilitato per impostazione predefinita. |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Controllo produzione | Controllo disponibilità materiali su richiesta per ordini di produzione | Questa funzione rende più veloce l'apertura della pagina **Ordini di produzione da rilasciare** che è disponibile dall'area di lavoro **Gestione area di produzione**. Senza questa funzionalità, il sistema controlla automaticamente se i materiali sono disponibili per tutti gli ordini di produzione elencati non appena si apre la pagina, il che può richiedere molto tempo se il numero di ordini è elevato. Quando questa funzionalità è abilitata, il sistema fornisce invece un pulsante della barra degli strumenti, che puoi utilizzare per avviare il controllo dei materiali solo per gli ordini selezionati e quando necessario. |
| Controllo produzione | (Anteprima) Registra il consumo di materiali nell'interfaccia di esecuzione dell'area di produzione (non WMS) | Questa funzionalità consente ai lavoratori di utilizzare l'interfaccia di esecuzione del piano di produzione per registrare il consumo di materiale, i numeri di batch e i numeri di serie. Questa funzionalità supporta solo gli articoli che non sono abilitati per l'utilizzo di processi di magazzino avanzati (WMS). Il supporto per gli articoli abilitati per WMS è pianificato per una versione futura.<p>Alcuni produttori, in particolare quelli all'interno delle industrie di processo, devono registrare esplicitamente la quantità di materiale consumato per ogni batch oppure ordine di produzione. Ad esempio, i lavoratori potrebbero utilizzare una bilancia per pesare la quantità di materiale consumato mentre lavorano. Per garantire la completa tracciabilità dei materiali, le organizzazioni devono anche registrare quali numeri di batch sono stati consumati durante la produzione di ciascun prodotto. |
| Controllo produzione | Dichiarare come finito il carico di lavoro di gestione del magazzino per l'unità cloud e di scala edge | Questa funzionalità consente ai lavoratori di utilizzare l'app per dispositivi mobili Warehouse Management per dichiarare un ordine di produzione o batch come finito quando l'app è in esecuzione su un carico di lavoro di gestione del magazzino su un'unità cloud o di scala edge. Per ulteriori informazioni, vedi [Dichiarato di finito e stoccato su un'unità di scala](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| Controllo produzione | Iniziare l'ordine di produzione nel carico di lavoro di gestione del magazzino per l'unità cloud e di scala edge | Questa funzionalità consente ai lavoratori di utilizzare l'app per dispositivi mobili Warehouse Management per iniziare un ordine di produzione o batch quando l'app è in esecuzione su un carico di lavoro di gestione del magazzino su un'unità cloud o di scala edge. |
| Warehouse Management | Nuove pagine del workbench di pianificazione del carico | Abilita due nuove pagine del workbench di pianificazione del carico: **Workbench di pianificazione del carico in ingresso** e **Workbench di pianificazione del carico in uscita**. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti argomenti della guida. Questi argomenti non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Argomenti nuovi o aggiornati |
|---|---|
| Gestione costi | [Report valore di magazzino](../cost-management/inventory-value-report-storage.md) |
| Gestione costi | [Esempi e logica di report sul valore di magazzino](../cost-management/inventory-value-report-examples.md) |
| Pianificazione generale | [Parametri di data e ora utilizzati da Ottimizzazione pianificazione](../master-planning/planning-optimization/date-time-used.md) |
| Pianificazione generale | [Impostazione della previsione della domanda](../master-planning/demand-forecasting-setup.md) |
| Pianificazione generale | [Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima per gli articoli](../master-planning/safety-stock-journal.md) |
| Controllo produzione | [Personalizzare l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-customize.md) |
| Controllo produzione | [Progettare l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-styles.md) |
| Vendite e marketing | [Miglioramenti delle prestazioni di pulizia della cronologia delle vendite](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Warehouse Management | [Account utente dispositivo mobile](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per le app Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.24 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.24 delle app Finance and Operations (novembre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.24, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

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
