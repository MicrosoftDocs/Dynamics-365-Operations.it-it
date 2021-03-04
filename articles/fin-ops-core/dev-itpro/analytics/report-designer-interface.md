---
title: Interfaccia Progettazione report
description: In questo articolo viene illustrato come spostarsi all'interno di Progettazione report e come utilizzare le varie opzioni per soddisfare specifiche esigenze.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f0fb8052948b2d1b9297d30d6c5da186f8898bfc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687467"
---
# <a name="report-designer-interface"></a>Interfaccia Progettazione report

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come spostarsi all'interno di Progettazione report e come utilizzare le varie opzioni per soddisfare specifiche esigenze.

## <a name="report-designer-menu-commands"></a>Comandi di menu di Progettazione report

Di seguito vengono descritti i comandi di menu e le opzioni che è possibile utilizzare per progettare i report finanziari. Alcuni comandi e opzioni di menu sono disponibili solo in condizioni specifiche. Ad esempio, i comandi per la promozione e la retrocessione delle unità gerarchiche sono disponibili solo se si modifica una definizione dell'albero gerarchico.

### <a name="file-menu"></a>Menu File

Il menu **File** è disponibile per tutti gli utenti e comprende i seguenti comandi.

| Comando                           | Descrizione |
|-----------------------------------|-------------|
| Nuovo                               | Creare una nuova definizione di report, definizione di riga, definizione di colonna, definizione di albero gerarchico, definizione di gruppo di report o cartella. Opzioni aggiuntive sono disponibili, in base al ruolo utente. |
| Aperto                              | Aprire una definizione di riga, definizione di colonna, definizione di albero gerarchico o definizione di report esistente. |
| Chiudi                             | Chiudere il blocco predefinito corrente. |
| Chiudi tutto                         | Chiudere tutti i blocchi predefiniti. |
| Salva                              | Salvare la definizione di riga, definizione di colonna, definizione di albero gerarchico o definizione di report corrente. |
| Salva con nome                           | Salvare la definizione di riga, definizione di colonna, definizione di albero gerarchico o definizione di report corrente con un nuovo nome. |
| Proprietà                        | Aprire la finestra di dialogo **Proprietà** in cui è possibile modificare il nome e la descrizione di un report. |
| Genera                          | Generare il report corrente. Questo comando è disponibile da una definizione di report. |
| Visualizza report                       | Aprire la versione più recente del report generato. Questo comando è disponibile da una definizione di report se è stato generato almeno un report. |
| Definizioni di report recenti         | Visualizzare un elenco di report che sono stati creati o modificati di recente. È possibile selezionare un report nell'elenco. |
| Definizioni di riga recenti            | Visualizzare un elenco di definizioni di riga che sono state create o modificate di recente. È possibile selezionare una definizione di riga nell'elenco. |
| Definizioni di colonna recenti         | Visualizzare un elenco di definizioni di colonna che sono stati create o modificate di recente. È possibile selezionare una definizione di colonna nell'elenco. |
| Definizioni di albero gerarchico recenti | Visualizzare un elenco di definizioni di albero gerarchico che sono stati create o modificate di recente. È possibile selezionare una definizione di albero gerarchico nell'elenco. |
| Esci                              | Uscire da Progettazione report. |

### <a name="edit-menu"></a>Menu Modifica

Il menu **Modifica** è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. In questo menu sono inclusi i comandi seguenti:

| Comando                                | Descrizione |
|----------------------------------------|-------------|
| Annulla                                   | Annullare l'ultima azione. |
| Ripeti                                   | Ripristinare l'ultima azione annullata. |
| Taglia                                    | Eliminare il testo selezionato e copiarlo negli Appunti. |
| Copia                                   | Copiare il testo selezionato negli Appunti. |
| Incolla                                  | Inserire il testo copiato o tagliato più di recente dagli Appunti. |
| Cancella                                  | Eliminare il contenuto della cella selezionata di blocco predefinito. |
| Trova                                   | Aprire la finestra di dialogo **Trova e sostituisci** in cui è possibile cercare il testo nel riquadro di visualizzazione. |
| Sostituisci                                | Aprire la finestra di dialogo **Trova e sostituisci** in cui è possibile cercare e sostituire il testo nel riquadro di visualizzazione. |
| Inserisci righe da dimensioni            | Aprire la finestra di dialogo **Inserisci righe da dimensioni** in cui è possibile selezionare i valori di dimensione da includere nella definizione di riga. Questo comando è disponibile da una definizione di riga. |
| Rinumera righe                          | Rinumerare tutti i codici numerici di riga. Questo comando è disponibile da una definizione di riga. |
| Collegamenti riga                              | Aprire la finestra di dialogo **Collegamenti riga** in cui è possibile specificare le origini dei collegamenti dei dati nelle definizioni di riga e nelle definizioni di albero gerarchico. Questo comando è disponibile da una definizione di riga. |
| Rettifica arrotondamento                    | Aprire la finestra di dialogo **Rettifiche arrotondamento** in cui è possibile specificare i parametri per l'arrotondamento. Questo comando è disponibile da una definizione di riga. |
| Gestisci set di dimensioni                  | Aprire la finestra di dialogo **Set di dimensioni** in cui è possibile creare e modificare i set di dimensioni. Questo comando è disponibile da una definizione di riga o una definizione di albero gerarchico. |
| Inserisci riga                             | Inserire una riga vuota nella definizione di riga o una riga di intestazione vuota nella definizione di colonna. Questo comando è disponibile da una definizione di riga o una definizione di colonna. |
| Elimina riga                             | Eliminare la riga selezionata dalla definizione di riga o la riga di intestazione selezionata dalla definizione di colonna. Questo comando è disponibile da una definizione di riga o una definizione di colonna. |
| Inserisci colonna                          | Inserire una colonna vuota nella definizione di colonna. Questo comando è disponibile da una definizione di colonna. |
| Elimina colonna                          | Eliminare la colonna selezionata dalla definizione di colonna. Questo comando è disponibile da una definizione di colonna. |
| Inserisci unità gerarchiche da dimensioni | Aprire la finestra di dialogo **Inserisci unità gerarchiche da dimensioni** in cui è possibile selezionare i valori di dimensione da includere nella definizione di albero gerarchico. Questo comando è disponibile da una definizione di albero gerarchico. |
| Importa gerarchia set di dimensioni         | Aprire la finestra di dialogo **Gerarchia set di dimensioni** in cui è possibile importare una gerarchia set di dimensioni dai dati finanziari. Questo comando è disponibile da una definizione di albero gerarchico per sistema basato su..\\dimensioni finanziarie\\dimensioni. |
| Inserisci unità gerarchica                  | Inserire una riga vuota nella definizione di albero gerarchico. Questo comando è disponibile da una definizione di albero gerarchico. |
| Elimina unità gerarchica                  | Eliminare la riga di unità gerarchica selezionata dalla definizione di albero gerarchico. Questo comando è disponibile da una definizione di albero gerarchico. |

### <a name="view-menu"></a>Menu Visualizza

Il menu **Visualizza** è disponibile per tutti gli utenti e comprende i seguenti comandi.

| Comando         | Descrizione                                                            |
|-----------------|------------------------------------------------------------------------|
| Pannello di navigazione | Mostrare o nascondere il pannello di navigazione.                                      |
| Barre degli strumenti        | Selezionare le barre degli strumenti che sono visibili.                                  |
| Barra di stato      | Mostrare o nascondere le informazioni di stato nella finestra **Progettazione report**. |
| Pagina iniziale    | Apre la pagina **iniziale**.                                             |

### <a name="format-menu"></a>Menu Formatta

Il menu **Formatta** è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. In questo menu sono inclusi i comandi seguenti:

| Comando               | Descrizione |
|-----------------------|-------------|
| Stili e formattazione | Aprire la finestra di dialogo **Stili e formattazione** in cui è possibile creare e modificare lo stile del testo delle definizioni di riga e delle definizioni di colonna. Questo comando è disponibile da una definizione di riga o una definizione di colonna. |
| Larghezza colonna          | Aprire la finestra di dialogo **Larghezza colonna** in cui è possibile impostare la larghezza della colonna selezionata. Questo comando è disponibile da una definizione di riga, una definizione di colonna o una definizione di albero gerarchico. |
| Nascondi                  | Nascondere la colonna selezionata. Questo comando è disponibile da una definizione di riga, una definizione di colonna o una definizione di albero gerarchico. |
| Scopri                | Spostare le colonne nascoste tra le colonne visibili selezionate. Questo comando è disponibile da una definizione di riga, una definizione di colonna o una definizione di albero gerarchico. |

### <a name="company-menu"></a>Menu Società

Il menu **Società** è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. In questo menu sono inclusi i comandi seguenti:

| Comando               | Descrizione                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Società             | Aprire la finestra di dialogo **Società** in cui è possibile creare e modificare le società.                                          |
| Gruppi di blocchi predefiniti | Aprire la finestra di dialogo **Gruppi di blocco predefinito** in cui è possibile creare, modificare, importare ed esportare i gruppi di blocchi predefiniti. |

### <a name="go-menu"></a>Menu Vai

Il menu **Vai** è disponibile per tutti gli utenti e include i comandi seguenti.

> [!NOTE]
> Questi comandi non producono effetti visibili a meno che il riquadro di spostamento non sia visibile.

| Comandi                   | Descrizione                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Definizioni di report         | Mostrare le definizioni di report nel pannello di navigazione.                                    |
| Definizioni di riga            | Mostrare le definizioni di riga nel pannello di navigazione.                                       |
| Definizioni di colonna         | Mostrare le definizioni di colonna nel pannello di navigazione.                                    |
| Definizioni di albero gerarchico | Mostrare le definizioni di albero gerarchico nel pannello di navigazione.                            |
| Sicurezza                   | Visualizzare le informazioni sulla sicurezza per utenti, gruppi e società nel pannello di navigazione. |

### <a name="tools-menu"></a>Menu Strumenti

Il menu **Strumenti** è disponibile per tutti gli utenti, ma alcuni comandi hanno disponibilità limitata. In questo menu sono inclusi i comandi seguenti:

| Comando                       | Descrizione |
|-------------------------------|-------------|
| Proteggi                       | Applicare una password al blocco predefinito corrente. Questo comando è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. |
| Stato coda report           | Aprire la finestra di dialogo **Stato coda report** in cui è possibile visualizzare tutti i report generati di recente e i dettagli per ogni report. |
| Informazioni sistema di origine     | Visualizzare le impostazioni del sistema Microsoft Dynamics ERP. Questo comando è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. |
| Elementi estratti             | Visualizzare le definizioni di riga, le definizioni di colonna, le definizioni di albero gerarchico e le definizioni di report attualmente aperte. Questo comando è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. |
| Aggiorna dati finanziari memorizzati nella cache | Aggiornare i dati nella colonna delle dimensioni finanziarie. |
| Opzioni                       | Aprire la finestra di dialogo **Opzioni** in cui è possibile modificare le preferenze utente per Progettazione report. |

### <a name="window-menu"></a>Menu Finestra

Il menu **Finestra** è disponibile per tutti gli utenti e comprende i seguenti comandi.

| Comando              | Descrizione |
|----------------------|-------------|
| Affianca orizzontalmente    | Visualizzare tutte le finestre aperte una accanto all'altra. |
| Affianca verticalmente      | Visualizzare tutte le finestre aperte una sopra l'altra. |
| In cascata              | Disporre tutte le finestre aperte in modo che la barra del titolo di ogni finestra sia visibile. |
| Blocca in orizzontale    | Bloccare la riga selezionata in modo che quando si scorre, la riga continua a essere visibile nella finestra. Questo comando è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. |
| Blocca in verticale      | Bloccare la colonna selezionata in modo che quando si scorre, la colonna continua a essere visibile nella finestra. Questo comando è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. |
| Elenco delle finestre aperte | Visualizzare l'elenco delle finestre aperte. Selezionare una finestra per portarla in primo piano. |

### <a name="help-menu"></a>Menu ?

Il menu **?** è disponibile per tutti gli utenti e comprende i seguenti comandi.

| Comandi | Descrizione                                                              |
|---------|--------------------------------------------------------------------------|
| ?    | Aprire la pagina dell'argomento della Guida per i report finanziari. |
|         |                                                                          |

## <a name="report-designer-toolbar-buttons"></a>Pulsanti della barra degli strumenti di Progettazione report
Nelle tabelle seguenti vengono descritti i pulsanti della barra degli strumenti che è possibile utilizzare per progettare i report. Alcuni pulsanti della barra degli strumenti sono disponibili solo in circostanze specifiche. Ad esempio, i pulsanti per la promozione e la retrocessione delle unità gerarchiche sono disponibili solo se si modifica una definizione dell'albero gerarchico.

### <a name="standard-toolbar"></a>Barra degli strumenti standard

La barra degli strumenti standard consente l'accesso rapido ai comandi di file e modifica. Nella barra degli strumenti sono inclusi i seguenti pulsanti.

| Pulsante                                                                                       | Descrizione |
|----------------------------------------------------------------------------------------------|-------------|
| [![Pulsante Nuovo](./media/rowc130389.png)](./media/rowc130389.png)                              | Creare una nuova (vuota) definizione di report, definizione di riga, definizione di colonna o definizione di albero gerarchico. |
| [![Pulsante Apri](./media/openfolderc130389.png)](./media/openfolderc130389.png)               | Aprire una definizione di riga, definizione di colonna, definizione di albero gerarchico o definizione di report esistente. |
| [![Pulsante Salva](./media/savec130389.png)](./media/savec130389.png)                           | Salvare la definizione di riga, definizione di colonna, definizione di albero gerarchico o definizione di report corrente. |
| [![Pulsante Copia](./media/copyc130389.png)](./media/copyc130389.png)                           | Copiare il testo selezionato negli Appunti. |
| [![Pulsante Taglia](./media/cutc130389.png)](./media/cutc130389.png)                              | Eliminare il testo selezionato e copiarlo negli Appunti. |
| [![Pulsante Incolla](./media/pastec130389.png)](./media/pastec130389.png)                        | Inserire il testo dagli Appunti. |
| [![Pulsante Annulla](./media/undoc130389.png)](./media/undoc130389.png)                           | Annullare l'ultima azione. |
| [![Pulsante Ripeti](./media/redoc130389.png)](./media/redoc130389.png)                           | Ripristinare l'ultima azione annullata. |
| [![Pulsante Trova](./media/findc130389.png)](./media/findc130389.png)                           | Aprire la finestra di dialogo **Trova e sostituisci** in cui è possibile cercare e sostituire il testo nella finestra attiva. |
| [![Pulsante Inserisci riga](./media/insertrowc130389.png)](./media/insertrowc130389.png)           | Inserire una riga vuota nella definizione di riga o una riga di intestazione vuota nella definizione di colonna. Questo pulsante è disponibile da una definizione di riga o una definizione di colonna. |
| [![Pulsante Inserisci colonna](./media/insertcolumnc130389.png)](./media/insertcolumnc130389.png)  | Inserire una colonna vuota nella definizione di colonna. Questo pulsante è disponibile da una definizione di colonna. |
| [![Pulsante Blocca](./media/lockc130389.png)](./media/lockc130389.png)                           | Applicare una password al blocco predefinito corrente. Questo pulsante è disponibile per gli utenti con ruolo **Progettazione** o **Amministratore**. |
| [![Pulsante Collegamento riga](./media/rowlinkc130389.png)](./media/rowlinkc130389.png)                 | Aprire la finestra di dialogo **Collegamenti riga** in cui è possibile specificare le origini dei collegamenti dei dati nelle definizioni di riga e nelle definizioni di albero gerarchico. Questo pulsante è disponibile da una definizione di riga. |
| [![Pulsante Promuovi](./media/promotec130389.png)](./media/promotec130389.png)                  | Promuovere un'unità della definizione di albero gerarchico. Quando si seleziona un'unità figlio quindi si fa clic su **Promuovi**, l'unità figlio verrà spostata nello stesso livello dell'unità padre. |
| [![Pulsante Abbassa](./media/demotec130389.png)](./media/demotec130389.png)                     | Abbassare un'unità della definizione di albero gerarchico. Quando si seleziona un'unità e quindi si fa clic su **Abbassa**, l'unità diventa un elemento figlio dell'unità che la precede. |
| [![Pulsante Espandi](./media/expandtreebuttonc130389.png)](./media/expandtreebuttonc130389.png) | Espandere tutte le unità della definizione di albero gerarchico al livello dell'unità selezionata. |
| [![Pulsante Comprimi](./media/collapsec130389.png)](./media/collapsec130389.png)               | Comprimere l'albero gerarchico. |
| [![Pulsante ?](./media/helpc130389.png)](./media/helpc130389.png)                           | Aprire la Guida. |

### <a name="formatting-toolbar"></a>Barra degli strumenti di formattazione

La barra degli strumenti di formattazione consente facilmente l'accesso ai comandi di stile. Nella barra degli strumenti sono inclusi i seguenti pulsanti.

| Pulsante                                                                                                       | Descrizione                                             |
|--------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| [![Pulsante Stile carattere](./media/formattingc130389.png)](./media/formattingc130389.png)                         | Applicare lo stile del carattere selezionato al testo corrente.      |
| [![Pulsante Carattere](./media/fonttype.png)](./media/fonttype.png)                                                 | Impostare il carattere selezionato al testo corrente.              |
| [![Pulsante Dimensione carattere](./media/fontsize.png)](./media/fontsize.png)                                            | Impostare la dimensione carattere selezionata al testo corrente (in punti). |
| [![Pulsante Grassetto](./media/boldc130389.png)](./media/boldc130389.png)                                           | Rendere il testo in grassetto.                             |
| [![Pulsante Corsivo](./media/italicsc130389.png)](./media/italicsc130389.png)                                   | Rendere il testo in corsivo.                           |
| [![Pulsante Sottolineatura](./media/underlinec130389.png)](./media/underlinec130389.png)                            | Rendere il testo sottolineato.                             |
| [![Pulsante Diminuisci rientro](./media/outdentlsc130389.png)](./media/outdentlsc130389.png)                      | Ridurre il rientro del testo corrente.                |
| [![Pulsante Aumenta rientro](./media/indentlsc130389.png)](./media/indentlsc130389.png)                        | Aumentare il rientro del testo corrente.                |
| [![Pulsante Colore di sfondo](./media/fillbackgroundcolorc130389.png)](./media/fillbackgroundcolorc130389.png) | Modificare il colore di sfondo della cella corrente.        |
| [![Pulsante Colore carattere](./media/fontcolorc130389.png)](./media/fontcolorc130389.png)                           | Modificare il colore del testo corrente.                   |

### <a name="report-designer-toolbar"></a>Barra degli strumenti di Progettazione report

La barra degli strumenti di Progettazione report consente l'accesso rapido ai comandi per spostarsi al suo interno. Nella barra degli strumenti sono inclusi i seguenti pulsanti.

| Pulsante                                                                                              | Descrizione |
|-----------------------------------------------------------------------------------------------------|-------------|
| [![Pulsante Definizione di report](./media/reportc130389.png)](./media/reportc130389.png)                 | Visualizzare la definizione di report elencata nel menu **Finestra**. |
| [![Pulsante Definizione di riga](./media/rowc130389.png)](./media/rowc130389.png)                          | Visualizzare la definizione di riga assegnata alla definizione di report attiva. |
| [![Pulsante Definizione di colonna](./media/columnc130389.png)](./media/columnc130389.png)                 | Visualizzare la definizione di colonna assegnata alla definizione di report attiva. |
| [![Pulsante Definizione di albero gerarchico](./media/treec130389.png)](./media/treec130389.png)             | Visualizzare la definizione di albero gerarchico assegnata alla definizione di report attiva. |
| [![Pulsante Visualizzatore di report](./media/reportviewerc130389.png)](./media/reportviewerc130389.png)         | Avviare il visualizzatore di report e mostrare la versione più recente del report generato. Questo pulsante è disponibile da una definizione di report se è stato generato almeno un report. |
| [![Pulsante Genera report](./media/generate-to-ddvc130389.png)](./media/generate-to-ddvc130389.png) | Genera un report a partire dalla definizione di report attiva. Questo pulsante è disponibile da una definizione di report. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Creazione di report finanziari](financial-reporting-intro.md)

[Generare report finanziari](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]