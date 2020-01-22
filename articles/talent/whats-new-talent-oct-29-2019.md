---
title: Novità o modifiche in Dynamics 365 Talent (29 ottobre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e2d79ee9e182df4a4efe65beb685567b1e7446ce
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897444"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Novità o modifiche in Dynamics 365 Talent (29 ottobre 2019)

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2586. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>Elimina parti senza ruoli deve essere attivo per impostazione predefinita (371233)

Quando si esegue il provisioning di un nuovo ambiente in Talent, **Elimina parti senza ruoli** è attivo per impostazione predefinita. Quando si elimina un lavoratore, la parte associata al lavoratore non viene rimossa a meno che questa impostazione non sia attiva. Questa modifica limita i record duplicati nella rubrica globale quando è necessario importare, modificare o reimportare i lavoratori.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>Le bozze e le richieste di congedo annullate devono poter essere eliminate in Common Data Service (376999)

Con questa modifica, è ora possibile eliminare le richieste di congedo con stato **Bozza** o **Annullato** in Common Data Service.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>I valori aggiuntivi dell'elenco nei campi personalizzati non vengono riflessi in Common Data Service quando si fa clic su Applica nel modulo Campi personalizzati (379599)

Quando si aggiungono nuovi valori di elenco a un campo personalizzato esistente che è già sincronizzato con Common Data Service, i valori ora sono disponibili in Common Data Service dopo aver applicato le modifiche nel modulo **Campi personalizzati**.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Applicare gli elenchi di controllo per l'inserimento tra le persone giuridiche quando esiste più di un impiego (371270)

Nella versione della settimana, è possibile applicare gli elenchi di controllo ai dipendenti con più di di impiego in **Modulo lavoratore > Elenchi di controllo**.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>La funzionalità di anteprima dell'iscrizione aperta ai vantaggi è stata rimossa

In concomitanza con l'annuncio nel [post di blog sugli investimenti strategici in Core HR per promuovere l'eccellenza operativa](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft ha rimosso la funzionalità di iscrizione aperta ai vantaggi dall'anteprima pubblica. Nuove funzionalità verranno rilasciate in futuro. L'utilizzo di produzione della funzionalità dell'iscrizione aperta ai vantaggi non è supportato.

## <a name="coming-soon"></a>Presto disponibili

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.

### <a name="feature-management-workspace"></a>Area di lavoro Gestione funzionalità

Le funzionalità vengono aggiunte e aggiornate in ogni versione. L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.

Per ulteriori informazioni sulle modifiche fornite con la gestione delle funzionalità, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
