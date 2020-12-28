---
title: Novità o modifiche in Dynamics 365 Talent (9 aprile 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
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
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a4d4de6cf28e24d1265395d6440df85edf71a0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461693"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-9-2019"></a>Novità o modifiche in Dynamics 365 Talent (9 aprile 2019)

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integrazione di Lifecycle Services (LCS) con "Segnala un problema"
In Attract and Onboard, i problemi segnalati dagli utenti finali mediante la funzionalità Segnala un problema ora generano automaticamente problemi per il supporto tecnico nel progetto LCS del cliente. Gli amministratori possono quindi valutare i problemi e inviarli a Microsoft quando necessario. Ciò è coerente con il modo in cui Core HR gestisce i problemi segnalati dagli utenti finali.

### <a name="relevance-search"></a>Ricerca di rilevanza
Nei pool di talenti, è ora possibile cercare competenze, nomi o informazioni relative al percorso informativo nell'intero database dei candidati. Non è più necessario specificare in quale sezione del profilo di un candidato si desidera effettuare la ricerca. Attract esegue la ricerca nell'intero profilo ed evidenzia tutte le corrispondenze trovate. Attract esegue la ricerca anche in tutti i documenti disponibili di un candidato e classifica i risultati della ricerca in modo intelligente. Inoltre, è possibile filtrare i risultati per origine o medaglia d'argento. Per ulteriori informazioni, vedere [Cercare e visualizzare profili di candidati](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Suggerimenti prospect
Attract consente di avviare la ricerca di candidati per una mansione non appena lo si attiva generando suggerimenti intelligenti sui candidati a partire dal database dei candidati dell'organizzazione. I suggerimenti includono le competenze e le informazioni sul percorso formativo identificate durante la ricerca di prospect pertinenti. Questi suggerimenti sono visualizzati nella scheda **Prospect** sotto una mansione, se attivati durante il processo di assunzione relativo alla mansione. Per ulteriori informazioni, vedere [Suggerimenti prospect](https://docs.microsoft.com/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Stati di disponibilità dei responsabili del colloquio
I programmatori dei colloqui saranno presto in grado di visualizzare gli stati **Fuori sede, Altra postazione di lavoro** per i responsabili dei colloqui, in modo da agevolare la programmazione degli orari più appropriati per tali responsabili.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Esperienza di colloquio dei candidati: salvare inviti nel calendario
Ora i candidati possono scaricare e salvare i relativi eventi di colloquio nei calendari personali utilizzando un file .ics allegato al messaggio di posta elettronica riepilogativo del colloquio che ricevono.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integrazione di Lifecycle Services (LCS) con Segnala un problema
In Attract and Onboard, i problemi segnalati dagli utenti finali mediante la funzionalità Segnala un problema ora generano automaticamente problemi per il supporto tecnico nel progetto LCS del cliente. Gli amministratori possono quindi valutare i problemi e inviarli a Microsoft quando necessario. Ciò è coerente con il modo in cui Core HR gestisce i problemi segnalati dagli utenti finali.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2225.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>La percentuale di piani variabili di base carica un importo non corretto
La versione di questa settimana corregge il problema che si verifica quando si caricano premi retributivi variabili utilizzando la percentuale dei piani di base.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>La selezione della data in Ultimo giorno di lavoro non funziona correttamente
Questa modifica risolve il seguente problema: quando gli utenti modificano il campo **Data di fine impiego** e selezionano la data utilizzando il controllo del calendario, un giorno viene aggiunto alla selezione.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Limitazione dei tipi di azione personali tramite l'azione intrapresa
Questa modifica limita i tipi di azione visualizzati quando si intraprendono specifiche azioni. Ad esempio, quando viene richiesta una nuova posizione, soltanto le azioni relative alla nuova posizione sono visualizzate nell'elenco delle azioni da selezionare. In precedenza, venivano visualizzate le azioni nuove e di modifica. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Trasferimento di un dipendente con retribuzione in una seconda persona giuridica
Questa versione consente il termine della retribuzione in una seconda persona giuridica se il trasferimento è interaziendale.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Impossibile selezionare la retribuzione per un impiego futuro durante un trasferimento
Quando si trasferisce un dipendente a una nuova persona giuridica, è ora possibile impostare la retribuzione per la nuova persona giuridica durante il processo di trasferimento.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>L'utente non può assegnare la retribuzione durante l'assegnazione della posizione
L'aggiunta di una nuova assegnazione della posizione ora consente la configurazione dei record di retribuzione fissa. 

## <a name="in-preview"></a>In anteprima

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Consentire la specifica dei codici motivo nei tipi di congedo
Le organizzazioni potrebbero necessitare di informazioni aggiuntive sulle richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Richiedere codici motivo per alcuni tipi di congedo nelle richieste di permesso
Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Ciò potrebbe essere dovuto ai criteri o ai requisiti normativi della società. Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane
La tracciabilità del tempo libero dei dipendenti e la comprensione di come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per i dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) per determinare i motivi dei saldi. 

## <a name="coming-soon"></a>Presto disponibili

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Miglioramenti all'interfaccia utente per la verifica di dipendenti duplicati
Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Per evitare di interrompere l'immissione di dati, il modulo Duplicati non viene aperto automaticamente.

###  <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi
Con l'aggiornamento 25 della piattaforma per Finance and Operations, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando avviate da un evento. 
