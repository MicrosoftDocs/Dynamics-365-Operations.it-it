---
title: Novità o modifiche in Dynamics 365 Human Resources (3 marzo 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 3 marzo 2020.
author: andreabichsel
manager: tfehr
ms.date: 03/03/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e4007daa51d661a2a6b67c323cfaf05c22543371
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128043"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (3 marzo 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.2955. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>La soluzione Dataverse è ora disponibile con le seguenti modifiche:

Una nuova soluzione Dataverse sarà presto disponibile con le seguenti modifiche:

| Descrizione | Modifica |
| ----------------------------------------- | --- |
| Modifiche all'entità **Posizione lavorativa** | Aggiunta di **Paese di retribuzione**</br>Aggiunta di **Dimensioni finanziarie** |
| Modifiche all'entità **Lavoratore** | Aggiunta di **Sequenza nome**</br>Aggiunta di **Lavora da casa**</br>Aggiunta di **Lingua**</br>Aggiunta di **Data di anzianità**</br>Aggiunta di **Data di ricorrenza annuale**</br>Aggiunta di **Data di assunzione originale** |
| Modifiche all'entità **Impiego** | Aggiunta di **Dimensioni finanziarie**</br>Aggiunta di **Motivo fine rapporto**</br>**Data di transizione** rinominata in **Data fine rapporto**</br>Aggiunta di **Date periodo di prova** |
| Modifiche all'entità **Indirizzo lavoratore** | Aggiunta di **Nome della via**</br>**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento |
| Nuove entità di impostazione della retribuzione variabile | **Tipo di piano di retribuzione variabile**</br>**Piano di retribuzione variabile**</br>**Regole distribuzione incentivi**</br>**Livello del piano di retribuzione variabile** |
| Nuova entità **Impiego calendario lavoratore** | Aggiunta di **Entità calendario lavoro** |
| Nuova entità **Dettagli posizione di retribuzione** | Aggiunta di **Dettagli posizione di retribuzione** |
| Nuova entità **Titolo** | Aggiunta di **Titolo**. La nuova entità **Titolo** sarà inclusa nel processo di sincronizzazione tra Human Resources e Dataverse. Inizialmente non vi verrà fatto riferimento dalle entità **Posizione lavorativa** o **Posizione**. |

Nelle prossime settimane, questi cambiamenti di entità saranno disponibili in tutti gli ambienti. Per installare manualmente l'ultima soluzione Dataverse per Human Resources:

1.  Accedere all'[Interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selezionare **Ambienti**.

3.  Trovare l'ambiente da aggiornare. L'ambiente deve corrispondere al **nome dell'ambiente** nella sezione **informazioni Common Data Service** del modulo **Informazioni su** in Human Resources.

4.  Selezionare l'ambiente per visualizzare i dettagli dell'ambiente.

5.  Selezionare **Gestisci soluzioni** nella barra di azione superiore. Una nuova finestra del browser viene visualizzata con l'**interfaccia di amministrazione di Dynamics 365** nel contesto dell'ambiente.

6.  Nell'elenco **Soluzione** selezionare **Ancora Dynamics 365 Human Resources**.

7.  Selezionare **Aggiorna** per applicare l'ultima soluzione.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>Problemi di importazione con l'entità dati di registrazione di congedo (406082)

Ora è possibile iscrivere un dipendente in un nuovo piano di congedo dello stesso tipo, purché la nuova data di iscrizione sia successiva alla data di iscrizione scaduta del piano precedente.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>Problema con l'esportazione delle aliquote nell'entità 401k payrollWorkerEnrolledBenefitDetail in DMF (420700)

Questa modifica corregge la funzionalità di esportazione per l'entità **payrollWorkerEnrolledBenefitDetail** per riflettere i valori attuali per il contributo del datore di lavoro.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>La ricerca nel modulo Lavoratore semplificato provoca il messaggio che indica che il campo Persona deve essere compilato (402525)

Quando si cerca un dipendente, non viene più visualizzato il messaggio indicante che occorre compilare il campo **Persona**.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>Il valore del campo Nota non viene visualizzato nel modulo Aggiungi altre competenze (380134)

Questa modifica risolve un problema durante la personalizzazione del modulo **Aggiungi altre competenze** in Self-service dipendenti.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>Più piani di retribuzione fissa non scadono quando si trasferiscono i dipendenti (389466)

Con questa modifica, tutti i record di retribuzione fissa attivi per la vecchia posizione scadranno alla data di transizione.

## <a name="in-preview"></a>In anteprima

Le seguenti funzionalità di anteprima diventano disponibili a partire dal 3 febbraio 2020:

- **Funzionalità di anteprima di Congedi e assenza** - Per ulteriori informazioni, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funzionalità di anteprima di Gestione benefit** - Per ulteriori informazioni, inclusi problemi noti, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)