---
title: Novità o modifiche in Dynamics 365 Talent (21 gennaio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
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
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6e18e8108a7382bfa052986bab5a8552e38100c6
ms.sourcegitcommit: a2f9dce06322dada6b5f1c82051ef2359f8c0f12
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081843"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Novità o modifiche in Dynamics 365 Talent (21 gennaio 2020)

[!include [banner](includes/banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract. Abbiamo aggiunto delle funzionalità a Attract per supportare il nostro recente annuncio, [Creazione di una forza lavoro più efficiente con Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Scaricare i dati dell'ambiente

Gli amministratori possono scaricare i dati del proprio ambiente. I dati vengono esportati in formato JSON standard con tutti i lavori, i candidati e la configurazione esportati in un file zip. Per ulteriori informazioni, vedere [Esportare dati da Attract e Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>Limitare l'accesso agli ambienti per gli utenti non amministratori

Gli amministratori possono ora limitare l'accesso all'ambiente per gli utenti non amministratori. Non è possibile annullare questa azione. Per ulteriori informazioni, vedere [Limitare l'accesso a Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

### <a name="exporting-onboarding-guides"></a>Esportare le guide di integrazione

Gli utenti possono ora esportare tutte le loro guide e modelli di integrazione in formato documento Word. Per ulteriori informazioni, vedere [Esportare dati da Attract e Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2726. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>Il campo di retribuzione annuale più recente nel modulo Verifica impiego non è coerente (392092)

Questa versione include una modifica che visualizzerà l'ultima valuta in base al selettore della società nel modulo **Verifica impiego**.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>Campo Noto come aggiunto alla ricerca del destinatario di commenti (407789)

Durante l'immissione di commenti sulle prestazioni, la ricerca di lavoratori non forniva informazioni sufficienti per determinare se i commenti erano inviati alla persona corretta. Abbiamo aggiunto una colonna **Noto come** per aiutare a identificare il nome univoco del dipendente.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>Il record HcmWorkerPayrollInfo viene creato senza un'associazione a un lavoratore (394526)

Questa versione include una modifica per non scrivere record HCMWorkerPayrollInfo senza riferimento a un dipendente.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Possibilità di modificare il reparto durante la navigazione dalla gerarchia di posizioni (341001)

Quando la sicurezza è impostata per negare l'accesso alla modifica dei reparti, la modifica è disabilitata durante la navigazione al modulo **Reparti** in tutti gli scenari.

## <a name="coming-soon"></a>Presto disponibili

Una nuova soluzione Common Data Service sarà presto disponibile con le seguenti modifiche:

| Descrizione | Modifica |
| --- | --- |
| Modifiche all'entità **Posizione lavorativa** | <ul><li>Aggiunta di **Paese di retribuzione**</li><li>Aggiunta di **Dimensioni finanziarie**</li></ul> |
| Modifiche all'entità **Lavoratore** | <ul><li>Aggiunta di **Sequenza nome**</li><li>Aggiunta di **Lavora da casa**</li><li>Aggiunta di **Lingua**</li><li>Aggiunta di **Data di anzianità**</li><li>Aggiunta di **Data di ricorrenza annuale**</li><li>Aggiunta di **Data di assunzione originale**</li></ul> |
| Modifiche all'entità **Impiego** | <ul><li>Aggiunta di **Dimensioni finanziarie**</li><li>Aggiunta di **Motivo fine rapporto**</li><li>**Data di transizione** rinominata in **Data fine rapporto**</li><li>Aggiunta di **Date periodo di prova**</li></ul> |
| Modifiche all'entità **Indirizzo lavoratore** | <ul><li>Aggiunta di **Nome della via**</li><li>**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento</li></ul> |
| Nuove entità di impostazione della retribuzione variabile | <ul><li>**Tipo di piano di retribuzione variabile**</li><li>**Piano di retribuzione variabile**</li><li>**Regole distribuzione incentivi**</li><li>**Livello del piano di retribuzione variabile**</li></ul> |
| Nuova entità **Impiego calendario lavoratore** | <ul><li>Aggiunta di **Entità calendario lavoro**</li></ul> |
