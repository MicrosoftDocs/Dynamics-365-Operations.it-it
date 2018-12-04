---
title: Immettere i saldi iniziali delle retribuzioni
description: Nell'argomento vengono descritti i passaggi necessari per immettere i saldi iniziali per codici reddito, detrazioni, benefit e imposte. Queste informazioni sono utili ai partner per migrare o trasferire dati per una nuova implementazione di retribuzione da un altro sistema.
author: kherr75
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 93333757995c874c2cf03514acff28a54ae7f787
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="enter-payroll-beginning-balances"></a>Immettere i saldi iniziali delle retribuzioni

[!include [banner](../../includes/banner.md)]

Nell'argomento vengono descritti i passaggi necessari per immettere i saldi iniziali per codici reddito, detrazioni, benefit e imposte. Queste informazioni sono utili ai partner che trasferiscono dati per una nuova implementazione di retribuzione da un altro sistema. Per prepararsi a immettere i saldi iniziali delle retribuzioni, vengono controllate le seguenti informazioni:

> * I record dipendente vengono immessi e sono disponibili nel sistema
> * I seguenti dati vengono impostati e assegnati ai dipendenti:
> 
> > * Cicli e periodi retributivi
> > * Codici di reddito
> > * Imposte
> > * Benefit e detrazioni
> 
> * La società dovrebbe aver selezionato la data in cui i saldi iniziali delle retribuzioni possono essere impostati.
> 
> * Sono state raccolte informazioni su tutti i ricavi, benefit/detrazioni, Contributi per benefit, imposte del dipendente e imposte del datore di lavoro e i relativi importi da inizio anno dal sistema legacy.

Dal momento che si prevede di immettere i saldi iniziali, valutare il livello di dettaglio dei dati. La maggior parte delle aziende immette un singolo importo consolidato da inizio anno. Tuttavia, se sono necessarie informazioni più dettagliate, i saldi possono essere immessi in incrementi trimestrali. La definizione del livello di dettaglio necessario determina il numero dei rendiconti finanziari di retribuzione da creare per ciascun lavoratore. Per un singolo importo da inizio anno, è necessario un solo rendiconto manuale per ciascun dipendente. Per fare ciò, utilizzare gli importi da inizio anno a partire dal rendiconto di pagamento finale del sistema precedente come importo immesso nel nuovo sistema di gestione delle retribuzioni.

Nel seguente esempio viene illustrato come è possibile immettere i saldi iniziali delle retribuzioni dei dipendenti, inclusi codici reddito, benefit/detrazioni e imposte. In un esempio pratico, ci sarebbe una voce per ogni codice reddito, benefit/detrazione, contributo di benefit, imposta dipendente e imposta datore di lavoro e l'importo immesso è l'importo da inizio anno. Utilizzo tale elenco di codici e importi, effettuare le seguenti operazioni per creare un rendiconto di pagamento e una busta paga manuali la contabilità disattivata per portare i saldi iniziali per scopo di retribuzione.  La contabilità viene disattivata in quanto è preferibile non registrare questo saldo di pagamento iniziale nella contabilità generale. Questo è stato effettuato nel sistema legacy e verrà riportato nel nuovo sistema quando si registrano i saldi iniziali nella contabilità generale.

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Istruzioni per impostare i codici i ricavi da utilizzare nei saldi iniziali delle retribuzioni
Quando si immettono i saldi iniziali delle retribuzioni, verificare che i codici reddito che verranno utilizzati siano configurati con l'opzione "Consenti modifica dei coefficienti buste paga" abilitata. In questo modo sarà possibile digitare manualmente l'importo dal sistema legacy. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Creare il rendiconto dei ricavi per fare in modo che dipendente abbia un saldo iniziale
Questa procedura consente di creare manualmente un rendiconto dei ricavi per ciascun lavoratore per l'ultimo periodo retributivo del sistema legacy, che genera le righe del rendiconto dei ricavi nel nuovo sistema di gestione delle retribuzioni. Immettere una riga per codice reddito e importo e ore da inizio anno. Di seguito sono riportati i passaggi di esempio:

1. Aprire la pagina **Tutte le buste paga** e fare clic su **Nuovo**.  

Immettere quanto riportato di seguito. 

| Campo      | Valore                 |
|------------|-----------------------|
| Lavoro     | Michael Redmond       |
| Ciclo retributivo  | sm                    |
| Periodo retributivo | 16/6/2017 - 30/6/2017 |

2. Nella scheda **Riga busta paga**, immettere i seguenti dati:

Riga 1: scheda **Riga buste paga**

| Campo            | Valore       |
|------------------|-------------|
| Codice reddito    | Retribuzione regolare |
| Quantità         | 1,00        |
| Intervallo             | 30.000      |
| Scheda Dettagli riga |             |
| Manuale           | (contrassegnato)    |

Riga 2: scheda **Riga buste paga**

| Campo            | Valore    |
|------------------|----------|
| Codice reddito    | Premio    |
| Quantità         | 1.0000   |
| Tasso             | 4250.00  |
| Scheda Dettagli riga |          |
| Manuale           | (contrassegnato) |

Riga 3: scheda **Riga buste paga**

| Campo           | Valore      |
|-----------------|------------|
| Codice reddito   | Provvigione |
| Quantità        | 1.0000     |
| Tasso            | !,299,00   |
| Tasso            | 1,299.00   |
| Scheda Dettagli riga |            |
| Manuale          | (contrassegnato)   |

> [!NOTE]
> L'impostazione del dispositivo di scorrimento **Manuale** su **Sì** nella scheda **Dettagli riga** per ogni riga della busta paga è fondamentale per avere l'immissione dei saldi iniziali delle retribuzioni per ogni lavoratore.

3. Nel riquadro **Azione**, fare clic su **Rilascia busta paga** USA-FED-ER-FICA.

4. Nel riquadro **Azione** fare clic su **Rendiconto di pagamento** per aprire la pagina **Genera rendiconti di pagamento** e per impostare quanto segue:

| Campo              | Valore     |
|--------------------|-----------|
| Data pagamento       | 6/30/2017 |
| Tipo di ciclo di pagamenti   | Manuale    |
| Disabilita contabilità |   Sì     |

> [!NOTE] 
> Questa opzione è disponibile solo quando il tipo di esecuzione di pagamento è manuale e se l'utente desidera disattivare la contabilità sull'esecuzione di retribuzione.

Fare clic su **OK** e chiudere il **Registro informazioni**.

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a>Perché il dispositivo di scorrimento Disabilita contabilità deve essere impostato su Sì quando si generano i rendiconti di pagamento?
Quando si imposta il dispositivo di scorrimento su **Sì**, le righe del rendiconto di pagamento non vengono distribuite alla contabilità generale. Nelle versioni precedenti gli importi di contabilità generale vengono aggiornati quando vengono immessi i saldi dei conti dal sistema legacy. L'immissione dei saldi iniziali per le retribuzioni consente di generare report contenenti informazioni di anni precedenti, nonché di identificare i limiti ai fini fiscali e dei benefit.   

### <a name="c-create-pay-statements-for-employees"></a>C. Creare rendiconti di pagamento per i dipendenti
Dopo aver generato i rendiconti di pagamento con saldi iniziali, è necessario verificare che i rendiconti di pagamento riflettano con precisione i dati relativi alle retribuzioni. È inoltre necessario aggiornare manualmente le informazioni su benefit e imposte in modo che corrispondano ai valori nel sistema precedente di gestione delle retribuzioni. Dopo aver verificato che gli importi dal sistema precedente delle retribuzioni corrispondano agli importi nei rendiconti correnti retributivo, completare i rendiconti di retribuzione.

1. Aprire la pagina **Tutti i rendiconti di pagamento**.

2. Evidenziare l'ultimo rendiconto di pagamento generato per Michael Redmond

3. Fare clic su **Modifica** per aprire la pagina **Rendiconto di pagamento**.

4. Aprire la scheda **Detrazioni per benefit** e immettere i seguenti dati:

|       Campo       |      Valore       |
|-------------------|------------------|
|      Benefit      | Importo detrazione |
|       401.000        |   Partecipazione    |
|      Rischi professionali       |      Sottospecie       |
| Spese di discreazione di reparto |   Partecipazione    |
|      Visione       |      Sottospecie       |

5. Nella scheda **Contributi per benefit** immettere i seguenti dati:

|  Campo  |        Valore        |
|---------|---------------------|
| Benefit | Importo di contribuzione |
|  401.000   |     Partecipazione     |
| Rischi professionali  |        Sottospecie        |
| Visione  |        Sottospecie        |

6. Nella scheda **Detrazioni imposta**, immettere i seguenti dati:

| Campo           | Valore            |
|-----------------|------------------|
| Codice imposta        | Importo detrazione |
| USA-FED-ER-FICA | 1600.00          |
| USA-FED-ER-MEDI | 825.75           |

7. Nella scheda **Contribuzioni imponibili**, immettere i seguenti dati:

8. Fare clic su **Calcola**.
   > [!IMPORTANT] 
   > Convalidare i totali del rendiconto di pagamento che corrispondono all'importo da inizio anno del sistema legacy per il lavoratore. Può essere necessario attendere a finalizzare il passaggio successivo per eseguire una convalida globale di tutti i rendiconti di pagamento aggregati. Una volta convalidati, finalizzare tutti i rendiconti di pagamento.

Lo stesso processo può essere eseguito negli incrementi trimestrali se necessario per tutti i trimestri precedenti in ogni anno. Questa operazione è necessaria solo se il cliente deve visualizzare i dati per trimestre senza tornare al sistema legacy.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>Se si commettere un errore nell'immissione dei saldi iniziali per un dipendente
È possibile stornare e immettere di nuovo le transazioni. Per stornare la transazione, è sufficiente completare i passaggi seguenti sulla **Tutti i rendiconti di pagamento**.

1. Fare clic su **Storna**.

2. Fare clic su **Sì** quando il messaggio "Quando si storna il rendiconto di pagamento, viene creato un rendiconto di pagamento di storno per compensare il rendiconto di pagamento. Il rendiconto di pagamento non può inoltre essere modificato. Stornare il rendiconto di pagamento?" viene visualizzato. 

Dopo aver stornato il rendiconto di pagamento, è possibile generarne uno nuovo per il lavoratore dalla busta paga creata in precedenza. Assicurarsi di correggere tutte le righe errate nella busta paga prima di generare il nuovo rendiconto di pagamento, quindi generare nuovi i rendiconti di pagamento con gli importi corretti. 

