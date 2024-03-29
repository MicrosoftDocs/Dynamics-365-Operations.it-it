---
title: Novità o modifiche in Dynamics 365 Human Resources (19 marzo 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 19 marzo 2020.
author: andreabichsel
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4f88a3a83794cc46f670143bdb97c9624cff8dd0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694755"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (19 marzo 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3014. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Lifecycle Services (LCS) per riferimento.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>I limiti di ambiente di Human Resources sono ora basati sulla licenza aggiornata (394595)

Il limite del numero di ambienti per progetto in Lifecycle Services (LCS) è cambiato. Il limite precedente era di due ambienti. Il limite del numero di ambienti di produzione e sandbox che è possibile creare per le risorse umane in LCS è ora basato sulla licenza aggiornata. Ora è possible creare tutti gli ambienti necessari per ogni progetto LCS, a seconda del numero di licenze acquistate. La nuova licenza, aggiornata il 1° febbraio 2020, consente ai clienti di acquistare ambienti aggiuntivi. Per ulteriori informazioni sui requisiti di licenza per ambienti aggiuntivi, consultare [Guida alle licenze di Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>Fornire la visualizzazione interaziendale dei dati sulle retribuzioni per dipendenti e dirigenti (403904)

Attivare questa funzionalità nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni sulle funzionalità di anteprima, vedere [Attivare o disattivare le funzionalità in anteprima](hr-admin-manage-features.md#enable-or-disable-preview-features).

Quando si abilita questa funzione, i manager possono vedere la retribuzione dei diretti subalterni e dei subalterni estesi senza dover accedere all'azienda di impiego. La cronologia completa delle retribuzioni è disponibile per qualsiasi società a cui il manager può accedere. Per ulteriori informazioni, vedere [Panoramica di Self-service dipendenti e Responsabile self-service](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Abilitare funzionalità di unione della rubrica globale (427189)

Ora è possible unire le voci duplicate della rubrica selezionando i record duplicati e scegliendo **Unisci** dalla pagina **Rubrica globale**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>Impossibile regolare il saldo dei congedi ferie per un piano senza ratei creato con la funzione Tipo di congedo multiplo attivata (419635)

Ora è possibile regolare i saldi per i piani di congedo creati con la funzione di anteprima **Tipo di congedo multiplo** abilitata in Gestione funzionalità.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Il campo della posizione primaria in WorkerPositionAssignmentEntity quando un dipendente conclude il rapporto di lavoro (420774)

Per i dipendenti con un rapporto di lavoro concluso, la posizione primaria che era attiva al momento del licenziamento è visualizzata nell'entità. Per le integrazioni, non verrà più creato un record duplicato per l'assegnazione della posizione di lavoro del dipendente. 

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>La soluzione Dataverse è ora disponibile con le seguenti modifiche:

| Descrizione | Resto |
| --- | --- |
| Modifiche all'entità **Posizione lavorativa** | <ul><li>Aggiunta di **Paese di retribuzione**</li>|
| Entità **Dimensioni posizione lavorativa** aggiunta | <ul><li>Aggiunta di **Dimensioni finanziarie**</li>
| Modifiche all'entità **Lavoratore** | <ul><li>Aggiunta di **Sequenza nome**</li><li>Aggiunta di **Lavora da casa**</li><li>Aggiunta di **Lingua**</li><li>Aggiunta di **Data di anzianità**</li><li>Aggiunta di **Data di ricorrenza annuale**</li><li>Aggiunta di **Data di assunzione originale**</li></ul> |
| Modifiche all'entità **Impiego** | <ul><li>Aggiunta di **Dimensioni finanziarie**</li><li>Aggiunta di **Motivo fine rapporto**</li><li>**Data di transizione** rinominata in **Data fine rapporto**</li><li>Aggiunta di **Date periodo di prova**</li></ul> |
| Modifiche all'entità **Indirizzo lavoratore** | <ul><li>Aggiunta di **Nome della via**</li><li>**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento</li></ul> |
| Nuove entità di impostazione della retribuzione variabile | <ul><li>**Tipo di piano di retribuzione variabile**</li><li>**Piano di retribuzione variabile**</li><li>**Regole distribuzione incentivi**</li><li>**Livello del piano di retribuzione variabile**</li></ul> |
| Nuova entità **Impiego calendario lavoratore** | <ul><li>Aggiunta di **Entità calendario lavoro**</li></ul> |
| Nuova entità **Dettagli posizione di retribuzione** | <ul><li>Aggiunta di **Dettagli posizione di retribuzione**</li></ul> |
| Nuova entità **Titolo** | <ul><li>**Titolo** è stato aggiunto</li></ul>La nuova entità **Titolo** è inclusa in Dataverse ma non è referenziata dalle entità **Posizione lavorativa** o **Lavoro** in questo momento. |

> [!NOTE]
> Le dimensioni finanziarie per le posizioni e per l'occupazione forniscono l'integrazione in una direzione per gli aggiornamenti da Human Resources a Dataverse. Gli aggiornamenti sulle dimensioni finanziarie al momento non vengono sincronizzati da Dataverse a Human Resources.

Nelle prossime settimane, questi cambiamenti di entità saranno disponibili in tutti gli ambienti. Per installare manualmente l'ultima soluzione Dataverse per Human Resources:

1.  Accedere all'[Interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selezionare **Ambienti**.

3.  Trovare l'ambiente da aggiornare. L'ambiente deve corrispondere al **nome dell'ambiente** nella sezione **informazioni Common Data Service** del modulo **Informazioni su** in Human Resources.

4.  Selezionare l'ambiente per visualizzare i dettagli dell'ambiente.

5.  Selezionare **Gestisci soluzioni** nella barra di azione superiore. Una nuova finestra del browser viene visualizzata con l'**interfaccia di amministrazione di Dynamics 365** nel contesto dell'ambiente.

6.  Nell'elenco **Soluzione** selezionare **Ancora Dynamics 365 Human Resources**.

7.  Selezionare **Aggiorna** per applicare l'ultima soluzione.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>L'anteprima di SharePoint non funziona in alcuni ambienti

Se l'anteprima del documento per i documenti memorizzati in SharePoint non funziona, provare la seguente procedura:

1. Verificare che l'account utente amministratore abbia un'e-mail associata al record utente. È possibile visualizzare tali informazioni nella pagina **Utente**. Se l'e-mail non è impostata, è necessario aggiungere l'e-mail e il provider con il componente aggiuntivo OData Excel. Per impostazione predefinita, l'indirizzo e-mail non è presente nella progettazione di Excel. È necessario modificare la progettazione di Excel, aggiungere tutti i campi, applicare e aggiornare. Dopo aver completato questi passaggi, è possibile aggiornare l'account amministratore.

2. Una volta che l'account amministratore ha un account e-mail associato, accedere a Human Resources con le credenziali di amministratore.

3. Accedere a un allegato in SharePoint per avviare l'anteprima del documento.

4. Accedere con un altro account utente che ha accesso agli allegati e verificare che l'anteprima funzioni come previsto.

## <a name="coming-soon"></a>Presto disponibili

### <a name="platform-update-33"></a>Update 33 della piattaforma

- App a pagina intera (anteprima): questa funzione di anteprima, che richiede di abilitare la funzione Viste salvate, consente a Power Apps e alle app di terze parti di essere aggiunte come esperienze a pagina intera tramite il dashboard.

- Viste salvate (anteprima): questa funzione di anteprima abilita le viste salvate, il che rappresenta un miglioramento significativo del sottosistema di personalizzazione. Questa funzione consente agli utenti di avere più set di personalizzazioni denominate per pagina. È inoltre possibile pubblicare le visualizzazioni nei ruoli di sicurezza.

- Esperienza di filtro "uno di" ottimizzata: questa funzionalità consente un'esperienza di filtro "uno di" ottimizzata che semplifica l'inserimento di più valori di filtro, un meccanismo più semplice per rimuovere singolarmente o tutti i valori di filtro e un sistema più compatto e intuitivo di visualizzazione dei valori del filtro.

- Campi consigliati: gli utenti devono spesso aggiungere campi a una griglia o a una pagina. Questo può essere difficile con così tanti campi disponibili. Invece di dover cercare in un ampio elenco, questa funzione consente al sistema di far emergere un set di campi consigliati in base a ciò che gli altri utenti aggiungono più spesso in scenari simili.

- Azioni predefinite permanenti nelle griglie: questa funzione garantisce che l'azione predefinita in una griglia sia collegata a una colonna specifica in una griglia, indipendentemente dal fatto che tale colonna venga spostata o nascosta.

## <a name="new-production-release-cadence"></a>Nuova cadenza di rilascio di produzione

A partire da aprile, la cadenza di rilascio di Human Resources passerà da un aggiornamento settimanale a un aggiornamento bisettimanale. Ciò garantirà l'allineamento con le procedure di implementazione sicure e manterrà elevati gli standard di stabilità e affidabilità del servizio. Stiamo mettendo in atto ulteriori test e controlli per verificare la corretta implementazione in ogni fase del processo. Per ulteriori informazioni sulla cadenza di rilascio, consultare [Processo di aggiornamento](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>In anteprima

Le seguenti funzionalità di anteprima sono disponibili a partire dal 3 febbraio 2020:

- **Funzionalità di anteprima di Congedi e assenza** - Per ulteriori informazioni, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funzionalità di anteprima di Gestione benefit** - Per ulteriori informazioni, inclusi problemi noti, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]