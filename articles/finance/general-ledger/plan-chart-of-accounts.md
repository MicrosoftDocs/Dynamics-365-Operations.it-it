---
title: Definire il piano dei conti
description: Questo argomento fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e568fca70ea2048d881681ff7ab8ebc6fad6450
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990366"
---
# <a name="plan-your-chart-of-accounts"></a>Definire il piano dei conti

[!include [banner](../includes/banner.md)]

Questo argomento fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.

Per tenere traccia e gestire le informazioni finanziarie in un'organizzazione, è possibile impostare un piano dei conti. Un piano dei conti è un insieme di conti che definiscono una struttura finanziaria. Per tenere ulteriormente traccia delle transazioni in tali conti, è possibile aggiungere segmenti. Questi segmenti sono noti con il nome di dimensioni finanziarie. Ad esempio, un conto spese potrebbe includere dimensioni finanziarie denominate Reparto, Centro di costo e Scopo. Le regole definite dall'utente determinano le modalità di collegamento delle dimensioni finanziarie ai conti principali e ad altre dimensioni finanziarie, nonché quelle di immissione delle transazioni. Queste regole definite dall'utente sono note come strutture dei conti e regole avanzate.

Il piano dei conti consiste in un elenco strutturato dei conti CoGe di una persona giuridica. Questo elenco viene utilizzato per preparare i report finanziari destinati agli uffici competenti e ai proprietari. I conti vengono innanzitutto raggruppati in tipi di conti, quindi ulteriormente aggregati in categorie più ampie. A livello generale, i conti vengono raggruppati in costi e ricavi (conti di gestione) e in attività e passività (conti collettivi).

Un piano dei conti può essere condiviso e utilizzato da qualsiasi persona giuridica in un'organizzazione. Il piano dei conti utilizzato da una persona giuridica è definito nella pagina **Contabilità generale**.

Di seguito vengono indicati alcuni fattori da prendere in considerazione quando si pianifica la struttura del piano dei conti per l'organizzazione:

- Gli adempimenti richiesti dal paese o dalla regione in cui ha sede l'organizzazione per quanto riguarda i report finanziari
- Gli adempimenti richiesti dalla persona giuridica
- Il grado di specifica richiesto, sia per le organizzazioni esterne che per la propria

Si crea il piano dei conti nella pagina **Piano dei conti**. È possibile creare conti principali dalla pagina **Piano dei conti** o dalla pagina **Conti principali**. Nei conti principali non è consigliabile utilizzare caratteri speciali come delimitatori del piano dei conti. Si potrebbe sperimentare instabilità oppure potrebbe essere necessario utilizzare sempre le ricerche o la finestra di dialogo quando si immettono combinazioni di conti e dimensioni. Per ulteriori informazioni, vedere [Creare un conto principale](tasks/create-main-account.md).

> [!NOTE]
> In Dynamics 365 for Finance and Operations versione 8.0 (aprile 2018), è possibile modificare il delimitatore del piano dei conti nella pagina **Parametri di contabilità generale**.

È consigliabile collegare i conti principali alle categorie dei conti principali, in modo da poter sfruttare i report finanziari predefiniti senza dover apportare eventuali modifiche. Di conseguenza, è possibile progettare e gestire i report in modo più rapido e facile.

Si creano strutture dei conti nella pagina **Configura strutture dei conti**. Le strutture dei conti consentono di definire combinazioni valide. Queste combinazioni, insieme ai conti principali, formano un piano dei conti. Per ulteriori informazioni, vedere [Creare strutture dei conti](tasks/create-account-structures.md).

**Sostituzioni persona giuridica**

Non tutti i conti principali sono validi per tutte le persone giuridiche e alcuni conti principali potrebbero essere pertinenti solo per un periodo di tempo specifico. In questo scenario, è possibile usare la sezione **Sostituzioni persona giuridica** per identificare quali sono le società per cui è necessario sospendere il conto principale, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva. Le sostituzioni a livello condiviso non possono essere più restrittive di quelle a livello di persona giuridica.

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Dimensioni finanziarie](financial-dimensions.md)
- [Creare e assegnare strutture di regole avanzate](tasks/create-assign-advanced-rule-structures.md)
