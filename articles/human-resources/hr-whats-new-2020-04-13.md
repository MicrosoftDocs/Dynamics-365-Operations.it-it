---
title: Novità o modifiche in Dynamics 365 Human Resources (13 aprile 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 13 aprile 2020.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 729490e7516d8c7aef7232c9f5c227d3207dcd68
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712426"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (13 aprile 2020)

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3136. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="new-production-release-cadence"></a>Nuova cadenza di rilascio di produzione

A partire da questo rilascio settimanale, la cadenza di rilascio di Human Resources passa da un aggiornamento settimanale a un aggiornamento bisettimanale. Per garantire l'allineamento con procedure di distribuzione sicure e mantenere elevati gli standard di stabilità e affidabilità nel servizio, il processo di distribuzione degli aggiornamenti del servizio in tutte le regioni è ora un'implementazione ogni due settimane. Ulteriori test e controlli sono applicati per verificare la corretta implementazione in ogni fase del processo. Per ulteriori informazioni sulla cadenza di rilascio, consultare [Processo di aggiornamento](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>Il campo della precisione di arrotondamento non è modificabile dopo aver specificato un tipo di arrotondamento (435616)

Con questa modifica, il campo **Precisione di arrotondamento** è ora disponibile dopo aver aggiornato il campo **Tipo di arrotondamento**.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>Impossibile modificare la data di fine iscrizione congedo quando il piano di congedo non ha periodi di attribuzione per competenza (413628)

Ora è possibile modificare la data di fine iscrizione senza ricevere l'errore indicante che il campo Base data di accumulo deve essere compilato.

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a>L'entità di impiego non si sincronizza con Common Data Service (430834)

Questa modifica corregge un problema a causa del quale i dati sull'impiego non erano sincronizzati in Common Data Service dopo aver aggiunto le dimensioni finanziarie. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Rimuovere l'associazione di più elementi padre per l'entità Intervallo orario del calendario di lavoro (431775)

Questa modifica rimuove l'associazione di più elementi padre per l'entità **Intervallo orario del calendario di lavoro**.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>Il filtro con la funzione CAST non funziona sull'entità Assegnazione lavoratore posizione della chiamata OData (431699)

Questo aggiornamento include una modifica per consentire il filtro con la funzione CAST in OData per l'entità **Assegnazione lavoratore posizione**.

## <a name="in-preview"></a>In anteprima

## <a name="leave-suspension"></a>Sospensione del congedo

È possibile sospendere le ferie e le assenze nelle risorse umane per un dipendente. La sospensione del congedo e interrompe la maturazione delle ferie per i tipi di congedi selezionati. Se la sospensione si verifica dopo l'elaborazione della maturazione, la sospensione delle ferie crea una rettifica proporzionale del saldo delle ferie del dipendente. Per ulteriori informazioni, vedere [Sospendere il congedo](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Regole di riporto

È possibile specificare un tipo di congedo riporto per i saldi del riporto in cui vengono trasferiti le rettifiche di riporto. Ad esempio, se un dipendente riporta 10 giorni, è possibile scegliere un tipo di congedo diverso per quei 10 giorni. Per ulteriori informazioni, vedere [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Problemi noti

## <a name="employment-details-entity"></a>Entità Dettagli impiego

L'entità **Dettagli impiego** è stata aggiornata con i seguenti campi:

- **PayFrequency**
- **ID categoria impiego**
- **Tipo di impiego**
- **ID EmploymentType**
- **Stato impiego benefit**

I dati di configurazione per questi campi si basano sulla gestione dei benefit abilitata nell'area di lavoro **Gestione funzionalità**. Non popolare o aggiornare questi campi nell'entità **Dettagli impiego** perché vengono restituiti errori durante l'importazione.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>L'anteprima di SharePoint non funziona in alcuni ambienti

Se l'anteprima del documento per i documenti memorizzati in SharePoint non funziona, provare la seguente procedura:

1. Verificare che l'account utente amministratore abbia un'e-mail associata al record utente. È possibile visualizzare tali informazioni nella pagina **Utente**. Se l'e-mail non è impostata, è necessario aggiungere l'e-mail e il provider con il componente aggiuntivo OData Excel. Per impostazione predefinita, l'indirizzo e-mail non è presente nella progettazione di Excel. È necessario modificare la progettazione di Excel, aggiungere tutti i campi, applicare e aggiornare. Dopo aver completato questi passaggi, è possibile aggiornare l'account amministratore.

2. Una volta che l'account amministratore ha un account e-mail associato, accedere a Human Resources con le credenziali di amministratore.

3. Accedere a un allegato in SharePoint per avviare l'anteprima del documento.

4. Accedere con un altro account utente che ha accesso agli allegati e verificare che l'anteprima funzioni come previsto.

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)