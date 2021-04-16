---
title: Novità o modifiche in Dynamics 365 Human Resources (8 marzo 2021)
description: In questo argomento vengono descritte le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources all'8 marzo 2021.
author: marcelbf
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7029f1dab1f10c2b237fafb7b5d8eeff9fa7a543
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790286"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Novità o modifiche in Dynamics 365 Human Resources (8 marzo 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive le funzionalità nuove, modificate o presto disponibili in Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle date di disponibilità generale previste, vedere [Panoramica del secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti nuove funzionalità e correzioni di bug. Le modifiche si applicano alla build 8.1.4017.

### <a name="new-features"></a>Nuove funzionalità

Le seguenti funzioni sono generalmente disponibili con questa versione.

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Visualizzazione interaziendale del congedo per responsabili | [Visualizzazione interaziendale del congedo dei dipendenti per responsabili](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurare i parametri di congedo e assenza](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. È possibile aggiornare questo argomento per includere correzioni di bug che sono state introdotte nella build dopo la pubblicazione iniziale di questo argomento.

| Numero problema | Uscita |  Descrizione |
| --- | --- | --- |
| 486611 | Il congedo è visualizzato nel calendario di congedo quando **Disabilita congedo in tutti i calendari** è abilitato | Se **Disabilita congedo in tutti i calendari** è abilitato, le informazioni sul congedo non vengono più visualizzate quando la funzionalità Miglioramenti del calendario di congedi e assenze è abilitata.|
| 508972 | Convalida mancante nell'entità Transazione bancaria per congedo e assenza | Quando si utilizza l'entità Transazione bancaria per congedo e assenza, i dipendenti non iscritti a un piano non possono più essere importati. |
| 554854 | L'aggiornamento del calendario nell'entità Impiego non riesce se l'entità Giuridica predefinita in Opzioni utente è diversa | L'utilizzo dell'entità Impiego per aggiornare il calendario di un dipendente non restituisce più un errore se l'entità giuridica predefinita in Opzioni utente è diversa. |
| 558347 | Quando si carica la pagina iniziale, viene visualizzato il messaggio "Impossibile creare un record in Configurazioni del formato". | Le personalizzazioni causano la visualizzazione dell'errore "Impossibile creare un record nelle configurazioni del modulo (FormRunConfiguration)" durante il caricamento della pagina iniziale. |
| 557327 | Area di lavoro Gestione benefit: spazio visualizzato sopra la griglia. | Risolto il problema relativo all'esperienza utente che comportava la visualizzazione di spazio non intenzionale sui bordi della griglia della tabella nell'area di lavoro Gestione benefit. |
| 557334 | Area di lavoro Gestione benefit: la casella a discesa di selezione **Periodo** deve apparire solo nella scheda **Riepilogo** | La casella a discesa di selezione **Periodo** ora è visualizzata solo quando la scheda **Riepilogo** è attiva nell'area di lavoro Gestione benefit e non nelle sezioni **Risultati processo** e **Collegamenti**. |
| 557336 | Area di lavoro Gestione benefit: testo **Iscrizione aperta con piani estratti** troncato nella visualizzazione affiancata | Modificato il testo nella visualizzazione affiancata in **Piani estratti...iscrizione aperta** per evitare il troncamento del contesto necessario. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per ulteriori informazioni su come attivare o disattivare le funzionalità, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
| --- | --- | --- |
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |
| Impedire ai dipendenti di modificare i dettagli di contatto aziendali | [Impedire ai dipendenti di modificare i dettagli di contatto aziendali](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Impedire la modifica delle informazioni personali](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Presto disponibili

| Funzionalità | Dettagli |
| --- | --- |
| Le competenze immesse da un manager per i propri dipendenti possono essere approvate automaticamente da un flusso di lavoro | Presto disponibili. |

Per un elenco completo delle funzionalità pianificate e delle relative versioni pianificate, vedi [Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica del primo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
