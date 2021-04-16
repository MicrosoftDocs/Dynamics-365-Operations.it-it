---
title: Flussi di lavoro di transazioni per la gestione degli sconti
description: Questo argomento spiega come impostare un flusso di lavoro di transazioni per la gestione degli sconti per approvare e attivare le transazioni.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831724"
---
# <a name="rebate-management-deal-workflows"></a>Flussi di lavoro di transazioni per la gestione degli sconti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Per approvare le transazioni di sconti, la gestione degli sconti utilizza la stessa piattaforma del flusso di lavoro delle altre app Finance and Operations. Ad ogni flusso di lavoro sono associati due processi di lavoro:

- Un elemento del flusso di lavoro attiva la transazione in modo che l'utente o il processo del flusso di lavoro possa approvare le transazioni.
- Un elemento del flusso di lavoro approva la transazione.

Prima di poter utilizzare una transazione di sconti, è necessario che sia attiva nel modulo **Gestione degli sconti**. Per attivare una transazione, devi prima creare e configurare un *Flusso di lavoro per la gestione degli sconti*.

Dopo che un flusso di lavoro è stato attivato per la gestione degli sconti, gli utenti non possono approvare manualmente le transazioni. Il flusso di lavoro deve essere sempre utilizzato.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Creare e gestire flussi di lavoro di transazioni per la gestione degli sconti

Per lavorare con i flussi di lavoro di transazioni per la gestione dei rimborsi, vai a **Gestione degli sconti \> Impostazioni \> Flussi di lavoro di gestione degli sconti**. Qui è possibile visualizzare, creare e aggiornare i flussi di lavoro secondo necessità. È possibile attivare un solo flusso di lavoro di questo tipo alla volta. Per ulteriori informazioni sui flussi di lavoro, come lavorare con la pagina **Flussi di lavoro di gestione degli sconti** e come creare flussi di lavoro, vedi [Panoramica del sistema del flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) e argomenti correlati.

## <a name="use-a-workflow-to-activate-a-deal"></a>Usrea un flusso di lavoro per attivare una transazione

Per attivare una transazione tramite un flusso di lavoro, apri la transazione (ad esempio, nella pagina **Tutte le transazioni di gestione degli sconti**). Quindi, nel riquadro azioni seleziona **Flusso di lavoro \> Invia**. Dopo che la nuova transazione è stata elaborata e approvata tramite il flusso di lavoro, sarà attiva e pronta per l'uso.

Dopo che una transazione è stata attivata non puoi modificarne l'impostazione. Se devi modificare una transazione attiva, disattivala e quindi creane una nuova. Se la nuova transazione assomiglierà alla vecchia, puoi crearla copiando la vecchia transazione.
