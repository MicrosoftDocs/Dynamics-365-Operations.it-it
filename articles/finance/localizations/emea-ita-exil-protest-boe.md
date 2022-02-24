---
title: Importazione di protesti effetti attivi
description: Questo argomento spiega come impostare e importare le informazioni di protesto da un file di protesto effetto attivo.
author: neserovleo
manager: AnnBe
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: v-lenest
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: cd46a1c745379233e6b4168cf68c8dc6a9247c10
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962608"
---
# <a name="bills-of-exchange-protest-import"></a>Importazione di protesti effetti attivi 

[!include [banner](../includes/banner.md)]

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
