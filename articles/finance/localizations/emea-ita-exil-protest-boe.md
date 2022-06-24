---
title: Importazione di protesti effetti attivi
description: Questo articolo spiega come impostare e importare le informazioni di protesto da un file di protesto effetto attivo.
author: anasyash
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: anasyash
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 8dacc1553879b27424701440ae1bb83dd477cffe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908953"
---
# <a name="bills-of-exchange-protest-import"></a>Importazione di protesti effetti attivi 

[!include [banner](../includes/banner.md)]

Questo articolo spiega come impostare e importare le informazioni di protesto dal file di protesto effetto attivo ricevuto dalla banca.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter utilizzare la funzionalità di importazione del protesto effetto attivo, devono essere soddisfatti i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzione di gestione di protesti per effetti attivi deve essere attivata nell'area di lavoro **Gestione delle funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="import-electronic-reporting-configurations"></a>Importare configurazioni per la creazione di report elettronici

La configurazione per la creazione di report elettronici, **Protesto effetto attivo RIBA (IT)**, deve essere importata da LCS prima di poterla utilizzare. Dopo aver importato la configurazione, il corrispondente **Modello di pagamento** e il **Mapping di modello di pagamento alle configurazioni RIBA di destinazione** verrà importato automaticamente.

## <a name="set-up-method-of-payment"></a>Imposta metodo di pagamento

Nella pagina **Metodo di pagamento - clienti**, abilitare il parametro **Formato di importazione elettronica generico**, quindi selezionare **Protesto effetto attivo RIBA (IT)**. 

## <a name="import-protest-information-from-an-electronic-file"></a>Importare le informazioni del protesto da un file elettronico

1. Per importare il file, creare un giornale di registrazione  **Protesta effetto attivo**, quindi selezionare **Righe giornale di registrazione**.
2. Selezionare **Funzioni** \> **Importa protesto**.
3. Nella finestra di dialogo selezionare il metodo di pagamento per l'importazione del protesto e allegare il file. Le righe del giornale di registrazione vengono create in base alle informazioni nel file.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
