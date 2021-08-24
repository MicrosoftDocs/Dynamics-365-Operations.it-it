---
title: Creare una nuova funzionalità di Fatturazione elettronica
description: Questo argomento spiega come creare una nuova funzionalità di Fatturazione elettronica quando non sono disponibili funzionalità configurabili per il tuo paese o area geografica.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744937"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Creare una nuova funzionalità di Fatturazione elettronica

[!include [banner](../includes/banner.md)]

Questo argomento spiega come creare una nuova funzionalità di Fatturazione elettronica quando non sono disponibili funzionalità configurabili per il tuo paese o area geografica.

Per creare una nuova funzionalità di Fatturazione elettronica, completa questi attività.

1. Crea una nuova configurazione del formato di file utilizzando la configurazione del modello di fattura fornita e il mapping di fatture esistente per la funzionalità che intendi creare.
2. Aggiungi le configurazioni del formato di file alle configurazioni delle funzionalità di Fatturazione elettronica.
3. Crea la configurazione delle funzionalità di Fatturazione elettronica.
4. Completa la nuova funzionalità di Fatturazione elettronica e pubblicala nel repository globale dell'organizzazione.
5. Distribuisci la nuova funzionalità di Fatturazione elettronica nell'ambiente del servizio.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Creare nuove configurazioni del formato di file derivate dal modello di fattura esistente

In questa procedura creerai le configurazioni del formato di file necessarie per la nuova funzionalità di Fatturazione elettronica che intendi creare. Puoi creare la configurazione del formato di file di fattura elettronica e qualsiasi altra configurazione di formato di file che potrebbe risultare necessaria per la nuova funzionalità di Fatturazione elettronica.

Prima di iniziare questa procedura, accedi all'account Regulatory Configuration Service (RCS).

1. In Microsoft Dynamics 365 Finance, nell'area di lavoro **Creazione di report elettronici**, seleziona **Repository** per il provider di configurazioni **Microsoft**.
2. Seleziona **Globale**, seleziona **Apri**, quindi, nel riquadro a sinistra, seleziona la configurazione **Modello di fattura**.

    > [!IMPORTANT]
    > Per il Brasile, seleziona invece il modello di configurazione **Documenti fiscali**.

3. Nella scheda **Configurazioni**, seleziona **Importa**.
4. Chiudere la pagina.
5. Chiudere la pagina.
6. Seleziona il riquadro **Configurazioni dreport** e quindi seleziona il modello di fattura importato.
7. Seleziona **Crea configurazione**, quindi seleziona **Formato basato sul modello di contesto della fattura**.
8. Immetti un nome e una descrizione per la configurazione del formato.
9. Nel campo **Tipo di formato** seleziona il tipo di estensione di file.
10. Seleziona **Crea configurazione**, quindi seleziona la configurazione di formato creata.
11. Seleziona **Progettazione** e utilizza lo strumento Progettazione formati per configurare il layout del file in modo che soddisfi le specifiche relative ai formati di file.
12. Chiudere la pagina.
13. Nella scheda **Versioni**, seleziona **Cambia stato** \> **Completato**.
14. Seleziona **Cambia stato** \> **Condividi** per pubblicare la configurazione del formato nel repository globale.

La nuova configurazione del formato di file deve essere condivisa con il dominio Microsoft prima che la configurazione possa essere utilizzata dal servizio Fatturazione elettronica.

1. Seleziona la configurazione del formato che stai utilizzando. Lo stato della configurazione deve essere **Condivisa**.
2. Nella scheda **Versioni**, seleziona **Condivisione avanzata** \> **Repository globale**.
3. Nella scheda **Condiviso con**, seleziona **Organizzazione**.
4. Nel campo **Parametri**, immetti **Microsoft.com** per condividere la configurazione del formato con il dominio Microsoft.
5. Selezionare **OK**.

## <a name="create-the-new-electronic-invoicing-feature"></a>Creare la nuova funzionalità di Fatturazione elettronica

1. In RCS nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
2. Seleziona **Aggiungi** e quindi seleziona **Nuova funzionalità**.
3. Immetti un nome e una descrizione per la funzionalità di Fatturazione elettronica.
4. Selezionare **Crea funzionalità**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Aggiungere configurazioni per le funzionalità di Fatturazione elettronica

1. Seleziona la funzionalità di Fatturazione elettronica che stai utilizzando.
2. Nella scheda **Configurazioni**, seleziona **Aggiungi**.
3. Nella griglia **Configurazioni**, cerca e seleziona le configurazioni di formato di file necessarie alla funzionalità di Fatturazione per generare il file di fatturazione elettronica.
4. Selezionare **OK**.

## <a name="add-electronic-invoicing-feature-setups"></a>Aggiungere impostazioni per le funzionalità di Fatturazione elettronica

1. Nella scheda **Impostazioni**, seleziona **Aggiungi**, quindi seleziona **Impostazione personalizzata**.
2. Immettere un nome e una descrizione per l'impostazione della funzionalità.
3. Nel campo **Tipo di impostazione**, seleziona **Pipeline di elaborazione**.
4. Selezionare **Crea**.
5. Seleziona l'impostazione desiderata e seleziona **Modifica**.
6. Nella scheda **Pipeline di elaborazione**, seleziona **Nuova** per aggiungere un'azione di pipeline. Per ulteriori informazioni sulle pipeline, vedi [Azioni](e-invoicing-configuration-rcs.md#actions).
7. Nella scheda **Regole di applicabilità** seleziona **Nuove** per aggiungere clausole di regole di applicabilità. Per ulteriori informazioni sulle regole di applicabilità, vedi [Regole di applicabilità](e-invoicing-configuration-rcs.md#applicability-rules).
8. Nella scheda **Variabili**, seleziona **Nuovo** per aggiungere variabili come necessario.
9. Seleziona **Salva**, quindi seleziona **Convalida** per verificare la coerenza della configurazione.
10. Chiudere la pagina.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Distribuire la funzionalità di Fatturazione elettronica nell'ambiente del servizio

Per informazioni su come completare questa attività, vedi [Distribuire la funzionalità di Fatturazione elettronica nell'ambiente di servizio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Distribuire la funzionalità di Fatturazione elettronica a un'applicazione connessa

Per informazioni su come completare questa attività, vedi [Configurare l'impostazione dell'applicazione](e-invoicing-get-started.md#configure-the-application-setup) e [Distribuire la funzionalità di Fatturazione elettronica nell'applicazione connessa](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
