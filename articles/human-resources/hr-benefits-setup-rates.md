---
title: Configurare i tassi
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a2626e9fc5f15bbdad0f6accf64bc4b211939ed0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009600"
---
# <a name="configure-rates"></a>Configurare i tassi

[!include [banner](includes/preview-feature.md)]

I tassi in Microsoft Dynamics 365 Human Resources definiscono la quantità di datori di lavoro e dipendenti che versano contributi per un benefit. Il valore può essere un importo o crediti flessibili, a seconda della configurazione.

Utilizzare i tassi per determinare la quantità di dipendenti e datori di lavoro che pagano per ogni benefit in base a diversi fattori. I tassi di copertura diventano effettivi a una determinata data, pertanto è quindi possibile conservare un record cronologico dei tassi. 

## <a name="set-up-rates"></a>Impostare i tassi

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tassi**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | Tasso | Il nome univoco che identifica il tasso di benefit. |
   | Descrizione | Una descrizione del tasso di benefit. |
   | Valido | La data in cui il tasso entra in vigore. Il valore predefinito è la data di sistema corrente. 
   | Scadenza | La data di fine del tasso. 31/12/2154 (che rappresenta mai) è il valore predefinito. |
   | Usa livelli | Il livello da utilizzare per il calcolo del tasso di benefit. Livello singolo per un tasso di benefit a un livello o Doppio livello per un tasso di benefit a due livelli. Un esempio di Doppio livello è un livello basato su sesso e età. |
   | Frequenza pagamenti | La frequenza di pagamento che determina ogni quanto tempo viene versato il tasso di premio benefit al fornitore del benefit. Ad esempio, se la frequenza di pagamento è mensile, il tasso di benefit rappresenta l'importo del pagamento mensile. |
   | Calcolo tasso di frequenza pagamenti | Il metodo per il calcolo del tasso di frequenza pagamenti: Standard o Annuale. |
   | Arrotondamento tasso di frequenza pagamenti | Il metodo per arrotondare il tasso: Standard o Troncato. |
   | Importo dipendente non fumatore | L'importo addebitato dal fornitore del benefit per un dipendente non fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo datore di lavoro non fumatore | L'importo addebitato dal fornitore del benefit per un dipendente non fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo dipendente fumatore | L'importo addebitato dal fornitore del benefit per un dipendente fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo datore di lavoro fumatore | L'importo addebitato dal fornitore del benefit per un dipendente fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo amministrativo | L'importo amministrativo addebitato da un amministratore di terze parti. È l'importo che il datore di lavoro paga all'amministratore di terze parti e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Tasso crediti flessibili | Il costo del benefit in numero di crediti flessibili. È applicabile solo ai tassi per piani di benefit associati a programmi di crediti flessibili. Se si utilizzano tassi a livelli, il tasso di credito flessibile è definito in Azioni> Tassi a livelli. |
   | Data di validità modifica | La data in cui la modifica al tasso di benefit diventa effettiva. Il sistema modificherà automaticamente il tasso di benefit e aggiornerà tutti i piani di benefit ad esso associati purché si esegua l'elaborazione dell'aggiornamento delle modifiche al tasso. Non è necessario impostare questa data a meno che si desideri che il sistema aggiorni automaticamente i piani di benefit per i dipendenti in base a questo tasso. Ciò è in genere riservato all'elaborazione automatica delle modifiche al tasso future. La data di entrata in vigore della modifica deve essere compresa tra la data di entrata in vigore e quella di scadenza del tasso di benefit. |
   | Modifica tasso completata | La casella di controllo Modifiche tasso completate verrà selezionata automaticamente una volta completate le modifiche al tasso di benefit mediante l'elaborazione dell'aggiornamento delle modifiche al tasso. |

4. Per tenere traccia e gestire le modifiche all'impostazione del tasso di benefit, selezionare **Azioni**, quindi selezionare **Gestisci versioni**.

5. Selezionare **Salva**. 

## <a name="set-up-tier-rates"></a>Impostare tassi a livelli

È possibile utilizzare tassi a livelli nell'impostazione del tasso se questo varia in base a vari fattori. Ad esempio, si potrebbero configurare tassi a livelli per indicare che se l'età è fino a 34,99 anni, l'importo per non fumatori è 2. Se l'età è fino a 39,99, l'importo per non fumatori è 3.

È anche possibile usare doppi livelli. Se si seleziona **Doppio livello** per il valore **Usa livelli** nel modulo **Impostazione tasso**, è possibile definire i tassi in base a due dimensioni. Ad esempio, si potrebbe configurare un sistema a doppio livello per indicare che per un maschio di età fino a 34,99 anni, l'importo per non fumatori è 2. Per un maschio di età fino a 39,99, l'importo per non fumatori è 3. Per una femmina di età fino a 34,99, l'importo per non fumatori è 1,8. Per una femmina di età fino a 39,99, l'importo per non fumatori è 2,8.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tassi**.

2. Selezionare uno o più tassi dall'elenco, selezionare **Azioni**, quindi selezionare **Tassi a livelli**.

3. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- | 
   | Descrizione | Il valore del campo Descrizione verrà applicato dalla descrizione nel record Impostazione tasso. Ciò consente di identificare a quale impostazione sono collegati i tassi a livello. |
   | Codice livello | Selezionare un codice di livello. I codici di livello sono definiti nel modulo Codici di livello. Il sistema visualizzerà automaticamente la descrizione del codice di livello nella griglia a sinistra. |
   | Tipo di livello | Specifica quale campo deve essere utilizzato come criterio di selezione per il processo di calcolo del tasso a livelli. Ad esempio:</br></br><ul><li>Se si utilizza Età, il sistema utilizzerà la data di nascita del dipendente nel processo di calcolo del tasso di benefit.</li><li>Se si utilizza Retribuzione, il sistema utilizzerà la retribuzione benefit del dipendente nel processo di calcolo del tasso di benefit.</li><li>Se si utilizza Tipo di mansione, il sistema utilizzerà il record della posizione attiva corrente del dipendente per determinare il tipo di mansione in base al record di mansione collegato alla posizione.</li></ul></br></br>I tipi di livelli sono Età, Retribuzione, Fisico, Sesso, Equivalente a tempo pieno, Tipo di mansione, Paese di retribuzione e Livello. | 
   | Livello | Il valore da utilizzare con il tipo di livello durante il processo di calcolo del tasso di benefit. Ad esempio:</br></br><ul><li>Se il tipo di livello è Età, sarebbe il valore dell'età.</li><li>Se il tipo di livello è Retribuzione, sarebbe l'importo della retribuzione.</li><li> Se il tipo di livello è Tipo di mansione, sarebbe il tipo di mansione.</li></ul></br></br>Con un tipo di livello Età o Retribuzione, il sistema utilizza un approccio crescente durante la selezione del tasso a livelli, il che significa che il valore nel campo Livello rappresenta il limite inferiore del livello. Con il tipo di livello Tipo di lavoro, il sistema utilizza un approccio di corrispondenza esatta durante la selezione del tasso a livelli. |
   | Tipo di calcolo | Specifica come utilizzare l'importo nel campo Importo di calcolo e quale calcolo matematico eseguire se necessario. Se il tipo di calcolo è un importo fisso, il sistema utilizza i campi Importo così come sono. Se il tipo di calcolo è per importo della retribuzione o della copertura in $, il sistema utilizza l'importo di calcolo e la direzione di calcolo nel calcolo matematico.</br></br>Se il tipo di calcolo è per importo della retribuzione in $, il sistema utilizzerà la seguente equazione matematica:</br></br>Retribuzione benefit annua divisa per l'importo di calcolo (arrotondato per eccesso o per difetto) moltiplicata per gli importi per fumatore o non fumatore per dipendente o datore di lavoro.</br></br>Se il tipo di calcolo è per importo della copertura in $, il sistema utilizzerà la seguente equazione matematica:</br></br>Importo della copertura diviso per l'importo di calcolo (arrotondato per eccesso o per difetto) moltiplicato per gli importi per fumatore o non fumatore per dipendente o datore di lavoro.</br></br>In entrambi i calcoli, la direzione di calcolo viene utilizzata per determinare se arrotondare per eccesso o per difetto la retribuzione benefit annua o l'importo della copertura diviso per l'importo di calcolo. |
   | Importo di calcolo | L'importo da utilizzare durante il processo di calcolo del tasso di benefit. Questo importo sarà il divisore durante il calcolo matematico del tasso a livelli. |
   | Direzione di calcolo | La direzione (Aumenta o Diminuisci) in base alla quale l'importo del risultato calcolato deve essere arrotondato. Il sistema supporta tre direzioni di calcolo: Vuoto (metodo esatto), Aumenta e Diminuisci.</br></br><ul><li>Se vuoto, il sistema utilizzerà il calcolo esatto dell'importo della retribuzione/copertura diviso per l'importo di calcolo. Se questo valore ha una frazione, il sistema lo utilizzerà nel calcolo.</li><li>Se la direzione è Aumenta, il sistema aumenterà il calcolo matematico dell'importo della retribuzione/copertura diviso per l'importo di calcolo all'intero successivo, il che significa che 12,25 aumenterà a 13.</li><li>Se la direzione è Diminuisci, il sistema diminuirà il calcolo matematico dell'importo della retribuzione/copertura diviso per l'importo di calcolo all'intero corrente, il che significa che 12,25 diminuirà a 12.</li></ul> |
   | Importo dipendente non fumatore | L'importo addebitato dal fornitore del benefit per un dipendente non fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo datore di lavoro non fumatore | L'importo addebitato dal fornitore del benefit per un dipendente non fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo dipendente fumatore | L'importo addebitato dal fornitore del benefit per un dipendente non fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo datore di lavoro fumatore | L'importo addebitato dal fornitore del benefit per un dipendente non fumatore. È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Importo amministrativo | L'importo amministrativo addebitato da un amministratore di terze parti. È l'importo che il datore di lavoro paga all'amministratore di terze parti e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso. |
   | Tasso non fumatore crediti flessibili | Il costo del benefit in crediti flessibili, basato sul calcolo definito per il livello per non fumatori. Ad esempio, se il tipo di calcolo è "Per importo della copertura in $", l'importo di calcolo è 10.000 e il tasso non fumatore in crediti flessibili è 6; ciò significa che se un dipendente non fumatore sceglie una copertura di $10.000, questa costerà 6 crediti flessibili. Se sceglie una copertura di $20.000, costerà 12 crediti flessibili e così via. |
   | Tasso fumatore crediti flessibili | Il costo del benefit in crediti flessibili, basato sul calcolo definito per il livello per fumatori. |

5. Selezionare **Salva**. 
