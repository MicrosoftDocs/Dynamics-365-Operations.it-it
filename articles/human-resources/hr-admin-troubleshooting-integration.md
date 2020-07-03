---
title: Domande frequenti sull'integrazione con Finance
description: In questo articolo vengono descritti i dati sincronizzati durante l'integrazione di Human Resources con Finance.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0a3389d6ce5f1985f7515e777a2bafae4eae5f0c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431109"
---
# <a name="integration-with-finance-faq"></a>Domande frequenti sull'integrazione con Finance

In questo argomento vengono fornite le risposte a domande comuni relative ai dati che vengono sincronizzati durante l'integrazione di Dynamics 365 Human Resources con Dynamics 365 Finance.

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Vengono sincronizzati tutti i dati o solo alcune entità di dati?

Viene sincronizzato un sottoinsieme di dati. Per un elenco di tutte le entità, vedere [Integrazione con Dynamics 365 Finance](hr-admin-integration-finance.md).

## <a name="why-dont-i-see-any-data-synced-to-common-data-service"></a>Perché non vedo i dati sincronizzati in Common Data Service?

Per impostazione predefinita, l'integrazione Common Data Service è disattivata nei nuovi ambienti che non includono i dati dimostrativi forniti. Per impostazione predefinita, è abilitata nei nuovi ambienti che contengono i dati dimostrativi e la sincronizzazione dei dati inizia quando l'ambiente viene sottoposto al provisioning. Una volta che l'ambiente è pronto per sincronizzare i dati è possibile attivare l'integrazione. Per ulteriori informazioni, vedere [Configurare l'integrazione di Common Data Service](hr-admin-integration-common-data-service.md).

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Posso creare un nuovo mapping senza utilizzare modelli?

I modelli rappresentano il punto di inizio. È possibile creare un modello personalizzato, ma un modello è sempre necessario durante la creazione di un progetto di integrazione. Per ulteriori informazioni sull'integratore di dati, i modelli e i progetti, vedere [Integrare i dati in Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>È possibile mappare le dimensioni finanziarie per il trasferimento tra Human Resources e Finance?

Le dimensioni finanziarie non sono attualmente incluse in Common Data Service e di conseguenza non fanno parte del modello predefinito. Questa entità è pianificata, ma al momento non è disponibile alcuna data di rilascio.

Per i dati in Finance ma non presenti in Human Resources, collegare due sistemi utilizzando **Configura collegamenti** in Human Resources.

![Mappa dimensioni finanziarie](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>Talvolta i dipendenti importati sono visualizzati in Lavoratori inattivi in Finance. Perché?

Questo errore può verificarsi se i dipendenti non hanno un record di dettagli di impiego attivo in Human Resources. Per risolvere questo problema, accedere a **Gestione personale \> Dipendenti \> Storico esperienze lavorative \> Gestione date** e verificare l'esistenza di un record di dettagli di impiego attivo.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Se si sceglie di mappare solo un sottoinsieme di campi, le modifiche apportate ai campi non mappati avvieranno una sincronizzazione?

La sincronizzazione dei dati segue la programmazione dell'esecuzione. L'integrazione selezionerà un record se un campo qualsiasi nel record cambia indipendentemente dall'inclusione del campo nel mapping di integrazione.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Come è possibile inviare solo modifiche di lavoratori attivi di lavoro e non i record con rapporto chiuso?

Con "Query avanzate", è possibile filtrare e rimodellare i dati di origine prima di inviarli alla destinazione.

![Query avanzata dei lavoratori attivi](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>È possibile specificare i campi da inviare a Finance per una specifica entità ?

I campi possono essere aggiunti o rimossi dall'attività di integrazione. Non tutti i campi dati esistenti nell'entità di Common Data Service verranno popolati a partire da Human Resources.
Ulteriori dati possono essere popolati via Power Apps.

![Aggiungere o rimuovere campi a e da un'attività di integrazione](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Dopo l'impostazione dell'integrazione come processo batch, Human Resources si è disconnesso dal sistema di destinazione. Come è possibile inviare lo stesso set di modifiche al sistema di destinazione?

Non è necessaria alcuna impostazione speciale per la gestione delle eccezioni. L'integratore di dati individuerà e segnalerà automaticamente gli errori che si verificano all'origine e alla destinazione e consentirà tentativi manuali. Tuttavia, non consente la rettifica manuale dei dati. Se gli aggiornamenti dei dati sono necessari, devono avvenire all'origine o alla destinazione.

## <a name="can-i-set-up-bi-directional-integration"></a>È possibile configurare l'integrazione bidirezionale?

No, l'integrazione è attualmente unidirezionale (da Human Resources a Finance and Operations). Tuttavia, è disponibile un modello predefinito per l'invio di dati da Human Resources a Finance.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Posso consentire l'eliminazione dei record nell'integrazione?

No, l'integratore di dati non acquisirà i record eliminati per il trasferimento di dati. Sono attualmente inclusi solo la creazione di dati e gli aggiornamenti (UPSERT).

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>È possibile ripetere l'esecuzione non riuscita? Se sì, invierà un file completo o solo le modifiche?

La prima esecuzione dell'integratore di dati è sempre un'esecuzione completa. Le esecuzioni successive sono basate sul rilevamento delle modifiche. In caso di esecuzione con errori, estrae i record nell'ambito dell'esecuzione e invia le modifiche più recenti da Common Data Service.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>Quando si salva il progetto, viene visualizzato l'errore: "Questo progetto contiene errori di mapping". Cosa fare?

Verificare la configurazione delle chiavi di integrazione, apportare le modifiche necessarie alla configurazione, quindi aggiornare le entità nel progetto.

Quando si utilizza il modello predefinito, le chiavi di integrazione saranno importate automaticamente. Questo problema può verificarsi quando nuove attività vengono aggiunte al modello esistente.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>In caso di un numero N di persone giuridiche in cui i lavoratori hanno impieghi, è necessario creare un mapping per ognuna?

Sì, per ogni persona giuridica in Finance, è necessario avere un progetto di integrazione distinto nell'integrazione dei dati.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>È possibile trasferire i dati che non fanno parte del modello predefinito fornito da Microsoft?

Sì, dei campi possono essere aggiunti a o rimossi dal modello esistente. Il modello può essere modificato affinché includa ulteriori dati da altre entità di Common Data Service. L'entità deve essere in Common Data Service affinché venga inclusa nel modello. 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Dopo la creazione di nuovi ambienti Finance e Human Resources, viene visualizzato l'errore "Il valore dati viola i vincoli di integrità". Perché?

I motivi di questo errore possono includere:

- Il trasferimento di dati ha generato l'estrazione di record duplicati all'origine (Common Data Service).

- Il trasferimento di dati ha valori nulli per i campi necessari in Finance and Operations. Verificare i dati in Common Data Service e soddisfare i requisiti di Finance and Operations.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Se sono presenti errori di esecuzione e l'ID dipendente non è stato sincronizzato, come è possibile trovare lo storico processi che include il record dipendente con l'errore?

L'integratore di dati creerà più progetti in Finance. La relazione tra l'attività dell'integratore di dati e il progetto Finance è uno a uno.

Identificare il tempo di esecuzione nello storico esecuzione dell'integratore di dati e cercare il progetto indice -1 in Finance. Se il numero di attività è 9 nell'integratore di dati, l'indice in Finance è 8.

1. Acquisire l'indice delle attività dall'integratore di dati (in questo esempio è "9 ").

    ![Acquisire l'indice di attività dall'integratore di dati](media/CaptureTaskIndex.png)

2. Tenere traccia del tempo di esecuzione del progetto.

    ![Tenere traccia del tempo di esecuzione del progetto](media/CaptureTimeOfExecution.png)

3. In Finance, identificare l'indice - 1. In questo esempio, il progetto con il suffisso "8 "e il tempo di esecuzione del progetto indice "0" corrisponde al tempo di esecuzione nel passaggio 2.

    ![Identificare l'indice](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>Dopo l'integrazione di Human Resources con Finance, i dati di Human Resources non sono visibili in Finance. Cosa fare?

L'integrazione con Finance è un processo in due fasi. La prima consiste nel verificare che i dati di Human Resources vengano aggiornati e siano disponibili in Common Data Service. Questa fase è una sincronizzazione quasi in tempo reale e può essere verificata in Power Apps esaminando i dati nelle entità di dati.

![Dati in Common Data Service](media/DataInCDS.png)

Se i dati non sono visualizzati come previsto in Common Data Service, verificare che l'entità sia supportata nell'integrazione. Per includere ulteriori dati in Common Data Service, sarà necessaria una modifica lato Microsoft.

Se l'entità è supportata e i dati sono disponibili in Common Data Service, verificare che il mapping sia corretto nell'integratore di dati. Se il mapping dell'integratore sembra corretto, verificare che i processi di gestione dei dati siano stati eseguiti correttamente. È possibile che si verifichino degli errori durante l'esecuzione dei processi batch. Per ulteriori informazioni sulla gestione dei dati, vedere [Gestione dei dati](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>Gli indirizzi dei dipendenti risultano non corretti dopo l'importazione degli stessi in Finance. Cosa fare?

La sequenza numerica di **ID ubicazione** utilizza lo stesso modello sia in Human Resources, sia in Finance. La sequenza numerica deve essere univoca su entrambi i lati di modo che non vi siano conflitti durante l'integrazione di dati da Common Data Service in Finance and Operations.

Durante l'implementazione di Human Resources, verificare che le sequenze numeriche non siano le stesse in Human Resources e in Finance. Verificare che tutte le sequenze numeriche non siano identiche quando i dati possono essere gestiti in entrambi i sistemi.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Durante la creazione del set di connessioni, non è possibile vedere la connessione nell'elenco a discesa Connessione. Cosa fare?

Quando si creano delle connessioni, verificare di scegliere Dynamics 365 Finance e Common Data Service.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Durante la sincronizzazione degli impieghi, viene visualizzato l'errore "CompanyInfo_FK inesistente"o "Valore 31/12/2154 23:59:59 non trovato nel campo Data di fine impiego della tabella correlata Impiego". Cosa fare?

Assicurarsi di eseguire il mapping alle persone giuridiche corrette. La sincronizzazione delle persone giuridiche non fa parte del modello predefinito, pertanto è previsto che ogni persona giuridica presente in Human Resources e Common Data Service sia anche presente in Finance.
Inoltre, verificare di selezionare le persone giuridiche corrette per il set di connessioni associato.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>Dopo la configurazione di un progetto, il mapping dei campi per Finance sembra essere vuoto. Cosa fare?

Aggiornare le entità di dati in Finance selezionando **Gestione dati \> Parametri framework \> Impostazioni entità \> Aggiorna l'elenco di entità.** Questa operazione dovrebbe durare un paio di minuti, dopodiché i mapping dovrebbero essere visibili. Questo problema si verifica quando si creano nuovi progetti.

![Mapping dei campi mancante](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Risorse aggiuntive

- Integratore di dati (ID): 

  - [Integrazione dei dati in Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator)

  - [Gestione e risoluzione degli errori nell'integratore di dati](https://docs.microsoft.com/powerapps/administrator/data-integrator-error-management)

  - [Rispondere alle richieste DSR per log generati dal sistema in Power Apps, Microsoft Power Automate e Common Data Service](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Gestione dei dati:

  - [Gestione dei dati](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json)
