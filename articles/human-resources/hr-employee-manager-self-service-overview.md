---
title: Panoramica self-service per dipendenti e manager
description: Questo articolo fornisce una panoramica dell'area di lavoro self-service per dipendenti e manager.
author: andreabichsel
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d7c68d22347861978eccff356139bab4fbc723b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790814"
---
# <a name="employee-and-manager-self-service-overview"></a>Panoramica self-service per dipendenti e manager

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo fornisce una panoramica dell'area di lavoro self-service per dipendenti e manager.

## <a name="edit-personal-details"></a>Modifica dettagli personali

Se è necessario aggiungere o modificare informazioni personali, vedere [Modificare le informazioni personali](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Utente non assegnato a un record lavoratore

Se non l'utente non è stato collegato a un record **Lavoratore** nella pagina **Utenti**, verrà visualizzato il seguente messaggio:

**ID utente non associato ad alcun record dipendente nel sistema. Non sarà possibile visualizzare né aggiornare le informazioni fino a quando non viene eseguita un'associazione. Per assistenza, contattare il responsabile o il team di supporto.**

Per associare un utente a un record **Lavoratore** passare a **Utenti** e selezionare l'utente. Selezionare **Modifica**, aggiungere il lavoratore corrispondente nel campo **Persona** nel modulo e selezionare **Salva**. Ora è possibile accedere al self-service dei dipendenti.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Requisiti di sicurezza per il self-service dipendenti e responsabili

Il self-service dipendenti e responsabili richiede due ruoli di sicurezza:

- I dipendenti richiedono il ruolo dipendente.
- I responsabili richiedono i ruoli dipendente e responsabile.

>[!NOTE]
>È inoltre possibile utilizzare ruoli personalizzati per accedere al self-service dipendenti e responsabili purché sia stato concesso loro l'accesso alle aree di lavoro dipendente e responsabile.<br>
>L'accesso del responsabile alle informazioni sui dipendenti si basa sulla gerarchia della riga di posizione corrente definita in Human Resources.

## <a name="employee-self-service"></a>Self-service dipendenti

La scheda **Informazioni personali** visualizza le seguenti informazioni per il self service dipendente.  

### <a name="summary"></a>Riepilogo

**Elementi di lavoro assegnati** visualizza tutte le approvazioni e gli elementi del flusso di lavoro assegnati al dipendente. È possibile configurare gli elementi flusso di lavoro per inviare messaggi e-mail all'utente.

**Questionari assegnati** visualizza tutti i questionari programmati assegnati direttamente al dipendente o al gruppo.

**Directory società** consente ai dipendenti di cercare informazioni relative alle persone all'interno dell'organizzazione. Le informazioni sul contatto pubbliche sono disponibili per tutti i dipendenti. La directory società è limitata alla società a cui il dipendente ha effettuato l'accesso.

**Calendario di team** mostra le informazioni del calendario del team. Per ulteriori informazioni, vedere [Visualizzare i calendari di team e società](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Informazioni personali sull'avanzamento professionale

La sezione **Informazioni professionali personali** del self-service dipendente contiene le schede relative a congedi e assenze, gestione delle prestazioni, competenze, vantaggi, attività e allegati.

La scheda **Saldi permessi** mostra i saldi di tutti i piani registrati. Questa carta prevede il saldo in base al metodo di attribuzione per competenza. È possibile inserire e inviare richieste di permesso che passeranno attraverso un processo di flusso di lavoro di approvazione. Per ulteriori informazioni sulla gestione di congedi e assenze, vedere [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md).

La scheda **Attività** visualizza le attività assegnate all'utente e consente di visualizzarle e gestirle.

La scheda **Prossimo corso registrato** mostra il prossimo corso in cui si è registrati. È possibile visualizzare e registrare solo i corsi aperti. Tutti i corsi che sono aperti per l'iscrizione hanno lo stato **Avviato** e consentono ai dipendenti di registrarsi automaticamente in questa scheda. A seconda delle impostazioni dell'organizzazione, la registrazione del corso potrebbe essere soggetta a un processo di approvazione.

La scheda **Certificati** visualizza il certificato e la data di scadenza del certificato più prossima alla data corrente. È possibile aggiornare, aggiungere o rimuovere certificati. A seconda delle impostazioni dell'organizzazione, gli aggiornamenti dei certificati potrebbero essere soggetti a un processo di approvazione.

La scheda **Prossima revisione programmata** mostra la prossima revisione delle prestazioni. È possibile iniziare una nuova revisione da questa scheda. Anche il manager o il rappresentante delle risorse umane può avviare revisioni. A seconda delle impostazioni dell'organizzazione, è possibile anche visualizzare, aggiornare e inviare revisioni di uscita da questa scheda.

È possibile gestire gli obiettivi con la scheda **Obiettivi prestazioni**. Questa carta mostra il numero di obiettivi presenti in ogni stato (**Non avviato**, **Operativo** e **Richiede miglioramento**). È possibile creare, aggiornare e rimuovere obiettivi, in base alla sicurezza basata su ruolo assegnata. Se desiderato, è possibile aggiungere nuovi obiettivi da gruppi o modelli. I manager e le risorse umane possono anche creare obiettivi per conto dei dipendenti e determinare i dettagli di ciascun obiettivo. I manager e i dipendenti possono collaborare su obiettivi e aggiornare attività, misure e stato. È anche possibile includere allegati.

È possibile visualizzare le competenze esistenti nella scheda **Competenze**. È possibile aggiornare le competenze, aggiungerne di nuove o rimuovere quelle che non sono più pertinenti. A seconda delle impostazioni dell'organizzazione, la modifica alle competenze potrebbe essere soggetta a un processo di approvazione.

È possibile visualizzare l'attuale retribuzione nella scheda **Retribuzione**. Selezionare **Mostra** per visualizzare la retribuzione annuale e l'importo dell'ultimo aumento. Se si lavora in più società, ogni importo annuale viene visualizzato sulla scheda. Per visualizzare la cronologia delle retribuzioni dettagliata, selezionare l'importo della retribuzione annuale per aprire il modulo **Cronologia delle retribuzioni fisse e variabili**. La retribuzione futura non viene visualizzata in questo modulo. Se è presente più di un impiego, è possibile passare da una società all'altra in questo modulo per visualizzare la cronologia delle retribuzioni senza accedere a ciascuna società.

Visualizzare e gestire i documenti con la scheda **Allegati**. È possibile gestire tutti gli allegati **esterni**. Sia le risorse umane che i dipendenti possono aggiungere allegati tramite il self service dipendente o il modulo **Lavoratore**. Gli allegati sono impostati su **Esterno** per impostazione predefinita.

### <a name="additional-information"></a>Informazioni aggiuntive

Questa sezione fornisce i collegamenti ad altre aree self-service dei dipendenti, simili alla sezione **Informazioni professionali personali**.

Registrarsi per ottenere vantaggi tramite il collegamento **Vantaggi**. Per ulteriori informazioni sulla gestione dei vantaggi, vedere [Panoramica dei vantaggi](hr-benefits-management-overview.md)

In **Prestazioni**, è possibile selezionare **Giornali di registrazione prestazioni** per creare voci del giornale di registrazione prestazioni da utilizzare su obiettivi e revisioni delle prestazioni. È possibile selezionare **Invia feedback** per fornire feedback ad altri dipendenti all'interno dell'organizzazione. A seconda delle impostazioni dell'organizzazione, i messaggi e-mail possono essere inviati al destinatario, al mittente e ai manager. È possibile inviare il feedback a tutti i dipendenti all'interno dell'organizzazione. L'invio del feedback non è limitato dalla società.

In **Competenze**, è possibile apportare modifiche a **Corsi**, **Formazione**, **Posizioni di fiducia** ed **Esperienza professionale**. A seconda delle impostazioni dell'organizzazione, gli aggiornamenti delle competenze potrebbero essere soggetti a un processo di approvazione.

È possibile visualizzare i dettagli del lavoro in **Organizzazione**. I dettagli del lavoro includono competenze, certificati e aree di responsabilità per la posizione principale. È anche possibile vedere tutte le attrezzature assegnate all'utente. A seconda delle impostazioni dell'organizzazione, la modifica alle attrezzature assegnate potrebbe essere soggetta a un processo di approvazione.

In **Questionario**, è possibile vedere i questionari completati. È anche possibile visualizzare i questionari a livello di società che non sono stati completati. È possibile scegliere di completare un questionario in qualsiasi momento. L'autore del questionario può determinare il periodo di tempo e il destinatario del questionario.

È possibile configurare i collegamenti definiti dall'utente in **Parametri risorse umane**. Ad esempio, è possibile definire i collegamenti ai rendiconto di retribuzione, alla documentazione di fine anno o a soluzioni esterne. Questi collegamenti vengono visualizzati nella parte inferiore di questa sezione, ma è possibile spostarli utilizzando la personalizzazione.

È inoltre possibile creare schede aggiuntive incorporando Power Apps all'interno dell'area di lavoro self service dipendente. Usare il menu **Impostazioni** per personalizzare la pagina con qualsiasi Power Apps. Nel menu **Impostazioni** è possibile scegliere di aggiungere una Power App, completare i dettagli e inserire l'app. Per impostazione predefinita, Power Apps appare come la prima scheda della sequenza. È possibile modificare l'ordine con la personalizzazione standard.

## <a name="my-team"></a>Team personale

La scheda **Team personale** visualizza le seguenti informazioni per il self service manager. Solo i manager possono accedere alla scheda **Team personale**.

### <a name="personnel-actions"></a>Azioni dipendente

Le azioni del personale vengono visualizzate in base alle opzioni di configurazione **Parametri condivisi risorse umane** e **Parametri risorse umane**. Quando abilitate per **Lavoratori**, le azioni del personale consentono nuove opzioni di menu, tra cui:

- **Richiedi nuovo dipendente**
- **Richiedi nuovo terzista**
- **Richiedi riassegnazione lavoratore**
- **Richiedi terminazione rapporto**
- **Richiesta di modifica della retribuzione**

È possibile configurare queste opzioni per utilizzare un flusso di lavoro di revisione e approvazione facoltativo.

L'abilitazione di **Azioni della posizione** attiva le seguenti opzioni:

- **Richiedi nuova posizione**
- **Richiedi modifica ai dettagli sulla posizione**

È anche possibile configurare queste opzioni per utilizzare un flusso di lavoro di revisione e approvazione facoltativo.

### <a name="summary"></a>Riepilogo

Le informazioni nella sezione **Sommario** dipendono dalle opzioni selezionate da HR in **Parametri risorse umane**. Nella scheda **Self service manager** della pagina **Parametri risorse umane**, è possibile configurare le opzioni per visualizzare i record in scadenza e le posizioni aperte. L'abilitazione di queste opzioni determina ciò che i manager possono vedere nella sezione **Sommario**.

È possibile configurare i seguenti riquadri per i manager:

- **Certificati in scadenza per il team personale**
- **Numero di identificazione in scadenza per il team personale**
- **Periodi di prova in scadenza per il team personale**
- **Screening in scadenza per il team personale**
- **Test in scadenza per il team personale**
- **Posizioni aperte per diretti subalterni e/o subalterni estesi**
- **Richieste di permesso in sospeso per il team**
- **Valutazione competenze team**
- **Analisi lacuna competenze**
- **Giornali di registrazione prestazioni team**
- **Obiettivi prestazioni team**
- **Revisioni prestazioni team**
- **Lavoratori prossimi a fine rapporto di impiego**

È possibile configurare le seguenti opzioni per permettere ai manager di apportare modifiche o aggiungere richieste di permesso per conto dei diretti subalterni:

- Attestati
- Corsi
- Articoli prestito
- Competenze
- Richieste di congedo e assenza

### <a name="my-team-information"></a>Informazioni personali sul team

Le informazioni del team consentono ai manager di visualizzare e aggiornare i diretti subalterni e i subalterni estesi. Per accedere ai subalterni estesi, selezionare il dipendente con i subalterni, quindi scegliere **Visualizza team** sulla scheda. Le stesse opzioni si applicano ai subalterni estesi come ai diretti subalterni. 

#### <a name="summary-tab"></a>Scheda Riepilogo

La scheda **Riepilogo** fornisce una visualizzazione rapida dei diretti subalterni. Se anche i diretti subalterni hanno lavoratori che riportano loro, la scheda mostra il numero di diretti subalterni nella sezione superiore, insieme a un pulsante **Visualizza team**. Le opzioni di ogni scheda si applicano al dipendente selezionato. Ad esempio, se si desidera inserire una richiesta di congedo per conto di un dipendente, selezionare il dipendente e quindi scegliere **Richiedi permesso** sopra le schede. 

Se si seleziona il pulsante **Dettagli** dopo aver selezionato un dipendente, vengono visualizzate le seguenti opzioni:

- **Attestati**
- **Retribuzione**
- **Corsi**
- **Revisioni**
- **Tempo libero**
- **Articoli prestati**
- **Obiettivi prestazioni**
- **Corsi registrati**
- **Competenze**
- **Invia riscontro**

A seconda delle impostazioni dell'organizzazione, è possibile apportare modifiche o solo visualizzare.

#### <a name="position-tab"></a>Scheda Posizione

La scheda **Posizioni** fornisce una vista di riepilogo dei dipendenti nella posizione principale. Vengono visualizzati il nome, il titolo e il reparto nell'area dell'intestazione di ogni scheda. Questa scheda include:

- **Data di anzianità** - Visualizzato dalla sezione di riepilogo del modulo lavoratore
- **Anni di servizio** - Calcolato in base alla data di inizio dell'impiego del dipendente
- **Numero di posizioni precedenti** - In base alla cronologia delle posizioni, selezionando questo numero si apre la vista dettagliata di tutte le posizioni precedentemente avute
- **Data di nascita** - Il mese e il giorno della data di nascita del dipendente

È possibile visualizzare i dati della posizione sia per i diretti subalterni che per i subalterni estesi.

#### <a name="compensation-tab"></a>Scheda Retribuzione

La scheda **Retribuzione** visualizza lo stipendio annuale del dipendente. Un identificativo dell'azienda viene visualizzato sotto l'importo della retribuzione. Se un dipendente ha più di un impiego e viene pagato da più persone giuridiche, il dipendente avrà più piani di retribuzione. Per visualizzare tutti i piani di retribuzione tra persone giuridiche senza cambiare società, è necessario abilitare la retribuzione interaziendale in **Human Resources > Parametri condivisi > Accesso avanzato > Abilita retribuzione interaziendale**.

Per visualizzare la cronologia delle retribuzioni, selezionare l'importo della retribuzione per aprire il modulo **Dettagli**. Vengono visualizzati solo i record di retribuzione fissa e variabile correnti e storici nel modulo **Retribuzione**. Se un dipendente ha più di un impiego, è possibile passare da una società all'altra per visualizzare la cronologia delle retribuzioni in ciascuna società o abilitare la retribuzione interaziendale nei parametri condivisi di Human Resources per visualizzare tutti i piani retributivi.

È possibile visualizzare la retribuzione sia per i diretti subalterni che per i subalterni estesi.

#### <a name="leave-and-absence-tab"></a>Scheda Congedo e assenza

La scheda **Congedo e assenza** visualizza i saldi principali per i dipendenti con attività. Per utilizzare o visualizzare un elenco completo delle attività, selezionare **Dettagli** e quindi selezionare **Permesso**. Nel modulo **Permesso**, è possibile visualizzare i saldi, le richieste, i permessi approvati e i saldi previsti per aiutare i dipendenti a gestire meglio il tempo. A seconda delle impostazioni dell'organizzazione, è anche possibile richiedere il permesso per i diretti subalterni e i subalterni estesi.

#### <a name="performance-goals-tab"></a>Scheda Obiettivi prestazioni

La scheda **Obiettivi prestazioni** riepiloga gli obiettivi delle prestazioni in base allo stato. Selezionare un numero per uno stato o selezionare gli obiettivi delle prestazioni dai **Dettagli** per vedere tutti gli obiettivi di un dipendente. I manager e i dipendenti possono aggiornare gli obiettivi secondo le necessità durante la durata dell'obiettivo.

I manager possono vedere tutti gli obiettivi del team selezionando il riquadro **Obiettivi prestazioni team** nella sezione **Riepilogo** di **Team personale**.

#### <a name="reviews-tab"></a>Scheda Revisioni

La scheda **Revisioni** riepiloga le revisioni che il dipendente ha in ogni stato: **In corso**, **Pronto per la revisione** e **Revisione finale**. Per accedere alla revisione di un dipendente, selezionare il pulsante **Dettagli** quindi selezionare le revisione su cui collaborare. In base a dove si trova una revisione nel processo del flusso di lavoro, è possibile vedere se la revisione è disponibile per l'aggiornamento. 

È possibile vedere tutte le revisioni del team selezionando il riquadro **Revisioni prestazioni team** nella sezione **Riepilogo** di **Team personale**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]