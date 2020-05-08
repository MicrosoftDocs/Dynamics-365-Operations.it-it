---
title: Creare contratti avanzati per la fatturazione in base allo stato di avanzamento
description: Questo argomento spiega come creare contratti di progetto in modo da poter generare fatture per i clienti, in base a una percentuale del lavoro completato.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282833"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Creare contratti avanzati per la fatturazione in base allo stato di avanzamento
[!include [banner](../includes/banner.md)]

Questo argomento spiega come creare contratti di progetto in modo da poter creare fatture per i clienti, in base a una percentuale del lavoro completato. Gli importi della fattura per le categorie di budget di lavoro, impostati per un progetto, vengono calcolati automaticamente, La tempistica della fattura viene impostata quando si negozia il contratto di progetto con il cliente.

Utilizzare le seguenti procedure per impostare un contratto, un progetto associato e le regole di fatturazione da utilizzare per calcolare gli importi della fattura per le categorie di budget di lavoro impostate per il progetto.

Dopo avere creato il contratto e il progetto, è possibile impostare i dettagli del progetto. Ad esempio, è possibile definire attività e assegnare lavoratori al progetto.

## <a name="example"></a>Esempio

L'organizzazione dell'utente è una società di sviluppo software Si concorda quindi di sviluppare un pacchetto di contabilità salariale per un cliente per una commissione totale di 20.000 dollari USA (USD). L'organizzazione accetta di fatturare al cliente man mano che si completano specifiche percentuali del progetto. È possibile impostare le seguenti categorie di progetti per il lavoro, in modo da poterle utilizzare nel processo di fatturazione:

- Consulenza
- Progetta
- Installazione

È inoltre possibile impostare regole di fatturazione che calcolano automaticamente gli importi delle fatture per la percentuale di lavoro di progetto completata in ciascuna categoria.

Il responsabile budget creerà un budget per le categorie di progetto. L'importo relativo al lavoro completato viene automaticamente calcolato come percentuale di lavoro effettivo rispetto agli importi a budget.

## <a name="prerequisites"></a>Prerequisiti

Prima di creare un progetto che utilizza regole di fatturazione, è necessario impostare le sequenze numeriche per le regole di fatturazione e un giornale di registrazione delle commissioni che viene utilizzato per la registrazione delle fatturazioni progressive.

1. Andare a **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.
2. Nella pagina **Parametri Gestione progetti e contabilità**, nella scheda **Sequenze numeriche**, impostare la sequenza numerica che si desidera utilizzare nel momento in cui vengono create le regole di fatturazione.
3. Andare a **Gestione progetti e contabilità** \> **Giornali di registrazione** \> **Commissioni**.
4. Nella pagina **Giornale di registrazione commissioni**, selezionare **Nuovo** e inserire il nome del giornale.

## <a name="create-a-contract-for-progress-billings"></a>Creare un contratto per fatturazioni progressive

Utilizzare questa procedura per creare un contratto di progetto per un progetto a prezzo fisso. Creare una fattura di progetto quando il lavoro nel progetto è completato e raggiunge una specifica percentuale.

1. Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Contratti di progetto**.
2. Nella pagina **Contratti di progetto**, selezionare **Nuovo**.
3. Nella finestra di dialogo **Nuovo contratto di progetto**, impostare i seguenti campi:

    - **Nome**
    - **Tipo di finanziamento**
    - **Fonte di finanziamento**
    - **Valuta di vendita** – Per impostazione predefinita, questa valuta viene utilizzata per le fatture dei clienti che sono associate al contratto di progetto. Tuttavia, è possibile cambiare la valuta di vendita su una fattura cliente specifico.

4. Selezionare **OK**. Le informazioni vengono copiate nell'intestazione della pagina **Contratti di progetto**.
5. Nella pagina **Contratti di progetto**, inserire il resto delle informazioni richieste per il progetto.

## <a name="create-a-project-for-progress-billings"></a>Creare un progetto per le fatturazioni progressive

Seguire i seguenti passaggi per creare un progetto e tutti i sottoprogetti associati a un contratto di progetto.

1. Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**.
2. Nella pagina **Tutti i progetti**, selezionare **Nuovo**.
3. Nella finestra di dialogo **Nuovo progetto**, nel campo **Tipo di progetto**, selezionare **Tempistica e materiali**.
4. Consente di selezionare un tipo di gruppo di progetti. Un gruppo di progetti definisce le informazioni di registrazione per i progetti assegnati al gruppo.
5. Selezionare **Crea progetto**.
6. Dopo avere creato il progetto, impostare la fase di progetto su **In corso**.

## <a name="create-a-budget-for-a-project"></a>Creare un budget per un progetto.

Le categorie di budget vengono utilizzate per calcolare automaticamente gli importi delle fatture per la percentuale di lavoro completata per ciascuna categoria. Seguire questi passaggi per creare delle categorie di budget per i costi stimati.

1. Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**.
2. Nella pagina **Tutti i progetti**, selezionare e aprire il progetto desiderato.
3. Nella pagina **Progetti**, nel riquadro azioni, nella scheda **Pianificare** nel gruppo **Budget**, selezionare **Budget del progetto**.
4. Nella pagina **Budget del progetto**, immettere un costo stimato per ogni categoria nel progetto.

## <a name="create-billing-rules-for-progress-billings"></a>Creare regole per fatturazioni progressive

1. Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Contratti di progetto**.
2. Nella pagina **Contratti di progetto**, selezionare e aprire un contratto di progetto.
3. Nella pagina del contratto di progetto, nella scheda dettaglio **Regole di fatturazione**, selezionare **Aggiungi**.
4. Nella pagina **Regola di fatturazione**, nel campo **Tipo di riga**, selezionare **Avanzamento**.
5. Nella scheda dettaglio **Dettagli regola di fatturazione**, nel campo **Valore di contratto** , immettere il valore totale del contratto.
6. Nel campo **Categorie** selezionare la categoria in cui registrare la transazione.
7. Nel campo **Progetto** selezionare il progetto che utilizza questa regola di fatturazione.
8. Facoltativo: Assegnare la regola di fatturazione a progetti aggiuntivi. Nella scheda dettaglio **Progetto**, nella sezione **Progetti disponibili**, selezionare un progetto, quindi selezionare il pulsante freccia a destra per aggiungere il progetto alla sezione **Progetti selezionati**.
9. Facoltativo: calcolare l'importo percentuale che il cliente trattiene dai pagamenti su una fattura. Nella scheda dettaglio **Condizioni di ritenuta sul pagamento**, selezionare la fonte di finanziamento, quindi nel campo **Percentuale ritenuta** , immettere la percentuale di ritenuta.
10. Ripetere la procedura per creare regole di fatturazione aggiuntive al contratto di progetto.
