---
title: Panoramica di Gestione benefit
description: Panoramica della funzionalità di anteprima Gestione benefit in Dynamics 365 Human Resources. Offrire opzioni di benefit estese ai propri dipendenti con un'esperienza online di facile utilizzo.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029465"
---
# <a name="benefits-management-overview"></a>Panoramica di Gestione benefit

[!include [banner](includes/preview-feature.md)]

Per rimanere competitivi, è necessario offrire una ricca gamma di benefit per attirare e trattenere i migliori dipendenti. Oltre ai benefit standard come la copertura medica e dentale, è possibile che si voglia offrire anche servizi estesi come assistenza all'adozione, programmi ricreativi e indennità per l'abbigliamento. La funzionalità di anteprima Gestione benefit in Microsoft Dynamics 365 Human Resources fornisce una soluzione flessibile che supporta una vasta gamma di opzioni di benefit. Human Resources include anche un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte.

- I piani di benefit avanzati consentono di creare e gestire piani di benefit unici e supportare tabelle di tassi di benefit complesse e livelli nidificati. È possibile creare facilmente programmi di benefit, pacchetti e regole di iscrizione automatica per un'esperienza per i dipendenti più semplice.

- I programmi di crediti flessibili consentono una ripartizione per supportare il pensionamento e altri eventi della vita.

- Le regole di idoneità estese consentono di rendere disponibili i benefit appropriati per i dipendenti appropriati.

- L'iscrizione online ai benefit fornisce un'esperienza semplice per i dipendenti.

- L'elaborazione di eventi reali qualificati si integra con Dipendente self-service e inoltre supporta eventi reali futuri.

Se si desidera accedere ai dati dimostrativi, sarà necessario ridistribuire l'ambiente sandbox.

È possibile fornire un feedback diretto o segnalare problemi all'indirizzo e-mail: D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Problemi noti di Gestione benefit

### <a name="eligibility-processing"></a>Elaborazione dell'idoneità

Quando si esegue l'idoneità per benefit che utilizzano un importo di copertura 1-5X stipendio, % di stipendio e Importo forfettario, è necessario impostare la data di **Dettagli del benefit** su **Data di inizio del dipendente** in **Storico esperienze lavorative**. È anche necessario includere **Ore lavorate**, **Frequenza pagamenti** e **Importo retribuzione benefit annuale**. Se il lavoratore ha una retribuzione fissa, immettere un valore in **Ore lavorate** e **Frequenza pagamenti**. L'importo della retribuzione annuale verrà calcolato. Se il dipendente è stipendiato, non è necessario specificare **Ore lavorate**. Quando si creano nuovi lavoratori, si consiglia di immettere prima la retribuzione fissa. Per aggiornare il record dei dettagli del benefit, selezionare **Lavoratore > Storico lavoratore > Dettagli impiego**. Modificare la data in base alla data di inizio del lavoratore.

### <a name="employee-self-service"></a>Dipendente self-service

L'importo del dipendente non viene calcolato durante l'aggiornamento dell'importo della copertura per l'assicurazione sulla vita. Ad esempio, quando a un dipendente viene offerto un piano di assicurazione sulla vita, può selezionare fino a $50.000 in copertura al costo di $ 0,36 per $1.000 di copertura.  Quando il dipendente aggiorna l'importo della copertura, il costo associato del dipendente rimane a zero.

Per un piano di benefit che consente una sola selezione di quel tipo di piano, l'utente riceve un errore se tenta di rinunciare a un piano dopo aver selezionato un piano. Ad esempio, un utente seleziona un piano sanitario e lo inserisce nel carrello. L'utente quindi seleziona **Rinuncia** per un altro piano sanitario. L'utente riceverà un messaggio di errore.

## <a name="enable-benefits-management"></a>Abilitare Gestione benefit

Gestione benefit è una funzionalità di anteprima ed è disponibile solo in ambienti **sandbox**. Questi articoli descrivono come attivare le funzionalità di anteprima in Human Resources. Indicano inoltre quali funzionalità esistenti in Human Resources sono sostituite da Gestione benefit o vengono disattivate in seguito all'attivazione di Gestione benefit.

- [Gestire le funzionalità](hr-admin-manage-features.md)
- [Funzionalità di anteprima: Gestione benefit](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a>Configurare Gestione benefit

Prima di poter creare piani di benefit per i dipendenti, è necessario configurare le opzioni per i piani.

- [Impostare i parametri di Gestione benefit](hr-benefits-setup-parameters.md)
- [Configurare le regole e le opzioni di idoneità](hr-benefits-setup-eligibility-rules.md)
- [Configurare opzioni di idoneità per contatti personali](hr-benefits-setup-contact-eligibility-options.md)
- [Creare opzioni di copertura](hr-benefits-setup-coverage-options.md)
- [Impostare frequenze di pagamento](hr-benefits-setup-payment-frequencies.md)
- [Configurare tipi di eventi reali](hr-benefits-setup-life-event-types.md)
- [Creare tipi di piani](hr-benefits-setup-plan-types.md)
- [Imposta i codici causale](hr-benefits-setup-reason-codes.md)
- [Impostare codici di livello](hr-benefits-setup-tier-codes.md)
- [Configurare i tassi](hr-benefits-setup-rates.md)
- [Configurare le detrazioni](hr-benefits-setup-deductions.md)
- [Configurare giorni di attesa](hr-benefits-setup-waiting-days.md)
- [Configurare periodi di attesa](hr-benefits-setup-waiting-periods.md)
- [Impostare regole di arrotondamento](hr-benefits-setup-rounding-rules.md)
- [Crea categorie di impieghi](hr-benefits-setup-employment-categories.md)
- [Impostare i tipi di impieghi](hr-benefits-setup-employment-types.md)
- [Configurare Dipendente self-service](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Creare piani di benefit

Questi articoli mostrano come creare piani di benefit, inclusi pacchetti e programmi di crediti flessibili.

- [Impostare piani di benefit](hr-benefits-plans-setup.md)
- [Creare piani di benefit per i lavoratori](hr-benefits-plans-worker.md)
- [Impostare programmi di crediti flessibili](hr-benefits-plans-flex-credit-programs.md)
- [Configurare eventi reali futuri](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Elaborare piani di benefit

È necessario elaborare alcune delle modifiche per renderle attive.

- [Elaborare l'idoneità di iscrizione](hr-benefits-process-enrollment-eligibility.md)
- [Elaborare eventi reali](hr-benefits-process-life-events.md)
- [Elaborare le modifiche a eventi reali](hr-benefits-process-life-event-changes.md)
- [Elaborare l'idoneità a eventi reali](hr-benefits-process-life-event-eligibility.md)
- [Elaborare modifiche ai tassi](hr-benefits-process-rate-changes.md)

