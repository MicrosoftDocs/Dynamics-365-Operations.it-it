---
title: Panoramica di gestione dei benefit
description: Panoramica della funzionalità di Gestione benefit in Dynamics 365 Human Resources. Offrire opzioni di benefit estese ai propri dipendenti con un'esperienza online di facile utilizzo.
author: andreabichsel
manager: tfehr
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4ae4270f3185f8795753ecdb209515ecd6e86486
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113155"
---
# <a name="benefits-management-overview"></a>Panoramica di Gestione benefit

Per rimanere competitivi, è necessario offrire una ricca gamma di benefit per attirare e trattenere i migliori dipendenti. Oltre ai benefit standard come la copertura medica e dentale, è possibile che si voglia offrire anche servizi estesi come assistenza all'adozione, programmi ricreativi e indennità per l'abbigliamento. Gestione benefit in Microsoft Dynamics 365 Human Resources fornisce una soluzione flessibile che supporta una vasta gamma di opzioni di benefit. Human Resources include anche un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte.

- I piani di benefit avanzati consentono di creare e gestire piani di benefit unici e supportare tabelle di tassi di benefit complesse e livelli nidificati. È possibile creare facilmente programmi di benefit, pacchetti e regole di iscrizione automatica per un'esperienza per i dipendenti più semplice.

- I programmi di crediti flessibili consentono una ripartizione per supportare il pensionamento e altri eventi della vita.

- Le regole di idoneità estese consentono di rendere disponibili i benefit appropriati per i dipendenti appropriati.

- L'iscrizione online ai benefit fornisce un'esperienza semplice per i dipendenti.

- L'elaborazione di eventi reali qualificati supporta eventi reali futuri.

Se si desidera accedere ai dati dimostrativi, sarà necessario ridistribuire l'ambiente sandbox.

## <a name="enable-benefits-management"></a>Abilitare Gestione benefit

In questo argomento viene descritto come attivare le funzionalità in Human Resources. Indica anche quali funzionalità esistenti in Human Resources sono sostituite da Gestione benefit o vengono disattivate in seguito all'attivazione di Gestione benefit.

> [!IMPORTANT]
> Dopo aver abilitato Gestione benefit in un ambiente di **Produzione** non è possibile disabilitarlo. Si consiglia di abilitare e testare Gestione benefit in un ambiente **sandbox** prima di abilitarlo in un ambiente di **Produzione**. Sono presenti differenze significative tra la funzionalità dei benefit legacy e la nuova funzionalità di Gestione benefit che richiedono una configurazione aggiuntiva e devono essere testati prima di essere messi in produzione.

- [Gestire le funzionalità](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Configurare le informazioni sui dipendenti

Prima di poter iscrivere dipendenti nei benefit, è necessario fornire le informazioni richieste. È necessario iscrivere un dipendente al **Piano di retribuzione fissa** alla data di inizio ed è necessario selezionare una **frequenza di pagamento dei benefit** nel campo **Dettagli impiego** del modulo **Lavoratore**.

Se un dipendente riceve un compenso supplementare come le commissioni, è possibile aggiungere un importo **Retribuzione annuale benefit** dal record dipendente. Le risorse umane useranno l'importo **Retribuzione annuale benefit** nel determinare gli importi di copertura, anziché l'importo annuale di retribuzione fissa. La **Retribuzione annuale benefit** deve essere valida a partire dalla data di inizio dell'impiegato o di quella del periodo di benefit, a seconda di quale è più recente. Se per un dipendente viene registrato sia una retribuzione fissa sia un importo di retribuzione annuale benefit, la retribuzione annuale benefit sarà utilizzata per determinare gli importi della copertura.

Quando si crea un piano di benefit che utilizza tariffe basate sul genere o sull'età, è necessario immettere una data di nascita e un genere affinché il dipendente possa calcolare il costo del benefit.

## <a name="configure-benefits-management"></a>Configurare la gestione dei benefit

Prima di poter creare piani di benefit per i dipendenti, è necessario configurare le opzioni per i piani.

- [Impostare i parametri di Gestione benefit](hr-benefits-setup-parameters.md)
- [Configurare le regole e le opzioni di idoneità](hr-benefits-setup-eligibility-rules.md)
- [Configurare le opzioni di idoneità del contatto personale](hr-benefits-setup-contact-eligibility-options.md)
- [Creare opzioni di copertura](hr-benefits-setup-coverage-options.md)
- [Impostare le frequenze pagamenti](hr-benefits-setup-payment-frequencies.md)
- [Configurare i tipi di eventi reali](hr-benefits-setup-life-event-types.md)
- [Creare i tipi di piano](hr-benefits-setup-plan-types.md)
- [Impostare i codici causale](hr-benefits-setup-reason-codes.md)
- [Impostare i codici livello](hr-benefits-setup-tier-codes.md)
- [Configurare le tariffe](hr-benefits-setup-rates.md)
- [Configurare le detrazioni](hr-benefits-setup-deductions.md)
- [Configurare i giorni di attesa](hr-benefits-setup-waiting-days.md)
- [Configurare i periodi di attesa](hr-benefits-setup-waiting-periods.md)
- [Impostare le regole di arrotondamento](hr-benefits-setup-rounding-rules.md)
- [Creare le categorie di impiego](hr-benefits-setup-employment-categories.md)
- [Impostare i tipi di impieghi](hr-benefits-setup-employment-types.md)
- [Configurare Dipendente self-service](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Creare piani di benefit

Questi articoli mostrano come creare piani di benefit, inclusi pacchetti e programmi di crediti flessibili.

- [Impostare i piani di benefit](hr-benefits-plans-setup.md)
- [Impostare i programmi di credito flessibile](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Elaborare i piani di benefit

È necessario elaborare alcune delle modifiche per renderle attive.

- [Elaborare l'idoneità di iscrizione](hr-benefits-process-enrollment-eligibility.md)
- [Elaborare eventi reali](hr-benefits-process-life-events.md)
- [Elaborare le modifiche a eventi reali](hr-benefits-process-life-event-changes.md)
- [Elaborare l'idoneità a eventi reali](hr-benefits-process-life-event-eligibility.md)
- [Elaborare modifiche ai tassi](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]