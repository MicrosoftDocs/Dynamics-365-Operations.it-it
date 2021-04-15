---
title: Novità o modifiche in Dynamics 365 Human Resources (16 settembre 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 16 settembre 2020.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf0e2d90b07cb488429311d04dfbc4d1d3520842
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800095"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (16 settembre 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3557. I numeri tra parentesi accanto ad alcune funzionalità si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.

## <a name="included-in-this-release"></a>Incluse in questa versione

-  [Visualizzazioni salvate - disponibilità generale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- Per ulteriori informazioni, vedi [Visualizzazioni salvate](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/saved-views). 

- Il modulo **Azioni della posizione** include ha una griglia delle dimensioni aggiornata e una nuova finestra di dialogo (469495).

- Se imposti **Limita l'accesso alle informazioni sui lavoratori** su Sì in **Accesso avanzato** in **Parametri condivisi risorse umane**, i moduli per i benefit ora mostrano solo i lavoratori appropriati (393384).

- Nuove opzioni di generazione di calendari nell'entità **WorkCalendar** (477055):<br>- Ora di fine predefinita<br>-    Ora di inizio predefinita<br>-  Venerdì è giorno lavorativo<br>-  Lunedì è giorno lavorativo<br>-  Sabato è giorno lavorativo<br>- Domenica è giorno lavorativo<br>- Giovedì è giorno lavorativo<br>- Martedì è giorno lavorativo<br>- Mercoledì è giorno lavorativo<br>- ID festività calendario lavorativo

- L'entità **LeaveBankTransactionV1** ora include il codice motivo (477823).

- Ora puoi salvare le registrazioni delle attività (492923).

- La pubblicazione dei dati viene ora completata da **HCMWorkerContactEntity** (427620).

- La Scheda dettaglio **Retribuzione** viene ora visualizzata per il tipo di lavoratore terzista nel modulo **Azioni del lavoratore** (482494).

- I campi **Livello** e **Piano** sono ora obbligatori se imposti **Retribuzione fissa**. Se lasci vuoti questi campi (482497), viene visualizzato un messaggio di errore.

- Il campo **Tipo di piano** in **Benefit** è ora un elenco a discesa (488768).

- Gli amministratori di sistema ora ricevono una notifica se un campo personalizzato viene eliminato da Human Resources (481408).

- Durante il processo di chiusura del dipendente, Human Resources si comporta come previsto e non cambia l'azienda selezionata dopo che sembra bloccata (479877). 

- I responsabili non possono più aggiungere una colonna numerica tramite la personalizzazione (485317).

- I responsabili non possono più rimuovere il filtro dell'intervallo di dati dai numeri di identificazione in scadenza (485321).

- Quando il campo **Subordinato a** è vuoto, i dettagli della posizione vengono ancora visualizzati quando si passa con il mouse sopra la posizione (433328).

- I dipendenti possono ora visualizzare le informazioni sul piano di benefit in Dipendente self-service (481676).

- I dipendenti possono ora vedere tutti i corsi registrati (429048).

- È ora possibile limitare le opzioni di visualizzazione per la pagina **Certificati professionali**. È possibile limitare le opzioni di visualizzazione alla persona giuridica corrente, in base allo stato del lavoratore e al tipo di lavoratore (451501). 


## <a name="in-preview"></a>In anteprima

### <a name="human-resources-app-in-teams"></a>App Human Resources in Teams

I dipendenti possono visualizzare i congedi e richiederli in Microsoft Teams. Possono interagire con un bot per creare richieste di congedo. Per ulteriori informazioni, vedere:

- [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano della prima ondata di rilascio di Dynamics 365 2020
- [App Human Resources in Teams](https://go.microsoft.com/fwlink/?linkid=2127841) nella documentazione di Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Funzioni di anteprima dell'app Human Resources in Teams
 
-  **Notifiche**: i mittenti e gli approvatori delle richieste di permesso verranno informati nell'app Human Resources in Teams. I responsabili dell'approvazione possono approvare o rifiutare le richieste di permesso. I mittenti riceveranno una notifica se la richiesta è stata approvata o rifiutata. Per ulteriori informazioni, vedere:
   - [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano del primo ciclo di rilascio del 2020 di Dynamics 365
   - [Abilitare le notifiche per l'app Human Resources in Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) nella documentazione di Human Resources
   - [Attivare o disattivare le notifiche di Teams per i singoli utenti](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) nella documentazione di Human Resources
   - [Notifiche di Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) nella documentazione di Human Resources
   - [Visualizzare il calendario dei congedi della team](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) nella documentazione di Human Resources
 
- **Calendario permessi del responsabile**: i responsabili possono vedere i permessi approvati e in sospeso per i loro diretti subalterni in una visualizzazione calendario. Questa visualizzazione fornisce una facile comprensione di quando i membri del team non sono al lavoro. Per ulteriori informazioni, vedere:
   - [Esperienza di congedo e assenza dei dipendenti in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) nel piano del primo ciclo di rilascio del 2020 di Dynamics 365
   - [Visualizzare il calendario dei congedi della team](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) nella documentazione di Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opzione di configurazione per posizionare l'elenco Elementi di lavoro assegnati all'utente (477004)

È ora disponibile una nuova opzione per posizionare l'elenco **Elementi di lavoro assegnati all'utente** nella colonna di destra della dashboard. Con questa modifica, tutti gli elementi di lavoro e gli elenchi di attività vengono visualizzati nella stessa area. Abilitare questa funzionalità attivandola in **Anteprima: miglioramenti dell'esperienza del flusso di lavoro** in Gestione funzionalità. Per ulteriori informazioni su come attivare le funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

Questa funzione promuove anche le opzioni del flusso di lavoro che appaiono nei moduli delle azioni del personale. Le opzioni del flusso di lavoro vengono visualizzate anche sopra la scheda dettaglio Azione per un accesso rapido. Per ulteriori informazioni, vedere: 

- [Miglioramenti all'esperienza del flusso di lavoro di organizzazione e gestione del personale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) nel piano del secondo ciclo di rilascio del 2020 di Dynamics 365

![Elementi di lavoro assegnati all'utente](./media/hr-workflow-work-items-assigned-to-me.png)

![Accesso rapido agli elementi del flusso di lavoro](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>Calendario di congedi e assenze

Questa versione include opzioni di calendario aggiuntive per i calendari di congedi e assenze. Per ulteriori informazioni, vedere [Visualizzare i calendari di team e società](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-calendar).

## <a name="coming-soon"></a>Presto disponibili

### <a name="checklist-entities-included-in-dataverse"></a>Elenco di controllo entità incluso in Dataverse

Le entità dell'elenco di controllo per i processi di onboarding, offboarding, trasferimenti e aziendali saranno presto disponibili in Dataverse.

### <a name="benefits-management-reason-codes"></a>Codici motivo gestione vantaggi

I codici motivo per la gestione dei vantaggi verranno presto combinati con i codici motivo esistenti in Human Resources. Se sono stati creati codici motivo nella gestione dei vantaggi che superano i 15 caratteri, è necessario modificare il nome del codice motivo nel modulo **Codici motivo** della gestione dei vantaggi in modo che abbia al massimo 15 caratteri. Dopo aver aggiornato il nome, il codice motivo verrà visualizzato sotto il modulo del codice motivo esistente in Gestione del personale. Questa modifica sarà disponibile in futuro e non influirà sul funzionamento esistente.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]