---
title: Regole di mapping della soluzione Invoice Capture
description: In questo articolo vengono fornite informazioni sulla configurazione delle regole di mapping della soluzione Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: cd0d06f7fd3ed946756e975d0706687c2d4acc93
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691233"
---
# <a name="invoice-capture-solution-mapping-rules"></a>Regole di mapping della soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le regole di mapping portano i dati anagrafici di base da Microsoft Dynamics 365 Finance o il sistema ERP (Enterprise Resource Planning). Dopo aver configurato le regole di mapping, vengono derivate le informazioni necessarie per creare fatture fornitore in Finance. Quando vengono utilizzate le regole di mapping, l'addetto alla contabilità fornitori (AP) verificherà lo stato invece di compilare manualmente tutti i valori dei campi mancanti.

Sono disponibili quattro tipi di regole di mapping:

- Persona giuridica
- Account fornitore
- Elemento
- Tipo di spesa

## <a name="manage-mapping-rules-by-using-the-app"></a>Gestire le regole di mapping utilizzando l'app

Per gestire le regole di mapping utilizzando l'app, seleziona **Impostazione**. La scheda **Impostazione regola di mapping** fornisce quattro opzioni:

- Persona giuridica 
- Account fornitore 
- Mapping articoli 
- Tipo di spesa

Ad esempio, seleziona l'opzione **Regole di mapping persone giuridiche**. Il codice della persona giuridica sarà identificato utilizzando la ragione sociale, l'indirizzo e il codice fiscale. Per una regola denominata **LE-USPM**, se la ragione sociale contiene il testo "Contoso Robotics USA", il codice della persona giuridica sarà **USPM**.

La pagina mostra tutte le regole di mapping attive. Se desideri visualizzare le regole di mapping inattive, seleziona **Regole persona giuridica per mapping attive**, quindi seleziona **Regole persona giuridica per mapping inattive**.

Le seguenti azioni sono disponibili per le regole di mapping.

### <a name="create-a-mapping-rule"></a>Creare una regola di mapping

È possibile utilizzare due metodi per creare una regola di mapping:

- Seleziona **Nuovo** per creare una nuova regola di mapping. Quindi immetti le informazioni per la regola di mapping. Il valore **Nome regola** deve essere univoco per ogni tipo di regola di mapping.
- Se selezioni una regola di mapping esistente, il pulsante **Copia** diventa disponibile. Selezionalo e nella finestra di dialogo visualizzata seleziona **OK**. Una regola di mapping viene creata duplicando la regola selezionata.

### <a name="edit-a-mapping-rule"></a>Modificare una regola di mapping

Per modificare una regola di mapping, seleziona un campo e cambia il valore.

### <a name="activatedeactivate-mapping-rules"></a>Attivare/disattivare le regole di mapping

Per disattivare una o più regole di mapping, selezionale nella pagina **Regole di mapping attive**, quindi seleziona **Disattiva**. Le regole vengono spostate dalla pagina **Regole di mapping attive** alla pagina **Regole di mapping inattive**.

Allo stesso modo, per attivare le regole di mapping, selezionale nella pagina **Regole di mapping inattive**, quindi seleziona **Attiva**.

### <a name="remove-mapping-rules"></a>Rimuovere regole di mapping

Per rimuovere le regole di mapping, selezionale e quindi seleziona **Elimina**.

### <a name="check-for-conflicts"></a>Verificare la presenza di conflitti

Se due regole di mapping hanno gli stessi valori per **Persona giuridica** e **Conto fornitore**, ma diversi valori **Nome articolo**, verrà rilevato un conflitto e la regola di mapping non verrà creata o aggiornata.

## <a name="importexport-mapping-rules-from-excel"></a>Importare/esportare regole di mapping da Excel

Un componente aggiuntivo di Excel può essere utilizzato per gestire le regole in un batch. Di seguito vengono illustrate le opzioni disponibili.

- Scarica un modello di Excel.
- Esporta su Excel.
- Importa da Excel.

### <a name="download-an-excel-template"></a>Scaricare un modello di Excel

Per scaricare un modello di Excel, seleziona **Scarica modello**. Quind, seleziona i campi da includere nel modello.

### <a name="export-to-excel"></a>Esporta in Excel

Puoi esportare in due modi:

- Seleziona **Apri in Excel Online** per aprire il file in Excel. È quindi possibile modificare il file online. Al termine, selezionare **Salva**. Tutte le modifiche verranno salvate nella pagina **Regola di mapping**.
- Seleziona **Scarica foglio di lavoro** per scaricare un file Excel che contiene le regole di mapping. È quindi possibile modificare il file. Quando hai finito, seleziona **Importa da Excel** per caricare il foglio di lavoro aggiornato.

### <a name="import-from-excel"></a>Importa da Excel

1. Seleziona **Importa da Excel** per importare i dati da un file XLSX. Puoi anche importare da valori separati da virgole (CSV) o file XML. Prima di importare, devi decidere se sono consentiti duplicati.
2. Seleziona **Rivedi mapping** per rivedere il mapping degli attributi e determinare se è corretto. Non puoi modificare la relazione del mapping.
3. Al termine, seleziona **Termina importazione** per avviare l'importazione.
4. Puoi selezionare **Tieni traccia del processo** tener traccia dell'avanzamento del processo di importazione.

    Lo stato dell'importazione viene aggiornato da **Fine** ad **Analisi in corso**, quindi da **Trasformazione in corso** e infine a **Completato**.

Al termine del processo di importazione, vengono visualizzate le statistiche relative alle operazioni riuscite, agli errori parziali, agli errori e al totale elaborato.
