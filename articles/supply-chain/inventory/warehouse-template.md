---
title: Impostare un magazzino utilizzando un modello di configurazione magazzino
description: In questo articolo viene illustrato come impostare un magazzino utilizzando un modello di configurazione magazzino.
author: yufeihuang
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 737b6f2f645ff270e5a49d54ca7542df3c075f94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856108"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Impostare un magazzino utilizzando un modello di configurazione magazzino

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come impostare un magazzino utilizzando un modello di configurazione magazzino. Esistono vari modelli di configurazione predefiniti da utilizzare. Per informazioni su come utilizzare tali modelli, vedere [Modelli di dati di configurazione](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Scenari in cui i modelli di configurazione possono essere utili

I modelli di configurazione possono essere utili in molti scenari. Di seguito sono riportati alcuni esempi.

- È stata completata e verificata una configurazione impostata in un ambiente di test e ora si desidera copiare l'impostazione in un ambiente di produzione.
- Si desidera eseguire l'implementazione del magazzino per più persone giuridiche o creare un nuovo magazzino nella stessa persona giuridica.
- Si desidera prepararsi rapidamente per una demo della funzionalità del magazzino.
- Si desidera che gli articoli e i magazzini esistenti utilizzino la funzionalità In Gestione del magazzino anziché la funzionalità nella Gestione inventario.

In questo articolo ci si concentra sul primo di questi scenari. Mostra come utilizzare un modello di configurazione per copiare una configurazione impostata da un ambiente di test a un ambiente di produzione.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Copiare una configurazione impostata da un ambiente di test a un ambiente di produzione

Per questo scenario, le impostazioni di configurazione per un magazzino e alcuni processi di transazione sono già esistenti in un ambiente di test. Ora si desidera copiare la configurazione impostata per il magazzino dall'ambiente di test a un ambiente di produzione.

> [!NOTE]
> È importante includere altri dati di configurazione correlati quando si copia un'impostazione di configurazione. Ad esempio, se si desiderano impostare i prodotti copiando le impostazioni da un ambiente di test. Tuttavia, non è possibile impostare un'ubicazione di prelievo fissa per un prodotto prima che il prodotto venga creato. Sebbene i singoli modelli di configurazione non supportino questo tipo di dipendenza, sono presenti modelli di dati predefiniti che lo supporto. È possibile includere facilmente questi modelli di dati predefiniti in un processo di configurazione.

### <a name="export-a-default-warehouse-template"></a>Esportare un modello di magazzino predefinito 

1. Aprire l'area di lavoro **Gestione dei dati**.

    > [!NOTE]
    > Se si utilizza per la prima volta questa area di lavoro, è necessario caricare tutte le entità di dati prima di continuare.

2. Selezionare il riquadro **Modelli** e quindi **Carica modelli predefiniti** per caricare i modelli predefiniti.

    > [!NOTE]
    > **Carica modelli predefiniti** è disponibile solo nella visualizzazione **migliorata**. Selezionare **Parametri framework** e quindi nel campo **Visualizza valori predefiniti** selezionare **Visualizzazione migliorata**.

3. Dopo che i modelli predefiniti vengono caricati, è possibile modificarli in modo che soddisfacciano i requisiti aziendali.

    > [!NOTE]
    > Per caricare i modelli predefiniti e i modelli di importazione, è necessario disporre di accesso come amministratore di sistema. Tale requisito assicura che tutte le entità vengano caricate correttamente nel modello.

4. Assicurarsi di essere nella persona giuridica da cui si desidera esportare i dati specifici della società.
5. Nell'area di lavoro selezionare **Esporta**.
6. Crea un nuovo progetto di esportazione
7. Selezionare **+ Aggiungi modello** e trovare il modello di magazzino predefinito **400 - WMS**. Questo modello aggiungere le entità di dati per la configurazione del magazzino.

    > [!NOTE]
    > Se i dati da esportare devono essere filtrati, ad esempio se si desidera esportare solo i dati relativi al magazzino specifico, è necessario valutare ciascuna entità di dati e aggiungere il filtro tramite una query. In alternativa, è possibile esportare tutti i dati e quindi eliminare i record che non sono necessari nei file di destinazione.

8. Selezionare **Esporta**. I dati correlati a tutte le entità di dati del progetto vengono esportati.

È possibile scaricare un file ZIP per il pacchetto dati. Questo file contiene tutti i dati nel formato selezionato, ad esempio formato Excel. Come menzionato, è possibile che alcuni record nei file di pacchetto dati debbano essere aggiornati prima di poter eseguire l'importazione nell'ambiente di produzione. Se si aggiorna un record, assicurarsi di non modificare il nome del file.

### <a name="import-a-warehouse-configuration-setup"></a>Importare un'impostazione di configurazione magazzino

1. Nell'ambiente di destinazione, verificare di trovarsi nella società in cui si desidera importare i dati di in magazzino.

    > [!NOTE]
    > Prima di eseguire l'importazione, è necessario identificare tutte le dipendenze dei dati. Ad esempio, il modello **Gestione magazzino** include un'entità di dati **Codici di smaltimento magazzino**. Questa entità contiene dati correlati all'impostazione **Codici smaltimento** (**Gestione magazzino** > **Impostazione** > **Dispositivo mobile** > **Codici smaltimento**). Se un'impostazione esistente già gestisce il processo di reso per gli ordini cliente, il campo **Codice smaltimento reso** contiene un valore. Il codice di smaltimento in questo campo è correlato all'entità di dati **Codice smaltimento**, che fa parte del modello **Vendite e marketing**. Se i dati dell'entità di dati **Codice smaltimento** non vengono importati prima dei dati del campo **Codici di smaltimento magazzino**, l'importazione avrà esito negativo.

2. Nell'area di lavoro **Gestione dei dati** selezionare **Importazione**.
3. Creare un nuovo progetto di importazione.
4. Selezionare **+ Aggiungi file** e caricare il file ZIP per il pacchetto dati.
5. Selezionare **Importa**. Nella visualizzazione **Migliorata** è possibile utilizzare l'opzione **Filtro** per visualizzare rapidamente una panoramica dei problemi che possono verificarsi durante l'importazione.

In **Visualizza registro di esecuzione** vengono fornite informazioni dettagliate su ciascuna entità di dati da importare. È possibile utilizzare la visualizzazione dei dati di gestione temporanea per visualizzare rapidamente i dati di destinazione. In questo modo, è possibile visualizzare come appaiono i dati importati nelle pagine correlate nell'applicazione. Quando si utilizzano i modelli di dati predefiniti, la sequenza di importazione per ogni entità di dati funziona in modo predefinito per garantire che tutti i dati dipendenti vengano importati per primi. Se le entità di dati personalizzate fanno parte del progetto, verificare che la sequenza corretta sia definita. Per ulteriori informazioni, vedere [Modelli di dati di configurazione](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

Per ulteriori informazioni su come utilizzare il modello di magazzino per copiare la configurazione di un magazzino da una società a una nuova società all'interno della stessa istanza, guardare questo video di 3 minuti su YouTube su [come utilizzare il modello di magazzino per copiare la configurazione di Finance and Operations](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-article"></a>Articolo correlato

[Modelli di dati di configurazione](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]