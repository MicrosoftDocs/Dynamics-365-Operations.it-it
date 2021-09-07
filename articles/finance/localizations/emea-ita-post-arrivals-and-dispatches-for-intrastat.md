---
title: Registrare arrivi e spedizioni per Intrastat
description: Questo argomento fornisce un esempio che mostra come registrare arrivi e spedizioni per Intrastat.
author: andosip
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: f7bd1811fd0e580a6b6655244c689268915d320e
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414789"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Registrare arrivi e spedizioni per Intrastat

[!include [banner](../includes/banner.md)]

Questo argomento fornisce un esempio che mostra come registrare arrivi e spedizioni per Intrastat. L'esempio usa la persona giuridica **ITCO**.

## <a name="setup"></a>Attrezzaggio

1. Importa l'ultima versione delle seguenti configurazioni per la creazione di report elettronici:

    - Modello Intrastat
    - Report Intrastat
    - Intrastat (IT)

    Ulteriori dettagli in [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

2. In Microsoft Dynamics 365 Finance, definisci le seguenti sequenze numeriche come continue: **Gene\_397**, **Acco\_16403**, **Gene\_407**, and **PUR\_EU**.

    1. Vai a **Amministrazione organizzazione** > **Sequenze numeriche** > **Sequenze numeriche**.
    2. Nella griglia, seleziona uno dei codici di sequenza numerica.
    3. Nel riquadro azioni, seleziona **Modifica**.
    4. Nella sezione Scheda dettaglio **Generale**, nella sezione **Impostazione**, imposta l'opzione **Continua** su **Sì**.
    5. Nel riquadro azioni selezionare **Salva**.

3. Imposta un indirizzo di magazzino.

    1. Vai a **Gestione magazzino** &gt; **Impostazioni** &gt; **Magazzino** &gt; **Magazzini**.
    2. Nell'elenco, seleziona il magazzino **11**.
    3. Nella Scheda dettaglio **Indirizzo** seleziona **Aggiungi**.
    4. Nella finestra di dialogo **Nuovo** **indirizzo**, nel campo **Nome** **o** **descrizione**, immetti **Principale**.
    5. Nel campo **Paese/area geografica** seleziona **ITA (Italia)**.
    6. Nel campo **Città** seleziona **Aprilia**.
    7. Selezionare **OK**.

4. Imposta i codici transazioni.

    1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Codici transazioni**.
    2. Seleziona **Nuovo** e imposta un codice transazione per i trasferimenti di proprietà.

        - Nel campo **Codice transazione** immetti **1**.
        - Nel campo **Nome** immetti **Trasferimento di proprietà**.

    3. Seleziona **Nuovo** e imposta un codice transazione per i resi.

        - Nel campo **Codice** **transazione** immetti **2**.
        - Nel campo **Nome**, immetti **Reso merci**.

5.  Imposta i parametri per il commercio estero.

    1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
    2. Nella scheda **Intrastat** nella Scheda dettaglio **Generale** nel campo **Codice** **transazione** seleziona **1**.
    3. Nel campo **Nota di accredito**, seleziona **2**.
    4. Nel campo **Periodo di dichiarazione vendite** seleziona **Mese**.
    5. Nel campo **Periodo di dichiarazione acquisti** seleziona **Mese**.
    6. Nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file** seleziona **Intrastat (IT)**.
    7. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
    8. Nella Scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.
    9. Nella Scheda dettaglio **Valore statistico** imposta l'opzione **Stampa ed esporta dati statistici** su **Sì**.
    10. Nella scheda **Proprietà paese/area geografica**, verifica che esistano le seguenti righe.

        | **Parte/paese/area geografica** | **Codice Intrastat** | **Valuta** | **Tipo di paese/area geografica** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | TS                 | EUR          | Nazionale                |
        | SMR                      | SM                 | EUR          | Nazionale speciale        |

    11. Nella barra degli strumenti seleziona **Nuovo** per creare la seguente riga.

        | **Parte/paese/area geografica** | **Codice Intrastat** | **Valuta** | **Tipo di paese/area geografica** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | DKK          | UE                      |

6. Imposta i numeri esenzione fiscale.

    1. Vai a **Imposta** > **Impostazione** > **IVA** > **Numeri esenzione fiscale**.
    2. Nel riquadro Azioni seleziona **Nuovo** per creare le seguenti righe.

        | **Paese** | **Numero esenzione fiscale** | **Ragione sociale** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | FORNITORE UE        |
        | DNK                | DK0987654321          | Report elettronici cliente      |

7. Imposta l'indirizzo del fornitore.

    1. Andare a **Contabilità fornitori** &gt; **Fornitori** &gt; **Tutti i fornitori**.
    2. Nella griglia, seleziona **Fornitore UE**.
    3. Nella Scheda dettaglio **Indirizzi** seleziona **Aggiungi**.
    4. Nella finestra di dialogo **Nuovo indirizzo**, nel campo **Nome o descrizione**, immetti **Germania**.
    5. Nel campo **Paese/Area geografica** seleziona **DEU**.
    6. Seleziona **OK** per creare il nuovo indirizzo.
    7. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **IVA**, nel campo **Numero esenzione fiscale** seleziona **Tutto**, quindi seleziona **DE1234567890**.
    8. Nel riquadro azioni selezionare **Salva**.

8. Imposta gli indirizzi del cliente.

    1. Vai a **Contabilità clienti** > **Clienti** > **Tutti i clienti**.
    2. Nella griglia seleziona **ITCO-000001**.
    3. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
    4. Nella finestra di dialogo **Nuovo indirizzo**, nel campo **Nome o descrizione**, immetti **San Marino**.
    5. Nel campo **Paese/Area geografica** seleziona **SMR**.
    6. Seleziona **OK** per creare il nuovo indirizzo.
    7. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **Fattura**, nel campo **Conto fatture**, seleziona **ITCO-000001**.
    8. Nel campo **Gruppo di sequenze numeriche** seleziona **IT\_VENDOM**.
    9. Nel riquadro azioni selezionare **Salva** e chiudere la pagina.
    10. Nella pagina **Tutti i clienti**, nella griglia seleziona **ITCO-000002**.
    11. Nella Scheda dettaglio **Indirizzi** seleziona **Aggiungi**.
    12. Nella finestra di dialogo **Nuovo indirizzo**, nel campo **Nome o descrizione**, immetti **Danimarca**.
    13. Nel campo **Paese/Area geografica** seleziona **DNK**.
    14. Seleziona **OK** per creare il nuovo indirizzo.
    15. Nella Scheda dettaglio **Dati demografici vendite**, nel campo **Valuta** seleziona **DKK**.
    16. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **IVA**, nel campo **Fascia IVA** seleziona **IT\_PUREU**.
    17. Nel campo **Numero esenzione fiscale**, seleziona **Tutto**, quindi seleziona **DK0987654321**.
    18. Nel riquadro azioni selezionare **Salva**.

9. Imposta la gerarchia di categorie.

    1. Vai a **Gestione informazioni sul prodotto** > **Impostazioni** > **Categorie e attributi** > **Gerarchie di categorie**.
    2. Nella griglia seleziona **Intrastat**.
    3. Nel riquadro azioni seleziona **Nuovo nodo di categoria**.
    4. Nel campo **Nome** immetti **Servizio**.
    5. Nel campo **Codice** immetti **123456**.
    6. Nel riquadro azioni selezionare **Salva**.

10. Impostare i prodotti.

    1. Vai a **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
    2. Nella griglia seleziona **ITEM**.
    3. Nella Scheda dettaglio **Acquisto**, nella sezione **Amministrazione**, nel campo **Fornitore** seleziona **ITCO-000001**.
    4. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **\[100 200 30\] Speaker**.
    5. Nella sezione **Origine**, nel campo **Paese/Area geografica**, seleziona **DEU**.
    6. Nel campo **Stato/provincia** seleziona **BE**.
    7. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure nette** nel campo **Peso netto** immetti **5**.
    8. Nel riquadro azioni selezionare **Salva**.
    9. Nella pagina **Prodotti rilasciati**, nella griglia seleziona **Articolo di servizio**.
    10. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **\[123456\] Servizio**.
    11. Nel riquadro azioni selezionare **Salva**.

11. Imposta i metodi di trasporto.

    1. Vai a **Imposta** > **Impostazione** > **Commercio estero** > **Metodo di trasporto**.
    2. Nel riquadro Azioni seleziona **Nuovo** per creare i seguenti metodi di trasporto.

        | **Trasporto** | **Descrizione** |
        |---------------|-----------------|
        | 1             | Strada            |
        | 2             | Via aerea             |

12. Imposta una modalità di consegna.

    1. Seleziona **Approvvigionamento** > **Impostazione** > **Distribuzione** > **Modalità di consegna**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nel campo **Modalità di consegna** immetti **1**.
    4. Nel campo **Descrizione** immetti **Camion**.
    5. Nella Scheda dettaglio **Commercio estero** nel campo **Trasporto**, seleziona **1 Strada**.
    6. Nel riquadro azioni selezionare **Salva**.

13. Imposta i termini di consegna.

    1. Vai a **Contabilità fornitori** > **Impostazioni** > **Termini di consegna**.
    2. Nell'elenco seleziona **CFR**.
    3. Nella Scheda dettaglio **Generale**, nel campo **Codice Intrastat** immetti **1**.

## <a name="post-arrivals-for-intrastat"></a>Registrare arrivi per Intrastat

### <a name="purchase-goods-by-using-a-purchase-order"></a>Acquistare merci utilizzando un ordine fornitore

Questa parte dell'esempio mostra come utilizzare un ordine fornitore per acquistare merci (articoli) dai paesi dell'Unione Europea (UE).

1. Vai a **Contabilità fornitori** > **Ordini fornitore** > **Tutti gli ordini fornitore**.
2.  Nel Riquadro azioni selezionare **Nuovo**.
3.  Nella finestra di dialogo **Crea ordine fornitore**, nel campo **Conto fornitore** seleziona **Fornitore UE**.
4.  Nella Scheda dettaglio **Amministrazione**, nel campo **Lingua** seleziona **it**.
5.  Selezionare **OK**.
6.  Nella visualizzazione **Intestazione**, nella Scheda dettaglio **Commercio** **estero** verifica che il campo **Codice transazione** sia impostato su **1**.
7.  Verifica che il campo **Provincia di origine/destinazione** sia impostato su **RM**.
8.  Nella Scheda dettaglio **Consegna**, nella sezione **Consegna**, nel campo **Modalità di consegna** seleziona **1**.
9.  Nel campo **Termini di consegna**, seleziona **CFR**.
10. Nella visualizzazione **Righe**, nella Scheda dettaglio **Righe ordine fornitore** nel campo **Codice articolo** seleziona **Articolo**.
11. Nel campo **Sito** selezionare **1**.
12. Nel campo **Magazzino** selezionare **11**.
13. Nel campo **Quantità** immettere **10**
14. Nel campo **Prezzo unitario** immettere **100**.
15. Nella scheda **Impostazione**, nella sezione **IVA**, nel campo **Fascia IVA articoli** seleziona **22%UE**.
16. Nel riquadro Azioni, nella scheda **Acquisto**, nel gruppo **Azioni**, seleziona **Conferma**.
17. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
18. Nel riquadro Azioni seleziona **Predefinito da**.
19. Nel campo **Quantità predefinita per le righe**, seleziona **Quantità ordinata**, quindi seleziona **OK**.
20. Nella Scheda dettaglio **Intestazione fattura fornitore**, nella sezione **Identificazione fattura**, nel campo **Numero** immetti **0001**.
21. Nella sezione **Date fatture**, nel campo **Data fattura** seleziona **9/7/2021**.
22. Nel riquadro Azioni, seleziona **Registra** per registrare la fattura.

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Acquistare servizi utilizzando una fattura fornitore

Questa parte dell'esempio mostra come utilizzare una fattura fornitore per acquistare servizi dai paesi della UE.

1. Vai a **Contabilità fornitori** > **Fatture** > **Giornale di registrazione fatture**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Nome** seleziona **VEND\_EUINV**.
4. Nel riquadro azioni seleziona **Righe**.
5. Nel campo **Data** immetti **9/7/2021**.
6. Nel campo **Tipo di conto** seleziona **Fornitore**.
7. Nel campo **Conto** seleziona **Fornitore UE**.
8. Nel campo **Data fattura** seleziona **9/7/2021**.
9. Nel campo **Fattura** immetti **ITA-0004**.
10. Nel campo **Credito** immetti **120000**.
11. Nel campo **Tipo di** **conto di contropartita** seleziona **Contabilità generale**.
12. Nel campo **Conto di contropartita** seleziona **110130**.
13. Nel campo **Fascia IVA** seleziona **IT\_PUREU**.
14. Nel campo **Fascia IVA articoli**, seleziona **22%UE**.
15. Nella scheda **Commercio estero**, segui questi passaggi:

    1. Nel campo **Codice transazione** seleziona **1**.
    2. Nel campo **Trasporto** seleziona **2 Aria**.
    3. Nel campo **Voce doganale** seleziona **\[123456\] Servizio**.
    4. Nel campo **Paese/Area geografica** seleziona **ITA**.
    5. Nel campo **Stato/provincia** seleziona **LAZ**.
    6. Nel campo **Provincia di origine/destinazione** seleziona **LT**.


16. Nel riquadro Azioni selezionare **Registra**.
17. Crea una dichiarazione Intrastat per gli arrivi.

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura fornitore** su **Sì**.
    4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

   ![Pagina del giornale di registrazione Intrastat, scheda Panoramica.](media/ita_intrastat_journal_vendor_invoice.png)

18. Rivedi la scheda **Generale** per l'ordine fornitore.

    ![Dettagli delle righe del giornale di registrazione Intrastat per ordine fornitore](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Rivedi la scheda **Generale** per la fattura fornitore.

    ![Dettagli delle righe del giornale di registrazione Intrastat per fattura fornitore](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Genera i dati del report Intrastat per gli arrivi.

    1. Nel riquadro azioni, seleziona **Output** > **Report**.
    2. Nella finestra di dialogo **Report Intrastat**, nella sezione **Data**, nel campo **Dal** seleziona **1/7/2021**.
    3. Nel campo **Al** seleziona **31/7/2021**.
    4. Nella sezione **Opzioni di esportazione** imposta le opzioni **Genera file** e **Genera report** su **Sì**.
    5. Nel campo **Nome file** immetti **File arrivi**.
    6. Nel campo **Nome file report** immetti **Report arrivi**.
    7. Nel campo **Direzione** seleziona **Arrivi**.
    8. Nel campo **Numero di riferimento** immetti **123456**.
    9. Seleziona **OK** per generare il report Intrastat e il file Intrastat ed esaminali.

    Nella figura seguente viene illustrato un esempio di un report Intrastat.

    ![Report arrivi Intrastat.](media/ita_intrastat_arrivals_report.png)

    Nella figura seguente viene illustrato un esempio di un file Intrastat.

    ![File arrivi Intrastat.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Registrare spedizioni per Intrastat

### <a name="sell-goods-by-using-a-sales-order"></a>Vendere merci utilizzando un ordine cliente

Questa parte dell'esempio mostra come utilizzare un ordine cliente per vendere merci (articoli) ai paesi dell'Unione Europea (UE).

1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona **ITCO-000002**.
4. Selezionare **OK**.
5. Nella visualizzazione **Intestazione**, nella Scheda dettaglio **Consegna**, nella sezione **Info consegna varie**, nel campo **Modalità di consegna** seleziona **1 Camion**.
6. Nel campo **Termini di consegna**, seleziona **CFR**.
7. Nella visualizzazione **Righe**, nella Scheda dettaglio **Righe ordine cliente** nel campo **Codice articolo** seleziona **ARTICOLO**.
8. Nel campo **Quantità** immettere **50**
9. Nel campo **Sito** selezionare **1**.
10. Nel campo **Magazzino** selezionare **11**.
11. Nel campo **Prezzo unitario** immettere **250**.
12. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Impostazione**, nella sezione **IVA**, nel campo **Fascia IVA articoli** seleziona **22%UE**.
13. Nel riquadro azioni selezionare **Salva**.
14. Nella scheda **Fattura** del riquadro Azioni, nel gruppo **Genera**, seleziona **Fattura** per creare la fattura per l'ordine.
15. Nella finestra di dialogo **Registrazione fattura**, nella Scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**.
16. Nella Scheda dettaglio **Impostazione**, nel campo **Data** **fattura**, seleziona **9/7/2021**.
17. Selezionare **OK**.
18. Rivedi le righe del giornale di registrazione Intrastat.

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura cliente** su **Sì**.
    4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat. La transazione della nota di accredito è contrassegnata come correzione e presenta un importo della fattura negativo.

        ![Pagina del giornale di registrazione Intrastat](media/ita_intrastat_journal_sales_order.png)

        ![Dettagli delle righe del giornale di registrazione Intrastat per ordine cliente](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Restituire merci utilizzando una nota di accredito

Questa parte dell'esempio mostra come utilizzare una nota di accredito per restituire merci (articoli) dai paesi dell'Unione Europea (UE).

1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona **ITCO-000002**.
4. Selezionare **OK**.
5. Nella visualizzazione **Intestazione**, nella Scheda dettaglio **Consegna**, nella sezione **Info consegna varie**, nel campo **Modalità di consegna** seleziona **1 Camion**.
6. Nel campo **Termini di consegna**, seleziona **CFR**.
7. Nella Scheda dettaglio **Commercio estero** nel campo **Codice transazione**, seleziona **2**.
8. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine cliente**, nel campo **Codice articolo** seleziona **ARTICOLO**.
9. Nel campo **Quantità** immetti **-10**.
10. Nel campo **Sito** selezionare **1**.
11. Nel campo **Magazzino** selezionare **11**.
12. Nel campo **Prezzo unitario** immettere **250**.
13. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Impostazione**, nella sezione **IVA**, nel campo **Fascia IVA articoli** seleziona **22%UE**.
14. Nella sezione **Ordine di reso**, nel campo **ID lotto resi**, seleziona il lotto che hai creato in precedenza.
15. Nel riquadro azioni selezionare **Salva**.
16. Nella scheda **Fattura** del riquadro Azioni, nel gruppo **Genera**, seleziona **Fattura** per creare la fattura per l'ordine.
17. Nella Scheda dettaglio **Parametri**, nella sezione **Parametro**, nel campo **Quantità** seleziona **Tutto**.
18. Nella finestra di dialogo **Registrazione fattura**, nella Scheda dettaglio **Impostazione**, nel campo **Data** **fattura**, seleziona **9/7/2021**.
19. Seleziona **OK** per registrare la fattura.
20. Rivedi le righe del giornale di registrazione Intrastat.

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura cliente** su **Sì**.
    4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat. La transazione della nota di accredito è contrassegnata come correzione e presenta un importo della fattura negativo.

    ![Nota di accredito del giornale di registrazione Intrastat](media/ita_intrastat_journal_credit_note.png)

    ![Dettagli delle righe del giornale di registrazione Intrastat per nota di accredito](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Vendere merci a San Marino utilizzando un ordine cliente

Questa parte dell'esempio mostra come utilizzare un ordine cliente per acquistare merci (articoli) a San Marino.

1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine cliente**, nel campo **Conto cliente**, seleziona **ITCO-000001**.
4. Selezionare **OK**.
5. Nella visualizzazione **Intestazione**, nella Scheda dettaglio **Consegna**, nella sezione **Info consegna varie**, nel campo **Modalità di consegna** seleziona **1**.
6. Nel campo **Termini di consegna**, seleziona **CFR**.
7. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine cliente**, nel campo **Codice articolo** seleziona **ARTICOLO**.
8. Nel campo **Quantità** immettere **30**
9. Nel campo **Sito** selezionare **1**.
10. Nel campo **Magazzino** selezionare **11**.
11. Nel campo **Prezzo unitario** immettere **200**.
12. Nel riquadro azioni selezionare **Salva**.
13. Nella scheda **Fattura** del riquadro Azioni, nel gruppo **Genera**, seleziona **Fattura** per creare la fattura per l'ordine.
14. Nella Scheda dettaglio **Parametri**, nella sezione **Parametro**, nel campo **Quantità** seleziona **Tutto**.
15. Nella finestra di dialogo **Registrazione fattura**, nella Scheda dettaglio **Impostazione**, nel campo **Data** **fattura**, seleziona **9/7/2021**.
16. Seleziona **OK** per registrare la fattura.
17. Rivedi le righe del giornale di registrazione Intrastat.

    1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
    2. Nel riquadro azioni seleziona **Trasferisci**.
    3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura cliente** su **Sì**.
    4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

   ![Giornale di registrazione Intrastat per San Marino](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Dettagli delle righe del giornale di registrazione Intrastat per San Marino](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Crea una dichiarazione Intrastat per le spedizioni.

    1. Vai a **Imposta** &gt; **Dichiarazioni** &gt; **Commercio estero** &gt; **Intrastat**.
    2. Nel riquadro azioni, seleziona **Output** &gt; **Report**.
    3. Nella finestra di dialogo **Report Intrastat**, nella sezione **Data**, nel campo **Dal** seleziona **1/7/2021**.
    4. Nel campo **Al** seleziona **31/7/2021**.
    5. Nella sezione **Opzioni di esportazione** imposta le opzioni **Genera file** e **Genera report** su **Sì**.
    6. Nel campo **Nome file** immetti **File spedizioni**.
    7. Nel campo **Nome file report** immetti **Report spedizioni**.
    8. Nel campo **Direzione** seleziona **Spedizioni**.
    9. Nel campo **Numero di riferimento** immetti **98754**.
    10. Seleziona **OK** per generare il report Intrastat e il file Intrastat.

        Nella figura seguente viene illustrato un esempio di un report Intrastat stampato.

        ![Report Intrastat](media/ita_intrastat_report_for_dispatches.png)

        Nella figura seguente viene illustrato un esempio di un file Intrastat stampato.

        ![File Intrastat per spedizioni](media/ita_intrastat_file_for_dispatches.png)
