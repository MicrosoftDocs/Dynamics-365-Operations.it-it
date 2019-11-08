---
title: Preparare metadati specifici dell'applicazione per RCS e ER
description: In questo argomento viene descritto come preparare metadati specifici dell'applicazione per Regulatory Configuration Service (RCS) e la creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 74750397dc344d74c018c27114357d3d05b95b7e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550109"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a>Preparare metadati specifici dell'applicazione per RCS e ER

[!include[banner](../includes/banner.md)]

In questo argomento vengono illustrati esempi delle seguenti attività:

- [Preparare i metadati dell'applicazione da utilizzare in RCS](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](#access-application-metadata-by-using-an-er-configuration)
- [Accedere ai metadati dell'applicazione utilizzando applicazioni connesse](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>Preparare i metadati dell'applicazione da utilizzare in RCS

La procedura seguente illustra come un utente con ruolo di **amministratore di sistema** o di **sviluppatore per la creazione di report elettronici** può creare una configurazione per la creazione di report elettronici (ER) che contiene metadati per l'applicazione e che viene utilizzata per la progettazione di configurazioni del mapping di modello ER in Regulatory Configuration Service (RCS). La configurazione del mapping di modello ER di esempio creata in questo esempio verrà utilizzata per accedere alle transazioni del commercio estero.

Per questo esempio, si desidera utilizzare RCS per progettare una soluzione ER per l'applicazione che verrà utilizzata per generare documenti elettronici contenenti informazioni del dominio aziendale per il commercio estero. Per specificare il mapping tra il modello di dati ER e le origini dei dati necessari, accedere ai metadati dell'applicazione in RCS. Di conseguenza, nell'ambito del processo di progettazione della soluzione ER è necessario configurare una nuova configurazione dei metadati ER contenente tutti i metadati attualmente necessari per generare report ER per il dominio aziendale selezionato.

> [!NOTE]
> In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società.

1. Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.
2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se il provider di configurazione non è visualizzato, completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Selezionare **Configurazioni dei metadati**.
4. Selezionare **Crea configurazione**.
5. Nella finestra di dialogo a discesa, nel campo **Nome**, immettere un nome. Per questo esempio, immettere **Metadati del commercio estero**.
6. Selezionare **Crea configurazione**.
7. Selezionare **Progettazione**.
8. Selezionare **Aggiungi**.

    > [!NOTE]
    > È possibile selezionare tutti i metadati per l'intera applicazione o per i modelli o moduli selezionati. In entrambi i casi, tenere presente che i seguenti metadati verranno aggiunti automaticamente: tabelle di record, enumerazioni e tipi di dati estesi. Se sono necessari ulteriori tipi di metadati, devono essere aggiunti manualmente.

È necessario aggiungere alcuni metadati correlati alle transazioni del commercio estero e selezionare manualmente elementi di metadati.

9. Selezionare **Aggiungi origine dati \> Record di tabella**.
10. Filtrare in base al valore **Intrastat** nel campo **Nome**.
11. Selezionare il record di tabella **Intrastat**.
12. Selezionare **OK**.

È necessario aggiungere informazioni sui metadati relative alla tabella di record Intrastat.

13. Nella struttura, selezionare **Record di tabella Intrastat \> \>Relazioni \> IntrastatCommodity (Record tabella EcoResCategory)**.
14. Selezionare **Aggiungi metadati**.

    > [!NOTE]
    > I metadati relativi alle relazioni necessarie per la tabella di record selezionata devono essere aggiunti manualmente.

15. Selezionare **Aggiungi origine dati**.
16. Selezionare **Enumerazione**.
17. Filtrare in base al valore **IntrastatDirection** nel campo **Nome**.
18. Selezionare il record di enumerazione **IntrastatDirection**.
19. Selezionare **OK**.
20. Selezionare **Salva**.
21. Chiudere la pagina.
22. Completare la versione bozza della configurazione dei metadati:

    1. Selezionare **Cambia stato \> Completa**.
    2. Selezionare **OK**.
    3. Selezionare la versione completata 1.

23. Esportare la versione completata della configurazione dei metadati dall'applicazione come file XML:

    1. Selezionare **Scambia \> Esporta come file XML**.
    2. Selezionare **OK**.

La configurazione dei metadati ER creata viene salvata come file **Metadati del commercio estero.xml**. È ora possibile importarla in RCS, di modo che possa essere utilizzata come origine dei metadati del dominio aziendale per il commercio estero. In base a queste informazioni, è possibile specificare il mapping tra i metadati dell'applicazione e il modello di dati ER.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Accedere ai metadati dell'applicazione utilizzando una configurazione ER

La seguente procedura illustra come un utente RCS con ruolo **Amministratore di sistema** o **Sviluppatore per la creazione di report elettronici** può progettare un nuovo mapping di modello ER utilizzando i metadati dell'applicazione. Sarà possibile accedere ai metadati dell'applicazione utilizzando la configurazione dei metadati ER contenente un set di metadati di esempio per accedere alle transazioni del commercio estero.

Prima di poter completare questa procedura, è necessario dapprima svolgere le seguenti procedure:

- [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [Preparare i metadati dell'applicazione da utilizzare in RCS](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.
2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se il provider di configurazione non è visualizzato, completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Importare la configurazione dei metadati ER che contiene i metadati per l'applicazione e che è configurata per generare documenti elettronici per il dominio aziendale per il commercio estero. Questa configurazione dei metadati ER è stata creata ed esportata come file XML nella procedura [Preparare i metadati dell'applicazione da utilizzare in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) vista in precedenza in questo argomento.

    1. Selezionare **Configurazioni dei metadati**.
    2. Selezionare **Scambia**.
    3. Selezionare **Carica da file XML**.
    4. Selezionare il file **Metadati del commercio estero.xml**.
    5. Selezionare **OK**.
    6. Chiudere la pagina.

4. Creare una configurazione del modello di dati:

    1. Selezionare **Configurazioni report**.
    2. Selezionare **Crea configurazione**.
    3. Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Modello del commercio estero**.
    4. Selezionare **Crea configurazione**.
    5. Selezionare **Progettazione**.
    6. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.

        1. Nel campo **Nome**, digitare **Radice**.
        2. Selezionare **Aggiungi**.
    
    7. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.

        1. Nel campo **Nome** digitare **Transazione**.
        2. Nel campo **Tipo di articolo** selezionare **Elenco di record**.
        3. Selezionare **Aggiungi**.
 
    8. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.

        1. Nel campo **Nome** digitare **Codice voce doganale**.
        2. Nel campo **Tipo di articolo** selezionare **Stringa**.
        3. Selezionare **Aggiungi**.

    9. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.

        1. Nel campo Nome digitare **Importo fatturato**.
        2. Nel campo **Tipo di articolo** selezionare **Reale**.
        3. Selezionare **Aggiungi**.

    10. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.

        1. Digitare **Data** nel campo **Nome**.
        2. Nel campo **Tipo di articolo** selezionare **Data**.
        3. Selezionare **Aggiungi**.
 
    11. Selezionare **Aggiungi \> Riferimento radice**.
    12. Selezionare **OK**.
    13. Selezionare **Salva**.
    14. Chiudere la pagina.
    15. Selezionare **Cambia stato \> Completa**.
    16. Selezionare **OK**.

5. Creare una configurazione del mapping di modello

    1. Selezionare **Crea configurazione**.
    2. Nella finestra di dialogo a discesa, nel campo **Nuovo** immettere **Mapping di modello basato sul modello di dati Modello del commercio estero**.
    3. Nel campo **Nome**, immettere **Mapping del commercio estero**.
    4. Selezionare **Crea configurazione**.
    5. Nella scheda dettaglio **Prerequisiti**, selezionare **Modifica**.
    6. Selezionare **Nuovo**.
    7. Nel campo **Tipo di componente prerequisito**, selezionare **Configurazione**.
    8. Selezionare la configurazione **Metadati del commercio estero**.
    9. Selezionare **Salva**. Da notare che il riferimento viene aggiunto alla versione 1 della configurazione **Metadati del commercio estero**. I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione del mapping di modello.
    10. Chiudere la pagina.
    11. Selezionare **Progettazione**.
    12. Selezionare **Progettazione**.
    13. Nella struttura selezionare **Dynamics 365 for Operations \> Record di tabella**.
    14. Selezionare **Aggiungi radice**.
    15. Nel campo **Nome** immettere **Intrastat**.
    16. Selezionare i record di tabella **Intrastat**.
    17. Selezionare **OK**.

        > [!NOTE]
        > Solo 2 tabelle sono disponibili poiché solo 2 tabelle sono state aggiunte al set di metadati attualmente utilizzato.

    18. Selezionare **Associa**.
    19. Nella struttura selezionare **Intrastat \> AmountMST**.
    20. Nella struttura selezionare **Transazione = Intrastat \> Importo fatturato**.
    21. Selezionare **Associa**.
    22. Nella struttura selezionare **Intrastat \> TransDate**.
    23. Nella struttura selezionare **Transazione = Intrastat \> Data**.
    24. Selezionare **Associa**.
    25. Nella struttura selezionare **Intrastat \> \>Relazioni \> IntrastatCommodity \> Codice**.
    26. Nella struttura selezionare **Transazione = Intrastat \> Codice voce doganale**.
    27. Selezionare **Associa**.
    28. Selezionare **Convalida**.

        > [!NOTE]
        > Dopo la convalida, gli elementi del modello di dati risulteranno associati agli articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione nella configurazione dei metadati ER.

    29. Selezionare **Salva**.

Quando necessario, è possibile estendere il set di metadati esistente nell'applicazione. È quindi possibile esportare la nuova versione completata della configurazione dei metadati ER, importarla in RCS e aggiornare i prerequisiti della configurazione del mapping di modello configurata per fare riferimento a una nuova versione della configurazione dei metadati importata.

> [!NOTE]
> Questo metodo per ottenere informazioni sui metadati dell'applicazione è l'unico disponibile per le applicazioni distribuite localmente (ovvero, quando un modello di distribuzione di dati aziendali locali \[LBD\] o on-premises è utilizzato per l'applicazione).

## <a name="access-application-metadata-by-using-connected-applications"></a>Accedere ai metadati dell'applicazione utilizzando applicazioni connesse

La seguente procedura illustra come un utente RCS con ruolo **Amministratore di sistema** o **Sviluppatore per la creazione di report elettronici** può progettare un nuovo mapping di modello ER utilizzando i metadati dell'applicazione. Per accedere ai metadati dell'applicazione online si utilizzerà l'applicazione connessa RCS. Un mapping di modello ER di esempio verrà configurato per accedere alle transazioni del commercio estero.

Per completare questa procedura, completare dapprima la procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md) in RCS. Se i passaggi nella procedura [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](#access-application-metadata-by-using-an-er-configuration) vista precedentemente in questo argomento non sono stati ancora completati, accedere alla pagina [Guide attività per la creazione di report elettronici per Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) per scaricare i seguenti file di configurazioni ER e salvarli localmente: **Metadati del commercio estero.xml**, **Modello del commercio estero.xml** e **Mapping del commercio estero.xml**.


### <a name="get-required-er-configurations"></a>Ottenere le configurazioni ER necessarie

Se i passaggi nella procedura [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](#access-application-metadata-by-using-an-er-configuration) vista precedentemente in questo argomento sono stati completati, si dispone già di tutte le configurazioni ER necessarie (configurazioni di metadati, modello e mapping del commercio estero) nell'istanza di RCS corrente. In tal caso, è possibile ignorare questa procedura.

1. Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Caricare i file di configurazione **Metadati del commercio estero.xml**, **Modello del commercio estero.xml** e **Mapping del commercio estero.xml** ripetendo li seguenti passaggi per ognuno:

    1. Selezionare **Scambia**.
    2. Selezionare **Carica da file XML**.
    3. Selezionare **Sfoglia** e selezionare un file.
    4. Selezionare **OK**.

### <a name="register-the-connection-with-the-application"></a>Registrare la connessione con l'applicazione

1. Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.
2. Selezionare **Applicazioni connesse**.
3. Assicurarsi che l'applicazione configurata sia basata su Microsoft Azure e che sia accessibile agli utenti RCS. L'utente RCS corrente deve avere accesso all'applicazione configurata ed essere registrato come utente di questa applicazione con un ruolo che fornisce privilegi di accesso ai metadati dell'applicazione.
4. Selezionare **Nuovo**.
5. Nel campo **Nome**, immettere **MiaAppConnessa** come nome dell'applicazione connessa.
6. Nel campo **Applicazione**, specificare l'URL dell'applicazione.
7. Nel campo **Tenant**, specificare il provider dell'applicazione.
8. Selezionare **Salva**. 
9. Quando si verifica la connessione all'applicazione configurata, nella pagina **Connettersi all'applicazione remota**, selezionare il collegamento **Fare clic qui per la connessione all'applicazione remota selezionata**. 
10. Selezionare **Verifica connessione** per convalidare l'accesso all'applicazione configurata.
11. Selezionare **Chiudi**.

Dopo il completamento di questa procedura e la convalida della connessione, i dettagli relativi a tenant e versione per l'applicazione configurata verranno aggiornati nella griglia corrente.

### <a name="review-the-existing-model-mapping-configuration"></a>Esaminare la configurazione del mapping di modello esistente

1. Andare a **Tutte le aree di lavoro \> Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Nella struttura, selezionare **Modello del commercio estero \> Mapping del commercio estero**.
4. Selezionare la scheda dettaglio **Prerequisiti**.

    > [!NOTE]
    > Attualmente, questo mapping fa riferimento alla configurazione dei metadati. I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.

4. Selezionare **Progettazione**.
5. Selezionare **Progettazione**.
6. Nella struttura selezionare **Dynamics 365 for Operations \> Record di tabella**.
7. Selezionare **Aggiungi radice**.
8. Nel campo **Tabella** immettere o selezionare un valore.

    > [!NOTE]
    > Attualmente, questo mapping fa riferimento alla configurazione dei metadati. I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.

9. Selezionare **Annulla**.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Assegnare l'applicazione connessa a un mapping di modello

1. Selezionare **Modifica**.
2. Nel campo **Applicazione connessa**, selezionare l'applicazione **MiaAppConnessa**.

    > [!NOTE]
    > Questo mapping fa riferimento ai metadati dell'applicazione connessa selezionata. Se un mapping fa riferimento contemporaneamente alla configurazione dei metadati e all'applicazione connessa, verranno utilizzati i metadati dell'applicazione connessa.

3. Selezionare **Progettazione**.
4. Selezionare **Progettazione**.
5. Nella struttura selezionare **Dynamics 365 for Operations \> Record di tabella**.
6. Selezionare **Aggiungi radice**.
7. Nel campo **Tabella** immettere o selezionare un valore.

    > [!NOTE]
    > A questo punto, sono disponibili più di due tabelle dell'applicazione in quanto questo mapping utilizza tutti i metadati dell'applicazione connessa che è stata assegnata agli stessi.

8. Selezionare **Annulla**.
9. Selezionare **Convalida**.

A questo punto sono stati associati gli elementi del modello di dati agli articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione connessa che è stata assegnata a questo mapping.

Quando è necessario valutare questo mapping di modello utilizzando i metadati di un'altra versione dell'applicazione, registrare un'altra applicazione connessa, assegnarla a questo mapping di modello e convalidarla in base ai nuovi metadati.

## <a name="additional-resources"></a>Risorse aggiuntive

In alternativa, è possibile riprodurre la guida attività **Preparare i metadati dell'applicazione da utilizzare in RCS** nell'applicazione nonché le guide attività **Accedere ai metadati dell'applicazione utilizzando una configurazione ER** e **Accedere ai metadati dell'applicazione utilizzando applicazioni connesse** in RCS. Queste guide attività possono essere scaricate dalla pagina [Guide attività per la creazione di report elettronici per Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).
