---
title: Creare un'app di esportazione dati ricorrente
description: In questo articolo viene illustrato come creare un'app di logica Microsoft Azure che esporta dati da Microsoft Dynamics 365 Human Resources in modo ricorrente.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 97972d2179c42e9d2d672cbebb75643ef0a02a62
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113088"
---
# <a name="create-a-recurring-data-export-app"></a>Creare un'app di esportazione dati ricorrente

In questo articolo viene illustrato come creare un'app di logica Microsoft Azure che esporta dati da Microsoft Dynamics 365 Human Resources in modo ricorrente. Il tutorial utilizza l'API REST del pacchetto DMF di Human Resources per esportare i dati. Dopo che i dati sono stati esportati, l'app di logica salva il pacchetto dati esportato in una cartella di Microsoft OneDrive for Business.

## <a name="business-scenario"></a>Scenario aziendale

In uno scenario aziendale tipico per le integrazioni di Microsoft Dynamics 365, i dati devono essere esportati in un sistema downstream secondo una programmazione ricorrente. Questa esercitazione mostra come esportare tutti i record dei lavoratori da Microsoft Dynamics 365 Human Resources e salva l'elenco dei lavoratori in una cartella di OneDrive for Business.

> [!TIP]
> I dati specifici esportati in questa esercitazione e la destinazione dei dati esportati sono solo esempi. È possibile modificarli facilmente in base alle proprie esigenze aziendali.

## <a name="technologies-used"></a>Tecnologie utilizzate

Questo tutorial utilizza le seguenti tecnologie:

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**- L'origine dati master per i lavoratori che verranno esportati.
- **[App per la logica di Azure](https://azure.microsoft.com/services/logic-apps/)** - La tecnologia che fornisce l'orchestrazione e la pianificazione dell'esportazione ricorrente.

    - **[Connettori](https://docs.microsoft.com/azure/connectors/apis-list)** - La tecnologia utilizzata per connettere l'app per la logica agli endpoint richiesti.

        - Connettore [HTTP con Azure AD](https://docs.microsoft.com/connectors/webcontents/)
        - Connettore [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)

- **[API REST del pacchetto DMF](../dev-itpro/data-entities/data-management-api.md)** - La tecnologia utilizzata per attivare l'esportazione e monitorarne l'avanzamento.
- **[OneDrive for Business](https://onedrive.live.com/about/business/)** - La destinazione per i lavoratori esportati.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare questa esercitazione, è necessario disporre dei seguenti elementi:

- Un ambiente di Human Resources con autorizzazioni a livello di amministratore nell'ambiente
- Una [sottoscrizione di Azure ](https://azure.microsoft.com/free/) per ospitare l'app per la logica

## <a name="the-exercise"></a>Esercitazione

Alla fine di questa esercitazione, si disporrà di un'app per la logica connessa all'ambiente di Human Resources e all'account OneDrive for Business. L'app per la logica esporterà un pacchetto di dati da Human Resources, attenderà il completamento dell'esportazione, scaricherà il pacchetto di dati esportato e salverà il pacchetto di dati nella cartella di OneDrive for Business specificata.

L'app per la logica completata sarà simile alla seguente illustrazione.

![Panoramica dell'app per la logica](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>Passaggio 1: creare un progetto di esportazione di dati in Human Resources

In Human Resources, creare un progetto di esportazione di dati che esporta i lavoratori. Assegnare al progetto il nome **Esportazione lavoratori** e assicurarsi che l'opzione **Genera pacchetto dati** sia impostata su **Sì**. Aggiungere una singola entità (**Lavoratore**) al progetto e selezionare il formato in cui esportare (in questa esercitazione viene utilizzato il formato Microsoft Excel).

![Progetto dati Esportazione lavoratori](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Prendere nota del nome del progetto di esportazione di dati. Dovrà essere utilizzato quando si crea l'app per la logica nel passaggio successivo.

### <a name="step-2-create-the-logic-app"></a>Passaggio 2: creare l'app per la logica

La maggior parte dell'esercitazione prevede la creazione dell'app per la logica.

1. Nel portale di Azure, creare un'app per la logica.

    ![Pagina di creazione dell'app per la logica](media/integration-logic-app-creation-1.png)

2. Nella finestra di progettazione di app per la logica, iniziare con un'app per la logica vuota.
3. Aggiungere un [trigger di programmazione della ricorrenza ](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) per eseguire l'app per la logica ogni 24 ore (o in base alla programmazione scelta).

    ![Finestra di dialogo Ricorrenza](media/integration-logic-app-recurrence-step.png)

4. Chiamare l'API REST DMF [ExportToPackage ](../dev-itpro/data-entities/data-management-api.md#exporttopackage) per pianificare l'esportazione del pacchetto di dati.

    1. Utilizzare l'azione **Richiama richiesta HTTP** dal connettore HTTP con Azure AD.

        - **URL risorsa di base:** l'URL dell'ambiente di Human Resources (non includere l'informazione path/namespace).
        - **URI risorsa Azure AD:** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > Il servizio Human Resources non fornisce ancora un connettore che espone tutte le API che compongono l'API REST del pacchetto DMF, come **ExportToPackage**. È invece necessario chiamare le API utilizzando le richieste HTTPS non elaborate tramite il connettore HTTP con Azure AD. Questo connettore utilizza Azure Active Directory (Azure AD) per l'autenticazione e l'autorizzazione a Human Resources.

        ![Connettore HTTP con Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. Accedere all'ambiente di Human Resources tramite il connettore HTTP con Azure AD.
    3. Impostare una richiesta **POST** HTTP per chiamare l'API REST DMF **ExportToPackage**.

        - **Metodo:** POST
        - **URL della richiesta:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **Corpo della richiesta:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Azione Richiama richiesta HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > È possibile che si intenda rinominare ogni passaggio di modo che risulti più descrittivo del nome predefinito, **Richiamare una richiesta HTTP**. Ad esempio, è possibile rinominare questo passaggio **ExportToPackage**.

5. [Inizializzare una variabile](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) per memorizzare lo stato di esecuzione della richiesta **ExportToPackage**.

    ![Azione Inizializza variabile](media/integration-logic-app-initialize-variable-step.png)

6. Attendere fino a quando lo stato di esecuzione dell'esportazione dei dati è **Operazione completata**.

    1. Aggiungere un [ciclo Until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) che si ripete fino a che il valore della variabile **ExecutionStatus** non è **Operazione completata**.
    2. Aggiungere un'azione **Ritarda** che attende cinque secondi prima di eseguire il polling dello stato di esecuzione corrente dell'esportazione.

        ![Contenitore del ciclo Until](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Impostare il valore del limite su **15** per attendere un massimo di 75 secondi (15 iterazioni × 5 secondi) per il completamento dell'esportazione. Se l'esportazione richiede più tempo, regolare il valore del limite in base alle esigenze.        

    3. Aggiungere un'azione **Richiama richiesta HTTP** per chiamare l'API REST DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) e impostare la variabile **ExecutionStatus** sul risultato della risposta **GetExecutionSummaryStatus**.

        > Questo esempio non esegue il controllo degli errori. L'API **GetExecutionSummaryStatus** può restituire stati terminali non riusciti (ovvero stati diversi da **Operazione completata**). Per ulteriori informazioni, vedere la [documentazione API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).

        - **Metodo:** POST
        - **URL della richiesta:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **Corpo della richiesta:** corpo('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > Potrebbe essere necessario inserire il valore **Corpo della richiesta** nella visualizzazione codice o nell'editor di funzioni nella finestra di progettazione.

        ![Azione Richiama richiesta HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Azione Imposta variabile](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > Il valore dell'azione **Imposta variabile** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) differirà dal valore del corpo della richiesta **Richiama richiesta HTTP 2** anche se la finestra di progettazione mostrerà i valori allo stesso modo.

7. Ottenere l'URL di download del pacchetto esportato.

    - Aggiungere un'azione **Richiama richiesta HTTP** per chiamare l'API REST DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).

        - **Metodo:** POST
        - **URL della richiesta:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **Corpo della richiesta:** {"executionId": body('GetExportedPackageURL')?['value']}

        ![Azione GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. Scaricare il pacchetto esportato.

    - Aggiungere una richiesta **GET** HTTP (un'[azione del connettore HTTP](https://docs.microsoft.com/azure/connectors/connectors-native-http)) integrata per scaricare il pacchetto dall'URL restituito nel passaggio precedente.

        - **Metodo:** GET
        - **URI:** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > Potrebbe essere necessario immettere il valore **URI** nella visualizzazione codice o nell'editor di funzioni nella finestra di progettazione.

        ![Azione GET HTTP](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > Questa richiesta non richiede alcuna autenticazione aggiuntiva, in quanto l'URL che l'API **GetExportedPackageUrl** restituisce include un token di firme di accesso condiviso che concede l'accesso per scaricare il file.

9. Salvare il pacchetto scaricato utilizzando il connettore [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).

    - Aggiungere l'azione [Crea file](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) di OneDrive for Business.
    - Connettersi all'account OneDrive for Business, come necessario.

        - **Percorso cartella:** una cartella qualsiasi
        - **Nome file:** worker\_package.zip
        - **Contenuto file:** il corpo del passaggio precedente (contenuto dinamico)

        ![Azione Crea file](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>Passaggio 3: testare l'app per la logica

Per testare l'app per la logica, selezionare il pulsante **Esegui** nella finestra di progettazione. Vengono eseguiti i passaggi per l'esecuzione dell'app per la logica. L'esecuzione dell'app per la logica dovrebbe terminare dopo 30-40 secondi e la cartella di OneDrive for Business dovrebbe includere un nuovo file di pacchetto contenente i lavoratori esportati.

Se viene segnalato un errore per un qualsiasi passaggio, selezionare quel passaggio nella finestra di progettazione ed esaminarne i campi **Input** e **Output**. Eseguire il debug e rettificare il passaggio come necessario per correggere gli errori.

L'illustrazione seguente mostra l'aspetto della finestra di progettazione di app per la logica quando tutti i passaggi dell'app per la logica vengono eseguiti correttamente.

![Esecuzione senza errori dell'app per la logica](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Riepilogo

In questa esercitazione, si è imparato a utilizzare un'app per la logica per esportare dati da Human Resources e a salvare i dati esportati in una cartella OneDrive for Business. È possibile modificare i passaggi di questa esercitazione come necessario in base alle proprie esigenze aziendali.


