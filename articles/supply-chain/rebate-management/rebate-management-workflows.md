---
title: Flussi di lavoro di transazioni per la gestione degli sconti
description: Questo articolo spiega come impostare un flusso di lavoro di transazioni per la gestione degli sconti per approvare e attivare le transazioni.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4f0590c4c906e746b54ac30fd6531b8c1cd67915
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067334"
---
# <a name="rebate-management-deal-workflows"></a>Flussi di lavoro di transazioni per la gestione degli sconti

[!include [banner](../includes/banner.md)]

Per approvare le transazioni di sconti, la gestione degli sconti utilizza la stessa piattaforma del flusso di lavoro delle altre app per la finanza e le operazioni. Ad ogni flusso di lavoro sono associati due processi di lavoro:

- Un elemento del flusso di lavoro approva la transazione.
- Un elemento del flusso di lavoro attiva la transazione in modo che l'utente o il processo del flusso di lavoro possa approvare le transazioni.

Prima di poter utilizzare una transazione di sconti, è necessario che sia attiva nel modulo **Gestione degli sconti**. Per attivare una transazione, devi prima creare e configurare un *Flusso di lavoro per la gestione degli sconti*.

Gli utenti non possono approvare manualmente le transazioni. Il flusso di lavoro deve essere sempre utilizzato.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Creare e gestire flussi di lavoro di transazioni per la gestione degli sconti

Per lavorare con i flussi di lavoro di transazioni per la gestione dei rimborsi, vai a **Gestione degli sconti \> Impostazioni \> Flussi di lavoro di gestione degli sconti**. Qui è possibile visualizzare, creare e aggiornare i flussi di lavoro secondo necessità. È possibile attivare un solo flusso di lavoro di questo tipo alla volta. Per ulteriori informazioni sui flussi di lavoro, come lavorare con la pagina **Flussi di lavoro di gestione degli sconti** e come creare flussi di lavoro, vedi [Panoramica del sistema del flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) e articoli correlati.

## <a name="use-a-workflow-to-activate-a-deal"></a>Usrea un flusso di lavoro per attivare una transazione

Per attivare una transazione tramite un flusso di lavoro, apri la transazione (ad esempio, nella pagina **Tutte le transazioni di gestione degli sconti**). Quindi, nel riquadro azioni seleziona **Flusso di lavoro \> Invia**. Dopo che la nuova transazione è stata elaborata e approvata tramite il flusso di lavoro, sarà attiva e pronta per l'uso.

Dopo che una transazione è stata attivata non puoi modificare la maggior parte dell'impostazione. Se devi modificare una transazione attiva, prima disattivala e quindi creane una nuova. Se la nuova transazione assomiglierà alla vecchia, puoi crearla copiando la vecchia transazione.

Puoi modificare le seguenti impostazioni per una transazione dopo che è stata attivata:

- Riconcilia per
- Garanzia cumulativa
- Profilo registrazione
- Profilo di registrazione per garanzia
- Note documenti
- Valuta
- Data di inizio
- Data di fine

Inoltre, le righe di sconto possono essere rimosse.

