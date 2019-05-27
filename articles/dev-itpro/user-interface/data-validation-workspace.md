---
title: Area di lavoro Elenco di controllo di convalida dati
description: L'area di lavoro Elenco di controllo di convalida dati consente di tenere traccia dei processi di convalida dei dati tra società, aree e persone. L'elenco di controllo può essere utilizzato durante una nuova implementazione, dopo un aggiornamento o dopo una migrazione.
author: bking
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: dd758ac5698d84532c0b724485cc6f0da83bc8e0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555564"
---
# <a name="data-validation-checklist-workspace"></a>Area di lavoro Elenco di controllo di convalida dati

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica dell'area di lavoro **Elenco di controllo di convalida dati** e della configurazione collegata.

L'area di lavoro **Elenco di controllo di convalida dati** consente di tenere traccia dei processi di convalida dei dati tra società, aree e persone. L'elenco di controllo può essere utilizzato durante una nuova implementazione, dopo un aggiornamento o dopo una migrazione. A seconda della visualizzazione dell'area di lavoro **Elenco di controllo di convalida dati**, vedrete tutte le attività e stati di un progetto di convalida dati o solo le attività assegnate all'utente.

È innanzitutto necessario selezionare un progetto di convalida dati nella parte superiore dell'area di lavoro. Tutti i dati visualizzati nell'area di lavoro vengono quindi filtrati in base al progetto di convalida dati selezionato.

## <a name="summary-tiles"></a>Sezioni Riepilogo

Le sezioni **Riepilogo** forniscono una panoramica del processo e includono indicatori che consentono di tenere traccia del processo di convalida dati. È possibile visualizzare tutte le attività restanti, le attività completate, le attività in corso e le attività non iniziate per il processo. Questa informazione viene utilizzata per tutte le società incluse nel progetto di convalida dati selezionato.

## <a name="tasks-and-status-section"></a>Sezione Attività e stati

Nella sezione **Attività e stato**, lo stato del progetto di convalida dati in generale viene visualizzato in diversi modi: stato in base alla persona giuridica, all'area e all'elenco attività. È inoltre possibile selezionare il filtro per visualizzare lo stato per una società specifica. Ciascuna scheda dello stato fornisce una scomposizione sia per percentuale che è stata completata sia per numero di attività rimanenti.

L'Ultima scheda è per l'elenco dettagliato attività. Questo elenco include l'elenco completo delle attività.
È possibile filtrare l'elenco attività in vari modi. Fare clic su **Modifica attività** per cambiare lo stato di un'attività o assegnare un'attività. Fare clic su **Allegati** per visualizzare gli allegati per un'attività.

Il nome dell'attività è un collegamento ipertestuale alla pagina di Microsoft Dynamics 365 for Finance and Operations a cui l'utente deve accedere per completare il lavoro. È possibile impostare il collegamento ipertestuale usando il campo **Nome voce di menu** quando si modifica o si crea un'attività dal modulo **Configura progetto di convalida dati**.

È possibile collegare file, note, immagini e URL a un'attività utilizzando l'azione **Allegati**. Ad esempio, è possibile allegare il file di report stampato per un'attività. Un'icona viene visualizzata nella colonna **Allegato** per l'attività se un allegato è presente.

L'opzione **Completato da** verrà immessa automaticamente dopo che l'attività è stata completata con il nome del lavoratore che ha completato l'attività. Quando un'attività è contrassegnata come completata, il campo **Data di completamento** viene aggiornato automaticamente alla data corrente e all'ora corrente.

## <a name="configure-data-validation-project-page"></a>Pagina Configura progetto di convalida dati

Per poter utilizzare l'area di lavoro **Elenco di controllo di convalida dati**, è necessario configurare il processo mediante la pagina **Configura progetto di convalida dati**. (Fare clic su **Aree di lavoro** \> **Elenco di controllo di convalida dati** \> **Configura progetto di convalida dati**).

## <a name="task-areas"></a>Aree attività

Le aree di attività si utilizzano per raggruppare attività di convalida dati in aree logiche di proprietà all'interno dell'organizzazione. Ad esempio, i gruppi Contabilità fornitori, Contabilità clienti, o Contabilità generale possono essere utilizzati come aree di attività.

La voce di menu **Nome voce di menu** è associata all'impegno lavorativo dell'attività e può essere utilizzata per accedere direttamente alla pagina associata dal collegamento di attività nell'area di lavoro. Ad esempio, un'attività di convalida dati che esegue il report **Aging contabilità fornitori** per la contabilità fornitori può essere collegata alla pagina del report **Aging contabilità fornitori**.
