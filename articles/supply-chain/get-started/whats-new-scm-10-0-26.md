---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.26 (maggio 2022)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.26.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: b44b044bf10115a7fcaf347a3b6f1759c2a68cb6
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219066"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.26 (maggio 2022)

[!include [banner](../includes/banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.26. Questa versione ha il numero di build 10.0.1192 ed è disponibile come segue:

- **Anteprima della versione:** marzo 2022
- **Disponibilità generale della versione (aggiornamento automatico):** aprile 2022
- **Disponibilità generale della versione (aggiornamento automatico):** maggio 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Potremmo aggiornare questo articolo per includere le funzionalità che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Inventario e logistica | [Query sulla visibilità delle scorte disponibili per supportare gli articoli di gestione avanzata del magazzino](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Supporto Inventory Visibility per articoli WMS](../inventory/inventory-visibility-whs-support.md) | Gestione funzionalità:<br>*Abilita articoli di magazzino in Visibilità inventario* |
| Inventario e logistica | [Available-to-promise per il componente aggiuntivo per la visibilità di magazzino](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [Visibilità dell'inventario con programmazioni di modifiche scorte disponibili e available-to-promise](../inventory/inventory-visibility-available-to-promise.md) | Abilitata dalla configurazione del servizio |
| Produzione | [Articoli a peso variabile per l'interfaccia di esecuzione dell'area di produzione](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [Come i lavoratori utilizzano l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-use.md) | Gestione funzionalità:<br>*Report sugli articoli a peso variabile dall'interfaccia di esecuzione area di produzione* |
| Produzione | Scheda Processi personali nell'interfaccia di esecuzione dell'area di produzione <!-- KFM: Add link to release plan when available --> | [Come i lavoratori utilizzano l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-use.md) | Gestione funzionalità:<br>*Scheda Processi personali nell'interfaccia di esecuzione dell'area di produzione* |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Approvvigionamento | Registra quantità registrate di prodotti stoccati e rimanenze di prodotti non stoccati per entrate e fatture fornitore | Questa funzionalità modifica il modo in cui le quantità di prodotti non stoccati (come i servizi) vengono registrate durante l'elaborazione delle fatture fornitore e delle spedizioni in entrata rispetto agli ordini di acquisto. La funzionalità modifica il comportamento dell'opzione quantità *Quantità e servizi registrati* per la registrazione di ricevute e fatture fornitore modificandola in modo che corrisponda al comportamento dell'opzione *Quantità registrata e prodotti non stoccati* già fornita al momento della registrazione delle quantità per i documenti di trasporto di vendita.<br><br>Quando si registra un'entrata prodotto o una fattura fornitore utilizzando l'opzione della quantità *Quantità e servizi registrati*, il sistema registra la quantità registrata di prodotti stoccati e registra la quantità rimanente di prodotti non stoccati (inclusi sia servizi che non servizi). Senza questa funzionalità, il sistema registra comunque la quantità registrata di prodotti stoccati (inclusi i servizi configurati come articoli stoccati) ma registra sempre l'intera quantità ordinata di prodotti di servizio non stoccati (e ignora i prodotti non stoccati che non sono di tipo *Servizio*). |
| Approvvigionamento | Sincronizza dimensioni di tracciabilità in righe ordine cliente e fornitore interaziendali | Questa funzionalità consente di controllare se le dimensioni di tracciabilità dei numeri di serie e di lotto sono sincronizzate tra le righe dell'ordine di acquisto e di vendita interaziendale. Aggiunge nuove impostazioni a entrambe le schede **Criteri ordine fornitore** e **Criteri ordine cliente** della pagina di configurazione **Interaziendale** per clienti e fornitori. Aggiorna anche i nomi di alcune impostazioni correlate e vicine per maggiore chiarezza.<br><br>Se stai utilizzando i processi di gestione del magazzino (WMS), tieni presente che questa funzionalità sincronizza solo numeri di serie e di batch le cui dimensioni sono superiori all'ubicazione nella gerarchia di prenotazione di destinazione. |
| Gestione informazioni sul prodotto | Pulisci valori attributo del prodotto | Questa funzionalità aggiunge un'attività periodica denominata **Pulisci valori attributo del prodotto**, che pulisce i record di valore attributo del prodotto non più associati ad alcun prodotto tramite una categoria di prodotto. |
| Gestione articoli e magazzino | (Russia) Impedimento delle discrepanze quando si emette il numero GTD per ordini fornitore che includono articoli abilitati da WMS | Questa funzionalità è disponibile solo per la Russia. Previene le discrepanze che si verificano durante l'emissione dei numeri di dichiarazione doganale (GTD) russi per gli ordini di acquisto di importazione che includono articoli abilitati per i processi di gestione del magazzino (WMS). Il processo di emissione di GTD modifica alcuni valori delle dimensioni inventariali nelle transazioni di magazzino correlate per le fatture incluse nel giornale di registrazione personalizzato, il che porta a discrepanze tra i record di lavoro per l'ordine d'acquisto e le transazioni di magazzino per l'acquisto. Quando questa funzione è abilitata, il processo di emissione di GTD genera un lavoro di adeguamento che elimina tali discrepanze. |
| Warehouse Management | Parser avanzato per codici a barre GS1 | Questa funzionalità aggiunge un parser avanzato per i dati dei simboli GS1. Il nuovo parser implementa l'algoritmo GS1 General Specification per l'analisi dei simboli GS1 e fornisce una convalida dei dati più forte. Per ulteriori informazioni, vedi [Scansione dei codici a barre GS1](../warehousing/gs1-barcodes.md). |
| Warehouse Management | Nuove pagine del workbench di pianificazione del carico | Aggiunge due nuove pagine del workbench di pianificazione del carico: **Workbench di pianificazione del carico in ingresso** e **Workbench di pianificazione del carico in uscita**. |
| Warehouse Management | Applicazione di gestione magazzino - Numero GTD vuoto | Questa funzionalità è disponibile solo per la Russia. Consente ai lavoratori che utilizzano l'app per dispositivi mobili Warehouse Management di lasciare vuoti i numeri di dichiarazione doganale russi (GTD) quando necessario. Se la dimensione di tracciabilità GTD è impostata per consentire valori vuoti, il sistema accetterà valori vuoti per GTD per le operazioni di inventario a condizione che l'inventario disponibile sia disponibile. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti articoli della guida. Questi articoli non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nelle sezioni precedenti. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Articoli nuovi o aggiornati |
|---|---|
| Gestione costi | Esempi e diagrammi aggiornati sono stati aggiunti a ciascuno dei seguenti articoli:<ul><li>[Informazioni su FIFO con valore fisico e contrassegno](../cost-management/fifo-physical-value-marking.md)</li><li>[Informazioni su LIFO con valore fisico e contrassegno](../cost-management/lifo-physical-value-marking.md)</li><li>[Data LIFO con valore fisico e contrassegno](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Prezzo di costo medio corrente](../cost-management/running-average-cost-price.md)</li><li>[Media ponderata con valore fisico e contrassegno](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per le app per la finanza e le operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.26 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.26 delle app per la finanza e le operazioni (maggio 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.26, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e cloud di settore: piano del primo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del primo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave1/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

