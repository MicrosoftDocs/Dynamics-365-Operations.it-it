---
title: (RCS) Importare file in formato XML con attributi facoltativi
description: In questo argomento vengono fornite informazioni su come un utente può progettare una configurazione di formato ER per importare file in formato XML con attributi facoltativi.
author: NickSelin
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 25ced72bc1bb1b18996c8bab986270fde0557ed3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744869"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) Importare file in formato XML con attributi facoltativi

[!include [banner](../../includes/banner.md)]

I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare una configurazione di formato ER per importare file in formato XML contenente attributi facoltativi. Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo". Prima di iniziare, scaricare e salvare localmente il file IncomingDocumentToLearnHowToHandleOptionalAttributes.xml dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

1.    Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**.
2.    Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).
3.    Fare clic su **Configurazioni report**.

## <a name="create-a-new-data-model-configuration"></a>Creare una nuova configurazione del modello di dati
1.    Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.
2.    Nel campo **Nome**, digitare "Modello per importare il file XML".
3.    Fare clic su **Crea configurazione**.
4.    Fare clic su **Progettazione**.
5.    Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
6.    Digitare "Radice" nel campo **Nome**.
7.    Scegliere **Aggiungi**.
8.    Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
9.    Digitare "Elenco" nel campo **Nome**.
10.    Nel campo **Tipo di articolo** selezionare **Elenco di record**.
11.    Scegliere **Aggiungi**.
12.    Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
13.    Digitare "Codice" nel campo **Nome**.
14.    Nel campo **Tipo di articolo** selezionare **Stringa**.
15.    Scegliere **Aggiungi**.
16.    Fare clic su **Salva**.
17.    Chiudere la pagina.
18.    Fare clic su **Cambia stato**.
19.    Fare clic su **Completa**.
20.    Fare clic su **OK**.

## <a name="create-a-format-for-data-import"></a>Creare un formato per l'importazione di dati
1.    Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.
2.    Nel campo **Nuovo** immettere "Formato basato sul modello di dati Modello per importare il file xml".
3.    Nel campo **Nome**, digitare "Formato per importare il file XML".
4.    Selezionare **Sì** nel campo **Supporta importazione dati**.
5.    Fare clic su **Crea configurazione**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Progettare un formato per analizzare il file in entrata in formato XML
1.    Fare clic su **Progettazione**.
2.    Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.
3.    Nella struttura selezionare **XML\Elemento**.
4.    Digitare "Radice" nel campo **Nome**.
5.    Fare clic su **OK**.
6.    Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
7.    Nella struttura selezionare **XML\Elemento**.
8.    Nel campo **Nome** digitare "Documento".
9.    Nel campo **Molteplicità** selezionare **Uno molti**.
10.    Fare clic su **OK**.
11.    Nella struttura selezionare **radice\documento**.
12.    Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
13.    Nella struttura selezionare **XML\Attributo**.
14.    Nel campo **Nome** digitare "ID".
15.    Fare clic su **OK**.
16.    Fare clic su **Salva**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Progettare un mapping di formato per salvare le informazioni analizzate nel modello di dati
1. Fare clic su **Mapping formato a modello**.
2. Fare clic su **Nuovo**.
3. Nel campo **Definizione** immettere o selezionare un valore.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo **Nome** digitare "Mapping".
6. Fare clic su **Salva**.
7. Fare clic su **Progettazione**.
8. Nella struttura espandere **formato**.
9. Nella struttura espandere **format\root: XML Element(root)**.
10.    Nella struttura selezionare **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
11.    Fare clic su **Associa**.
12.    Nella struttura, espandere **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
13.    Nella struttura selezionare **format\root: XML Element(root)\document: XML Element 1..* (documento)\id**.
14.    Nella struttura espandere **Elenco = format.root.document**.
15.    Nella struttura selezionare **Elenco = format.root.document\Codice**.
16.    Fare clic su **Associa**.
17.    Fare clic su **Salva**.
18.    Chiudere la pagina.
 
## <a name="run-format-mapping"></a>Eseguire il mapping di formato
1. Fare clic su **Esegui**.
2. Fare clic su **Sfoglia** e selezionare **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Fare clic su **OK**.

> [!NOTE]
> Il file selezionato non è stato importato in quanto la progettazione del formato presuppone l'esistenza dell'attributo "id" per l'elemento "documento", ma il file importato non contiene tale attributo.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modificare la struttura del formato per gestire l'attributo xml come facoltativo
1. Chiudere la pagina.
2. Nella struttura espandere **radice\documento**.
3. Nella struttura selezionare **radice\documento\id**.
4. Selezionare **Sì** nel campo **Stringa vuota per attributo mancante**.
5. Fare clic su **Salva**.
 
## <a name="run-format-mapping-to-test-changes"></a>Eseguire il mapping di formato per testare le modifiche
1. Fare clic su **Mapping formato a modello**.
2. Fare clic su **Esegui**.
3. Fare clic su **Sfoglia** e selezionare il file **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Fare clic su **OK**.
5. Esaminare il file generato. 

> [!NOTE]
> Lo stesso file è stato importato in quanto la progettazione del formato ora considera l'attributo "id" per l'elemento "documento" come facoltativo.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]