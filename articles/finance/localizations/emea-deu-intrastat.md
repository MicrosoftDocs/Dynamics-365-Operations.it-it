---
title: Intrastat tedesca
description: Questo argomento contiene informazioni sulla dichiarazione Intrastat in Germania.
author: anasyash
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 50c412fdfd7118843d285cbb70e8e44847c9d4a5
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7487927"
---
# <a name="german-intrastat"></a>Intrastat tedesca

[!include [banner](../includes/banner.md)]

La pagina **Intrastat** viene usata per generare e visualizzare le informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE). La dichiarazione Intrastat tedesca contiene informazioni sul commercio di merci per il reporting. Il report è formattato secondo le linee guida delle autorità tedesche che sono presentate alla pagina [6.2 Dichiarazioni file in formato INSTAT/XML](https://www-idev.destatis.de/idev/doc/intra_en/hilfe6_2.html).

La tabella seguente mostra i campi inclusi nella dichiarazione Intrastat tedesca.

| Campi | Spedizioni | Arrivi |
|-------------------------|-------------------------|-------------------------|
| Periodo di riferimento | X | X |
| Codice direzione | X | X |
| Valuta della dichiarazione Intrastat</br>**Nota**: questa valuta è la <em>valuta di contabilità</em>. | X | X |
| Codice voce doganale | X | X |
| Nome voce doganale | X | X |
| Codice unità supplementare | X | X |
| Stato membro di spedizione/destinazione | X | X |
| Massa netta | X | X |
| Quantità in unità supplementari | X | X |
| Paese di origine |  | X |
| Importo fattura | X |  |
| Valore statistico | X | X |
| Natura delle transazioni | X | X |
| Modalità di trasporto | X | X |
| Codice area</br>**Nota:**</br><ul></br><li>Se il paese o la regione di origine è la Germania e la fattura riguarda le spedizioni, viene visualizzato un codice Intrastat per lo stato di origine.</li></br><li>Se il paese o la regione di origine non è la Germania e la fattura è per le spedizioni, viene visualizzato il codice **99**.</li></br><li>Se la fattura riguarda gli arrivi, viene visualizzato un codice Intrastat per lo stato.</li></br></ul> | X | X |
| Codice porto/aeroporto/porto interno | X | X |
| Termini di consegna | X | X |


## <a name="set-up-intrastat"></a>Impostare Intrastat

1. Imposta i codici della società.

    1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
    2. Nella Scheda dettaglio **Commercio estero e logistica**, nella sezione **Identificazione**, nel campo **DVR**, immetti l'ID contratto di interscambio. Questo ID verrà incluso nel report.
    3. Nel campo **Partita IVA esportazione**, immetti il numero di partita IVA della società per l'esportazione.
    4. Nel campo **Partita IVA importazione**, immetti il numero di partita IVA della società per l'importazione.
    5. Nel campo **Codice Intrastat**, immetti il codice Intrastat assegnato alla persona giuridica.
    6. Nella Scheda dettaglio **Registrazione fiscale**, nel campo **Partita IVA**, immetti la partita IVA della società.

    > [!NOTE]
    > Se si genera un report Intrastat per le consociate, nel campo **Partita IVA**, inserisci la partita IVA della società consolidata.

2. In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), nella raccolta di risorse condivise scarica l'ultima versione delle seguenti configurazioni per la creazione di report elettronici per la dichiarazione Intrastat.

    - Modello Intrastat
    - Report Intrastat
    - INSTAT XML
    - INSTAT XML (DE)

3. Imposta i parametri per il commercio estero:

    1. In Dynamics 365 Finance, vai a **Imposta** > **Impostazioni** > **Parametri per il commercio estero**.
    2. Nella scheda **Intrastat** nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **XLM Intrastat (DE)**.
    3. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
    4. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.
    5. Nel campo **Codice transazione**, seleziona il codice transazione per i trasferimenti di proprietà. Utilizzi questo codice per le transazioni che producono trasferimenti effettivi o pianificati di proprietà dietro compensazione (finanziaria o altro). Lo usi anche per le correzioni.
    6. Nel campo **Nota di accredito**, seleziona il codice transazione per il reso della merce.
    7. Nel campo **Lavoratore** seleziona la persona di contatto per il report Intrastat. In alternativa, nella scheda **Contatto** immetti o seleziona i valori per i campi **Nome**, **Telefono**, **Fax**, **E-mail**, e **Indirizzo Internet**. Questi campi sono inclusi nel report.
    8. Nel campo **Ufficio**, seleziona l'ufficio Intrastat.
    9. Vai a **Imposta** > **Imposte indirette** > **IVA** > **Uffici IVA** e inserisci le seguenti informazioni per l'ufficio Intrastat selezionato nel passaggio precedente:

       - Identificazione ufficio
       - Indirizzo
       - Informazioni contatto

    10. Nella scheda **Proprietà paese/area geografica**, nel campo **Paese/area geografica**, elenca tutti i paesi o le aree geografiche con cui la tua società ha relazioni commerciali. Per ogni paese o area geografica, nel campo **Tipo di paese/area geografica**, seleziona **UE**, in modo che il paese o l'area geografica appaia nel report Intrastat.

4. Imposta i codici area geografica.

    1. Scegli **Amministrazione organizzazione** > **Rubrica globale** > **Indirizzi** > **Impostazione indirizzo**.
    2. Nella scheda **Stato/regione o provincia**, nel campo **Paese/area geografica**, seleziona **DEU**, quindi seleziona **Applica filtro**.
    3. Nella griglia seleziona lo stato. Quindi nel campo **Codice Intrastat** immetti il codice Intrasta univoco.

5. Imposta l'indirizzo di origine per un prodotto.

    1. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
    2. Seleziona il prodotto nella griglia.
    3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Paese di origine** seleziona **DEU**.

6. Seleziona **Imposta** > **Impostazioni** > **Commercio estero** > **Compressione di Intrastat** e seleziona i campi da confrontare quando vengono riepilogati i dati Intrastat. Per l'Intrastat tedesca, seleziona i seguenti campi:

    - Voce doganale
    - Paese/area geografica
    - Correzione
    - Direzione
    - Termini di consegna
    - Fattura
    - Paese di origine
    - Porto
    - Paese del mittente
    - Stato del mittente
    - Procedura statistica
    - Codice transazione
    - Trasporto
    - Numero esenzione fiscale

### <a name="intrastat-transfer"></a>Trasferimento Intrastat

Nella pagina **Intrastat**, nel riquadro azioni, seleziona **Trasferisci** per trasferire automaticamente le informazioni sul commercio intracomunitario da ordini di vendita, fatture a testo libero, ordini di acquisto, fatture fornitore, ricevute di prodotti fornitore **,** fatture di progetto e ordini di trasferimento. Verranno trasferiti solo i documenti che hanno un paese dell'UE come paese o regione di destinazione (per le spedizioni) o consegna (per gli arrivi).

In alternativa, puoi inserire manualmente le transazioni selezionando **Nuovo** nel riquadro azioni.

### <a name="generate-an-intrastat-report"></a>Generare un report Intrastat

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni, seleziona **Output** > **Report**.
3. Nella finestra di dialogo **Report Intrastat**, imposta i seguenti campi.

    | Campo | descrizione |
    |-------------------------|-------------------------|
    | Data di inizio | Seleziona la data di inizio per il report. |
    | Data di fine | Seleziona la data di fine per il report. |
    | Genera file | Imposta questa opzione su **Sì** per generare un file .xml. |
    | Nome file | Lascia vuoto il campo. Il nome di file viene generato automaticamente e consiste del valore del tag XML **&lt;envelopeId&gt;** più l'estensione del nome di file **.xml**.</br>Il valore **&lt;envelopeId&gt;** è una concatenazione dei seguenti elementi, in quest'ordine:</br><ol type="1"></br><li>Il valore del tag **&lt;interchangeAgreementId&gt;**</li></br><li>Un trattino (-)</li></br><li>Il valore del tag **&lt;referencePeriod in YYYYMM&gt;**</li></br><li>Un trattino (-)</li></br><li>Il valore del tag **&lt;Envelope/DateTime/date in YYYYMMDD&gt;**</li></br><li>Un trattino (-)</li></br><li>Il valore del tag **&lt;Envelope/DateTime/time in hhmm&gt;**</li></br></ol> |
    | Direzione | <ul></br><li>Seleziona **Arrivi** per generare un report sugli arrivi intracomunitari.</li></br><li>Seleziona **Spedizioni** per generare un report sulle spedizioni intracomunitarie.</li></br><li>Seleziona **Entrambi** per generare un report su arrivi e spedizioni.</li></br></ul> |
    | Numero di registrazione fiscale | Inserire il numero di registrazione da utilizzare per generare il codice identificativo del mittente, se il numero è diverso dalla partita IVA della persona giuridica. |


## <a name="example"></a>Esempio

Questo esempio mostra come registrare arrivi e spedizioni per Intrastat. Utilizza la persona giurdica **DEMF**.

1. In [LCS](https://lcs.dynamics.com/Logon/Index), nella raccolta di risorse condivise, scarica l'ultima versione delle seguenti configurazioni per la creazione di report elettronici per il formato della dichiarazione Intrastat:

    - Modello Intrastat
    - Report Intrastat
    - XML Intrastat
    - XML Intrastat (DE)

2. Crea codici transazione.

    1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Codici transazioni**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nel campo **Codice** **transazione** immetti **21**.
    4. Nel campo **Nome**, immetti **Reso merci**.
    5. Nel riquadro azioni selezionare **Salva**.

3. Imposta il numero di identificazione dell'ufficio.

    1. Seleziona **Imposte** > **Imposte indirette** > **IVA** > **Uffici IVA**.
    2. Nell'elenco, seleziona **Ufficio tributario**.
    3. Nel campo **Identificazione ufficio**, immetti **123**.

4. Imposta i codici area geografica.

    1. Scegli **Amministrazione organizzazione** > **Rubrica globale** > **Indirizzi** > **Impostazione indirizzo**.
    2. Nella scheda **Stato/regione o provincia**, nel campo **Paese/area geografica**, seleziona **DEU**, quindi seleziona **Applica filtro**.
    3. Nella griglia seleziona **BE**, quindi nel campo **Codice Intrastat**, immetti **11**.
    4. Nel riquadro azioni selezionare **Salva**.

5. Imposta i parametri per il commercio estero.

    1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
    2. Nella scheda **Intrastat** nella Scheda dettaglio **Generale** nel campo **Codice** **transazione** seleziona **11**.
    3. Nel campo **Nota di accredito**, seleziona **21**.
    4. Nel campo **Ufficio** seleziona **Ufficio tributario**.
    5. Nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **XML INSTAT (DE)**.
    6. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
    7. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** assicurati che **Intrastat** sia selezionato.
    8. Nella scheda **Proprietà paese/area geografica**, seleziona **Nuovo**.
    9. Nel campo **Paese/Area geografica della parte** seleziona **FRA**.
    10. Nel campo **Tipo di paese** selezionare **UE**.

6. Assegna un codice voce doganale a un prodotto e imposta l'origine del prodotto. I campi **Codice voce doganale**, **Paese/Area geografica di origine** e **Stato di origine** verranno quindi automaticamente impostati sugli ordini cliente e sugli ordini fornitore quando selezioni il prodotto.

    1. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
    2. Nella griglia seleziona **D0001**.
    3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **920 20 34**.
    4. Nella sezione **Origine**, nel campo **Paese/Area geografica**, seleziona **DEU**.
    5. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure** nel campo **Peso netto** immetti **12**.
    6. Nel riquadro azioni selezionare **Salva**.

7. Assegna il trasporto a una modalità di consegna. Il codice di trasporto verrà quindi impostato automaticamente negli ordini quando si seleziona la modalità di consegna.

    1. Seleziona **Approvvigionamento** > **Impostazione** > **Distribuzione** > **Modalità di consegna**.
    2. Nell'elenco seleziona **10**.
    3. Nella Scheda dettaglio **Commercio estero** nel campo **Trasporto**, seleziona **01**.

8. Crea un ordine cliente con un cliente UE.

    1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nella finestra di dialogo **Crea ordine cliente** nella Scheda dettaglio **Cliente**, nella sezione **Cliente**, nel campo **Conto cliente** seleziona **DE-012**.
    4. Nella Scheda dettaglio **Generale**, nella sezione **Dimensioni di immagazzinamento**, nel campo **Sito**, seleziona **1**.
    5. Nel campo **Magazzino** selezionare **11**.
    6. Selezionare **OK**.
    7. Nella scheda **Intestazione** nella Scheda dettaglio **Commercio estero** nel campo **Porto** seleziona **53**.
    8. Nel campo **Procedura statistica**, seleziona **31710**.
    9.  Nella scheda **Riche**, nella Scheda dettaglio **Righe ordine** **cliente** nel campo **Codice articolo** seleziona **D0001**. Quindi, nel campo **Quantità** immetti **10**.
    10. Nella Scheda dettagli **Dettagli riga**, nella scheda **Commercio estero**, assicurati che i campi **Codice transazione**, **Trasporto**, **Voce doganale** e **Paese/Area geografica di origine** siano impostati automaticamente.
    11. Nel riquadro azioni selezionare **Salva**.
    12. Nel riquadro azioni, nella sezione **Genera** della scheda **Fattura**, seleziona **Fattura**.
    13. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**.
    14. Seleziona **OK** per registrare la fattura.

9.  Trasferisci la transazione al giornale di registrazione Intrastat ed esamina il risultato.

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**.
    4. Seleziona **Filtro**.
    5. Nella finestra di dialogo **Filtro Intrastat**, nella scheda **Intervallo**, seleziona la prima riga e assicurati che il campo **Campo** sia impostato su **Data**.
    6. Nel campo **Criteri** seleziona la data corrente.
    7. Seleziona **OK** per chiudere la finestra di dialogo **Filtro Intrastat**.
    8. Seleziona **OK** per chiudere la finestra di dialogo **Intrastat (trasferimento)** ed esamina il risultato. La riga rappresenta l'ordine cliente creato in precedenza.

        ![La riga rappresenta l'ordine cliente nella pagina Intrastat](media/intrastat_deu_1.png)

10. Seleziona la riga della transazione, quindi seleziona la scheda **Generale** per visualizzare maggiori dettagli.

    ![Dettagli dell'ordine cliente nella scheda Generale della pagina Intrastat](media/intrastat_deu_2.png)

11. Crea una nota di accredito utilizzando un ordine cliente.

    1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nella finestra di dialogo **Crea ordine cliente** nella Scheda dettaglio **Cliente**, nella sezione **Cliente**, nel campo **Conto cliente** seleziona **DE-012**.
    4. Nella Scheda dettaglio **Generale**, nella sezione **Dimensioni di immagazzinamento**, nel campo **Sito**, seleziona **1**.
    5. Nel campo **Magazzino** selezionare **11**.
    6. Nella scheda **Intestazione** nella Scheda dettaglio **Commercio estero** nel campo **Porto** seleziona **53**.
    7. Nel campo **Procedura statistica**, seleziona **31710**.
    8. Nella scheda **Riche**, nella Scheda dettaglio **Righe ordine** **cliente** nel campo **Codice articolo** seleziona **D0001**. Quindi, nel campo **Quantità** immetti **-2**.
    9. Nella Scheda dettagli **Dettagli riga** nella scheda **Commercio estero** nel campo **Codice transazione** seleziona **21**.
    10. Assicurati che i campi **Trasporto**, **Voce doganale** e **Paese/Area geografica di origine** siano impostati automaticamente.
    11. Nel riquadro azioni selezionare **Salva**.
    12. Nel riquadro azioni, nella sezione **Genera** della scheda **Fattura**, seleziona **Fattura**.
    13. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**.
    14. Seleziona **OK** per registrare la fattura.

12. Trasferisci la transazione al giornale di registrazione Intrastat ed esamina il risultato.

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**.
    4. Seleziona **OK** per chiudere la finestra di dialogo **Intrastat (trasferimento)** ed esamina il risultato. È stata aggiunta una nuova riga dove il campo **Direzione** è impostato su **Arrivi**.            
        Questa riga rappresenta il reso fisico della merce.

        ![Riga per il reso fisico della merce nella pagina Intrastat](media/intrastat_deu_3.png)

13. Seleziona la riga della transazione, quindi seleziona la scheda **Generale** per visualizzare maggiori dettagli.

    ![Dettagli del reso fisico della merce nella scheda Generale della pagina Intrastat](media/intrastat_deu_4.png)

14. Crea una correzione utilizzando un ordine cliente:

    1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nella finestra di dialogo **Crea ordine cliente** nella Scheda dettaglio **Cliente**, nella sezione **Cliente**, nel campo **Conto cliente** seleziona **DE-012**.
    4. Nella Scheda dettaglio **Generale**, nella sezione **Dimensioni di immagazzinamento**, nel campo **Sito**, seleziona **1**.
    5. Nel campo **Magazzino** selezionare **11**.
    6. Nella scheda **Intestazione** nella Scheda dettaglio **Commercio estero** nel campo **Porto** seleziona **53**.
    7. Nel campo **Procedura statistica**, seleziona **31710**.
    8. Nella scheda **Riche**, nella Scheda dettaglio **Righe ordine** **cliente** nel campo **Codice articolo** seleziona **D0001**. Quindi, nel campo **Quantità** immetti **-3**.
    9. Nella Scheda dettagli **Dettagli riga** nella scheda **Commercio estero** nel campo **Codice transazione** seleziona **11**.
    10. Assicurati che i campi **Trasporto**, **Voce doganale** e **Paese/Area geografica di origine** siano impostati automaticamente.
    11. Nel riquadro azioni selezionare **Salva**.
    12. Assicurati che il campo **Codice transazione** sia impostato su 11.
    13. Nel riquadro azioni, nella sezione **Genera** della scheda **Fattura**, seleziona **Fattura**.
    14. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**.
    15. Seleziona **OK** per registrare la fattura.

15. Trasferisci la transazione al giornale di registrazione Intrastat ed esamina il risultato:

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**.
    4. Seleziona **OK** per chiudere la finestra di dialogo **Intrastat (trasferimento)** ed esamina il risultato. È stata aggiunta una nuova riga in cui appare un segno di spunta nella colonna **Correzione**.

        ![Riga per la correzione nella pagina Intrastat](media/intrastat_deu_5.png)

16. Seleziona la riga della transazione, quindi seleziona la scheda **Generale** per visualizzare maggiori dettagli.

    ![Dettagli della correzione nella scheda Generale della pagina Intrastat](media/intrastat_deu_6.png)

17. Nel riquadro azioni, seleziona **Output** > **Report**.
18. Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data** seleziona il mese dell'ordine cliente creato.
19. Nella sezione **Opzioni** **di esportazione** imposta l'opzione **Genera file** su **Sì**.
20. Nel campo **Nome file** immetti il nome richiesto.
21. Seleziona **OK** ed esamina il report che viene generato. Nella seguente tabella sono riportati i valori del report di esempio.

    | **Nome**                  | **Fattura di vendita**  |   **Correzione**   | **Nota di accredito** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | D                  | A                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Speaker            | Speaker            | Speaker         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

