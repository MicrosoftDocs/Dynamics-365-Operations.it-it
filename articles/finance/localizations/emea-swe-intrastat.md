---
title: Intrastat svedese
description: Questo argomento contiene informazioni sulla creazione di report Intrastat in Svezia.
author: andosip
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 404fb8dff1519aefb2f4af25eb95dfa6fce75b7c
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417084"
---
# <a name="swedish-intrastat"></a>Intrastat svedese

[!include[banner](../includes/banner.md)]

La pagina **Intrastat** viene usata per generare e visualizzare le informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE). La dichiarazione Intrastat svedese contiene informazioni sul commercio di merci per il reporting.

I seguenti campi sono inclusi nella dichiarazione Intrastat svedese:

   - Codice ISO del paese partner
   - Codice transazione
   - Codice voce doganale
   - Unità supplementari
   - Peso
   - Importo fattura

## <a name="set-up-intrastat"></a>Impostare Intrastat

Importa l'ultima versione delle seguenti configurazioni per la creazione di report elettronici:

   - Modello Intrastat
   - Report Intrastat
   - Intrastat (SE)

Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. In Microsoft Dynamics 365 Finance, vai a **Imposta** > **Impostazione** > **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **Intrastat (SE)**.
3. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
4. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.
5. Nel campo **Codice transazione**, seleziona il codice transazione per i trasferimenti di proprietà. Utilizzi questo codice per le transazioni che producono trasferimenti effettivi o pianificati di proprietà dietro compensazione (finanziaria o di altro tipo). Lo usi anche per le correzioni. Le aziende in Svezia utilizzano codici di transazione a una cifra.
6. Nel campo **Nota di accredito**, seleziona il codice transazione per il reso della merce. Utilizzi questo codice per la restituzione della merce dopo che la transazione è stata registrata sotto il codice della transazione. Le aziende in Svezia utilizzano codici di transazione a una cifra.
7. Nella scheda **Proprietà paese/area geografica**, nel campo **Paese/area geografica**, elenca tutti i paesi o le aree geografiche con cui la tua società ha relazioni commerciali. Per ogni paese che fa parte della UE, nel campo **Tipo di paese/area geografica**, seleziona **UE**, in modo che il paese appaia nel report Intrastat.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Impostare i parametri di prodotto per la dichiarazione Intrastat

1. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
2. Seleziona un prodotto nella griglia.
3. Nella Scheda dettaglio **Commercio estero**, nella sezione **Intrastat**, nel campo **Voce doganale** seleziona il codice della voce doganale.
4. Nella Scheda dettaglio **Gestione articoli** nel campo **Peso netto** immetti il peso del prodotto in chilogrammi.
5. Seleziona **Imposta** > **Impostazioni** > **Commercio estero** > **Compressione di Intrastat** e seleziona i campi da confrontare quando vengono riepilogati i dati Intrastat. Per l'Intrastat svedese, seleziona i seguenti campi:

    - Voce doganale
    - Codice transazione
    - Direzione
    - Paese/area geografica
    - Correzione
    - Fattura

## <a name="intrastat-transfer"></a>Trasferimento Intrastat

Nella pagina **Intrastat**, nel riquadro azioni, puoi selezionare **Trasferisci** per trasferire automaticamente le informazioni sul commercio intracomunitario da ordini di vendita, fatture a testo libero, ordini di acquisto, fatture fornitore, ricevute di prodotti fornitore, fatture di progetto e ordini di trasferimento. Verranno trasferiti solo i documenti che hanno un paese dell'UE come paese o regione di destinazione (per le spedizioni) o consegna (per gli arrivi).

In alternativa, puoi inserire manualmente le transazioni selezionando **Nuovo** nel riquadro azioni.

### <a name="generate-an-intrastat-report"></a>Generare un report Intrastat

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni, seleziona **Output** > **Report**.
3. Nella finestra di dialogo **Report Intrastat**, imposta i seguenti campi.

    | Campo            | descrizione                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Data di inizio        | Seleziona la data di inizio per il report.                                                                                               |
    | Data di fine          | Seleziona la data di fine per il report.                                                                                                 |
    | Genera file    | Imposta questa opzione su **Sì** per generare un file .txt per il report Intrastat.                                                       |
    | Nome file        | Immetti il nome del file .txt.                                                                                                    |
    | Genera report  | Imposta questa opzione su **Sì** per generare un file .xlsx per il report Intrastat.                                                     |
    | Nome file report | Immetti il nome del file .xlsx.                                                                                                   |
    | Direzione        | Seleziona **Arrivi** per un report sugli arrivi intracomunitari. Seleziona **Spedizioni** per un report sulle spedizioni intracomunitarie. |

4. Seleziona **OK** ed esamina i report generati.

## <a name="example"></a>Esempio

Questo esempio mostra come registrare arrivi e spedizioni per Intrastat. Utilizza la persona giurdica **DEMF**.

### <a name="preliminary-setup"></a>Impostazioni preliminari

1. Vai a **Amministrazione organizzazione** > **Organizzazione** > **Persone giuridiche** e seleziona la persona giuridica **DEMF**.
2. Nella Scheda dettaglio **Indirizzi**, seleziona **Modifica**, quindi, nel campo **Paese/area geografica**, seleziona **SWE (Svezia)**.
3. Importa l'ultima versione delle seguenti configurazioni per la creazione di report elettronici:

    - Modello Intrastat
    - Report Intrastat
    - Intrastat (SE)

### <a name="create-transaction-codes"></a>Creare i codici transazione

1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Codici transazioni**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Codice** **transazione** immetti **1**.
4. Nel campo **Nome**, immetti **Transazioni normali**.
5. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella Scheda dettaglio **Generale** nel campo **Codice** **transazione** seleziona **1**.
3. Nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file** seleziona **Intrastat (SE)**.
4. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
5. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** assicurati che **Intrastat** sia selezionato.
6. Nella scheda **Proprietà paese/area geografica**, seleziona **Nuovo**.
7. Nel campo **Paese/Area geografica della parte** seleziona **SWE**.
8. Nel campo **Tipo di paese/area geografica** seleziona **Nazionale**.
9. Nel campo **Paese/area geografica della parte** seleziona **DEU**, quindi nel campo **Tipo di paese/area geografica** seleziona **UE**.

### <a name="set-up-product-information"></a>Impostare le informazioni prodotto

1. Vai a **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
2. Nella griglia seleziona **D0001**.
3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **100 200 30**.
4. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure** nel campo **Peso netto** immetti **5**.
5. Nel riquadro azioni selezionare **Salva**.

### <a name="change-the-site-address"></a>Modificare l'indirizzo del sito

1. Vai a **Gestione magazzino** > **Impostazione** > **Magazzino** > **Siti**.
2. Nella griglia seleziona **1**.
3. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
4. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **SWE**.
5. Selezionare **OK**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Creare un ordine cliente con un cliente UE

1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine cliente** nella Scheda dettaglio **Cliente**, nella sezione **Cliente**, nel campo **Conto cliente** seleziona **DE-015**.
4. Nella Scheda dettaglio **Generale**, nella sezione **Dimensioni di immagazzinamento**, nel campo **Sito**, seleziona **1**.
5. Nel campo **Magazzino** selezionare **11**.
6. Selezionare **OK**.
7. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine cliente**, nel campo **Codice articolo** seleziona **D0001**. Quindi, nel campo **Quantità** immetti **10**.
8. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Commercio estero**, assicurati che i campi **Codice transazione** e **Voce doganale** siano impostati automaticamente.
9. Nel riquadro azioni selezionare **Salva**.
10. Nel riquadro azioni, nella sezione **Genera** della scheda **Fattura**, seleziona **Fattura**.
11. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**.
12. Seleziona **OK** per registrare la fattura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Trasferire la transazione al giornale di registrazione Intrastat ed esaminare il risultato

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**.
4. Seleziona **Filtro**.
5. Nella finestra di dialogo **Filtro Intrastat**, nella scheda **Intervallo**, seleziona la prima riga e assicurati che il campo **Campo** sia impostato su **Data**.
6. Nel campo **Criteri** seleziona la data corrente.
7. Seleziona **OK** per chiudere la finestra di dialogo **Filtro Intrastat**.
8. Seleziona **OK** per chiudere la finestra di dialogo **Intrastat (trasferimento)** ed esamina il risultato. La riga rappresenta l'ordine cliente creato in precedenza.

    ![Righe del giornale di registrazione Intrastat per ordine cliente](media/swe_intrastat_journal_sales_order.png)

9. Seleziona la riga della transazione, quindi seleziona la scheda **Generale** per visualizzare maggiori dettagli.

    ![Dettagli delle righe del giornale di registrazione Intrastat per ordine cliente](media/swe_intrastat_journal_sales_order_line_details.png)

10. Nel riquadro azioni, seleziona **Output** > **Report**.
11. Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data** seleziona il mese dell'ordine cliente creato.
12. Nella sezione **Opzioni** **di esportazione** imposta l'opzione **Genera file** su **Sì**. Quindi, nel campo **Nome file** immetti il nome richiesto.
13. Imposta l'opzione **Genera report** su **Sì**. Quindi, nel campo **Nome file report** immetti il nome richiesto.
14. Nel campo **Direzione** seleziona **Spedizioni**.
15. Seleziona **OK** ed esamina il report in formato .txt che viene generato. Nella seguente tabella sono riportati i valori del report di esempio.

    | Codice ISO del paese partner | Codice transazione | Codice voce doganale | Unità supplementari | Peso | Importo fattura |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | TS                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Esamina il report in formato Excel che viene generato.

    ![Report Intrastat](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai a **Contabilità fornitori** > **Ordini fornitore** > **Tutti gli ordini fornitore**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine fornitore**, nel campo **Conto fornitore** seleziona **DE-001**.
4. Selezionare **OK**.
5. Nella scheda **Intestazione**, nella Scheda dettaglio **Commercio** **estero** verifica che il campo **Codice transazione** sia impostato su **1**.
6. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine fornitore**, nel campo **Codice articolo** seleziona **D0001**. Quindi, nel campo **Quantità** immetti **6**.
7. Nel riquadro Azioni, nella scheda **Acquisto**, nel gruppo **Azioni**, seleziona **Conferma**.
8. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
9. Nel riquadro Azioni seleziona **Predefinito da**. Nel campo **Quantità predefinita per le righe**, seleziona **Quantità ordinata**. Selezionare **OK**.
10. Nella Scheda dettaglio **Intestazione fattura fornitore**, nella sezione **Identificazione fattura**, nel campo **Numero** immetti **0001**.
11. Nel riquadro Azioni, seleziona **Registra** per registrare la fattura.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Creare una dichiarazione Intrastat per gli arrivi

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura fornitore** su **Sì**.
4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

    ![Giornale di registrazione Intrastat per ordine fornitore](media/swe_intrastat_journal_purchase_order.png)

5. Rivedi la scheda **Generale** per l'ordine fornitore.

    ![Dettagli delle righe del giornale di registrazione Intrastat per ordine fornitore](media/swe_intrastat_journal_purchase_order_line_details.png)

6. Nel riquadro azioni, seleziona **Output** > **Report**.
7. Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data** seleziona il mese dell'ordine cliente creato.
8. Nella sezione **Opzioni** **di esportazione** imposta l'opzione **Genera file** su **Sì**. Quindi, nel campo **Nome file** immetti il nome richiesto.
9. Imposta l'opzione **Genera report** su **Sì**. Quindi, nel campo **Nome file report** immetti il nome richiesto.
10. Nel campo **Direzione** seleziona **Arrivi**.
11. Seleziona **OK** ed esamina il report in formato .txt che viene generato. Nella seguente tabella sono riportati i valori del report di esempio.

    | Codice ISO del paese partner | Codice transazione | Codice voce doganale | Unità supplementari | Peso | Importo fattura |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | TS                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Esamina il report in formato Excel che viene generato.

    ![Report arrivi Intrastat](media/swe_intrastat_arrivals_report.png)
