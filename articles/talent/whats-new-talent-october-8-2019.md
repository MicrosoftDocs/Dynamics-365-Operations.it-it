---
title: Novità o modifiche in Dynamics 365 Talent (8 ottobre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
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
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 06758ff5eb1c00ae299b1b8849fcabb0cd9593e8
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896637"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Novità o modifiche in Dynamics 365 Talent (8 ottobre 2019)

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2542. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>Rimozione dell'iscrizione aperta ai vantaggi dall'anteprima pubblica

In concomitanza con l'annuncio nel [post di blog sugli investimenti strategici in Core HR per promuovere l'eccellenza operativa](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/), Microsoft rimuove la funzionalità di iscrizione aperta ai vantaggi dall'anteprima pubblica il 18 ottobre 2019. Nuove funzionalità verranno rilasciate in futuro. L'utilizzo in produzione della funzione di iscrizione aperta ai vantaggi attualmente in anteprima pubblica non sarà supportato. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>L'integrazione di Common Data Service è ora disattivata per impostazione predefinita nei nuovi provisioning (343675)
 
Quando si effettua il provisioning di nuovi ambienti, l'integrazione Common Data Service è disattivata. Per ulteriori informazioni, vedere [Configurare l'integrazione di Common Data Service](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Inserimento e navigazione dei dipendenti semplificati

La funzionalità per l'inserimento e la navigazione dei dipendenti è ora disponibile in tutti gli ambienti. Per attivare questa funzionalità, accedere a **Amministrazione sistema \> Collegamenti \> Impostazione \> Paramenti di sistema \> Funzionalità di previsione** e selezionare **Navigazione e modulo lavoratore avanzati**. La funzionalità è quindi attivata per tutti gli utenti. È possibile disattivare questa opzione in qualsiasi momento.

Per ulteriori informazioni, vedere [Inserimento dati dei dipendenti semplificati](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.

### <a name="attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Attract e Onboard creano lavoratori inattivi in Core HR (380517)

La versione di questa settimana risolve un problema per cui Attract e Onboard creano lavoratori inattivi in Core HR.

### <a name="the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>Il flusso di lavoro ha esito negativo quando il responsabile ha effettuato l'accesso a un'altra società durante il licenziamento di un dipendente (346852)

Il flusso di lavoro non restituisce più l'esito negativo in base alla persona giuridica a cui il responsabile ha effettuato l'accesso.

### <a name="missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Informazioni mancanti in HcmOnboardingWorkerChecklistTaskEntity (349591)

La versione include informazioni aggiuntive su **HcmOnboardingWorkerChecklistTaskEntity**. Di seguito sono riportati alcuni esempi.

- **Nome gruppo** quando il tipo assegnato è **gruppo**
- **Nome dipendente** quando il tipo assegnato è **dipendente**
- **Nome responsabile** quando il tipo assegnato è **responsabile**

### <a name="entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Le entità non sono elencate in ordine alfabetico in amministrazione di Common Data Service (377414)

Le entità ora sono elencate in ordine alfabetico nella pagina **Amministrazione di CDS**.

### <a name="changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>La modifica del tipo di lavoro con una data futura non consente l'assegnazione di una posizione (339958)

Questa modifica consente di assegnare posizioni in caso di modifica dei tipi di lavoratore (ad esempio, da dipendente a terzista).

### <a name="updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>L'aggiornamento dell'entità per la transazione bancaria di congedo di Common Data Service crea un nuovo record in Talent (352938)

La transazione di congedo è ora aggiornata durante un aggiornamento a Common Data Service per le transazioni bancarie di congedo.

### <a name="the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>Il titolo degli allegati per gli elementi di feedback mostra la descrizione del feedback (343765)

La descrizione del feedback non appare più nel titolo dell'allegato.

### <a name="compensation-workflow-comments-field-shows-incorrect-content-339297"></a>Il campo Commenti sul flusso di lavoro di compensazione mostra contenuto errato (339297)

Questa modifica mostra il contenuto del campo **%HcmActionState.HcmWorkerActionComment.Comments%**.

### <a name="workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>WorkCalendarEntity e WorkCalendarDayEntity non sono esposti tramite OData (376329)

In questa versione, **WorkCalendarEntity** e **WorkCalendarDayEntity** sono ora disponibili tramite Open Data Protocol (OData).

### <a name="hcmworkerentity-is-slow-when-odata-is-used-375221"></a>HCMWorkerEntity è lento quando si utilizza OData (375221)

Le modifiche migliorano le prestazioni di **HCMWorkerEntity** quando la progettazione cartella di lavoro di Microsoft Excel viene utilizzata.

### <a name="manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>La voce del giornale di registrazione prestazioni del responsabile mostra un errore dopo aver eliminato un giornale di registrazione prestazioni e averne creato uno nuovo (336061)

Questa versione corregge un problema che si verifica dopo l'eliminazione di un giornale di registrazione prestazioni e la creazione di uno nuovo immediatamente dopo. La correzione modifica il comportamento nella funzionalità responsabile self-service.

## <a name="coming-soon"></a>Presto disponibili

### <a name="print-performance-reviews"></a>Stampare le valutazioni delle prestazioni

Vedere [Stampare le valutazioni delle prestazioni](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) nel piano della seconda ondata di rilascio di Dynamics 365: 2019.
