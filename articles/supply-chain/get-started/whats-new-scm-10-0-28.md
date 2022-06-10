---
title: Anteprima di Dynamics 365 Supply Chain Management 10.0.28 (agosto 2022)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.28.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 306ff9be80c7a7a947b9132e3c9b4b9ec799b265
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813123"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10028-august-2022"></a>Anteprima di Dynamics 365 Supply Chain Management 10.0.28 (agosto 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione di anteprima 10.0.28. Questa versione ha il numero di build 10.0.1264 ed è disponibile con il seguente programma:

- **Anteprima della versione:** maggio 2022
- **Disponibilità generale della versione (aggiornamento automatico):** luglio 2022
- **Disponibilità generale della versione (aggiornamento automatico):** luglio 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo argomento per includere le funzionalità che sono state aggiunte nella build dopo che questo argomento è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Inventario e logistica | [Entità di integrazione dei costi di spedizione per spedizionieri di terze parti](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Panoramica delle entità dei costi di spedizione](../landed-cost/landed-cost-entities-overview.md) | Abilitato per impostazione predefinita |
| Pianificazione | [Supporto di Ottimizzazione pianificazione per durata a scaffale](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Presto disponibile <!-- KFM: Vendor is preparing this. Expected May 20. --> | Abilitato per impostazione predefinita |

<!-- KFM: Confirm status of this feature:
| Planning | [Demand Driven Material Requirements Planning (DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | Coming soon | Feature management:<br>*(Preview) DDMRP for Planning Optimization* | -->

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Gestione articoli e magazzino | Abilita la visualizzazione delle scorte disponibili interaziendali solo per quantità disponibile diversa da zero | Questa funzione consente di scegliere se includere gli articoli con quantità disponibile zero nell'elenco delle scorte disponibili interaziendali. Puoi controllare questa opzione usando l'impostazione **Non mostrare articoli con quantità disponibile pari a zero nell'elenco delle scorte disponibili interaziendali**, che questa funzione aggiunge alla pagina **Parametri di gestione articoli e magazzino**. |
| Gestione articoli e magazzino | (India) Per le regole dei prezzi di trasferimento, ignorare l'ubicazione quando "Codice magazzino di origine" è impostato su "Tutti" | <p>Questa funzione si applica solo alle ubicazioni dell'India. Rende più intuitivo il processo di impostazione dei prezzi di trasferimento per gli articoli nei trasferimenti di magazzino.</p><p>Puoi impostare i prezzi di trasferimento configurando ogni articolo con le regole dei prezzi di trasferimento. Un modo per eseguire questa configurazione consiste nell'includere una riga di regola in cui il campo **Codice magazzino di origine** è impostato su *Tutti*. Questa impostazione indica che il prezzo di trasferimento definito dalla riga deve essere applicato indipendentemente dal magazzino da cui viene prelevato l'articolo. Quando questa funzione è abilitata, le regole del prezzo di trasferimento in cui il campo **Codice magazzino di origine** è impostato su *Tutti* ignorano l'impostazione **Ubicazione**. Pertanto, la regola si applicherà indipendentemente dall'ubicazione specificata nell'ordine di trasferimento. Questo comportamento è probabilmente quello previsto, poiché l'ubicazione è al di sotto del magazzino nella gerarchia delle dimensioni di stoccaggio.</p><p>Senza questa funzione, il sistema applica regole di questo tipo solo quando l'ubicazione nell'ordine di trasferimento corrisponde esattamente all'ubicazione impostata per la regola. (Se per la regola è impostata un'ubicazione vuota, il sistema applicherà la regola solo per trasferire gli ordini che hanno anche un valore vuoto per l'ubicazione.)</p> |
| Gestione articoli e magazzino | Pulizia dati report scorte disponibili | Questa funzionalità offre un modo per pulire i dati usati per creare i report *Archiviazione report scorte disponibili*. |
| Controllo produzione | Assegna le attività di progetto per le righe contratto di assistenza e ordine di assistenza | Questa funzione aggiunge un campo denominato **Attività di progetto** al contratto di assistenza e alle righe dell'ordine di assistenza, in modo da poter impostare un'attività di progetto. La funzione aiuterà a prevenire gli errori di blocco quando si registrano giornali di registrazione del progetto di gestione assistenza che richiedono l'impostazione di un'attività di progetto.  |
| Warehouse Management | Servizio di prelievo manuale righe di trasferimento per amministratori o utenti attendibili simili | Questa funzione consente agli amministratori di prelevare manualmente le transazioni di magazzino correlate alle righe di trasferimento. Queste righe includono quelle che sono già state rilasciate al magazzino. Gli amministratori dovrebbero eseguire questa selezione solo in casi eccezionali, ad esempio quando il sistema è danneggiato. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti argomenti della guida. Questi argomenti non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nelle sezioni precedenti. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Argomenti nuovi o aggiornati |
|---|---|
| Gestione costi | [Prezzo di entrata fisso](../cost-management/fixed-receipt-price.md) |
| Gestione costi | [Domande frequenti sui costi di inventario](../cost-management/inventory-costing-faq.md) |
| Gestione costi | [Principio di contabilità generale di registrazione nel conto di addebito](../cost-management/post-to-charge-account-accounting-principle.md) |
| Gestione inventario | [Dettagli sulle operazioni di magazzino](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.28 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.28 delle app per finanza e operazioni (giugno 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.28, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

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
