---
title: Convalidare le transazioni punto vendita per il calcolo dei rendiconti
description: In questo articolo vengono descritte le funzionalità per la convalida delle transazioni punto vendita in Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4be40189777a37495f185467050b61af47b684d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890515"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Convalidare le transazioni punto vendita per il calcolo dei rendiconti

[!include [banner](includes/banner.md)]

In questo articolo vengono descritte le funzionalità per la convalida delle transazioni punto vendita in Microsoft Dynamics 365 Commerce. Il processo di convalida identifica e contrassegna le transazioni che causeranno errori di registrazione, prima che vengano rilevate dal processo di registrazione rendiconti.

Quando si tenta di registrare un rendiconto, il processo di convalida può non riuscire a causa di dati incoerenti nelle tabelle di transazioni di commercio. Ecco alcuni esempi di fattori che possono causare queste incoerenze:

- Il totale delle transazioni nella tabella di intestazione non corrisponde al totale delle transazioni nelle righe.
- Il numero di articoli specificato nella tabella di intestazione non corrisponde al numero di articoli nella tabella delle transazioni.
- Le imposte nella tabella di intestazione non corrispondono all'importo delle imposte nelle righe. 

Se il processo di registrazione rendiconti preleva transazioni incoerenti, le fatture di vendita e i giornali di registrazione pagamenti creati possono causare problemi di registrazione del rendiconto. Il processo **Convalida transazioni punto vendita** evita che si verifichino tali problemi garantendo che solo le transazioni che superano le regole di convalida delle transazioni vengano passate al processo di calcolo dei rendiconti delle transazioni.

La figura seguente mostra i processi diurni ricorrenti per il caricamento delle transazioni, la convalida delle transazioni e il calcolo e la registrazione dei rendiconti delle transazioni e i processi di fine giornata per il calcolo e la registrazione dei rendiconti finanziari.

![Figura che mostra i processi diurni ricorrenti per il caricamento delle transazioni, la convalida delle transazioni e il calcolo e la registrazione dei rendiconti delle transazioni e i processi di fine giornata per il calcolo e la registrazione dei rendiconti finanziari](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Regole di convalida delle transazioni punto vendita

Il processo batch **Convalida transazioni punto vendita** controlla la coerenza delle tabelle di transazioni di commercio, in base alle regole di convalida seguenti.

> [!NOTE]
> Le regole di convalida continueranno a essere aggiunte nelle versioni successive.

### <a name="transaction-header-validation-rules"></a>Regole di convalida delle intestazioni delle transazioni

Nella tabella seguente sono elencate le regole di convalida delle intestazioni delle transazioni che vengono verificate a fronte dell'intestazione delle transazioni di vendita al dettaglio prima che tali transazioni vengano passate alla registrazione dei rendiconti.

| Regola | Descrizione |
|-------|-------------|
| Data attività | Questa regola verifica che la data attività della transazione sia associata a un periodo fiscale aperto in contabilità generale. |
| Arrotondamento valuta | Questa regola verifica che gli importi delle transazioni vengano arrotondati in base alla regola di arrotondamento valuta. |
| Conto cliente | Questa regola verifica che il cliente usato nella transazione sia presente nel database. |
| Importo sconto | Questa regola verifica che l'importo di sconto nell'intestazione equivalga alla somma degli importi di sconto presenti nelle righe. |
| Stato registrazione documento fiscale (Brasile) | Questa regola verifica che il documento fiscale possa essere registrato correttamente. |
| Importo lordo | Questa regola verifica che l'importo lordo nell'intestazione della transazione corrisponda all'importo netto, IVA inclusa, delle righe di transazione più spese. |
| Netto | Questa regola verifica che l'importo netto nell'intestazione della transazione corrisponda all'importo netto, IVA esclusa, delle righe di transazione più spese. |
| Netto + imposte | Questa regola verifica che l'importo lordo nell'intestazione della transazione corrisponda all'importo netto, IVA esclusa, delle righe di transazione più tutte le imposte e le spese. |
| Numero di articoli | Questa regola verifica che il numero di articoli specificato nell'intestazione della transazione corrisponda alla somma delle quantità nelle righe della transazione. |
| Importo del pagamento | Questa regola verifica che l'importo del pagamento nell'intestazione della transazione corrisponda alla somma di tutte le transazioni di pagamento. |
| Calcolo esenzione imposta | Questa regola verifica che la somma dell'importo calcolato e dell'importo esente da imposta delle righe addebiti corrisponda all'importo calcolato originale. |
| Prezzi IVA inclusa | Questa regola verifica che il flag **Prezzi comprensivi di IVA** sia coerente nell'intestazione della transazione e nelle transazioni fiscali. |
| Transazione non vuota | Questa regola verifica che la transazione contenga righe e che almeno una riga non sia vuota. |
| Insufficienza/Eccedenza pagamento | Questa regola verifica che la differenza tra l'importo lordo e l'importo del pagamento non superi la configurazione massima di insufficienza/eccedenza pagamento. |

### <a name="transaction-line-validation-rules"></a>Regole di convalida delle righe di transazione

Nella tabella seguente sono elencate le regole di convalida delle righe di transazione che vengono verificate a fronte delle transazioni di vendita al dettaglio prima che tali transazioni vengano passate alla registrazione dei rendiconti.

| Regola | Descrizione |
|-------|-------------|
| Codice a barre | Questa regola verifica che tutti i codici a barre degli articoli usati nelle righe di transazione siano presenti nel database. |
| Righe addebiti | Questa regola verifica che la somma dell'importo calcolato e dell'importo esente da imposta delle righe addebiti corrisponda all'importo calcolato originale. |
| Resi gift card | Questa regola verifica che non vi siano resi di gift card nella transazione. |
| Variante articolo | Questa regola verifica che tutti gli articoli e tutte le varianti in uso nelle righe di transazione siano presenti nel database. |
| Sconto riga | Questa regola verifica che l'importo di sconto riga equivalga alla somma delle transazioni di sconto. |
| Imposta riga | Questa regola verifica che l'importo di imposta riga equivalga alla somma delle transazioni fiscali. |
| Prezzo negativo | Questa regola verifica che non siano usati prezzi negativi nelle righe di transazione. |
| Numero di serie controllato | Questa regola verifica che il numero di serie sia presente nella riga di transazione per gli articoli controllati tramite numero di serie. |
| Dimensione numero di serie | Questa regola verifica che non venga indicato alcun numero di serie se la dimensione del numero di serie dell'articolo non è attiva. |
| Contraddizione segno | Questa regola verifica che il segno della quantità e il segno dell'importo netto corrispondano in tutte le righe di transazione. |
| Esente da IVA | Questa regola verifica che la somma del prezzo e dell'importo esente da imposta delle voci corrisponda al prezzo originale. |
| Assegnazione del gruppo di imposte | Questa regola verifica che la combinazione della fascia IVA e della fascia IVA articoli produce un'intersezione fiscale valida. |
| Conversioni unità di misura | Questa regola verifica che per l'unità di misura di tutte le righe sia disponibile una conversione valida nell'unità di misura di magazzino. |

## <a name="enable-the-store-transaction-validation-process"></a>Abilitare il processo di convalida delle transazioni punto vendita

Configurare il processo **Convalida transazioni punto vendita** per esecuzioni periodiche in Commerce Headquarters (**Retail e Commerce \> Retail e Commerce IT \> Registrazione POS**). Il processo batch è programmato in base alla gerarchia organizzativa del punto vendita. È consigliabile configurare questo processo batch in modo che venga eseguito alla stessa frequenza dei processi batch **Processo P** e **Calcolo rendiconti transazionali**.

## <a name="results-of-the-validation-process"></a>Risultati del processo di convalida

I risultati del processo batch **Convalida transazioni punto vendita** possono essere visualizzati su ogni transazione di punto vendita al dettaglio. Il campo **Stato di convalida** nel record di transazione è impostato su **Operazione completata**, **Errore** o **Nessuna**. Il campo **Ora ultima convalida** mostra la data dell'ultima esecuzione della convalida.

La tabella seguente descrive ogni stato di convalida.

| Stato convalida | Descrizione |
|-------------------|-------------|
| Operazione completata | Tutte le regole di convalida abilitate sono state superate. |
| Errore | Una regola di convalida abilitata ha individuato un errore. È possibile visualizzare maggiori dettagli dell'errore selezionando **Errori di convalida** nel riquadro Azioni. |
| Nessuna | Il tipo di transazione non richiede l'applicazione delle regole di convalida. |

![Pagina delle transazioni punto vendita che mostra il campo Stato di convalida e il pulsante Errori di convalida.](./media/valid-checker-validation-status-errors.png)

Solo le transazioni con stato di convalida **Operazione completata** verranno inserite nei rendiconti transazionali. Per visualizzare le transazioni con stato **Errore**, esaminare il riquadro **Errori di convalida cash-and-carry** nell'area di lavoro **Dati finanziari punto vendita**.

![Riquadri nell'area di lavoro Dati finanziari punto vendita.](./media/valid-checker-cash-carry-validation-failures.png)

Per altre informazioni su come correggere gli errori di convalida cash-and-carry, vedere [Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa](edit-cash-trans.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
