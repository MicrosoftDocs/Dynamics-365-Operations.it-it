---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.22 (novembre 2021)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: b95f131a45c11748cfd4c66c47e5a51c765ed486
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740412"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.22 (novembre 2021)

[!include [banner](../includes/banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.22. Questa versione ha il numero di build 10.0.995 ed è disponibile come segue:

- **Anteprima della versione:** settembre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** novembre 2021

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. La colonna *Funzionalità* fornisce collegamenti al [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), dove puoi vedere le date di rilascio ufficiali per ciascuna funzionalità. La colonna *Ulteriori informazioni* fornisce altri dettagli e/o collegamenti alla documentazione correlata. Per determinare come attivare una funzione, vedere la colonna *Abilitato da*. Per ulteriori informazioni su come utilizzare gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Potremmo aggiornare questo articolo per includere le funzionalità che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Pianificazione | [Supporto all'ottimizzazione della pianificazione per l'allocazione delle risorse basata sulle capacità](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Pianificazione con selezione delle risorse in base alla capacità](../master-planning/planning-optimization/capability-based-scheduling.md) | Gestione funzionalità: (*Programmazione capacità infinita per Ottimizzazione pianificazione*) |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato). Se desideri utilizzare una di queste funzionalità, devi abilitarle esplicitamente in [gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Topologia ibrida distribuita | *(Non è richiesta alcuna gestione delle funzionalità).* | <p>Questa versione espande le capacità di pianificazione del carico in uscita del carico di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale.</p><p>Per ulteriori informazioni, vedere [Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Gestione modifiche di progettazione | Generazione di varianti per prodotti di progettazione | <p>Questa funzione consente di generare diverse varianti per un prodotto tecnico, in base al colore, alle dimensioni, allo stile o alle dimensioni della configurazione.</p><p>Per ulteriori informazioni, vedere [Generare varianti per prodotti di progettazione](../engineering-change-management/engineering-variants.md).</p> |
| Gestione articoli e magazzino | Integrazione visibilità inventario con offset prenotazione | <p>Questa funzione può essere abilitata solo dopo aver abilitato la funzionalità *Integrazione della visibilità dell'inventario*. Fornisce funzionalità per compensare le prenotazioni effettuate su Visibilità inventario.</p><p>Per maggiori informazioni, vedere [Prenotazioni di visibilità dell'inventario](../inventory/inventory-visibility-reservations.md).</p> |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti articoli della guida. Questi articoli non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Articoli nuovi o aggiornati |
|---|---|
| Gestione modifiche di progettazione | [Panoramica sulla gestione delle modifiche tecniche](../engineering-change-management/product-engineering-overview.md) ora elenca tutte le funzionalità correlate e opzionali disponibili nella gestione delle funzionalità |
| Pianificazione generale | [Impostazione della previsione della domanda](../master-planning/demand-forecasting-setup.md) |
| Pianificazione generale | [Requisiti di rete e informazioni sul pegging](../master-planning/planning-optimization/net-requirements.md) |
| Warehouse Management | [Rilascia in magazzino](../warehousing/release-to-warehouse-process.md) fornisce una panoramica dettagliata del processo di rilascio completo al magazzino |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per le app per la finanza e le operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.22 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.22 delle app per la finanza e le operazioni (novembre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.22, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

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

