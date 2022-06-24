---
title: Personalizza le configurazioni fiscali per la ricerca dei dati master
description: Questo articolo spiega come personalizzare le configurazioni fiscali per estendere la funzionalità di ricerca dei dati master.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 31c15c47fa1dc6861ff555a991d5f9233b7df35e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845186"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Personalizza le configurazioni fiscali per la ricerca dei dati master

[!include [banner](../includes/banner.md)]

Segui i passaggi in questo articolo per personalizzare le configurazioni fiscali per estendere la funzionalità di ricerca dei dati master.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Importa una configurazione fiscale fornita da Microsoft

1. In Regulatory Configuration Service (RCS), nell'area di lavoro **Creazione di report elettronici**, seleziona il provider delle configurazioni **Microsoft**.
2. Selezionare **Archivi**.
3. Seleziona **Globale** e quindi seleziona **Apri**.
4. Seleziona una configurazione fiscale, ad esempio **Configurazione del calcolo dell'imposta** e quindi sulla scheda **Versioni**, seleziona una versione.
5. Selezionare **Importa**.

> [!NOTE]
> Per impostazione predefinita viene importato il mapping del modello Dataverse. Se ricevi messaggi di avviso durante il processo di importazione della configurazione, abilita le entità virtuali in Dataverse. Per ulteriori informazioni, vedi [Abilitare entità virtuali di Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Creare una nuova configurazione del modello di dati personalizzato

1. Nell'area di lavoro **Creazione di report elettronici**, seleziona **Configurazioni fiscali** e quindi seleziona la configurazione del modello dati da estendere. Ad esempio, seleziona **Modello di dati per il calcolo delle imposte**.
2. Selezionare **Crea configurazione**.
3. Seleziona **Modello di documento imponibile derivato da Nome: Modello di dati per il calcolo delle imposte, Microsoft**.
4. Nel campo **Nome** digitare **Modello di dati personalizzazione**.
5. Selezionare **Crea configurazione**.

## <a name="create-customized-reference-models"></a>Creare modelli di riferimento personalizzati

1. Nella pagina **Configurazioni fiscali**, seleziona **Modello di dati personalizzazione**, quindi seleziona **Progettazione**.
2. Seleziona il pulsante con i puntini di sospensione (**...**) e quindi seleziona la vista **Modello di riferimento**.

    [![Modello di riferimento.](./media/pic2.png)](./media/pic2.png)

3. Creare il modello di riferimento personalizzato. Il modello personalizzato è un modello radice. L'entità personalizzata è un elenco di record. Il campo personalizzato è un campo stringa che si desidera utilizzare nella ricerca. È possibile aggiungere più campi secondo le necessità.
4. Seleziona il pulsante con i puntini di sospensione (**...**) e quindi seleziona la vista **Documento tassabile**.
5. Seleziona l'attributo da associare al modello di riferimento personalizzato. Ad esempio, seleziona **Attributo personalizzato**, quindi segui questi passaggi:

    1. Seleziona **Seleziona il modello di riferimento**.
    2. Seleziona **Modello personalizzato**, quindi **OK**. Il nome del modello di riferimento viene aggiornato al valore del campo **Chiave naturale**.

        [![Finestra di dialogo Seleziona modello di riferimento.](./media/pic5.png)](./media/pic5.png)

    3. Seleziona **Salva** e quindi **Operazione completata**.

## <a name="create-a-customized-model-mapping-configuration"></a>Creare una nuova configurazione del mapping del modello personalizzato

1. Nell'area di lavoro **Creazione di report elettronici**, seleziona **Configurazioni fiscali** e quindi seleziona la configurazione **Mapping del modello Dataverse**.
2. Nel campo **Impostazione predefinita per mapping di modello**, seleziona **No**.
3. Selezionare **Crea configurazione**.
4. Seleziona **Modello di documento imponibile derivato da Nome: Modello di dati Dataverse, Microsoft**.
5. Nel campo **Nome** digitare **Mapping del modello di personalizzazione**.
6. Nel campo **Modello di destinazione**, seleziona il modello di dati **Modello dati di personalizzazione**.
7. Selezionare **Crea configurazione**.

    [![Finestra di dialogo a discesa Crea configurazione.](./media/pic6.png)](./media/pic6.png)

8. Seleziona **Mappatura del modello di personalizzazione** e imposta il campo **Applicazione connessa** alla connessione creata al passaggio 8 in [Configurare un ambiente per la ricerca dei dati master](tax-service-set-up-environment-master-data-lookup.md).
9. Impostare il campo **Impostazione predefinita per il mapping del modello** su **Sì**.

## <a name="create-customized-model-mappings"></a>Crea mapping del modello personalizzati

1. Nella pagina **Configurazioni fiscali**, seleziona **Mapping del modello di personalizzazione**.
2. Seleziona **Progettazione**, quindi **Modello di personalizzazione**.

    [![Modello di personalizzazione.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Mappa un mapping del modello su un'entità Dataverse

1. Nella pagina **Progettazione mapping modello**, seleziona **Modello di personalizzazione**, quindi seleziona **Progettazione**.
2. Nella struttura ad albero **Tipi di origini dati**, seleziona **Tabella Dataverse**.
3. Nella scheda **Origini dati**, seleziona **Aggiungi radice**.
4. Nel campo **Nome**, immetti **Dataverse personalizzato**.
5. Nel secondo campo **Nome**, seleziona un'entità.
6. Selezionare **OK**.

    [![Finestra di dialogo Proprietà dell'origine dati "Tabella".](./media/pic9.png)](./media/pic9.png)

7. Seleziona **Dataverse personalizzato** ed **Entità personalizzata**, quindi seleziona **Associa**.

    [![Dataverse personalizzato e associazione di entità personalizzate.](./media/pic10.png)](./media/pic10.png)

8. In **Dataverse personalizzato** e **Campo personalizzato**, seleziona un campo, quindi seleziona **Associa**.

    [![Dataverse personalizzato e associazione di campi personalizzati.](./media/pic11.png)](./media/pic11.png)

9. Seleziona **Salva** e quindi **Operazione completata**.

## <a name="create-a-customized-tax-configuration"></a>Creare una nuova configurazione fiscale

1. Nell'area di lavoro **Creazione di report elettronici**, seleziona **Configurazioni fiscali** e quindi seleziona **Configurazione del calcolo dell'imposta**.
2. Selezionare **Crea configurazione**.
3. Seleziona **Configurazione del servizio per le imposte derivata da Nome: Configurazione calcolo delle imposte, Microsoft**.
4. Nel campo **Nome** digitare **Configurazione personalizzazione**.
5. Selezionare **Crea configurazione**.
6. Seleziona **Configurazione personalizzazione**, quindi seleziona **Progettazione**.
7. Nel campo **Modello di dati**, seleziona **Modello dati di personalizzazione**.
8. Nel campo **Versione modello di dati** seleziona la versione del modello di dati corrispondente.

    [![Sezione proprietà.](./media/pic13.png)](./media/pic13.png)

9. Selezionare **Completa**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
