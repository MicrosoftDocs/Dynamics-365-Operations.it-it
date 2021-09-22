---
title: Anteprima di Dynamics 365 Supply Chain Management 10.0.22 (Novembre 2021)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6fc4b9d0a0f5319c8a75e7d687ee82ea81497844
ms.sourcegitcommit: a21166da59675e37890786ebf7e0f198507f7c9b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2021
ms.locfileid: "7471862"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10022-november-2021"></a>Anteprima di Dynamics 365 Supply Chain Management 10.0.22 (Novembre 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento elenca le funzionalità nuove o modificate nell'anteprima della versione 10.0.22. di Microsoft Dynamics 365 Supply Chain Management. Questa versione ha il numero di build 10.0.995 ed è disponibile come segue:

- **Anteprima della versione:** settembre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2021
- **Disponibilità generale della versione (aggiornamento automatico):** novembre 2021

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. La colonna *Funzionalità* fornisce collegamenti al [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), dove puoi vedere le date di rilascio ufficiali per ciascuna funzionalità. La colonna *Ulteriori informazioni* fornisce altri dettagli e/o collegamenti alla documentazione correlata. Per determinare come attivare una funzione, vedere la colonna *Abilitato da*. Per ulteriori informazioni su come utilizzare gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Potremmo aggiornare questo argomento per includere le funzionalità che sono state inserite nella build dopo che questo argomento è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da   |
|---|---|---|---|
| Pianificazione | [Supporto all'ottimizzazione della pianificazione per l'allocazione delle risorse basata sulle capacità](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Programmazione con capacità infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) | Gestione funzionalità: (*Programmazione capacità infinita per Ottimizzazione pianificazione*) |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato). Se desideri utilizzare una di queste funzionalità, devi abilitarle esplicitamente in [gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Area funzionale | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Gestione costi | Creare giustificativi correlati per rivalutazioni di arrotondamento costi standard | <p>Quando viene effettuata una registrazione finanziaria di magazzino (come una fattura di un ordine cliente o una transazione di magazzino), questa funzionalità fa sì che il sistema crei un giustificativo separato per qualsiasi rivalutazione di arrotondamento dei costi standard correlata e lo alleghi al giustificativo della registrazione finanziaria come giustificativo correlato.</p><p>Senza questa funzione, il sistema registra le rivalutazioni di arrotondamento dei costi standard sulla stessa registrazione del giustificativo. Tale comportamento può talvolta causare informazioni sulla data in conflitto, poiché le rivalutazioni utilizzano la sessione o la data di sistema, mentre le registrazioni finanziarie utilizzano la data di registrazione.</p> |
| Topologia ibrida distribuita | *(Non è richiesta alcuna gestione delle funzionalità).* | <p>Questa versione espande le capacità di pianificazione del carico in uscita del carico di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale.</p><p>Per ulteriori informazioni, vedere [Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Gestione modifiche di progettazione | Generazione di varianti per prodotti di progettazione | <p>Questa funzione consente di generare diverse varianti per un prodotto tecnico, in base al colore, alle dimensioni, allo stile o alle dimensioni della configurazione.</p><p>Per ulteriori informazioni, vedere [Generare varianti per prodotti di progettazione](../engineering-change-management/engineering-variants.md).</p> |
| Gestione articoli e magazzino | Integrazione visibilità inventario con offset prenotazione | <p>Questa funzione può essere abilitata solo dopo aver abilitato la funzionalità *Integrazione della visibilità dell'inventario*. Fornisce funzionalità per compensare le prenotazioni effettuate su Visibilità inventario.</p><p>Per maggiori informazioni, vedere [Prenotazioni di visibilità dell'inventario](../inventory/inventory-visibility-reservations.md).</p> |
| Vendite e marketing | Limita il numero di ordini cliente che è possibile selezionare per la registrazione | <p>Questa funzionalità viene abilitata automaticamente. Aggiunge un campo **Numero massimo di ordini cliente per la registrazione** alla pagina **Parametri contabilità clienti**. Questo campo permette di definire il numero massimo di ordini cliente che possono essere selezionati quando vengono registrate conferme, distinte di prelievo, documenti di trasporto e fatture dalla pagina della lista degli ordini cliente. Il valore predefinito è *100*.</p><p>La funzione aiuta a migliorare le prestazioni della pagina dell'elenco degli ordini cliente quando viene selezionato un numero considerevole di ordini cliente. Non ha alcun impatto sul numero di ordini di vendita che possono essere elaborati da un compito periodico.</p> |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti argomenti della guida. Questi argomenti non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nella sezione precedente. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Argomenti nuovi o aggiornati |
|---|---|
| Gestione modifiche di progettazione | [Panoramica sulla gestione delle modifiche tecniche](../engineering-change-management/product-engineering-overview.md) ora elenca tutte le funzionalità correlate e opzionali disponibili nella gestione delle funzionalità |
| Pianificazione generale | [Impostazione della previsione della domanda](../master-planning/demand-forecasting-setup.md) |
| Pianificazione generale | [Requisiti netti e informazioni di pegging con Ottimizzazione pianificazione](../master-planning/planning-optimization/net-requirements.md) |
| Warehouse Management | [Rilascia in magazzino](../warehousing/release-to-warehouse-process.md) fornisce una panoramica dettagliata del processo di rilascio completo al magazzino |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per le app Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.22 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.22 delle app Finance and Operations (novembre 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md). <!-- KFM: Confirm link -->

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.22, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

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
