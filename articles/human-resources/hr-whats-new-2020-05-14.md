---
title: Novità o modifiche in Dynamics 365 Human Resources (14 maggio 2020)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 14 maggio 2020.
author: andreabichsel
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb4693f3c856e7abcc39cbd658183d01ec98a066
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063749"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (14 maggio 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3244. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.

## <a name="platform-changes"></a>Modifiche della piattaforma

Le modifiche alla piattaforma sono incluse nella versione di questa settimana. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.10 delle app per finanza e operazioni (maggio 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md). Questa versione include correzioni di bug e modifiche alle viste salvate.
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a>Verificare che le distinte di prelievo Dataverse siano coerenti con le enumerazioni Leave (436343)

Le distinte di prelievo Dataverse sono ora coerenti con le enumerazioni Leave.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>Consenti agli utenti di configurare il flusso di lavoro della richiesta di congedo in base all'importo della richiesta (300044)

Gli utenti possono configurare i flussi di lavoro delle richieste di congedo in base alla quantità delle richieste.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>Il nuovo modulo del lavoratore espone i dati attraverso il menu Visualizza quando è abilitata la sicurezza avanzata (403185)

Questa versione corregge le modalità di visualizzazione dei lavoratori attraverso le persone giuridiche quando è abilitato l'accesso avanzato e sono accessibili i lavoratori di altre società.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Consenti l'esecuzione della maturazione delle ferie per un singolo piano o una singola azienda (318844)

Con questa modifica, puoi eseguire la maturazione per un'azienda o un piano.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>Mostra l'equivalente al tempo pieno della posizione (ETP) nel modulo dei lavoratori iscritti (414658)

Il valore FTE dalla posizione di un lavoratore determina il tasso di maturazione di un lavoratore quando l'opzione FTE è abilitata sul tipo di congedo. Questo campo è ora incluso nel modulo **Lavoratori iscritti** e nella finestra **Iscrizione collettiva**.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Aggiungi processo batch con scadenza saldo congedi (431266)

È ora disponibile un nuovo processo batch che viene eseguito quotidianamente. Diminuisce il saldo residuo delle ferie quando le date di scadenza diventano correnti.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>L'esportazione di contatti personali per un dipendente che utilizza l'entità persona di contatto personale del lavoratore non esporta i contatti personali con il tipo di relazione padre (345893)

L'entità dati **Persona di contatto personale del lavoratore** (**HcmPersonalContactPersonEntity** in DMF e **PersonalContactPerson** in OData) non è stata in grado di esportare i contatti personali che hanno un tipo di relazione **Padre**. Questo problema è stato risolto per i contatti personali creati dopo questa modifica. Contatti personali esistenti di tipo **Padre** verranno risolti in una versione successiva.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>I codici motivo vengono visualizzati in diversi scenari quando sono contrassegnati come Congedo e assenza e il modulo dipendente semplificato è abilitato (434163)

Questa modifica limita i codici motivo solo ai codici Permesso e Assenza quando si abilita l'inserimento semplificato dei dipendenti.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>La funzionalità di anteprima Assegna un piano di ferie ai dipendenti in futuro visualizza l'errore (433555)

Questa modifica corregge un errore quando un piano ferie ha due tipi di ferie assegnati e si tenta di assegnare un dipendente.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>Il banner Introduzione appare per tutti gli utenti (441731)

Con questa modifica, il banner Introduzione viene nascosto per gli utenti che non sono amministratori di sistema o amministratori della gestione dei dati. 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>L'entità Indirizzo lavoratore Dataverse funziona in modo diverso in termini di date effettive di data e ora in Human Resources (425071)

Questa modifica mantiene le informazioni sull'indirizzo allineate in determinati scenari, in base alle date dell'indirizzo.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>Impossibile aggiungere un allegato a una richiesta di congedo approvata (425407)

Con la versione di questa settimana, puoi aggiungere allegati alle richieste di ferie approvate senza modificare la richiesta di ferie.

## <a name="in-preview"></a>In anteprima

## <a name="leave-suspension"></a>Sospensione del congedo

È possibile sospendere le ferie e le assenze nelle risorse umane per un dipendente. La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati. Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente. Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Aggiornamento dell'esperienza utente per indicare che l'accumulo è sospeso (429550)

L'esperienza utente ora indica che l'accumulo è stato sospeso per un piano.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Sospendere l'accumulo dei congedi per determinati tipi di congedo (272447)

In questa versione le risorse umane possono creare una regola per sospendere gli accumuli dei congedi per i dipendenti con richieste di congedo inserite per congedi non retribuiti. Il congedo non retribuito può essere un tipo, ma non è necessario che lo sia. È possibile sospendere qualsiasi congedo in base a un altro tipo di congedo.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Entità DMF disponibile per le sospensioni degli accumuli (429549)

Un'entità DMF è ora disponibile per le sospensioni degli accumuli.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Aggiungere il codice motivo alle sospensioni degli accumuli (429547)

Codici motivo sono stati aggiunti alla sospensione degli accumuli.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Iniziare la transizione dai parametri delle risorse umane ai parametri di congedo e assenza

Questa versione inizia a combinare i parametri delle risorse umane con i parametri di congedo e assenza.

## <a name="carry-forward-rules"></a>Regole di riporto

È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto. Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni. Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]