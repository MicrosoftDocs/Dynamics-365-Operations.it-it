---
title: Data di competenza per le transazioni e il report giornale di registrazione fiscale
description: In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia
author: anasyash
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Italy
ms.author: anasyash
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9942bbb091e759295fc0b22fd9ba02f5408041c0
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557438"
---
# <a name="competence-date-for-transactions-and-the-fiscal-journal-report"></a>Data di competenza per le transazioni e il report giornale di registrazione fiscale

In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia.

In Italia, le società devono utilizzare una data di registrazione per registrare le transazioni. La data di registrazione nel giornale di registrazione fiscale corrisponde alla data in cui la società conferma la transazione.

Le transazioni di chiusura e correzione avvengono in genere alla data in cui lo stato patrimoniale viene approvato dal consiglio di amministrazione. Possono tuttavia essere anche completate diversi mesi dopo l'ultimo giorno dell'anno fiscale. Tali transazioni devono essere dichiarate nel giornale di registrazione fiscale italiano alla data di registrazione, che deve coincidere con la data di conferma. Le transazioni devono tuttavia avere un riferimento alla relativa data di competenza, che rappresenta la data in cui la transazione influisce sull'importo del saldo.

## <a name="turn-on-the-competence-date-functionality"></a>Attiva la funzionalità della data di competenza

1.  Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.

2.  Nella pagina **Parametri di contabilità generale**, nella scheda **Contabilità generale** impostare l'opzione **Riferimento alla data competenza nella data della transazione** su **Sì**.

    Dopo aver attivato la funzionalità della data di competenza, è possibile specificare **Data transazione** come data di conferma per ogni giornale di registrazione utilizzabile per registrare le transazioni di correzione e di chiusura per l'anno fiscale:

    -   Giornale di registrazione generale (**Contabilità generale** \> **Inserimenti nel giornale di registrazione** \> **Giornali di registrazione generale**)
    -   Giornale di registrazione cespiti (**Cespiti** \> **Scritture contabili** \> **Giornale di registrazione cespiti**)
    -   Riconciliazione estratti conto bancario (**Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari** \> **Riconcilia** \> **Riconciliazione estratti conto**)
    -   Rettifiche periodo di chiusura (**Contabilità generale** \> **Periodo chiuso** \> **Rettifiche periodo di chiusura**)
    -   Chiusura di fine anno (**Contabilità generale** \> **Periodo chiuso** \> **Chiusura di fine anno** \> **Esegui chiusura fiscale**)
    -   Progetto - Registra costi (**Gestione progetti e contabilità** \> **Periodico** \> **Tempistica e materiali** \> **Registra costi** \> **Registra**)
    -   Progetto - Accumula ricavi (**Gestione progetti e contabilità** \> **Periodico** \> **Tempistica e materiali** \> **Accumula ricavi**)
    -   Progetto - Stima registrata (**Gestione progetti e contabilità** \> **Periodico** \> **Stime** \> **Registra stime**)
    -   Progetto - Storna stima (**Gestione progetti e contabilità** \> **Periodico** \> **Stime** \> **Storna stime**)

## <a name="fiscal-journal-report"></a>Report Giornale di registrazione fiscale

Il report **Giornale di registrazione fiscale** italiano (**Contabilità generale \> Richieste e report \> Giornale di registrazione fiscale**) è un report mensile che elenca tutti i giustificativi e gli inserimenti nel giornale di registrazione nell'ordine, in base alla data di registrazione.

In questo report sono inclusi i seguenti campi:

-   Numero riga
-   Data di registrazione
-   Data competenza
-   Numero documento (numero giustificativo)
-   Data del documento
-   Nome e numero del conto CoGe
-   Nome e numero del conto cliente o fornitore
-   Descrizione
-   Valuta
-   Importo in Dare o in Avere del documento

![Transazioni del report Giornale di registrazione fiscale](media/ITA-Competence-date-for-transactions-1-fiscal-journal.png)

## <a name="example"></a>Esempio

L'anno fiscale della società inizia l'1 gennaio e termina il 31 dicembre. Lo stato patrimoniale viene approvato il 15 aprile. Di conseguenza, le transazioni di chiusura e correzione vengono dichiarate nel giornale di registrazione fiscale italiano ad aprile, ma influiscono sul saldo al 31 dicembre.

1. Andare a **Contabilità generale** \> **Inserimenti nel giornale di registrazione** \> **Giornali di registrazione generali**.
2. Nella pagina **Giornale di registrazione generale** specificare 31 dicembre nel campo **Data**.
3. Nel campo **Data transazione** specificare il 15 aprile.
4. Registrare la transazione.

    ![Pagina del giustificativo giornale di registrazione](media/ITA-Competence-date-for-transactions-2-general-journal.png)

5. Andare a **Contabilità generale** \> **Richieste di informazioni e report** \> **Giornale di registrazione fiscale** ed eseguire il report. La transazione viene riportata nella riga del giornale di registrazione fiscale. Il campo **Data di registrazione** è impostato sul 15 aprile e il campo **Data competenza** è impostato sul 31 dicembre.

    ![Pagina Giornale di registrazione fiscale](media/ITA-Competence-date-for-transactions-3-fiscal-journal.png)

6. Andare a **Contabilità generale \> Richieste di informazioni e report \> Bilancio di verifica** ed esegui il report.

    ![Descrizione interfaccia utente grafica e descrizione generata automaticamente](media/ITA-Competence-date-for-transactions-4-trial-balance.png)

7. Andare a **Contabilità generale** \> **Richieste di informazioni e report** \> **Transazioni giustificativo**.
8. Nella pagina **Transazioni giustificativo** aggiungere la colonna **Data transazione**.
9. Verificare il campo **Data** sia impostato sul 31 dicembre e il campo **Data transazione** sia impostato sul 15 aprile.

## <a name="fiscal-journal-page-numbering-improvements"></a>Miglioramenti alla numerazione delle pagine del giornale fiscale

È possibile abilitare la funzionalità **(Italia) Miglioramenti alla numerazione delle pagine del giornale fiscale** nell'area di lavoro **Gestione funzionalità**.

Questa funzionalità migliora la logica di calcolo per la numerazione delle pagine nel report del giornale fiscale italiano. Per aggiornare e memorizzare i numeri di pagina, stampare il rapporto su una schermata con la funzionalità **Visualizzatore PDF report** abilitata o stampare il report su un file in formato PDF. I numeri di pagina vengono calcolati utilizzando il nuovo algoritmo quando il report del giornale fiscale viene stampato in formato PDF. I numeri di pagina vengono memorizzati in modo che le pagine del report del mese successivo inizino in sequenza utilizzando il numero successivo a quello memorizzato. Questa funzionalità abilita anche un algoritmo per raggruppare righe con gli stessi valori di colonna in una riga, in modo che solo le pagine necessarie siano incluse nella stampa del report.

Se è necessario calcolare il numero di documenti inclusi nel giornale di registrazione fiscale, completare i seguenti passaggi.

1.  Stampare il report in un formato di file PDF.
2.  Convertire il PDF in Microsoft Excel utilizzando un software di conversione.
3.  Creare una tabella pivot e nel campo **Righe**, selezionare **N. doc.**.

    ![Tabella pivot di Excel](media/ExcelPivotTable.png)

Il numero di documenti è uguale al numero di righe nella tabella pivot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

