---
title: Aggiungere analisi alle aree di lavoro tramite Power BI Embedded
description: In questo argomento viene illustrato come importare un report di Power BI nella scheda Analisi di un'area di lavoro.
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5cfb2377ad290bff9c50819876d79a9d4b2a73d8
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848599"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Aggiungere analisi alle aree di lavoro tramite Power BI Embedded

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Questa funzionalità è supportata in Dynamics 365 for Finance and Operations (versione 7.2 e successiva).

## <a name="introduction"></a>Introduzione
In questo argomento viene illustrato come importare un report di Microsoft Power BI nella scheda **Analisi** di un'area di lavoro. Per l'esempio fornito qui, verrà estesa l'area di lavoro **Gestione prenotazione** nell'applicazione di gestione flotta per includere un'area di lavoro di analisi in una scheda **Analisi**.

## <a name="prerequisites"></a>Prerequisiti
+ Accedere a un ambiente di sviluppo in cui è in esecuzione l'aggiornamento 8 della piattaforma o una versione successiva.
+ Un report analitico (file .pbix) creato utilizzando Microsoft Power BI Desktop e con un modello dati che ha origine dal database dell'archivio dell'entità.

## <a name="overview"></a>Panoramica
Se si estende un'area di lavoro dell'applicazione esistente o si introduce una nuova area di lavoro propria, è possibile utilizzare le visualizzazioni analitiche importate per offrire visualizzazioni perspicaci e interattive dei dati aziendali. Il processo per l'aggiunta di una scheda analitica dell'area di lavoro è costituito da quattro passaggi.

1. Aggiungere un file .pbix come risorsa Dynamics 365.
2. Definire una scheda analitica dell'area di lavoro.
3. Importare la risorsa .pbix nella scheda dell'area di lavoro.
4. Facoltativo: aggiungere le estensioni per personalizzare la visualizzazione.

> [!NOTE]
> Per ulteriori informazioni su come creare report analitici, vedere [Introduzione a Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/). Questa pagina offre notevoli approfondimenti che consentono di creare soluzioni efficaci per la creazione di report analitici.

## <a name="add-a-pbix-file-as-a-resource"></a>Aggiungere un file .pbix come risorsa
Prima di iniziare è necessario creare o visualizzare il report di Power BI che verrà importato nell'area di lavoro. Per ulteriori informazioni su come creare report analitici, vedere [Introduzione a Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).

Seguire questi passaggi per aggiungere un file .pbix come elemento del progetto di Visual Studio.

1. Creare un nuovo progetto nel modello appropriato.
2. In Esplora soluzioni selezionare il progetto, fare clic con il pulsante destro del mouse e quindi selezionare **Aggiungi** \> **Nuovo elemento**.
3. Nella finestra di dialogo **Aggiungi nuovo articolo**, in **Elementi operazioni**, selezionare il modello **Risorsa**.
4. Immettere un nome che verrà utilizzato per fare riferimento al report nei metadati X++, quindi fare clic su **Aggiungi**.

    ![Finestra di dialogo Aggiungi nuovo articolo](media/analytical-workspace-add.png)

5. Individuare il file .pbix contenente la definizione di report analitico, quindi fare clic su **Apri**.

    ![Selezionare una finestra di dialogo del file di risorse](media/analytical-workspace-select-resource.png)

Dopo aver aggiunto un file .pbix come risorsa Dynamics 365, è possibile importare i report nelle aree di lavoro e aggiungere collegamenti diretti utilizzando le voci di menu.

## <a name="add-a-tab-control-to-an-application-workspace"></a>Aggiungere un controllo della scheda a un'area di lavoro dell'applicazione
In questo esempio verrà estesa l'area di lavoro **Gestione prenotazione** del modello di gestione flotta aggiungendo la scheda **Analisi** alla definizione del modulo **FMClerkWorkspace**.

Nella figura che segue viene mostrato l'aspetto del modulo **FMClerkWorkspace** nello strumento di progettazione in Microsoft Visual Studio.

![Il modulo FMClerkWorkspace prima delle modifiche](media/analytical-workspace-definition-before.png)

Seguire questi passaggi per estendere la definizione di modulo per l'area di lavoro **Gestione prenotazione**.

1. Aprire lo strumento di progettazione del modulo per estendere la definizione di progettazione.
2. Nella definizione di progettazione selezionare l'elemento principale che è contrassegnato come **Progettazione | Modello: Area di lavoro operativa**.
3. Fare clic con il pulsante destro del mouse e selezionare **Nuovo** \> **Scheda** per aggiungere un controllo nuovo denominato **FormTabControl1**.
4. Nello strumento di progettazione del modulo selezionare **FormTabControl1**.
5. Fare clic con il pulsante destro del mouse e scegliere **Nuova scheda** per aggiungere una nuova scheda.
6. Assegnare alla scheda un nome significativo, ad esempio **Area di lavoro**.
7. Nello strumento di progettazione del modulo selezionare **FormTabControl1**.
8. Fare clic con il pulsante destro del mouse e scegliere **Nuova scheda**.
9. Assegnare alla scheda un nome significativo, ad esempio **Analisi**.
10. Nello strumento di progettazione del modulo selezionare **Analisi (scheda)**.
11. Impostare la proprietà **Titolo** su **Analisi**.
12. Fare clic con il pulsante destro del mouse sul controllo e quindi selezionare **Nuovo** \> **Gruppo** per aggiungere un nuovo controllo gruppo di moduli.
13. Assegnare al gruppo di moduli un nome significativo, ad esempio **powerBIReportGroup**.
14. Nello strumento di progettazione del modulo selezionare **PanoramaBody (scheda)**, quindi trascinare il controllo sulla scheda **Area di lavoro**.
15. Nella definizione di progettazione selezionare l'elemento principale che è contrassegnato come **Progettazione | Modello: Area di lavoro operativa**.
16. Fare clic con il pulsante destro del mouse e scegliere **Rimuovi criterio**.
17. Fare di nuovo clic con il pulsante destro del mouse e quindi selezionare **Aggiungi modello** \> **Area di lavoro a schede**.
18. Eseguire una build per verificare le modifiche.

Nell'illustrazione riportata di seguito viene mostrato l'aspetto della progettazione dopo l'applicazione di tali modifiche.

![FMClerkWorkspace dopo le modifiche](media/analytical-workspace-definition-after.png)

Dopo aver aggiunto i controlli del modulo che verranno utilizzati per includere il report dell'area di lavoro, è necessario definire la dimensione del controllo padre in modo che si adatti al layout. Per impostazione predefinita, sia la pagina **Riquadro filtri** che la pagina **Scheda** saranno visibili nel report. Tuttavia, è possibile modificare la visibilità di questi controlli a seconda del cliente di destinazione del report.

> [!NOTE]
> Per le aree di lavoro incluse, si consiglia di utilizzare le estensioni per nascondere sia la pagina **Scheda** che la pagina **Riquadro filtri**, per coerenza.

L'attività di estensione della definizione di modulo dell'applicazione è stata completata. Per ulteriori informazioni su come utilizzare le estensioni per effettuare personalizzazioni, vedere [Personalizzazione: overlayering ed estensioni](../extensibility/customization-overlayering-extensions.md).

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>Aggiungere la regola business X++ per importare un controllo del visualizzatore
Seguire questi passaggi per aggiungere la regola business che inizializza il controllo del visualizzatore di report incluso nell'area di lavoro **Gestione prenotazione**.

1. Aprire lo strumento di progettazione del modulo **FMClerkWorkspace** per estendere la definizione di progettazione.
2. Premere F7 per accedere al codice che sta dietro la definizione del codice.
3. Aggiungere il seguente codice X++.

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. Eseguire una build per verificare le modifiche.

L'attività di aggiunta della regola business per inizializzare il controllo del visualizzatore di report incluso è stata completata. Nell'illustrazione riportata di seguito viene mostrato l'aspetto dell'area di lavoro dopo l'applicazione di tali modifiche.

![Report incluso nell'area di lavoro](media/analytical-workspace-final.png)

> [!NOTE]
> È possibile accedere alla visualizzazione operativa esistente utilizzando le schede dell'area di lavoro sotto il titolo della pagina.

## <a name="reference"></a>Riferimento

### <a name="pbireporthelperinitializereportcontrol-method"></a>Metodo PBIReportHelper.initializeReportControl
In questa sezione vengono fornite informazioni sulla classe degli helper utilizzata per importare un report di Power BI (risorsa .pbix) in un controllo del gruppo di moduli.

#### <a name="syntax"></a>Sintassi
```
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>Parametri

| Nome             | descrizione                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | Nome della risorsa .pbix.                                                                              |
| formGroupControl | Controllo del gruppo di moduli al quale applicare il controllo del report Power BI.                                              |
| defaultPageName  | Nome della pagina predefinita.                                                                                       |
| showFilterPane   | Valore booleano che indica se il riquadro filtri deve essere visualizzato (**True**) o nascosto (**False**).     |
| showNavPane      | Valore booleano che indica se il riquadro di spostamento deve essere visualizzato (**True**) o nascosto (**False**). |
| defaultFilters   | Filtri di base per il report Power BI.                                                                 |
