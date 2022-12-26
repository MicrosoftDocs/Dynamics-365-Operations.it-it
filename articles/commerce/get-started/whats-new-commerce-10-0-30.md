---
title: Anteprima di Dynamics 365 Commerce 10.0.30 (Novembre 2022)
description: Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics 365 Commerce 10.0.30.
author: josaw1
ms.date: 12/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: a449c7eff21c059555f9659ea932705858d26275
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831749"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>Anteprima di Dynamics 365 Commerce 10.0.30 (Novembre 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo elenca le funzionalità nuove o modificate nella versione di anteprima 10.0.30 di Microsoft Dynamics 365 Commerce. Questa versione ha il numero di build 10.0.1362 ed è disponibile con il seguente programma:

- **Anteprima della versione:** settembre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** novembre 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo articolo per includere le funzionalità che sono state aggiunte nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---------|------------------|----------------|--------------| 
| Supporto clienti   | Chatta su un sito di e-commerce utilizzando un bot Power Virtual Agents. | Questa funzionalità darà agli utenti del sito di e-commerce la possibilità di utilizzare un bot di chat Power Virtual Agents per le richieste di supporto. | Abilitato da amministratori/autori per gli utenti finali |
| Informazioni dettagliate  |  Effettua lo streaming degli eventi di POS Operational Insights sul tuo account Application Insights. | [Accedi ai log in Application Insights](../dev-itpro/operational-insights.md#enable-diagnostic-events-in-application-insights)   |  Consenso esplicito per i professionisti IT/sviluppatori   |
|  Pagamenti  | Supporto per ordini PayPal oltre il periodo di autorizzazione di 29 giorni. | Il periodo massimo di autorizzazione per PayPal è di 29 giorni, dopodiché è necessario generare una nuova autorizzazione e ID ordine. In alternativa, PayPal offre un'opzione in cui un ordine PayPal può essere referenziato come ordine generale, consentendo più autorizzazioni e acquisizioni rispetto allo stesso ID ordine, invece di generare una nuova autorizzazione e ID ordine a 29 giorni). | Quando si configura il connettore di pagamento PayPal in Commerce headquarters, il campo **OrderIntent** è stato aggiunto e può assumere due valori:<p><p>- **Autorizza** - Questa configurazione è l'impostazione predefinita (se il campo è lasciato vuoto, **Autorizza** agirà come predefinito). La configurazione di **OrderIntent** su **Autorizza** esegue la correlazione al valore **processing_instructione** PayPal di **NO_INSTRUCTION**. L'ordine sarà autorizzato con PayPal e l'autorizzazione non potrà essere modificata quando verrà utilizzato questo valore.<p>- **Salva** - quando il valore **OrderIntent** è impostato su **Salva**, viene effettuata la correlazione al valore PayPal **processing_instruction** di **ORDER_SAVED_EXPLICITLY**. I riferimenti dell'ordine verranno salvati nel servizio PayPal quando viene utilizzato questo valore.  |
| Accesso POS  | [Abilitare le funzionalità di diagnosi self-service per l'accesso al POS](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Questa funzionalità offre capacità di diagnosi self-service in POS e Commerce headquarters per aiutare i dipendenti e i manager dei punti vendita a identificare e risolvere rapidamente le cause principali dei problemi di accesso al POS.<p><p>- I messaggi di errore mostrati nella schermata di accesso al POS sono stati migliorati per fornire informazioni concrete sulla causa principale che possono aiutare i dipendenti del negozio che utilizzano il POS a capire cosa è andato storto in modo che possano eseguire le azioni necessarie per risolvere il problema.<p>- Una funzione **Accesso test** è disponibile nella pagina **Lavoratori** in Commerce headquarters in modo che i responsabili dei punti vendita che hanno configurato i dispositivi POS possano simulare l'accesso al POS. In caso di errore di accesso, questa funzione fornisce guide utili alla risoluzione dei problemi in modo che i responsabili possano controllare le configurazioni pertinenti, correggere i problemi e convalidare le correzioni.  | In base all'impostazione predefinita |


## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Dynamics 365 Finance 10.0.30 include gli aggiornamenti della piattaforma. Per altre informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.30 delle app per la finanza e le operazioni](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ognuno degli aggiornamenti che fanno parte della versione 10.0.30, accedi a Lifecycle Services (LCS) e visualizza l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-features"></a>Funzionalità rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](removed-deprecated-features-commerce.md) descrive le funzionalità che sono state rimosse o deprecate per Commerce.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
