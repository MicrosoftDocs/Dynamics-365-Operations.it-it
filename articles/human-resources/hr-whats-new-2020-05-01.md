---
title: Novità o modifiche in Dynamics 365 Human Resources (1 maggio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 1 maggio 2020.
author: Darinkramer
manager: AnnBe
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 074c678d9d8294aabf4e78b2a6ee0fa53efbaf23
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419211"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (1 maggio 2020)

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.3196. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Nuove entità Gestione delle prestazioni disponibili nel framework di gestione dei dati (DMF)

Ora sono disponibili le seguenti entità. Se queste entità non sono elencate nell'elenco delle entità, usare l'opzione **Aggiorna entità** in **Parametri framework > Impostazioni entità > Aggiorna elenco entità**.

- **Competenza di discussione**
- **Obiettivi di discussione**
- **Misura di discussione**
- **Argomento di discussione**
- **Giornale di registrazione prestazioni**
- **Misurazione**
- **Misura obiettivo**

Inoltre, **Punteggio totale** e **Punteggio medio** sono stati aggiunti all'entità **Discussione**.

## <a name="increase-length-of-leave-request-comments-275641"></a>Aumentare la lunghezza dei commenti nelle richieste di congedo (275641)

I commenti nelle richieste di congedo consentono ora l'uso di più di 100 caratteri.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>I commenti finali nelle revisioni non vengono visualizzati quando il responsabile o il dipendente ha effettuato l'accesso a un'altra società (431688)

Tutti i commenti verranno ora visualizzati alla visualizzazione delle revisioni.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>I collegamenti definiti dall'utente non sono supportati nel nuovo modulo Lavoratore (390374)

I collegamenti definiti dall'utente sono ora abilitati nel modulo **Lavoratore** semplificato.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity provoca l'arresto anomalo dell'API OData (439476)

Questa modifica corregge l'arresto anomalo dell'API. Un nome duplicato ha generato questo errore.

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

## <a name="known-issues"></a>Problemi noti

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