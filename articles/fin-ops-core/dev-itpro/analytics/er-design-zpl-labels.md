---
title: Progettare una nuova soluzione per i report elettronici per stampare etichette ZPL
description: Questo articolo spiega come progettare una nuova soluzione di reporting elettronico (ER) per stampare etichette ZPL (Zebra Programming Language).
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: f861fe63c6d7d00d0a9f84d33c0d1b1b23735b61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845717"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Progettare una nuova soluzione per i report elettronici per stampare etichette ZPL

[!include [banner](../includes/banner.md)]


Questo articolo spiega come un utente con il ruolo di amministratore di sistema, sviluppatore per la creazione di report elettronici o consulente funzionale per la creazione di report elettronici può configurare i parametri del framework di [Creazione di report elettronici (ER)](general-electronic-reporting.md), progettare le [configurazioni](general-electronic-reporting.md#Configuration) ER richieste per una nuova soluzione ER per accedere ai dati del sistema di gestione del magazzino e generare etichette di ubicazione di magazzino personalizzate in formato Zebra Programming Language (ZPL). Queste operazioni possono essere completate nella società **USRT**.

## <a name="business-scenario"></a>Scenario aziendale

Rappresenti un'azienda che ha implementato la gestione del magazzino in Microsoft Dynamics 365 Finance. Ogni ubicazione di magazzino deve essere etichettata con un'etichetta autoadesiva che includa un codice a barre. Gli addetti al magazzino utilizzeranno lettori di codici a barre portatili per scansionare i codici a barre.

Tutte le ubicazioni di magazzino sono state etichettate nell'ambito delle attività precedenti al passaggio allo stato live. Tuttavia, devi anche essere in grado di stampare etichette di ubicazione del magazzino su richiesta se le etichette esistenti vengono danneggiate o se le scaffalature del magazzino vengono riconfigurate. Utilizzando la funzionalità ER rilasciata di recente, è possibile configurare una nuova soluzione ER che consente a un supervisore di magazzino di stampare etichette direttamente su una stampante termica per etichette.

## <a name="configure-the-er-framework"></a>Configurare il framework ER

Segui i passaggi in [Configurare il framework ER](er-quick-start2-customize-report.md#ConfigureFramework) per impostare il set minimo di parametri ER. È necessario completare questa configurazione prima di iniziare a utilizzare il framework ER per progettare una nuova soluzione ER.

## <a name="design-a-domain-specific-data-model"></a>Progettare un modello di dati specifici di un dominio

Crea una nuova configurazione ER che contenga un componente [modello di dati](er-overview-components.md#data-model-component) per il dominio di gestione del magazzino. Questo modello di dati verrà utilizzato come origine dati quando si progetta un formato ER per generare le etichette di ubicazione di magazzino.

### <a name="import-a-data-model-configuration"></a>Importare una configurazione del modello di dati

Segui questi passaggi per importare il modello di dati obbligatorio da un file XML fornito da Microsoft. In alternativa, puoi creare il tuo modello di dati come descritto nella sezione successiva.

1. Scarica il file [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) e salvalo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella pagina **Configurazioni**, nel riquadro Azioni, seleziona **Exchange** \> **Carica da file XML**.
5. Seleziona **Sfoglia**, quindi trova e seleziona il file **Warehouse model.version.1.xml**.
6. Selezionare **OK** per importare la configurazione.

![Configurazione del modello di dati ER importata nella pagina Configurazioni.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Creare una configurazione del modello di dati

Invece di importare il file del modello di dati fornito da Microsoft, puoi creare un modello di dati da zero. Per un esempio che mostra come completare questa attività, vedi [Creare una nuova configurazione del modello di dati](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Esaminare il modello di dati

È possibile visualizzare una versione modificabile del modello dati configurato nella pagina **Progettazione del modello di dati**.

![Struttura del modello dati ER nella pagina Progettazione del modello di dati.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Progettare un mapping del modello per il modello di dati configurato

In qualità di utente nel ruolo di sviluppatore per la creazione di report elettronici, è necessario creare una nuova configurazione ER che contenga un componente [mapping del modello](er-overview-components.md#model-mapping-component) per il modello di dati di magazzino. Questo componente implementa il modello di dati configurato per Dynamics 365 Finance ed è specifico di tale app. È necessario configurarlo per specificare gli oggetti dell'applicazione che devono essere utilizzati per compilare il modello di dati configurato con i dati dell'applicazione in fase di runtime. Per completare questa attività, è necessario essere a conoscenza di come la struttura dati del dominio aziendale di gestione del magazzino viene implementata in Finance.

### <a name="import-a-model-mapping-configuration"></a>Importare una configurazione del mapping del modello

Segui questi passaggi per importare il mapping del modello obbligatorio da un file XML fornito da Microsoft. In alternativa, puoi creare il tuo mapping del modello come descritto nella sezione successiva.

1. Scarica il file [Warehouse model mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) e salvalo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella pagina **Configurazioni**, nel riquadro Azioni, seleziona **Exchange** \> **Carica da file XML**.
5. Seleziona **Sfoglia**, quindi trova e seleziona il file **Warehouse model mapping.version.1.1.xml**.
6. Selezionare **OK** per importare la configurazione.

![Configurazione del mapping del modello ER importata nella pagina Configurazioni.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Creare una configurazione del mapping di modello

Invece di importare il file del mapping del modello da Microsoft, puoi creare un mapping del modello da zero. Per un esempio che mostra come completare questa attività, vedi [Creare una nuova configurazione del mapping del modello](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>Esaminare il mapping di modello

È possibile visualizzare una versione modificabile del mapping del modello configurato nella pagina **Progettazione mapping modello**.

![Struttura del mapping del modello ER nella pagina Progettazione mapping modello.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Progettare un formato

In qualità di utente nel ruolo di consulente funzionale per la creazione di report elettronici, è necessario creare una nuova configurazione ER che contenga un componente di [formato](er-overview-components.md#format-component). Per configurare questo componente, utilizzerai il codice ZPL II per specificare il layout dell'etichetta dell'ubicazione del magazzino.

### <a name="import-a-format-configuration"></a>Importare una configurazione del formato

Segui questi passaggi per importare il formato obbligatorio da un file XML fornito da Microsoft. In alternativa, puoi creare il tuo formato come descritto nella sezione successiva.

1. Scarica il file [Warehouse location labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) e salvalo sul computer locale.
2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni report**.
4. Nella pagina **Configurazioni**, nel riquadro Azioni, seleziona **Exchange** \> **Carica da file XML**.
5. Seleziona **Sfoglia**, quindi trova e seleziona il file **Warehouse location labels.version.1.1.xml**.
6. Selezionare **OK** per importare la configurazione.

![Configurazione del formato ER importata nella pagina Configurazioni.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Creare una configurazione di formato

Invece di importare il file del formato fornito da Microsoft, puoi creare un formato da zero. Per un esempio che mostra come completare questa attività, vedi [Creare una nuova configurazione del formato](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>Esaminare il formato

È possibile visualizzare una versione modificabile del formato configurato nella pagina **Progettazione del formato**.

![Struttura del formato ER nella pagina Progettazione formato.](./media/er-design-zpl-labels-format.png)

L'origine dati `model.Location.Label` di questo formato è configurata per generare etichette che contengono le seguenti informazioni:

- Il titolo del magazzino come testo
- Il titolo del magazzino come codice a barre
- Il titolo dell'ubicazione
- Cifre di controllo

Nella pagina **Designer formula** per l'origine dati, la formula ER utilizzata per generare etichette include una funzione `CONCATENATE` che combina le informazioni nel layout desiderato.

![Formula per l'origine nella finestra Designer formula.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> Il layout dell'etichetta è progettato in modo che il titolo dell'ubicazione e le cifre di controllo siano allineati al centro dell'etichetta. Tuttavia, ZPL II non supporta l'allineamento centrale per i codici a barre. Pertanto, la formula dell'origine dati `model.Location.Warehouse.Alignment` viene utilizzata per allineare il codice a barre al centro dell'etichetta. Questa formula calcola l'offset sinistro del codice a barre, in base al numero di caratteri nel titolo del magazzino.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>Prepara il tuo ambiente per visualizzare in anteprima le etichette generate

L'esempio seguente utilizza un'applicazione di emulazione stampante per etichette ZPL per mostrare un'anteprima delle etichette generate sullo schermo. Segui questi passaggi per abilitare questa opzione.

1. Aggiungi la destinazione ER [Stampante](er-destination-type-print.md) per il formato ER **Etichetta ubicazione di magazzino** e configurala per inviare le etichette generate da Finance all'[agente di distribuzione documenti](install-document-routing-agent.md).
2. Installa e configura l'agente di distribuzione documenti per instradare le etichette generate da Finance a una stampante locale accessibile dalla workstation corrente.
3. Aggiungi una stampante locale per la workstation corrente e configurala per passare le etichette generate dall'agente di distribuzione documenti a un'applicazione di emulazione della stampante.
4. Installa un'applicazione di emulazione di stampante come estensione del browser Web Chrome e configurala per passare le etichette generate da una stampante locale a un servizio Web che eseguirà il rendering delle etichette generate e le restituirà all'emulatore di stampante per l'anteprima.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>Report ER</p>
<p>Destinazione stampante</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Agente di distribuzione documenti</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Stampante locale</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Emulatore di stampante</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Servizio Web di rendering</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Installare e configurare un'applicazione di emulazione della stampante

Aggiungi un'applicazione di emulazione stampante per il motore di rendering ZPL al tuo browser Web Chrome. Questo esempio usa l'emulatore [Stampante Zpl](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) basato sul [servizio Web Labelary ZPL](http://labelary.com/service.html). L'applicazione dell'emulatore di stampante passerà le etichette generate in formato ZPL da una stampante locale al servizio Web e quindi restituirà le etichette come file PDF o PNG per l'anteprima.

1. Nel Chrome Web Store, trova e seleziona l'applicazione dell'emulatore di stampante che desideri utilizzare. Quindi seleziona **Aggiungi a Chrome** per aggiungerlo al tuo Web browser Chrome.

    ![Aggiunta dell'applicazione dell'emulatore di stampante al Web browser Chrome dal Chrome Web Store.](./media/er-design-zpl-labels-add-app.png)

2. Seleziona **Avvia app** per eseguire l'applicazione dell'emulatore di stampante dal Web browser Chrome.

    ![Esecuzione dell'applicazione dell'emulatore di stampante dal Web browser Chrome.](./media/er-design-zpl-labels-run-app.png)

3. Configura l'applicazione in esecuzione:

    1. Disattiva l'applicazione.
    2. Nelle impostazioni della stampante, imposta l'host su **127.0.0.1**.
    3. Imposta la porta su **9100**.

        ![Configurazione dell'applicazione di emulazione della stampante.](./media/er-design-zpl-labels-configure-app.png)

    4. Riattiva l'applicazione. Dovresti ricevere un messaggio che indica che la stampante è stata avviata sull'host e sulla porta specificati.

        ![L'applicazione dell'emulatore di stampante è stata riattivata.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Poiché l'applicazione dell'emulatore di stampante utilizzata in questo esempio si basa su un servizio Web per il rendering delle etichette, assicurarsi che le impostazioni di sicurezza consentano di comunicare con il servizio. In caso contrario, l'applicazione non riceverà le etichette sottoposte a rendering e non sarà disponibile alcuna anteprima di tali etichette.

### <a name="add-and-configure-a-local-printer"></a>Aggiungere e configurare una stampante locale

[Aggiungi una nuova stampante locale](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b) che il dispositivo possa utilizzare per passare le etichette generate dall'agente di distribuzione documenti a un'applicazione di emulazione della stampante.

1. In Windows, seleziona **Start** \> **Impostazioni** \> **Dispositivi** \> **Stampanti\& scanner**.
2. Seleziona **Impostazioni stampanti e scanner**.
3. Per **Aggiungi una stampante o uno scanner**, selezionare **Aggiungi dispositivo**.
4. Per **La stampante che voglio non è elencata**, seleziona **Aggiungi manualmente**.
5. Nel campo **Trova una stampante con altre opzioni**, seleziona **Aggiungi una stampante locale o una stampante di rete con le impostazioni manuali**.
6. Nel campo **Scegli una porta della stampante**, seleziona **Crea una nuova porta**, quindi segui questi passaggi:

    1. Nel campo **Tipo di porta**, seleziona **Porta TCP/IP standard**.
    2. Nel campo **Nome host o indirizzo IP**, immetti **127.0.0.1**.
    3. Nel campo **Nome porta**, immetti **ZPL**.
    4. Aspetta fino al completamento dell'operazione **Rilevamento porta TCP/IP**.
    5. Nel campo **Tipo di dispositivo**, seleziona **Personalizzato**, quindi seleziona **Impostazioni**.
    6. Verifica siano specificate le seguenti impostazioni della porta:

        - **Nome porta:** ZPL
        - **Nome stampante o indirizzo IP:** 127.0.0.1
        - **Protocollo:** Non elaborato
        - **Numero porta:** 9100

7. Nel campo **Installa il driver della stampante**, seleziona **Generico/Solo testo**.
8. Nel campo **Nome stampante**, immetti **ZebraPrinter**.

![Aggiunta di una stampante locale per il dispositivo corrente.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>Installare e configurare DRA

Prepara l'agente di distribuzione documenti per trasferire le etichette generate da Finance alla stampante locale configurata.

1. [Installa l'agente di distribuzione documenti](install-document-routing-agent.md#install-the-document-routing-agent).
2. [Configura l'agente di distribuzione documenti](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [Registra la stampante locale](install-document-routing-agent.md#register-network-printers) nell'agente di distribuzione documenti.
4. [Attiva la stampante locale](install-document-routing-agent.md#administer-network-printers) nel tuo ambiente finanziario.

![Preparazione dell'agente di distribuzione documenti per stampare le etichette generate.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>Configurare la destinazione ER

Prepara la destinazione ER per trasferire le etichette generate da Finance all'agente di distribuzione documenti.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Destinazione report elettronici**.
2. Nella pagina di **Destinazione Creazione di report elettronici** , nel riquadro Azione, seleziona **Nuovo**.
3. Nel campo **Riferimento**, seleziona **Etichette ubicazione magazzino**.
4. Sulla Scheda dettaglio **Destinazione file**, selezionare **Nuovo**.
5. Nel campo **Nome** immettere **Etichette**.
6. Nel campo **Nome componente file**, selezionare **Report**.
7. Selezionare **Impostazioni**.
8. Nella finestra di dialogo **Impostazioni di destinazione**, nella scheda **Stampante**, impostare l'opzione **Abilitato** per **Sì**.
9. Nel campo **Nome stampante**, seleziona **ZebraPrinter**.
10. Nel campo **Tipo di distribuzione documento** selezionare **ZPL**.
11. Seleziona **OK**.

![Configurazione della destinazione ER per il formato etichette di ubicazione di magazzino nella pagina di destinazione Creazione di report elettronici.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Rivedere le ubicazioni di magazzino

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Magazzino** \> **Ubicazioni**.
2. Nella pagina **Ubicazioni**, filtra per visualizzare solo le ubicazioni che hanno un valore nel campo **Cifre di controllo**.

![Revisione delle ubicazioni del magazzino nella pagina Ubicazioni.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Stampare etichette di ubicazione del magazzino

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni** nell'albero di configurazione, espandere **Modello di magazzino** e selezionare **Etichette ubicazione magazzino**.
3. Nel Riquadro azioni selezionare **Esegui**.
4. Nella finestra di dialogo **Parametri creazione di report elettronici**, nella scheda **Record da includere**, seleziona **Filtro**.
5. Nella scheda **Intervallo**, trova la riga in cui il campo **Tabella** è impostato su **Ubicazione** e il campo **Campo** è impostato su **Ubicazione**. Nel campo **Criteri** immettere **LPEnabled**.
6. Seleziona **OK**.
7. Seleziona **OK**. Viene generata un'etichetta che viene visualizzata nella pagina di anteprima nell'applicazione di emulazione della stampante.

![Revisione di un'etichetta generata nella pagina di anteprima dell'applicazione di emulazione della stampante ZPL.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Modificare il layout di un'etichetta

È possibile modificare il layout corrente delle etichette di ubicazione del magazzino. L'esempio seguente mostra come modificare il layout in modo che le etichette generate includano un ID profilo ubicazione.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Imposta **Usa destinazioni per lo stato bozza** [parametro utente ER](electronic-reporting-destinations.md#applicability) su **Sì**.
3. Nella pagina **Configurazioni** nell'albero di configurazione, espandere **Modello di magazzino** e selezionare **Etichette ubicazione magazzino**.
4. Selezionare **Progettazione**.
5. Nella pagina **Progettazione formati**, nella scheda **Mapping**, seleziona l'origine dati `model.Location.Label`.
6. Nella finestra di dialogo **Proprietà origine dati** seleziona **Modifica** \> **Modifica formula**.
7. Nella pagina **Designer formule**, nel campo **Formula**, rivedi la formula ER utilizzata per generare etichette.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. Aggiorna la formula per aggiungere un ID profilo ubicazione alle etichette generate.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Seleziona **Salva**.
10. Seleziona **OK**.
11. Nel Riquadro azioni selezionare **Esegui**.
12. Nella finestra di dialogo **Parametri creazione di report elettronici**, nella scheda **Record da includere**, seleziona **Filtro**.
13. Nella scheda **Intervallo**, trova la riga in cui il campo **Tabella** è impostato su **Ubicazione** e il campo **Campo** è impostato su **Ubicazione**. Nel campo **Criteri** immettere **Hangar**.
14. Seleziona **OK**.
15. Seleziona **OK**. Viene generata un'etichetta che viene visualizzata nella pagina di anteprima nell'applicazione di emulazione della stampante.

![Revisione di un'etichetta generata che include un ID profilo di ubicazione nella pagina di anteprima dell'applicazione emulatore della stampante ZPL.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Codifica

> [!NOTE]
> È necessario sincronizzare l'impostazione di codifica del componente **Comune\\File** del formato ER modificabile e l'impostazione appropriata dell'etichetta progettata. Il valore del campo **[Codifica](er-suppress-bom-characters.md)** del componente **Comune\\File** non deve contraddire un comando ZPL utilizzato per controllare la codifica dell'etichetta (ad esempio, il comando `^CI`). ER non convalida che queste impostazioni siano sincronizzate.

## <a name="additional-resources"></a>Risorse aggiuntive

[Destinazione stampante](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
