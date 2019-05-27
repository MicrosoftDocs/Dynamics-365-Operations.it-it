---
title: Selezionare le definizioni del modello dati quando si creano i formati
description: Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc357db8acbdb98741a694a8a9d3c0c0625c50e4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551091"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a>Selezionare le definizioni del modello dati quando si creano i formati

[!include [task guide banner](../../includes/task-guide-banner.md)]

Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo". 

Questa procedura descrive come un elemento radice del modello può essere selezionato come definizione del modello dati per l'inserimento di una configurazione di formato ER progettata per generare documenti elettronici. In questa procedura verrà aggiunta una nuova configurazione di formato ER per la società di esempio Litware, Inc. 

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. I passaggi possono essere completati mediante un set di dati qualsiasi.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".  
2. Fare clic su Configurazioni report.

## <a name="add-a-new-er-data-model-configuration"></a>Aggiungere una nuova configurazione del modello dati ER
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
    * Aggiungiamo una nuova configurazione del modello ER contenente un modello dati progettato per essere utilizzato come origine dati per la generazione di report ER.  
2. Nel campo Nome digitare "Modello di pagamento (fittizio)".
    * Modello di pagamento (fittizio)  
3. Fare clic su Crea configurazione.
4. Fare clic su Progettazione.
    * Aprire la finestra di progettazione ER per specificare la struttura del modello dati della configurazione.  
    * Si supponga di progettare il modello dati per il dominio dei pagamenti aziendali per supportare 2 metodi di pagamento, ovvero bonifico e addebito diretto.  
5. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
6. Nel campo Nome digitare "Pagamenti - bonifico".
    * Pagamenti - bonifico  
7. Scegliere Aggiungi.
8. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
9. Nel campo Nuovo nodo come immettere 'Radice modello'.
10. Nel campo Nome digitare "Pagamenti - addebito diretto".
    * Pagamenti - addebito diretto  
11. Scegliere Aggiungi.
12. Fare clic su Salva.
13. Chiudere la pagina.
14. Fare clic su Cambia stato.
    * Completare la versione bozza del modello per renderlo disponibile nei mapping e nei formati del nuovo modello.  
15. Fare clic su Completa.
16. Fare clic su OK.

## <a name="start-to-enter-a-new-er-format-configuration"></a>Iniziare a immettere una nuova configurazione dei formati ER
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nuovo immettere "Formato in base al modello dati Modello di pagamento (fittizio)".
3. Nel campo Definizione modello dati immettere o selezionare un valore.
    * Si noti che tutti gli elementi radice sono attualmente disponibili per la selezione come definizione di modello dati. È possibile continuare la progettazione del formato utilizzando uno degli elementi radice necessari del modello dati. Un mapping di modello mancante per l'elemento radice selezionato non impedisce di continuare.  
4. Chiudere la pagina.

## <a name="add-a-new-er-model-mapping-configuration"></a>Aggiungere una nuova configurazione del mapping di modello ER
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nuovo immettere "Mapping modello in base al modello dati Modello di pagamento (fittizio)".
3. Nel campo Nome digitare "Mapping modello di pagamento (fittizio)".
    * Mapping di modelli di pagamento (fittizio)  
4. Nel campo Definizione modello dati immettere o selezionare un valore.
5. Fare clic su Crea configurazione.

## <a name="design-er-model-mappings"></a>Progettare mapping di modello ER
1. Fare clic su Progettazione.
    * Utilizzare la finestra di progettazione ER per specificare i mapping di modello per gli elementi radice necessari.  
2. Fare clic su Progettazione.
    * Simulare l'impostazione del mapping di modello selezionato per l'elemento radice del modello selezionato.  
3. Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.
4. Fare clic su Aggiungi radice.
5. Nel campo Nome digitare "Contabilità generale".
6. Nel campo Tabella digitare "LedgerJournalTrans".
    * LedgerJournalTrans  
7. Fare clic su OK.
8. Fare clic su Salva.
9. Chiudere la pagina.
10. Chiudere la pagina.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Iniziare a immettere un'altra nuova configurazione dei formati ER
1. Nella struttura selezionare "Payment model (fictitious)".
2. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
3. Nel campo Nuovo immettere "Formato in base al modello dati Modello di pagamento (fittizio)".
4. Nel campo Definizione modello dati immettere o selezionare un valore.
    * Si noti che ora solo un elemento radice è disponibile per eseguire il mapping a origini dati dell'applicazione. Quando viene introdotto almeno un mapping di modello, solo gli elementi radice del modello che sono mappati alle origini dati dell'applicazione possono essere selezionati come modello di definizione mentre il formato ER viene aggiunto.   
5. Chiudere la pagina.

