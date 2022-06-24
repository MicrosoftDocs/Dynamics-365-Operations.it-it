---
title: Creare una funzionalità di globalizzazione
description: In questo articolo viene illustrato come creare una funzionalità di globalizzazione.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c622b350f79d36b8fda12598ceae57ee9c7095e9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889832"
---
# <a name="create-a-globalization-feature"></a>Creare una funzionalità di globalizzazione

[!include [banner](../includes/banner.md)]

Puoi creare una funzionalità di fatturazione elettronica da zero o basarla su una funzionalità esistente. Quando crei una funzionalità da zero, è necessario aggiungere manualmente le configurazione di Creazione di report elettronici e altri componenti come la configurazione della funzionalità e i dettagli di configurazione dell'applicazione. Quando si crea una funzionalità basata su una funzionalità esistente, la nuova funzionalità eredita tutte le configurazioni ei parametri della funzionalità di base. È possibile rivedere ciò che viene copiato dalla funzionalità di base alla nuova funzionalità.

## <a name="create-a-feature-from-scratch"></a>Creare una funzionalità da zero

Questa sezione spiega come creare una funzionalità di fatturazione elettronica quando non sono disponibili funzionalità di globalizzazione nel repository globale per gli scenari aziendali predefiniti.

Per creare una funzionalità per la fatturazione elettronica, segui questi passaggi.

1. Accedi al tuo account Regulatory Configuration Service (RCS).
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Selezionare **Aggiungi**, quindi, nella finestra di dialogo a discesa, selezionare l'opzione **Nuova funzionalità**.
4. Immetti un nome e una descrizione per la funzionalità di fatturazione elettronica.
5. Selezionare **Crea funzionalità**. La prima versione della nuova funzionalità viene visualizzata sul lato destro della pagina e ha lo stato di **Bozza**.

    Successivamente, è necessario aggiungere le configurazioni ER e le configurazioni delle funzionalità. Prima di aggiungere configurazioni in formato ER nuove o esistenti, assicurati che esistano nel tuo repository RCS locale.

6. Seleziona la funzionalità di fatturazione elettronica che stai utilizzando.
7. Nella scheda **Configurazioni**, seleziona **Aggiungi**.
8. Nella griglia **Configurazioni**, esplora e seleziona le configurazioni di formato richieste per la pipeline di elaborazione (ad esempio, per generare file di fattura elettronica o elaborare risposte da servizi Web esterni).
9. Seleziona **OK**. È ora possibile utilizzare le configurazioni nelle azioni della pipeline di elaborazione. Per ulteriori informazioni, vedi [Utilizzare le configurazioni](e-invoicing-work-configurations.md).
10. Per aggiungere una configurazione della funzionalità di fatturazione elettronica, crearla nella scheda **Configurazioni** della pagina **Nuova funzionalità**. Per ulteriori informazioni, vedi [Utilizzare l'impostazione delle funzioni](e-invoicing-feature-setup.md).
11. Completa la configurazione e distribuisci la funzionalità di fatturazione elettronica nell'ambiente del servizio. Per altre informazioni, vedi [Completare, pubblicare e distribuire una funzionalità di globalizzazione](e-invoicing-complete-publish-deploy-globalization-feature.md).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Creare configurazioni del formato di file derivate dal modello di fattura esistente

Puoi saltare questa sezione se non devi creare configurazioni ER ma puoi riutilizzare le versioni esistenti come base.

Questa procedura mostra come creare le configurazioni del formato di file necessarie per la nuova funzionalità di fatturazione elettronica che intendi creare. Crea la configurazione del formato di file di fattura elettronica e qualsiasi altra configurazione di formato di file che potrebbe risultare necessaria per la nuova funzionalità di Fatturazione elettronica.

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni report**.
3. Seleziona il **Modello fattura** oppure, per gli scenari brasiliani, seleziona il **Modello fiscale**.
4. Seleziona **Crea configurazione**, quindi nella finestra di dialogo a discesa, seleziona l'opzione **Formato basato sulla fattura del modello di dati**.
5. Immetti un nome e una descrizione per la configurazione del formato.
6. Nel campo **Tipo di formato** seleziona il tipo di estensione di file.
7. Nel campo **Definizione modello di dati**, seleziona la struttura radice a cui mappare il tuo formato. Ad esempio, **InvoiceCustomer** viene utilizzato per i formati di fattura cliente.
8. Selezionare **Crea configurazione**.
9. Seleziona la nuova configurazione di formato.
10. Seleziona **Progettazione** e utilizza lo strumento Progettazione formati per configurare il layout del file in modo che soddisfi le specifiche relative ai formati di file.
11. Chiudere la pagina.
12. Nella scheda **Versioni**, seleziona **Cambia stato** \> **Completato**.
13. Seleziona **Cambia stato** \> **Condividi** per pubblicare la configurazione del formato nel repository globale.

Le nuove configurazioni del formato di file devono essere condivise con il dominio Microsoft prima che possano essere utilizzate dal servizio di fatturazione elettronica.

1. Seleziona la configurazione del formato che stai utilizzando. Lo stato della configurazione deve essere **Condivisa**.
2. Nella scheda **Versioni**, seleziona **Condivisione avanzata** \> **Repository globale**.
3. Nella scheda **Condiviso con**, seleziona **Organizzazione**.
4. Nel campo **Parametri**, immetti **microsoft.com** per condividere la configurazione del formato con il dominio Microsoft.
5. Seleziona **OK**.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Creare una funzionalità basata su una funzionalità esistente

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Nel campo **Provider configurazione**, verifica che il provider di configurazione attivo sia selezionato. In questo modo, la nuova funzionalità di fatturazione elettronica apparirà nell'elenco dopo la sua creazione. Se il provider di configurazione attivo non è selezionato, la nuova funzionalità verrà filtrata dall'elenco.
4. Selezionare **Aggiungi**, quindi, nella finestra di dialogo a discesa, selezionare l'opzione **Basato sulla versione esistente**.
5. Immettere un nome e una descrizione per la funzionalità.
6. Nel campo **Funzionalità di base**, seleziona la versione base della funzionalità.
7. Selezionare **Crea funzionalità**. La funzionalità viene creata e ha lo stato **Bozza**.
8. Esaminare i componenti della funzionalità per determinare se sono necessari degli aggiornamenti:

    - Rivedere le configurazioni, nel caso in cui sia necessario personalizzare i formati per la creazione di report elettronici (ER) e la relativa associazione con mapping di formati per la versione della funzionalità.
    - Esaminare l'impostazione, nel caso sia necessario personalizzare la scheda **Azioni**, la scheda **Regole di applicabilità** o la scheda **Variabili** per la versione della funzionalità.

9. Completa la configurazione e distribuisci la funzionalità di fatturazione elettronica nell'ambiente del servizio. Per altre informazioni, vedi [Completare, pubblicare e distribuire una funzionalità di globalizzazione](e-invoicing-complete-publish-deploy-globalization-feature.md).
