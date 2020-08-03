---
title: Novità o modifiche in Dynamics 365 Human Resources (10 marzo 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 03/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1843095c41428d377341154c9f2140085831e770
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555258"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (10 marzo 2020)

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.2985. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Impossibile accedere al report di analisi di lacuna competenze (394460)

Questo report non è supportato in Dynamics 365 Human Resources. La voce di menu per stampare il report SSRS è stata rimossa.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Messaggio errato durante l'accesso alla pagina Guida introduttiva (417950)

Con questa modifica, la sicurezza nasconde questa voce di menu se non si ha accesso al modulo.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Manutenzione semplificata delle attività per i dipendenti (380538)

Il modulo di manutenzione delle attività del lavoratore elenca tutte le attività per un dipendente in inserimento, offboarding, transizioni e processi aziendali. È possibile eliminare, riassegnare o aggiornare lo stato delle attività.

Esempio: Benjamin Martin è un amministratore dei benefit. Durante l'inserimento del dipendente, vengono create le attività per Benjamin per rivedere la selezione dei benefit del nuovo dipendente. Benjamin ha attività passate che ha completato e attività future che deve completare. Benjamin decide di lasciare l'azienda, quindi le attività devono essere riassegnate o rimosse. Il modulo di manutenzione dell'attività (nel riquadro azioni del modulo **Lavoratore**) consente di riassegnare o rimuovere tutte le attività di Benjamin.  

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>La soluzione Common Data Service è ora disponibile con le seguenti modifiche:

| descrizione | Resto |
| --- | --- |
| Modifiche all'entità **Posizione lavorativa** | <ul><li>Aggiunta di **Paese di retribuzione**</li>|
| Entità **Dimensioni posizione lavorativa** aggiunta | <ul><li>Aggiunta di **Dimensioni finanziarie**</li>
| Modifiche all'entità **Lavoratore** | <ul><li>Aggiunta di **Sequenza nome**</li><li>Aggiunta di **Lavora da casa**</li><li>Aggiunta di **Lingua**</li><li>Aggiunta di **Data di anzianità**</li><li>Aggiunta di **Data di ricorrenza annuale**</li><li>Aggiunta di **Data di assunzione originale**</li></ul> |
| Modifiche all'entità **Impiego** | <ul><li>Aggiunta di **Dimensioni finanziarie**</li><li>Aggiunta di **Motivo fine rapporto**</li><li>**Data di transizione** rinominata in **Data fine rapporto**</li><li>Aggiunta di **Date periodo di prova**</li></ul> |
| Modifiche all'entità **Indirizzo lavoratore** | <ul><li>Aggiunta di **Nome della via**</li><li>**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento</li></ul> |
| Nuove entità di impostazione della retribuzione variabile | <ul><li>**Tipo di piano di retribuzione variabile**</li><li>**Piano di retribuzione variabile**</li><li>**Regole distribuzione incentivi**</li><li>**Livello del piano di retribuzione variabile**</li></ul> |
| Nuova entità **Impiego calendario lavoratore** | <ul><li>Aggiunta di **Entità calendario lavoro**</li></ul> |
| Nuova entità **Dettagli posizione di retribuzione** | <ul><li>Aggiunta di **Dettagli posizione di retribuzione**</li></ul> |
| Nuova entità **Titolo** | <ul><li>**Titolo** è stato aggiunto</li></ul> La nuova entità **Titolo** è inclusa in Common Data Service ma non è referenziata dalle entità **Posizione lavorativa** o **Lavoro** in questo momento. |

> [!NOTE]
> Le dimensioni finanziarie per le posizioni e per l'occupazione forniscono l'integrazione in una direzione per gli aggiornamenti da Human Resources a Common Data Service. Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Common Data Service a Human Resources.

Nelle prossime settimane, questi cambiamenti di entità saranno disponibili in tutti gli ambienti. Per installare manualmente l'ultima soluzione Common Data Service per Human Resources:

1.  Accedere all'[Interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selezionare **Ambienti**.

3.  Trovare l'ambiente da aggiornare. L'ambiente deve corrispondere al **nome dell'ambiente** nella sezione **informazioni Common Data Service** del modulo **Informazioni su** in Human Resources.

4.  Selezionare l'ambiente per visualizzare i dettagli dell'ambiente.

5.  Selezionare **Gestisci soluzioni** nella barra di azione superiore. Una nuova finestra del browser viene visualizzata con l'**interfaccia di amministrazione di Dynamics 365** nel contesto dell'ambiente.

6.  Nell'elenco **Soluzione** selezionare **Ancora Dynamics 365 Human Resources**.

7.  Selezionare **Aggiorna** per applicare l'ultima soluzione.

## <a name="in-preview"></a>In anteprima

Le seguenti funzionalità di anteprima sono disponibili a partire dal 3 febbraio 2020:

- **Funzionalità di anteprima di Congedi e assenza** - Per ulteriori informazioni, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funzionalità di anteprima di Gestione benefit** - Per ulteriori informazioni, inclusi problemi noti, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Presto disponibili

### <a name="platform-update-33"></a>Update 33 della piattaforma

- App a pagina intera (anteprima): questa funzione di anteprima, che richiede di abilitare la funzione Viste salvate, consente a Power Apps e alle app di terze parti di essere aggiunte come esperienze a pagina intera tramite il dashboard.

- Viste salvate (anteprima): questa funzione di anteprima abilita le viste salvate, il che rappresenta un miglioramento significativo del sottosistema di personalizzazione. Questa funzione consente agli utenti di avere più set di personalizzazioni denominate per pagina. È inoltre possibile pubblicare le visualizzazioni nei ruoli di sicurezza.

- Esperienza di filtro "uno di" ottimizzata: questa funzionalità consente un'esperienza di filtro "uno di" ottimizzata che semplifica l'inserimento di più valori di filtro, un meccanismo più semplice per rimuovere singolarmente o tutti i valori di filtro e un sistema più compatto e intuitivo di visualizzazione dei valori del filtro.

- Campi consigliati: gli utenti devono spesso aggiungere campi a una griglia o a una pagina. Questo può essere difficile con così tanti campi disponibili. Invece di dover cercare in un ampio elenco, questa funzione consente al sistema di far emergere un set di campi consigliati in base a ciò che gli altri utenti aggiungono più spesso in scenari simili.

- Azioni predefinite permanenti nelle griglie: questa funzione garantisce che l'azione predefinita in una griglia sia collegata a una colonna specifica in una griglia, indipendentemente dal fatto che tale colonna venga spostata o nascosta.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)