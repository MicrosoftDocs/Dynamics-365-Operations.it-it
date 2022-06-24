---
title: Creare piani di retribuzione fissa
description: Questo articolo descrive i componenti che devono essere impostati per creare un piano di retribuzione fissa e iscrivere i dipendenti.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable, HcmCompensationWorkspace
audience: Application User
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: f254afc37d5afae48c3b2b3b16bd86634ac9aa3a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875744"
---
# <a name="create-a-fixed-compensation-plans"></a>Creare piani di retribuzione fissa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La retribuzione fissa fa riferimento allo stipendio lordo regolare o alle retribuzioni del dipendente. Questo articolo descrive i componenti che devono essere impostati per creare un piano di retribuzione fissa e iscrivere i dipendenti.

Gli importi di retribuzione fissa possono essere calcolati per i dipendenti in base a fattori quali prestazioni, regione e incrementi di budget. Dynamics 365 Human Resources supporta tipi di retribuzione basati su scala, fascia o grado retributivo.

## <a name="fixed-compensation-components"></a>Componenti di retribuzione fissa
### <a name="compensation-levels"></a>Livelli retributivi

Puoi utilizzare **livelli retributivi** per impostare la retribuzione per lavori diversi. In questo modo garantisci che i dipendenti responsabili di quei lavori vengano pagati adeguatamente. Nella pagina **Livelli retributivi** è possibile impostare i livelli retributivi per ogni scala, fascia o grado. Utilizzare i pulsanti **Su** e **Giù** per inserire i livelli nell'ordine corretto, in base al relativo tipo. Impostando i livelli retributivi su una mansione, è possibile garantire che tutti i dipendenti che detengono una posizione per tale mansione vengano retribuiti allo stesso livello.

### <a name="reference-points"></a>Punti di riferimento

I **punti di riferimento** sono le colonne nella griglia che definiscono gli intervalli di retribuzione per ciascun livello. Il livello retributivo corrisponde alla riga nella griglia. I punti di riferimento tipici per un piano di tipo grado è un valore minimo, un punto intermedio e un valore massimo. È possibile creare i punti di riferimento nella pagina **Impostazioni punti di riferimento**.

### <a name="compensation-grids"></a>Griglie retributive

Dopo aver impostato i livelli e i punti di riferimento, è possibile combinarli per creare una **griglia di retribuzione**. Nella pagina **Griglie retributive**, definire le informazioni sulla griglia. Ad esempio, specificare lo scopo per il quale la griglia viene utilizzata, il tipo di piano con cui verrà utilizzata e le colonne o i punti di riferimento necessari nella griglia. Dopo aver completato l'immissione di tali informazioni, fare clic su **Struttura retributiva** per aggiungere livelli e importi alla griglia. 

**Suggerimento:** utilizzare la funzione **Modifiche di massa** sulla struttura retributiva per impostare gli importi iniziali, quindi l'incremento per percentuali o importi tra i livelli o i punti di riferimento.

### <a name="pay-frequencies"></a>Frequenze retribuzione

Le **Frequenze retribuzione** vengono utilizzate per definire la modalità in cui viene specificato lo stipendio o la retribuzione di un dipendente (ad esempio 10 EUR all'ora o 50.000 EUR all'anno) e la conversione tra le tariffe orarie, settimanali, mensili (12 mesi) e annuali. Ad esempio, una società che utilizza una settimana lavorativa di 38 ore per i relativi dipendenti retribuiti all'ora imposta una frequenza di retribuzione pari a una frequenza oraria di 1, settimanale di 38, mensile di 164,6666666667 e annuale di 1.976. Queste conversioni vengono utilizzate per calcolare le diverse tariffe retributive visualizzate nel record di retribuzione fissa del dipendente.

## <a name="fixed-compensation-plans"></a>Piani di retribuzione fissa
È possibile progettare il piano di retribuzione fissa per combinare tutti i componenti configurati. Per creare un piano di retribuzione fissa, aprire la pagina **Piani di retribuzione fissa**. In questa pagina è possibile immettere un nome e una descrizione del piano, selezionare il tipo di piano (scala, fascia o grado), selezionare la frequenza di retribuzione che verrà utilizzata per la tariffa retributiva del dipendente (importo orario, annuale e così via) e impostare alcune opzioni che controllano come viene elaborata l'elaborazione. 

L'impostazione **Tolleranza non compresa nell'intervallo** consente di specificare con quale rigidità si desidera assicurarsi che gli importi di retribuzione siano compresi tra il valore minimo e massimo. Una tolleranza di tipo **Rigido** richiede che la retribuzione rientri nell'intervallo definito per un livello specificato. Una tolleranza **Flessibile** avvisa quando l'importo di retribuzione non rientra nell'intervallo ma consente di continuare. Se la tolleranza è impostata su **Nessuno**, è possibile immettere qualsiasi importo di retribuzione per un dipendente senza ricevere messaggi di errore o di avviso. 

L'impostazione **Regola di assunzione** consente di specificare se tutti i dipendenti devono ricevere lo stesso aumento, indipendentemente dalla data in cui sono stati assunti (**Regola di assunzione** = **Nessuno**) o se i dipendenti devono ottenere una percentuale del premio, in base alla durata di assunzione durante il ciclo (**Regola di assunzione** = **Percentuale**). 

Una **matrice di utilizzo del range** è utile se vuoi ridurre il tempo necessario affinché i dipendenti raggiungano il punto intermedio del rispettivo range o aumentare il tempo necessario affinché i dipendenti raggiungano il punto di riferimento massimo nel range. Ad esempio, si desidera assegnare ai dipendenti che si trovano nella fascia del 25 percento di livello inferiore del rispettivo range il 110 percento del loro premio per raggiungimento obiettivi, ma si desidera assegnare ai dipendenti che si trovano nella fascia del 25 percento di livello superiore del rispettivo range solo l'80 percento del loro premio per raggiungimento obiettivi, in modo da impedire loro il raggiungimento del valore massimo altrettanto rapidamente. 

Dopo aver definito gli elementi di base del piano di retribuzione fissa, è possibile impostare la struttura retributiva per il piano. Fare clic su **Imposta retribuzione**. Viene visualizzato un dispositivo di scorrimento che offre tre opzioni:

-   **Crea una nuova matrice di retribuzione** selezionando un'impostazione di punti di riferimento e immettendo un nome per la griglia.
-   **Crea una nuova matrice di retribuzione** effettuando una copia di una griglia esistente che è possibile utilizzare come punto di partenza.
-   **Utilizza una matrice di retribuzione esistente** che è già stata definita. Tutti i piani di retribuzione che utilizzano la stessa griglia ricevono aggiornamenti se la griglia viene modificata.

Una volta selezionata un'opzione, verrà visualizzata la pagina **Struttura retributiva** e sarà possibile apportare modifiche alla griglia di retribuzione nuova o esistente.

## <a name="fixed-compensation-enrollment"></a>Iscrizione a un piano di retribuzione fissa
### <a name="determine-who-is-eligible-for-the-plan"></a>Stabilire chi è idoneo per il piano

Il primo passaggio per l'iscrizione dei dipendenti a un piano di retribuzione fissa consiste nello stabilire chi è idoneo per la retribuzione definita nel piano. Finché non si determina l'idoneità, non sarà possibile assegnare il piano ai dipendenti. Per impostare l'idoneità, aprire la finestra di dialogo **Regole di idoneità**. In questa finestra è possibile creare una nuova regola di idoneità per il piano di retribuzione e definire i criteri che il dipendente deve osservare per essere considerato idoneo a un piano. È possibile limitare l'idoneità in base al reparto, al sindacato, al paese di retribuzione (località), alla mansione, alla funzione lavorativa, al tipo di mansione o al livello retributivo. I dipendenti possono essere iscritti a un piano di retribuzione solo se soddisfano tutte le condizioni impostate nella regola di idoneità. 

**Nota:** le regole di idoneità vengono utilizzate per determinare l'idoneità per i piani di retribuzione fissa e variabile. 

La regola di idoneità considera il valore di campi specifici nei record **Mansione**, **Posizione**, e **Dipendente** per stabilire se un dipendente è idoneo per un piano di retribuzione.

-   Nella pagina **Mansione**, la regola di idoneità considera i seguenti campi:
    -   Il campo **Mansione**
    -   Nella scheda **Classificazione mansione**, i campi **Funzione** e **Tipo di mansione**
    -   Nella scheda **Retribuzione**, il campo **Livello**
-   Nella pagina **Posizioni**, la regola di idoneità considera i campi **Reparto** e **Paese di retribuzione**.

La regola di idoneità considera inoltre i sindacati associati al dipendente (nella pagina **Dipendenti**, nella scheda **Lavoratore**, fare clic su **Informazioni personali** &gt; **Sindacati**).

### <a name="define-fixed-compensation-actions"></a>Definire azioni relative alla retribuzione fissa

Le **Azioni retribuzione fissa** vengono utilizzate quando si impostano o si applicano modifiche alla retribuzione fissa di un dipendente. Le azioni retribuzione fissa consentono di immettere nomi descrittivi per i tipi di azioni che un responsabile retribuzione e benefit può eseguire. Tipi diversi di azioni dispongono di una logica speciale, in modo da poter essere utilizzati in situazioni specifiche. 

Ad esempio, se la retribuzione fissa viene impostata per un dipendente, è possibile utilizzare solo azioni con un tipo di **Assunzione/Riassunzione**. In questo caso, è consigliabile creare tre azioni diverse di tipo **Assunzione/Riassunzione** e nominarle **Assunzione**, **Riassunzione** e **Trasferimento**. Si dispone così di una spiegazione più descrittiva del motivo per cui la retribuzione fissa è stata assegnata a un dipendente o è stata modificata.

### <a name="enroll-the-employee"></a>Iscrivere il dipendente al piano

È ora possibile assegnare un piano di retribuzione fissa a un dipendente. Aprire la pagina **Dipendenti**, quindi selezionare il dipendente per iscriverlo al piano di retribuzione. Nel riquadro azioni fare clic su **Retribuzione** &gt; **Piano fisso**. È ora possibile creare una nuova azione di retribuzione fissa per tale dipendente. 

**Nota:** il campo del **piano di retribuzione** indica solo i piani per i quali un dipendente è idoneo in base alle regole di idoneità impostate per ciascun piano. Se non si specifica alcuna regola di idoneità per un piano, nessun dipendente sarà idoneo per tale piano. 

L'importo di retribuzione specificato per un piano di retribuzione del tipo di grado o fascia viene verificato in modo che rientri nei punti di riferimento minimo e massimo per il livello retributivo specificato sulla mansione del dipendente. Se l'importo di retribuzione non rientra nell'intervallo consentito, viene visualizzato un messaggio di errore o di avviso, a seconda del livello di tolleranza impostato nel piano di retribuzione fissa.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
