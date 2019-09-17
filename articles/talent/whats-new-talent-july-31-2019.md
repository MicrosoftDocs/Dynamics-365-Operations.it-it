---
title: Novità e modifiche in Dynamics 365 for Talent (31 luglio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1fffe1bd8739723294c027c174d5e959c1c6010a
ms.sourcegitcommit: 4ff8c2c2f3705d8045df66f2c4393253e05b49ed
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864581"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-july-30-2019"></a>Novità e modifiche in Dynamics 365 for Talent (30 luglio 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2409.


### <a name="region-support-for-canada-and-southeast-asia"></a>Supporto regionale per Canata e Asia sudorientale

Siamo lieti di annunciare che le regioni Canada e Asia sudorientale sono disponibili per Microsoft Dynamics 365 for Talent dal 1° agosto 2019. Con questa modifica, è possibile creare ambienti nelle regioni del Canada e asiatiche e tutti i dati in Talent verranno conservati solo all'interno di tali regioni. È possibile creare un ambiente in queste nuove regioni selezionando la posizione nella nuova finestra di dialogo Nuovo ambiente e utilizzare l'ambiente per eseguire il provisioning di Talent in LCS come descritto in [Eseguire il provisioning di Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

La migrazione dei dati dei progetti esistenti da altre regioni verso le regioni del Canada e asiatiche non è supportata. È possibile eseguire il provisioning solo di nuovi progetti alle nuove regioni supportate.

### <a name="new-active-positions-list-page"></a>Nuova pagina elenco Posizioni attive

Le opzioni per gli elenchi basati sulla posizione ora sono: **Tutte le posizioni**, **Posizioni attive**, **Posizioni aperte** e **Posizioni inattive**. La nuova pagina elenco **Posizioni attive** visualizza solo le posizioni, aperte o completate, che sono attive alla data corrente. 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a>Consentire ai partecipanti al corso di essere aggiunti a corsi aperti

Le modifiche di questa settimana correggono il problema per cui solo i diretti subalterni possono essere registrati a corsi aperti.

### <a name="fte-analysis-displaying-incorrect-fte-number"></a>L'analisi FTE visualizza un numero FTE errato

L'opzione **Analisi FTE** è stata corretta nella scheda **Analisi** di **Gestione dipendente**.

### <a name="final-comments-label-translation"></a>Traduzione dell'etichetta dei commenti finali

L'etichetta **Commenti finali** è ora tradotta nel modulo di revisione.

## <a name="in-preview"></a>In anteprima

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Le funzionalità di anteprima vengono attivate solo nelle istanze sandbox

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile specificare se il tipo di istanza è **Produzione** o **Sandbox**. Le istanze **Sandbox** consentono di testare tle nuove funzionalità prima dell'utilizzo. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di **produzione**. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza **Sandbox**, contattare il [supporto tecnico](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) per avviare la richiesta di modifica.

Per ulteriori informazioni su come vengono pubblicate le modifiche, vedere [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visualizzare informazioni estese per le prestazioni in Responsabile self-service

Una nuova opzione consentirà ai responsabili di visualizzare le prestazioni dei report diretti ed estesi. Attualmente, i responsabili linea possono assegnare e aggiornare obiettivi prestazionali e pubblicare nuove revisioni. Inoltre, i responsabili diretti e i relativi dipendenti possono gestire e aggiornare giornali di registrazione prestazioni per garantire la corretta esecuzione del processo di valutazione delle prestazioni. Una volta questa modifica implementata, i responsabili potranno visualizzare e gestire informazioni relative alle prestazioni per i report estesi oltre che per quelli diretti.
