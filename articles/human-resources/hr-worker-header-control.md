---
title: Controllo intestazione lavoratore
description: Questo articolo fornisce informazioni sul controllo dell'intestazione personalizzabile in Self-service dipendente, nell'hub Persone e nella pagina Lavoratore in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445948"
---
# <a name="worker-header-control"></a>Controllo intestazione lavoratore

Microsoft Dynamics 365 Human Resources fornisce un controllo dell'intestazione personalizzabile in **Self service dei dipendenti**, nell'hub **Persone** e sulla pagina **Lavoratore** semplificata. L'intestazione contiene informazioni chiave sul lavoratore e anche azioni con un clic come inviare e-mail, chiamare o inviare messaggi. L'intestazione può essere modificata rimuovendo i campi o aggiungendo campi, inclusi i campi personalizzati, per mostrare informazioni aggiuntive. Per utilizzare il nuovo controllo dell'intestazione, vai a **Gestione funzionalità** e abilita la funzionalità **Controllo intestazione lavoratore**.

## <a name="personalization"></a>Personalizzazione

Uno dei principali vantaggi del controllo dell'intestazione lavoratore è la possibilità di personalizzare le informazioni visualizzate nell'intestazione.

In alto a destra dell'intestazione c'è un gruppo di tre campi che mostrano dati diversi, a seconda dello stato del dipendente. Questo gruppo di campi è denominato porzione In evidenza dell'intestazione. Puoi personalizzare la parte In evidenza dell'intestazione rimuovendo i campi correnti o aggiungendo campi. I campi che possono essere aggiunti alla parte In evidenza nel controllo dell'intestazione sono diversi per **Self service dipendenti**, hub **Persone** e la pagina **Lavoratore**.

## <a name="employee-self-service"></a>Dipendente self-service

L'intestazione del lavoratore sulla pagina **Self service dipendenti** contiene le seguenti informazioni:

- Nome lavoratore
- Numero dipendente
- Titolo posizione
- Reparti
- Tipo di lavoratore
- Persona giuridica dell'impiego
- Anni di servizio
- Subordinato a (responsabile)
- Tipo di posizione

L'intestazione contiene anche un'azione con un clic per modificare le informazioni personali individuali. Seleziona **Modifica dettagli personali** per aprire la pagina **Informazioni personali** in **Self service dipendenti**.

## <a name="people-hub"></a>Hub contatti

L'intestazione del lavoratore nell'hub **Persone** (la pagina **area di lavoro Persone**) contiene le seguenti informazioni:

- Nome lavoratore
- Numero dipendente
- Titolo posizione
- Reparti
- Tipo di lavoratore
- Persona giuridica dell'impiego
- Anni di servizio
- Subordinato a (responsabile)
- Tipo di posizione

L'intestazione contiene anche azioni con un solo clic come inviare e-mail, chiamare o inviare messaggi. Se un utente sta visualizzando le proprie informazioni sulla pagina **area di lavoro Persone**, la sezione dell'azione con un clic singolo include il pulsante **Modifica dettagli personali**. L'utente può selezionare questo pulsante per aprire la pagina **Informazioni personali** in **Self service dipendenti**.

## <a name="streamlined-worker-page"></a>Pagina del lavoratore semplificata

L'intestazione del lavoratore sulla pagina **Lavoratore** semplificata contiene le seguenti informazioni:

- Nome lavoratore
- Numero dipendente
- Titolo posizione
- Reparti
- Tipo di lavoratore
- Persona giuridica dell'impiego

A seconda dello stato del dipendente, i dati nell'intestazione potrebbero cambiare. Ad esempio, se il dipendente ha lasciato l'azienda, il controllo di intestazione contiene un badge **Uscito**, la data di fine del rapporto di lavoro e il motivo della cessazione.

La tabella seguente mostra i dati che appaiono nell'intestazione per i diversi stati dei dipendenti.

| Stato dipendenti | Dati mostrati | Nota |
|-----------------|--------------------|------|
| In sospeso | <ul><li>Name</li><li>Numero dipendente</li><li>Titolo posizione</li><li>Reparto</li><li>Tipo di lavoratore</li><li>Persona giuridica</li><li>Badge in attesa</li><li>Data di inizio</li><li>Subordinato a</li><li>Tipo di posizione</li></ul> | |
| Assunto di recente | <ul><li>Name</li><li>Numero dipendente</li><li>Titolo posizione</li><li>Reparto</li><li>Tipo di lavoratore</li><li>Persona giuridica</li><li>Badge Assunto di recente</li><li>Anni di servizio</li><li>Subordinato a</li><li>Tipo di posizione</li></ul> | Per impostazione predefinita, il badge **Assunto di recente** viene mostrato per i dipendenti che sono stati assunti negli ultimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, immettere un intervallo di tempo nella sezione **Intervallo date assunzioni recenti**. Ad esempio, per visualizzare il badge **Assunto di recente** per i dipendenti assunti negli ultimi 14 giorni, imposta il campo **Periodo** su **14** e il campo **Unità** su **giorni**. |
| Dipendente attivo | <ul><li>Name</li><li>Numero dipendente</li><li>Titolo posizione</li><li>Reparto</li><li>Tipo di lavoratore</li><li>Persona giuridica</li><li>Data di inizio</li><li>Subordinato a</li><li>Tipo di posizione</li></ul> | |
| Uscita | <ul><li>Name</li><li>Numero dipendente</li><li>Titolo posizione</li><li>Reparto</li><li>Tipo di lavoratore</li><li>Persona giuridica</li><li>Badge in uscita</li><li>Anni di servizio</li><li>Subordinato a</li><li>Tipo di posizione</li></ul> | Per impostazione predefinita, il badge **In uscita** viene mostrato per i dipendenti che lasceranno nei prossimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, immettere un intervallo di tempo nella sezione **Intervallo date lavoratori prossimi a fine rapporto di impiego**. Ad esempio, per visualizzare il badge **In uscita** per i dipendenti che lasceranno l'azienda nei prossimi 14 giorni, imposta il campo **Periodo** su **14** e il campo **Unità** su **giorni**. |
| Usciti | <ul><li>Badge Uscito</li><li>Numero dipendente</li><li>Data di fine impiego</li><li>Codice motivo</li></ul> | Per impostazione predefinita, il badge **Uscito** viene mostrato per i dipendenti che hanno lasciato negli ultimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, immettere un intervallo di tempo nella sezione **Intervallo di date lavoratori usciti**. Ad esempio, per visualizzare il badge **Uscito** per i dipendenti che hanno lasciato l'azienda negli ultimi 14 giorni, imposta il campo **Periodo** su **14** e il campo **Unità** su **giorni**. |
