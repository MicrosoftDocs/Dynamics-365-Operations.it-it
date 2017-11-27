---
title: Componenti del report finanziario
description: In questo articolo viene illustrato l'utilizzo dei componenti, o blocchi predefiniti, delle definizioni dei report nei report finanziari. Tali blocchi predefiniti includono le definizioni di riga, di colonna e di albero gerarchico. L'articolo spiega come organizzare e bloccare i blocchi predefiniti e come utilizzare i gruppi di blocchi predefiniti.
author: aolson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7b283b8550bd7e5eff969d45c761d0a54d93a33e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="financial-report-components"></a>Componenti del report finanziario

[!include[banner](../includes/banner.md)]


In questo articolo viene illustrato l'utilizzo dei componenti, o blocchi predefiniti, delle definizioni dei report nei report finanziari. Tali blocchi predefiniti includono le definizioni di riga, di colonna e di albero gerarchico. L'articolo descrive come organizzare e bloccare i blocchi predefiniti. 

La filosofia di progettazione alla base di Progettazione report finanziari è suddividere le informazioni in componenti o blocchi predefiniti più piccoli possibile e quindi mescolare e abbinare i componenti necessari. La formattazione del report è pertanto separata dai dati finanziari ed è possibile modificare la struttura di un report senza modificare i dati finanziari nel sistema Microsoft Dynamics ERP. Utilizzando questo approccio dei blocchi predefiniti, è possibile combinare testo, importi e calcoli, per generare i report necessari. Inoltre, la flessibilità incoraggia la creatività semplificando la visualizzazione delle operazioni in vari modi. I singoli blocchi predefiniti di definizione di report sono simili a un foglio tridimensionale, ma con maggiore potenza. Una definizione di report specifica la definizione di riga, la definizione di colonna e la definizione facoltativa dell'albero gerarchico da utilizzare per il report. Sono inoltre incluse le informazioni sull'archiviazione del report generato e sul formato. 

## <a name="building-blocks-of-a-report"></a>Blocchi predefiniti di un report
| Blocco predefinito            | descrizione                     | Ulteriori informazioni                                    |
|---------------------------|---------------------------------|---------------------------------------------------------|
| Definizione riga            | Una definizione di riga definisce le righe descrittive, ad esempio, le retribuzioni o le vendite, in un report. Vengono inoltre elencati i valori o le dimensioni di segmenti che contengono i valori per ogni voce e sono inclusi la formattazione e i calcoli di riga.                                                    | [Definizioni di riga](row-definitions-financial-reporting.md)                       |
| Definizione colonna         | Una definizione di colonna definisce il periodo da utilizzare quando si estraggono i dati dalle dimensioni finanziarie. Include inoltre la formattazione e i calcoli della colonna.                                                                                                                                 | [Definizioni di colonna](column-definitions-financial-reports.md)         |
| Definizione di albero gerarchico | La definizione di un albero gerarchico è simile a un organigramma. Contiene le singole unità di report che rappresentano ogni casella nel grafico. Le unità possono essere singoli reparti di dati finanziari o unità di livello superiore che riepilogano i dati da altre unità di report. | [Definizioni di albero gerarchico](financial-reporting-tree-definitions.md) |
| Definizione di report         | Una definizione di report utilizza una definizione di riga, una definizione di colonna e una definizione facoltativa dell'albero gerarchico per creare un report. Sono anche riportate opzioni e impostazioni aggiuntive da utilizzare per personalizzare un report.                                                                    | [Definizione di report](design-financial-report-definitions.md)                  |

Se è la prima volta che si progettano report, può essere utile utilizzare la procedura guidata per creare rapidamente una definizione di report da personalizzare successivamente. Se si ha esperienza nella progettazione dei report e si desidera più flessibilità, è possibile combinare blocchi predefiniti nuovi o esistenti per creare una nuova definizione di report. Non è necessario comprendere tutte le opzioni disponibili per la definizione dei report per generare report di qualità. Quando si acquisisce dimestichezza con la progettazione dei report, è possibile espandere le definizioni dei report per utilizzare le funzionalità più avanzate. Dopo avere creato un report di base, è possibile personalizzare la definizione di report e qualsiasi blocco predefinito nella definizione di report.

## <a name="organize-the-building-blocks"></a>Organizzare i blocchi predefiniti
Utilizzare le cartelle per organizzare i blocchi predefiniti in Progettazione report. Tutte le cartelle sono specifiche del tipo di blocco predefinito che contengono. Ad esempio, tutte le cartelle contenenti le definizioni di riga vengono situate nel riquadro **Definizioni di riga** di Progettazione report.

### <a name="create-a-folder"></a>Creare una cartella

1.  In Progettazione report, selezionare il tipo di blocco predefinito da organizzare nel pannello di navigazione. Ad esempio, per ordinare una definizione di riga, fare clic su **Definizioni di riga**.
2.  Nel pannello di navigazione, selezionare la cartella esistente sotto cui creare la nuova cartella e quindi completare uno dei passaggi seguenti:
    -   Fare clic con il pulsante destro del mouse sulla cartella padre e selezionare **Nuova cartella**.
    -   Selezionare la cartella padre, fare clic su **File** e scegliere **Nuova cartella**.

3.  Quando la nuova cartella viene visualizzata, immettere il nome della nuova cartella e premere INVIO.

## <a name="lock-a-building-block"></a> Bloccare un blocco predefinito
È possibile creare una password per bloccare e proteggere un blocco predefinito. In tal modo si aggiunge un livello di sicurezza al componente del report senza proteggere l'intero sistema. Una password può aiutare a proteggere le informazioni del blocco predefinito che sono importanti per il processo di dichiarazione di fine mese. Un utente in qualsiasi ruolo può bloccare un blocco predefinito. Tuttavia, altri utenti hanno sempre accesso in sola lettura a un componente bloccato. Gli utenti possono aprire, modificare e salvare il componente bloccato con un nuovo nome. Un utente con il ruolo di amministratore può sempre accedere e modificare un blocco predefinito bloccato.
1.  In Progettazione report, aprire il componente di report da bloccare, ad esempio una definizione di riga, una definizione di colonna, una definizione di report o una definizione di albero gerarchico.
2.  Nel menu **Strumenti**, fare clic su **Proteggi/Rimuovi protezione**. È inoltre possibile fare clic sull'icona **Proteggi/Rimuovi protezione** (un lucchetto) nella barra degli strumenti.
3.  Nella finestra di dialogo **Proteggi** immettere e confermare una password, quindi fare clic su **OK**. L'icona del lucchetto nella barra degli strumenti è evidenziata quando un blocco predefinito aperto viene bloccato.

Per sbloccare un blocco predefinito bloccato, aprire il blocco predefinito e quindi fare clic sull'icona **Proteggi/Rimuovi protezione** nella barra degli strumenti. In alternativa, nel menu **Strumenti**, fare clic su **Proteggi/Rimuovi protezione**.

## <a name="building-block-groups"></a>Gruppi di blocchi predefiniti

I blocchi predefiniti sono le definizioni di riga, le definizioni di colonna, le definizioni di albero gerarchico e le definizioni di report che vengono create per un report. I gruppi di blocchi predefiniti sono raccolte di definizioni e set di dimensioni associati a una società. 


### <a name="view-a-building-block-group"></a>Visualizzare un gruppo di blocchi predefiniti

È possibile visualizzare tutti i blocchi predefiniti assegnati a un gruppo di blocchi predefiniti. È inoltre possibile esportare o importare un gruppo di blocchi predefiniti.
1.  In Progettazione report scegliere **Gruppi di blocchi predefiniti** dal menu **Società**.
2.  Nella finestra di dialogo **Gruppi di blocchi predefiniti**, selezionare il blocco predefinito da visualizzare.
3.  Fare clic su **Visualizza** per aprire la finestra di dialogo **Visualizza gruppo di blocchi predefiniti** e visualizzare il contenuto del gruppo di blocchi predefiniti.
4.  Fare clic su **Chiudi** per chiudere le finestre di dialogo.

### <a name="export-a-building-block-group"></a>Esportare un gruppo di blocchi predefiniti

È possibile esportare un gruppo di blocchi predefiniti o blocchi predefiniti di report specifici in un gruppo di blocchi predefiniti. È possibile utilizzare il gruppo di blocchi predefiniti esportato come backup. È inoltre possibile copiare i dati esportati tra installazioni di Finance and Operations. La funzionalità di progettazione report include gli stili di carattere e i set di dimensioni di riferimento con il gruppo di blocchi predefiniti.
1.  In Progettazione report, menu **Società**, fare clic su **Gruppi di blocchi predefiniti**.
2.  Nella finestra di dialogo **Gruppi di blocchi predefiniti** selezionare il gruppo che si desidera esportare e quindi fare clic su **Esporta**.
3.  Nella finestra di dialogo **Esporta**, selezionare le definizioni di report da esportare:
    -   Per esportare tutte le definizioni di report e i blocchi predefiniti associati, fare clic su **Seleziona tutto**.
    -   Per esportare specifici report, righe, colonne, alberi o set di dimensioni, fare clic sulla scheda appropriata e selezionare gli elementi da esportare. Per selezionare più elementi in una scheda, tenere premuto CTRL. **Nota**: quando si selezionano i report da esportare, vengono selezionate le righe, le colonne, gli alberi e i set di dimensioni associati.

4.  Una volta selezionati gli elementi da esportare, fare clic su **Esporta**.
5.  Nella finestra di dialogo **Salva con nome**, selezionare un'ubicazione in cui esportare il gruppo di blocchi predefiniti.
6.  Nel campo **Nome file** immettere un nome per il file. Progettazione report aggiunge automaticamente l'estensione di file .tdbx.
7.  Fare clic su **Salva**. Il gruppo di blocchi predefiniti viene salvato nel percorso specificato.

### <a name="import-a-building-block-group"></a> Importare un gruppo di blocchi predefiniti

È possibile importare un gruppo di blocchi predefiniti in un gruppo di blocchi predefiniti esistente. Tutti i gruppi di blocchi predefiniti importati conservano gli stili di carattere e i riferimenti alle società originali e includono i set di dimensioni pertinenti.
1.  In Progettazione report, menu **Società**, fare clic su **Gruppi di blocchi predefiniti**.
2.  Nella finestra di dialogo **Gruppi di blocchi predefiniti** selezionare il blocco predefinito in cui importare un gruppo di blocchi predefiniti, quindi fare clic su **Importa**.
3.  Nella finestra di dialogo **Apri** selezionare il gruppo di blocchi predefiniti da importare, quindi fare clic su **Apri**.
4.  Nella finestra di dialogo **Importa**, selezionare le definizioni di report da importare:
    -   Per importare tutte le definizioni di report e i blocchi predefiniti di supporto, fare clic su **Seleziona tutto**.
    -   Per importare specifici report, righe, colonne, alberi o set di dimensioni, selezionare i report, le righe, le colonne, gli alberi o i set di dimensioni da importare.

5.  Una volta selezionati gli elementi da importare, fare clic su **Importa**.

### <a name="undo-a-checkout-of-a-building-block"></a>Annullare l'estrazione di un blocco predefinito

Quando si apre un blocco predefinito, gli utenti possono accedere al blocco predefinito solo in modalità di sola lettura. Talvolta un utente può dimenticare di chiudere un blocco predefinito o arrestare il sistema senza aver chiuso il blocco predefinito. Di conseguenza, il blocco predefinito risulta estratto e non può essere aperto da altri utenti. In queste situazioni, un amministratore dei report finanziari può utilizzare la finestra di dialogo **Elementi estratti** per archiviare i blocchi predefiniti lasciati in stato estratto dagli utenti. **Nota:** è necessario disporre del ruolo di amministratore per archiviare i blocchi predefiniti usando la finestra di dialogo **Elementi estratti**.
1.  In Progettazione report, nel menu **Strumenti**, fare clic su **Elementi estratti**.
2.  Nella finestra di dialogo **Elementi estratti** selezionare **Mostra elementi di tutti gli utenti**. L'elenco verrà aggiornato per visualizzare tutti i blocchi predefiniti estratti con l'indicazione degli utenti che hanno effettuato l'estrazione.
3.  Selezionare un blocco predefinito e quindi fare clic su **Annulla estrazione**.
4.  Fare clic su **Sì** per archiviare il blocco predefinito.

# <a name="see-also"></a>Vedere anche

[Creazione di report finanziari](financial-reporting-intro.md)




