---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (11 gennaio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a89ba455acbed9724da6826ac4d41c6a481490
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "856140"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-11-2019"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (11 gennaio 2019)

[!include [banner](includes/banner.md)]

**Build 8.1.2100**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="changes"></a>Modifiche

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Convalida delle richieste di congedo mediante previsione del saldo disponibile
Le modifiche apportate in questa versione consentono ai dipendenti di richiedere congedi futuri senza sottrarli dal relativo saldo corrente. I flussi di lavoro standard saranno utilizzati per tutte le richieste future. Per ulteriori informazioni, leggere [Attribuire permessi in base alle ore lavorate](leave-accrue-hours-worked.md).

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Visualizzazione del saldo di congedo previsto in Dipendente self-service e Persone
Questa funzionalità consente la visualizzazione dei saldi per periodi di congedo futuri da parte del reparto risorse umane nonché da responsabili e dipendenti. I dipendenti possono visualizzare i saldi futuri nell'area di lavoro **Dipendente self-service** e il reparto risorse umane ha accesso alle stesse informazioni utilizzando l'area di lavoro **Persone**.

### <a name="notifications-for-changing-leave-balances"></a>Notifiche per la modifica dei saldi di congedo
I saldi di congedo visualizzeranno il saldo corrente dei dipendenti. I saldi futuri sono disponibili nelle aree di lavoro **Dipendente self-service** e **Persone** immettendo una data iniziale per il calcolo del saldo previsto.

Per visualizzare i saldi previsti, sono stati aggiunti degli elementi nelle seguenti aree:
  - Scheda**Tempo libero** nell'area di lavoro **Dipendente self-service**.
  - Scheda**Congedo e assenza** nell'area di lavoro **Responsabile self-service**.
  - Pagina**Congedo e assenza** nell'area di lavoro **Persone**.

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Utilizzo dei decimali per i piani di retribuzione variabile (piani in contanti)
I piani e i premi in contanti variabili presentano ora la flessibilità per importi e sostituzioni di valori con importi decimali.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>Impossibile modificare le date nei piani di retribuzione variabili dopo il salvataggio del piano
Questa modifica consente l'aggiornamento della data di fine del piano (estensione o scadenza) dopo che il piano è stato salvato. È sempre possibile attivare o disattivare i piani che non dipendono da date di inizio e di fine.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>Informazioni sulle retribuzioni disponibili all'assegnazione del ruolo di sicurezza Amministratore retribuzioni
Il ruolo Amministratore retribuzioni è stato aggiornato per avere accesso alle informazioni sulle retribuzioni durante il processo di richiesta.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Dipendente self-service | Il drill-down della gerarchia delle posizioni non richiama il nodo padre
Sono state apportate delle modifiche per eliminare un errore che si verificava all'aggiunta della gerarchia delle posizioni a nuove aree di lavoro e lo spostamento nella struttura organizzativa.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Nuovo messaggio di convalida quando il numero di dipendente successivo è in uso
È stata apportata una modifica per determinare il problema quando si assume un dipendente e il numero di dipendente successivo è in uso.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>Area di lavoro Dipendente self-service selezionata come pagina di avvio iniziale
Quando l'area di lavoro **Dipendente self-service** viene selezionata come pagina di avvio iniziale per un utente e a quell'utente non è assegnato il ruolo dipendente, il sistema visualizza il dashboard predefinito.

### <a name="termination-reason-code-updates-position-assignment-record"></a>Il codice del motivo di fine rapporto aggiorna il record di assegnazione della posizione
Il codice del motivo di fine rapporto ora aggiorna l'assegnazione della posizione quando si chiude un rapporto dipendente e si termina la posizione. 
