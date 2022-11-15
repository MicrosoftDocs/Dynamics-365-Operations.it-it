---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.30 (novembre 2022)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.30.
author: kamaybac
ms.date: 11/07/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 20674ebd9d49b077371998f53d2b22c74f888fc6
ms.sourcegitcommit: 613be2f35e600ae1a1fa7ea2ae30e78984ca398a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2022
ms.locfileid: "9748466"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10030-november-2022"></a>Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.30 (novembre 2022)

[!include [banner](../includes/banner.md)]

Questo articolo elenca le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management versione 10.0.30. Questa versione ha il numero di build 10.0.1362 ed è disponibile con il seguente programma:

- **Anteprima della versione:** settembre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** novembre 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo articolo per includere le funzionalità che sono state aggiunte nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Inventario e logistica | [Tener traccia delle quantità prenotate temporanee all'interno delle allocazioni](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/track-soft-reserved-quantities-within-allocations) | [Allocazione inventario di Inventory Visibility](../inventory/inventory-visibility-allocation.md) |  Abilitata dalla [configurazione del servizio](../inventory/inventory-visibility-configuration.md) |
| Produzione | [Monitorare le apparecchiature con Intelligence dei dati del sensore](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Home page di Intelligence dei dati del sensore](../sensor-data-intelligence/sdi-home-page.md) | Gestione funzionalità:<br>*(Anteprima) Intelligence dei dati del sensore* |
| Warehouse Management | [Deviazioni multilivello per l'app per dispositivi mobili Warehouse Management](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/multi-level-detours-warehouse-management-mobile-app) | [Configura le deviazioni per i passaggi nelle voci di menu del dispositivo mobile](../warehousing/warehouse-app-detours.md) | Gestione funzionalità:<br>*Deviazioni multilivello per l'app per dispositivi mobili Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Miglioramento delle funzionalità inclusi in questa versione

Questa tabella elenca i miglioramenti delle funzionalità incluse in questa versione. Ciascuno di questi miglioramenti fornisce un miglioramento incrementale a una funzionalità esistente. Poiché sono solo miglioramenti, non sono elencati nel [piano di rilascio](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Tuttavia, per garantire che questi miglioramenti non siano in conflitto con le personalizzazioni o le preferenze esistenti, ognuno di essi è disattivato per impostazione predefinita (se non diversamente specificato).

Se desideri attivare o disattivare una di queste funzionalità, devi farlo in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modulo | Nome della funzionalita in gestione funzionalità | Ulteriori informazioni |
|---|---|---|
| Controllo produzione | Informazioni sulla disponibilità nella pagina Ordini di produzione da rilasciare | Aggiunge una colonna per la quantità di scorte disponibili per la voce nella sezione Righe della pagina **Ordini di produzione da rilasciare**. |
| Gestione trasporto | Assegnare le spedizioni ai segmenti di itinerario correlati | Questa funzione consente al sistema di ripartire i costi di trasporto delle spedizioni in modo più accurato, anche per carichi con spedizioni multiple consegnate a destinazioni di vari segmenti lungo un unico itinerario. Assegna ogni spedizione al segmento di itinerario più adatto in base agli indirizzi di destinazione della spedizione e del segmento. La funzione calcola quindi il costo di trasporto di ciascuna spedizione in proporzione al costo di trasporto totale del carico, in base al peso relativo, al volume, alla quantità e alla distanza percorsa della spedizione. Questa funzionalità si applica solo alle spedizioni gestite tramite il modulo Gestione trasporti (TMS). |

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Supply Chain Management 10.0.30 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.30 delle app Finance and Operations (novembre 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ognuno degli aggiornamenti che fanno parte della versione 10.0.30, accedi a Lifecycle Services (LCS) e visualizza l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e cloud di settore: piano del primo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
