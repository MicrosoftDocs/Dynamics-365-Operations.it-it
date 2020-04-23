---
title: Importazione di protesti effetti attivi
description: Questo argomento spiega come impostare e importare le informazioni di protesto da un file di protesto effetto attivo.
author: neserovleo
manager: AnnBe
ms.date: 03/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: v-lenest
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 962ddc20fdc6059debcd00fb571c8c4cebe75dce
ms.sourcegitcommit: c03bd0fcf663e4e3e83db52fc9255ef1e3de34bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2020
ms.locfileid: "3176169"
---
# <a name="bills-of-exchange-protest-import"></a>Importazione di protesti effetti attivi 

[!include [banner](../includes/banner.md)]


[!include [banner](../includes/preview-banner.md)]

Questo argomento spiega come impostare e importare le informazioni di protesto dal file di protesto effetto attivo ricevuto dalla banca.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter utilizzare la funzionalità di importazione del protesto effetto attivo, devono essere soddisfatti i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzione di gestione di protesti per effetti attivi deve essere attivata nell'area di lavoro **Gestione delle funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="import-electronic-reporting-configurations"></a>Importare configurazioni per la creazione di report elettronici

La configurazione per la creazione di report elettronici, **Protesto effetto attivo RIBA (IT)**, deve essere importata da LCS prima di poterla utilizzare. Dopo aver importato la configurazione, il corrispondente **Modello di pagamento** e il **Mapping di modello di pagamento alle configurazioni RIBA di destinazione** verrà importato automaticamente.

## <a name="set-up-method-of-payment"></a>Imposta metodo di pagamento

Nella pagina **Metodo di pagamento - clienti**, abilitare il parametro **Formato di importazione elettronica generico**, quindi selezionare **Protesto effetto attivo RIBA (IT)**. 

## <a name="import-protest-information-from-an-electronic-file"></a>Importare le informazioni del protesto da un file elettronico

1. Per importare il file, creare un giornale di registrazione  **Protesta effetto attivo**, quindi selezionare **Righe giornale di registrazione**.
2. Selezionare **Funzioni** \> **Importa protesto**.
3. Nella finestra di dialogo selezionare il metodo di pagamento per l'importazione del protesto e allegare il file. Le righe del giornale di registrazione vengono create in base alle informazioni nel file.
