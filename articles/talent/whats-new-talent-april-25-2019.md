---
title: Novità o modifiche in Dynamics 365 Talent (23 aprile 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cbafea9063844dd3f19e5828ab37632e04591f18
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897899"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Novità o modifiche in Dynamics 365 Talent (23 aprile 2019)

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2253. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS).

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati
Nella versione di questa settimana, le seguenti entità supportano campi personalizzati: livello retributivo, opzione benefit, tipo di competenza e paese di retribuzione

### <a name="additional-odata-entities-302992"></a>Entità aggiuntive OData (302992)
Le seguenti entità sono ora supportate all'interno di OData: esperienza professionale dei lavoratori e percorso formativo del lavoratore.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Allegati del Giornale di registrazione prestazioni per manager e dipendenti (308248)
In questa versione, gli allegati sono ora disponibili sia per i manager che per i dipendenti durante la creazione e l'aggiornamento delle voci del giornale delle prestazioni.

### <a name="employee-rehire-flag-always-available-310047"></a>Flag di riassunzione del dipendente sempre disponibile (310047)
L'opzione di riassunzione dei dipendenti è ora disponibile per l'aggiornamento al di fuori del processo di fine rapporto. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>Non è possibile modificare il nome del **Metodo di pagamento personale** (308815)
La personalizzazione è stata abilitata per consentire la modifica dell'etichetta **Metodo di pagamento personale** in Dipendente self-service.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>Le dimensioni finanziarie rispetto a una posizione non possono essere eliminate (293908)
Le dimensioni finanziarie possono ora essere rimosse quando si richiede una modifica per una posizione esistente e le dimensioni finanziarie superano i vincoli interaziendali. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>Il cliente non può pubblicare nuovamente i dati in Talent all'apertura dei dati da Excel (302955)
Questa modifica corregge un problema di pubblicazione quando si utilizzano le tabelle correlate.

## <a name="in-preview"></a>In anteprima

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Consentire la specifica dei codici motivo nei tipi di congedo
Le organizzazioni potrebbero necessitare di informazioni aggiuntive sulle richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Richiedere codici motivo per alcuni tipi di congedo nelle richieste di permesso
Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Ciò potrebbe essere dovuto ai criteri o ai requisiti normativi della società. Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane
La tracciabilità del tempo libero dei dipendenti e la comprensione di come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per il tempo libero dei dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) per determinare i motivi dei saldi.

## <a name="coming-soon"></a>Presto disponibili

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Miglioramenti all'interfaccia utente per la verifica di dipendenti duplicati
Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Per evitare di interrompere l'immissione di dati, il modulo Duplicati non viene aperto automaticamente.
## <a name="known-issues"></a>Problemi noti

### <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi
Con l'aggiornamento 26 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando le notifiche sono attivate da un evento.
