---
title: Anteprima di Dynamics 365 Supply Chain Management 10.0.27 (luglio 2022)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.27.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: a91f2cdae0fed75f07d6cae86d24aeedfca80e94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844498"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10027-july-2022"></a>Anteprima di Dynamics 365 Supply Chain Management 10.0.27 (luglio 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione di anteprima 10.0.27. Questa versione ha il numero di build 10.0.1227 ed è disponibile con il seguente programma:

- **Anteprima della versione:** aprile 2022
- **Disponibilità generale della versione (aggiornamento automatico):** giugno 2022
- **Disponibilità generale della versione (aggiornamento automatico):** luglio 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo articolo per includere le funzionalità che sono state aggiunte nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Inventario e logistica | [Allocazione inventario per il componente aggiuntivo visibilità inventario](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | [Allocazione inventario di Inventory Visibility](../inventory/inventory-visibility-allocation.md) | Abilitato per impostazione predefinita |
| Produzione | Visualizzazione "Registrazioni quotidiane" per l'interfaccia di esecuzione dell'area di produzione | [In che modo i lavoratori utilizzano l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-use.md) e [Visualizzare i saldi delle ferie nell'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-payroll-stats.md) | Gestione funzionalità:<br>*Visualizzazione "Registrazioni quotidiane" per l'interfaccia di esecuzione dell'area di produzione* |
| Pianificazione | [Supporto di Ottimizzazione pianificazione per conto lavoro](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Gestire il lavoro in conto lavoro in produzione](../production-control/manage-subcontract-work-production.md) | Abilitato per impostazione predefinita |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Pianificazione generale | Considera il lead time magazzino per la creazione di un ordine di trasferimento pianificato | Quando viene creato un ordine di trasferimento pianificato, questa funzione fa sì che il sistema consideri il lead time di magazzino specificato nelle impostazioni dell'ordine predefinito dell'articolo quando calcola la data di ricevimento dell'ordine di trasferimento pianificato per l'impostazione di controllo della data di consegna come lead time dell'ordine di trasferimento pianificato di tipo *Nessuno* o *Vendite*. Quando viene specificato il lead time del trasferimento, il valore verrà utilizzato per il calcolo della data di ricevimento e i giorni di trasporto verranno ignorati. |
| Approvvigionamento | Informazioni fiscali contratto broker predefinite nelle righe fattura fornitore | Questa funzione introduce la logica per impostare i valori predefiniti per i campi **IVA** e **IVA articoli** nelle righe fattura fornitore contratto broker. Questa logica viene applicata solo quando il tipo di spesa nella riga del contratto broker è contabilità generale/contabilità generale. La fascia IVA articoli riceve il valore predefinito dalla categoria di approvvigionamento broker (se impostata) o dal tipo di spesa. La fascia IVA riceve il valore predefinito dal conto fornitore. |
| Approvvigionamento | Limita il numero di righe ordine fornitore per attività batch | Questa funzionalità consente di ottimizzare le prestazioni del sistema durante la registrazione di conferme ed entrate prodotti. Aggiunge una nuova impostazione denominata **Righe per attività** nella scheda **Consegna** della pagina **Parametri di approvvigionamento**. La nuova impostazione consente di limitare il numero di righe ordine fornitore elaborate da ogni attività batch. Pertanto, può impedire alle attività batch di grandi dimensioni di rallentare il sistema. |
| Gestione informazioni sul prodotto | Popola valori attributi del prodotto | Questa funzionalità aggiunge un'attività periodica denominata *Popola valori attributi del prodotto*. Questa nuova attività periodica crea i record di valore attributo del prodotto mancanti per gli attributi associati a prodotti tramite una categoria di prodotto. |
| Controllo produzione | Configurazione aggiuntiva nell'interfaccia di esecuzione dell'area di produzione | <p>Questa funzione aggiunge le opzioni seguenti alla pagina **Configurare esecuzione area di produzione**:</p><ul><li>**Apri automaticamente la finestra di dialogo di avvio** – Quando questa opzione è abilitata, la finestra di dialogo **Avvia processo** viene aperta automaticamente quando i lavoratori utilizzano la barra di ricerca per trovare un processo.</li><li>**Apri automaticamente la finestra di dialogo di avvio al completamento della ricerca** – Quando questa opzione è abilitata, la finestra di dialogo **Segnala stato** viene aperta automaticamente quando i lavoratori utilizzano la barra di ricerca per trovare un processo.</li><li>**Quantità rimanente predefinita nella finestra di dialogo di avanzamento del report** – Quando questa opzione è abilitata, la finestra di dialogo **Segnala stato** mostra la quantità rimanente da segnalare su un processo di produzione.</li></ul><p>Per ulteriori informazioni, vedi [Configurare l'interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md).</p> |
| Controllo produzione | Team di produzione nell'interfaccia di esecuzione dell'area di produzione | <p>Quando più lavoratori vengono assegnati allo stesso processo di produzione, ora possono nominare un lavoratore come pilota. I restanti lavoratori diventano automaticamente assistenti del pilota. Per il team risultante, solo il pilota deve registrare lo stato del processo, mentre i record di tempo si applicano a tutti i membri del team. Questa funzionalità supporta anche uno scenario denominato *assisti risorsa*. In questo scenario, un lavoratore può registrarsi come assistente per un altro lavoratore e diventare quindi il pilota del gruppo appena formato.</p><p>Per ulteriori informazioni, vedi [Modalità di utilizzo dell'interfaccia di esecuzione dell'area di produzione da parte dei lavoratori](../production-control/production-floor-execution-use.md).</p> |
| Controllo produzione | Report sugli articoli pianificazione nell'interfaccia di esecuzione dell'area di produzione | Questa funzionalità semplifica il processo di dichiarazione degli ordini batch per gli articoli pianificazione nell'interfaccia di esecuzione dell'area di produzione. Quando un ordine batch viene creato per un prodotto con tipo di produzione *Articolo pianificazione*, è possibile dichiarare come finiti solo i co-prodotti e i sottoprodotti dell'ordine batch specifico. Gli ordini batch per gli articoli pianificazione vengono in genere utilizzati per supportare i processi di disassemblaggio, in cui un prodotto materie prime viene disassemblato in più prodotti specifici. Quando si dichiara come finito un ordine batch per un articolo pianificazione, i lavoratori possono visualizzare solo i co-prodotti e i sottoprodotti nella finestra di dialogo **Segnala stato**. In precedenza era visualizzato anche l'articolo pianificazione che può essere fuorviante per i lavoratori. |

## <a name="new-and-updated-documentation-resources"></a>Risorse della documentazione nuove e aggiornate

Abbiamo recentemente aggiunto o aggiornato in modo significativo i seguenti articoli della guida. Questi articoli non sono necessariamente correlati alle nuove funzionalità aggiunte per questa versione, come elencato nelle sezioni precedenti. Tuttavia, potrebbero aiutarti a ottenere di più dalle funzionalità esistenti.

| Area funzionale | Articoli nuovi o aggiornati |
|---|---|
| Gestione costi | [Data media ponderata con Includi valore fisico e contrassegno](../cost-management/weighted-average-date.md) |
| Topologia ibrida distribuita | [Provare unità di scala in una topologia ibrida distribuita](../cloud-edge/cloud-edge-try-out.md) |
| Doppia scrittura | [Sincronizzare su richiesta con il motore di determinazione del prezzo di Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Warehouse Management | [Rilascio in magazzino](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.27 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.27 delle app per finanza e operazioni (giugno 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.27, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

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
