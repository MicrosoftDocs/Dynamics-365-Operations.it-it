---
title: Novità o modifiche in Dynamics 365 Human Resources (12 febbraio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 12 febbraio 2020.
author: andreabichsel
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7ce265627bf5cef023770be3f8953e12d49866be
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686913"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (12 febbraio 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.2867. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>Le entità esistenti CompFixedEmpls e HcmPersonImage devono essere accessibili da OData (414178)

Con la versione di questa settimana, le entità **CompFixedEmpls** e **HcmPersonImage** sono ora pubbliche e disponibili tramite ODAta.

## <a name="delete-employment-from-dataverse-doesnt-work-when-employment-details-arent-active-403193"></a>L'eliminazione dell'impiego da Dataverse non funziona quando i dettagli sull'impiego non sono attivi (403193)

Questa modifica ora consente di eliminare l'impiego tramite Dataverse quando non esistono dettagli sull'impiego attivi.

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>Il flusso di lavoro di registrazione del corso cambia lo stato su completato e restituisce errori dopo la seconda approvazione (409749)

Il flusso di lavoro di registrazione del corso è stato aggiornato per consentire più approvatori.

## <a name="in-preview"></a>In anteprima

Le seguenti funzionalità di anteprima sono disponibili a partire dal 3 febbraio 2020:

- **Funzionalità di anteprima di Congedi e assenza** - Per ulteriori informazioni, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funzionalità di anteprima di Gestione benefit** - Per ulteriori informazioni, inclusi problemi noti, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Presto disponibili

### <a name="platform-update-32"></a>Update 32 della piattaforma 

L'update 32 della piattaforma sarà presto disponibile. [Ulteriori informazioni sull'update 32 della piattaforma sono disponibili qui](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).

### <a name="updated-dataverse-solution"></a>Soluzione Dataverse aggiornata

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

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]