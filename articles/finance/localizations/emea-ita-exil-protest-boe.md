---
title: Importazione di protesti effetti attivi
description: Questo articolo spiega come impostare e importare le informazioni di protesto da un file di protesto effetto attivo.
author: AdamTrukawka
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: atrukawk
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.search.form: ''
ms.openlocfilehash: ded7ffed97fe3aa384692e2e606bb45f6e0274a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273794"
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
