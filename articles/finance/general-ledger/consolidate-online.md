---
title: Consolidamenti finanziari online
description: In questo articolo vengono descritti i consolidamenti finanziari online nella contabilità generale.
author: aprilolson
ms.date: 12/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 5843ac78adf32e738d9882c7f4e9e04a79200700
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838281"
---
# <a name="online-financial-consolidations"></a>Consolidamenti finanziari online

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti i consolidamenti finanziari online nella contabilità generale. Prima di leggere questo articolo, leggi l'articolo [Panoramica dei consolidamenti finanziari e delle conversioni di valuta](financial-consolidations-currency-translation.md).

Dopo aver completato la configurazione, immettere i dettagli del consolidamento nella pagina **Consolidato [online]**. Al termine, è possibile fare clic su **OK** o **Batch** per elaborare il consolidamento.

## <a name="criteria"></a>Criteri
Nella scheda **Criteri** della pagina **Consolidato [online]**, si definiscono i conti, i periodi e il tipo di dati da consolidare.

![Scheda Criteri.](./media/criteria-consolidate-online.png "Scheda Criteri")

Ecco una spiegazione dei vari campi nella scheda:

- **Descrizione** - Immettere una descrizione precisa del periodo che si sta consolidando.
- **Conto principale** - Utilizzare i campi di questa sezione per definire i conti principali da elaborare.

    - **Da** e **A** - Specificare un intervallo di conti da elaborare. Se si lasciano vuoti questi campi, tutti i conti di tutte le società verranno spostati verso la società di consolidamento. Di conseguenza, se si esegue il consolidamento di quattro società e ogni società ha un piano dei conti diverso, tutti i conti di tutte e quattro le società verranno creati nella società di consolidamento.
    - **Utilizza conto di consolidamento** - Se si imposta questa opzione su **Sì**, diventa disponibile il campo **Selezionare il conto di consolidamento di origine**. In questo campo, selezionare se tutti i conti devono essere consolidati nel conto di consolidamento impostato nella pagina **Conti principali** o se selezionare il conto in uno dei gruppi di conti di consolidamento.
    - **Gruppo di conti di consolidamento** - Selezionare il gruppo da utilizzare per il mapping dei conti principali per il consolidamento.

- **Periodo di consolidamento** - Utilizzare i campi disponibili in questa sezione per definire il periodo di consolidamento.

    - **Da** e **A** - Specificare un intervallo di date per il consolidamento. Se questi campi vengono lasciati vuoti, il consolidamento verrà elaborato per tutti i periodi definiti nel calendario di contabilità generale per la società. È consigliabile non lasciare vuoti questi campi.
    - **Seleziona importo consolidamento da**: utilizza questo campo per specificare se verranno utilizzati gli importi in valuta di contabilizzazione o gli importi in valuta di dichiarazione delle società di origine per aggiornare gli importi in valuta di contabilizzazione della società di consolidamento.

        - Seleziona **Valuta di contabilizzazione** per utilizzare gli importi in valuta di contabilizzazione delle società di origine per aggiornare gli importi in valuta di contabilizzazione nella società di consolidamento. Quando viene selezionato questo valore, utilizza il campo **Valuta di contabilizzazione consolidata** per definire come verranno calcolate le valute di contabilizzazione nella società di consolidamento.
        - Seleziona **Valuta di dichiarazione** per utilizzare gli importi in valuta di dichiarazione delle società di origine per calcolare gli importi in valuta di contabilizzazione nella società di consolidamento.

            - Se la valuta di dichiarazione della società di origine è uguale alla valuta di contabilizzazione della società di consolidamento, gli importi in valuta di dichiarazione vengono copiati dalla società di origine alla società di consolidamento.
            - Se la valuta di dichiarazione della società di origine è diversa dalla valuta di contabilizzazione della società di consolidamento, i valori vengono convertiti utilizzando le informazioni di cambio definite nella scheda **Conversione valuta** di questa pagina per calcolare i valori della società di consolidamento.

    - **Consolida valuta di contabilizzazione** – Questo campo è disponibile solo se il campo **Seleziona importo consolidamento da** è impostato su **Valuta di contabilizzazione**. Utilizzalo per specificare se gli importi in valuta di contabilizzazione delle società di origine vengono convertiti tramite i tassi di cambio o copiati nella società di consolidamento. Seleziona **Usa conversione valuta** per utilizzare le informazioni sul tasso di cambio definite nella scheda **Conversione valuta** per calcolare i saldi della contabilità di consolidamento. Seleziona **Utilizza importo in valuta di contabilizzazione** per copiare gli importi in valuta di contabilizzazione delle società di origine nella società di consolidamento.

        - Se la valuta di contabilizzazione della società di origine è uguale alla valuta di contabilizzazione della società di consolidamento, gli importi in valuta vengono copiati dalla società di origine alla società di consolidamento.
        - Se la valuta di contabilizzazione della società di origine è diversa dalla valuta di contabilizzazione della società di consolidamento, i valori vengono convertiti utilizzando le informazioni di cambio definite nella scheda **Conversione valuta** per calcolare i valori della società di consolidamento.

    - **Includi importi effettivi** - Impostare questa opzione su **Sì** per consolidare i dati effettivi.
    - **Includi importi di budget** - Impostare questa opzione su **Sì** per consolidare i dati del registro di budget.
    - **Ricrea i saldi durante il processo di consolidamento** - Non è consigliabile impostare questa opzione su **Sì**. Ricostruire invece i saldi come processo batch separato.

- **Modelli di budget** - Se è stato scelto di consolidare i dati di budget, utilizzare i campi di questa sezione per definire i modelli di budget.

    - **Da** e **A** - Specificare l'intervallo di modelli da utilizzare.
    - **Tipo di tasso del budget** - Selezionare il tipo di tasso del budget da utilizzare per la conversione di valuta dei dati del budget.

## <a name="financial-dimensions"></a>Dimensioni finanziarie
Nella scheda **Dimensioni finanziarie** si definiscono le dimensioni che devono essere incluse nella società di consolidamento. Per selezionare una dimensione, impostare il campo **Specifica** su **Dimensione** e definire l'ordine della dimensione nella società di consolidamento.

![Scheda Dimensioni finanziarie.](./media/financial-dimensions-cons.png "Scheda Dimensioni finanziarie")

Indipendentemente dall'ordine che si definisce, **Conto principale** sarà sempre il primo segmento.

## <a name="legal-entities"></a>Persone giuridiche
Nella scheda **Persone giuridiche** si definiscono le società che devono essere incluse nella società di consolidamento. Si definisce inoltre la percentuale di proprietà di tali società. Se si specifica una proprietà inferiore al 100%, verrà eseguito il rollup della percentuale specificata alla società di consolidamento. Per tutte le differenze di conversione, il campo **Tipo di conto per differenze di conversione** viene utilizzato per selezionare il conto principale dall'impostazione nella pagina **Conti per transazioni automatiche**.

![Scheda Persone giuridiche.](./media/legal-entities-cons.png "Scheda Persone giuridiche")

![Pagina Conti per transazioni automatiche.](./media/accounts-for-automatic-cons.png "Pagina Conti per transazioni automatiche")

## <a name="elimination"></a>Eliminazione
Nella scheda **Eliminazione** sono disponibili tre opzioni per elaborare le eliminazioni:

- Selezionare la regola di eliminazione, quindi nel campo **Opzioni proposta** selezionare **Solo proposta**. Questa opzione elaborerà l'eliminazione durante il processo di consolidamento, ma registrerà tutto in un unico passaggio. È possibile registrare nel giornale di registrazione in un secondo momento.
- Selezionare la regola di eliminazione, quindi nel campo **Opzioni proposta** selezionare **Registra solo**. Questa opzione elaborerà l'eliminazione durante il processo di consolidamento e registrerà tutto in un unico passaggio.
- Eseguire una proposta di eliminazione separatamente dal processo di consolidamento utilizzando il giornale di registrazione eliminazioni.

![Scheda Eliminazione.](./media/elimination-cons-onl.png "Scheda Eliminazione")

Per ulteriori informazioni sulle eliminazioni, vedere [Regole di eliminazione](./elimination-rules.md).

## <a name="currency-translation"></a>Conversione valuta
Nella scheda **Conversione valuta** si definiscono la persona giuridica, il conto e il tipo di tasso di cambio e la percentuale. Se la società di consolidamento è mappata su conti principali diversi da quelli della società di origine, il conto principale della società di consolidamento deve essere inserito nei campi **Data iniziale** e **Data finale**, non i conti principali della società di origine. Per ogni riga della persona giuridica e dei conti principali, sono disponibili tre opzioni nel campo **Applica tasso di cambio da**:

- **Data consolidamento** – La data definita nel campo **Fine periodo di consolidamento** nella scheda **Criteri** per il consolidamento da usare per ottenere il tasso di cambio. Questo tasso è equivalente alla quotazione corrente o frequenza di fine mese. Sarà visibile un'anteprima del tasso, ma non sarà possibile modificarlo.
- **Data della transazione** - La data di ogni transazione verrà utilizzata per selezionare un tasso di cambio. Questa opzione viene utilizzata principalmente per i cespiti e spesso è denominata tasso storico. Non è possibile visualizzare un'anteprima del tasso, perché saranno presenti molti tassi per le diverse transazioni nell'intervallo di conti.
- **Tariffa definita dall'utente** - Dopo avere selezionato questa opzione, è possibile immettere il tasso di cambio desiderato. Questa opzione può essere utile per i tassi di cambio medi o se si esegue il consolidamento in base a un tasso di cambio fisso.

![Scheda Conversione valuta.](./media/currency-translation-cons-online.png "Scheda Conversione valuta")

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori informazioni sul consolidamento e sulle conversioni di valuta, vedi l'articolo padre di questo articolo [Panoramica dei consolidamenti finanziari e delle conversioni di valuta](./financial-consolidations-currency-translation.md).

Per informazioni sugli scenari in cui si potrebbero generare rendiconti finanziari consolidati, vedere [Generare rendiconti finanziari consolidati](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
