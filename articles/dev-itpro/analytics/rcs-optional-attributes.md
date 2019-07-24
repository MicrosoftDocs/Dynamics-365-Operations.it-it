---
title: Preparare metadati specifici dell'applicazione per RCS e ER
description: In questo argomento vengono fornite informazioni sulla progettazione di formati ER che specificano attributi XML per analizzare i documenti elettronici in entrata in formato XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a6fc1e54444584895aa75ae91d39143f27e34d8
ms.sourcegitcommit: d0fa7eb2166a30314205e7f70bbeaff6fbd5fb55
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "1726577"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a>Preparare metadati specifici dell'applicazione per RCS e ER

È possibile progettare formati di report elettronici (ER) per analizzare documenti elettronici in entrata in formato XML. Determinati attributi di elementi XML possono essere specificati nel formato ER progettato come facoltativi. Ciò consentirà di gestire correttamente i file in entrata con e senza tali attributi XML. È quindi possibile utilizzare il contenuto di tali file per aggiornare i dati dell'applicazione.

Per ulteriori informazioni su questa funzionalità, completare i passaggi nell'argomento [(RCS) Importare file in formato XML con attributi facoltativi](tasks/import-files-xml-format-optional-attributes.md), che fa parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677). È possibile scaricare questa guida attività e i file di esempio associati dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).


| Descrizione contenuto       | File                                                         |
|---------------------------|--------------------------------------------------------------|
| File di esempio in formato XML | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml     |
| Guida attività                | (RCS) Importare file in formato XML con attributi facoltativi.axtr |


I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare una configurazione di formato ER per importare file in formato XML contenente attributi facoltativi. Per completare questi passaggi, è necessario dapprima completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md). Prima di iniziare, scaricare e salvare localmente il file IncomingDocumentToLearnHowToHandleOptionalAttributes.xml dall'Area download Microsoft (https://go.microsoft.com/fwlink/?linkid=874684).

1. Andare a **Amministrazione organizzazione** > **Aree di lavoro** > **Creazione di report elettronici**.
2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se questo provider di configurazione non è visualizzato, completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Fare clic su **Configurazioni report**.

## <a name="create-a-new-data-model-configuration"></a>Creare una nuova configurazione del modello di dati
1. Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.
2. Nel campo **Nome**, digitare "Modello per importare il file XML".
3. Fare clic su **Crea configurazione**.
4. Fare clic su **Progettazione**.
5. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
6. Digitare "Radice" nel campo **Nome**.
7. Scegliere **Aggiungi**.
8. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
9. Digitare "Elenco" nel campo **Nome**.
10. Nel campo **Tipo di articolo** selezionare **Elenco di record**.
11. Scegliere **Aggiungi**.
12. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
13. Digitare "Codice" nel campo **Nome**.
14. Nel campo **Tipo di articolo** selezionare **Stringa**.
15. Scegliere **Aggiungi**.
16. Fare clic su **Salva**.
17. Chiudere la pagina.
18. Fare clic su **Cambia stato**.
19. Fare clic su **Completa**.
20. Fare clic su **OK**.

## <a name="create-a-format-for-data-import"></a>Creare un formato per l'importazione di dati
1. Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.
2. Nel campo **Nuovo** immettere "Formato basato sul modello di dati Modello per importare il file xml".
3. Nel campo **Nome**, digitare "Formato per importare il file XML". 
4. Selezionare **Sì** nel campo **Supporta importazione dati**.
5. Fare clic su **Crea configurazione**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Progettare un formato per analizzare il file in entrata in formato XML
1. Fare clic su **Progettazione**.
2. Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.
3. Nella struttura selezionare **XML\Elemento**.
4. Digitare "Radice" nel campo **Nome**.
5. Fare clic su **OK**.
6. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
7. Nella struttura selezionare **XML\Elemento**.
8. Nel campo **Nome** digitare "Documento".
9. Nel campo **Molteplicità** selezionare **Uno molti**.
10. Fare clic su **OK**.
11. Nella struttura selezionare **radice\documento**.
12. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
13. Nella struttura selezionare **XML\Attributo**.
14. Nel campo **Nome** digitare "id".
15. Fare clic su **OK**.
16. Fare clic su **Salva**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Progettare un mapping di formato per salvare le informazioni analizzate nel modello di dati
1.  Fare clic su **Mapping formato a modello**.
2.  Fare clic su **Nuovo**.
3.  Nel campo **Definizione** immettere o selezionare un valore.
4.  Nel campo **Nome** digitare "Mapping".
5.  Fare clic su **Salva**.
6.  Fare clic su **Progettazione**.
7.  Nella struttura espandere **formato**.
8.  Nella struttura espandere **formato\radice: elemento XML (radice)**.
9.  Nella struttura selezionare **formato\radice: elemento XML (radice)\documento: elemento XML 1..* (documento)**.
10. Fare clic su **Associa**.
11. Nella struttura espandere **formato\radice: elemento XML (radice)\documento: elemento XML 1..* (documento)**.
12. Nella struttura selezionare **formato\radice: elemento XML (radice)\documento: elemento XML 1..* (documento)\id**.
13. Nella struttura espandere **Elenco = format.root.document**.
14. Nella struttura selezionare **Elenco = format.root.document\Codice**.
15. Fare clic su **Associa**.
16. Fare clic su **Salva**.
17. Chiudere la pagina.

## <a name="run-format-mapping"></a>Eseguire il mapping del formato
1. Fare clic su **Esegui**.
2. Fare clic su **Sfoglia** e selezionare il file **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Fare clic su **OK**.

> [!NOTE]
> Il file selezionato non è stato importato in quanto la progettazione del formato presuppone l'esistenza dell'attributo "id" per l'elemento "documento", ma il file importato non contiene tale attributo.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modificare la struttura del formato per gestire l'attributo xml come facoltativo
1. Chiudere la pagina.
2. Nella struttura espandere **radice\documento**.
3. Nella struttura selezionare **radice\documento\id**.
4. Nel campo **Stringa vuota per attributo mancante**, selezionare **Sì**.
5. Fare clic su **Salva**.

## <a name="run-format-mapping-to-test-changes"></a>Eseguire il mapping di formato per testare le modifiche
1. Fare clic su **Mapping formato a modello**.
2. Fare clic su **Esegui**.
3. Fare clic su **Sfoglia** e selezionare il file **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Fare clic su **OK**.
5. Esaminare il file generato. Da notare che lo stesso file è stato importato in quanto la progettazione del formato ora considera l'attributo "id" per l'elemento "documento" come facoltativo.
