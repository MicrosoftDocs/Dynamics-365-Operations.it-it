---
title: Comunicazione annuale imposte
description: Questo argomento fornisce informazioni sul report di comunicazione annuale delle imposte in Italia.
author: anasyash
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 264294
ms.search.region: Italy
ms.author: anasyash
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 1e1920ecc01d3057d6a5c22c7dd239a59254b546
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826481"
---
# <a name="yearly-tax-communication"></a>Comunicazione annuale imposte

[!include [banner](../includes/banner.md)]

Il report **Comunicazione annuale imposte** contiene le informazioni della dichiarazione annuale delle imposte per l'Italia da inviare all'ufficio tributario.

## <a name="prerequisites"></a>Prerequisiti

Configurare i libri IVA italiani seguendo le istruzioni in [Libri IVA italiani](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-ita-fiscal-books.md#set-up-sales-tax-books).

## <a name="set-up-the-yearly-tax-communication-report"></a>Configurare il report di comunicazione annuale delle imposte

1. In Microsoft Dynamics 365 Finance, andare a **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**.
2. Nella Scheda dettaglio **Numeri di registrazione**, nel campo **Partita IVA** immetter la partita IVA della propria società.
3. Nella Scheda dettaglio **Registrazione fiscale**, nel campo **Codice fiscale** immettere il codice fiscale della propria società.
4. In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), nella raccolta di risorse condivise scaricare le ultime versioni delle configurazioni per la creazione di report elettronici per i seguenti formati della dichiarazione IVA:

    - **Modello dei report fiscali italiani**
    - **Comunicazione annuale imposte (IT)**
    - **Mapping dei modelli di comunicazione annuale IVA**

Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

5. In Finance andare a **Imposte \> Impostazione \> Parametri \> Parametri di Contabilità generale**.
6. Nella scheda **Sequenze numeriche** selezionare una sequenza numerica per il riferimento **ID comunicazione imposte**.
7. Nella scheda **IVA**, nel campo **Mapping formato** della Scheda dettaglio **Comunicazione annuale imposte** selezionare il formato **Comunicazione annuale imposte (IT)** scaricato in precedenza.
8. Andare a **Imposta \> Impostazione \> IVA \> Impostazioni comunicazione annuale imposte**.

![Pagina Impostazioni comunicazione annuale imposte](media/1_Yearly_tax_communication_setup.png)

> [!NOTE]
> Per visualizzare il modulo "Comunicazione annuale IVA" per l'anno 2020 e le relative istruzioni, vedere [Modello e istruzioni - IVA 2020](https://www.agenziaentrate.gov.it/portale/web/guest/iva-2020/modello-e-istruzioni-imprese).

9. Nella scheda **Impostazione campi** creare righe e impostare i seguenti campi su di esse.

<table>
<tbody>
<tr>
<td>
<p><strong>Campo</strong></p>
</td>
<td>
<p><strong>Descrizione</strong></p>
</td>
</tr>
<tr>
<td>
<p>ID campo</p>
</td>
<td>
<p>Immettere il numero di identificazione del campo.</p>
</td>
</tr>
<tr>
<td>
<p>Descrizione</p>
</td>
<td>
<p>Immettere una descrizione del campo.</p>
</td>
</tr>
<tr>
<td>
<p>Formattazione</p>
</td>
<td>
<p>Selezionare il formato richiesto del campo. Per ulteriori informazioni sui formati disponibili, vedere la sezione <a href="https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/IT_Yearly_tax_communication/articles/finance/localizations/emea-ita-yearly-tax-communication.md#formats-of-the-fields">Formati dei campi</a> più avanti in questo argomento.</p>
</td>
</tr>
<tr>
<td>
<p>Calcolo</p>
</td>
<td>
<p>Selezionare un metodo di calcolo:</p>
<ul>
<li><strong>Manuale</strong> &ndash; Il valore viene immesso manualmente.</li>
<li><strong>Transazione fiscale</strong> &ndash; Il valore viene raccolto dalle transazioni fiscali.</li>
<li><strong>Totale</strong> &ndash; Il valore viene calcolato utilizzando una formula composta dai valori di altri campi (solo i campi per i quali il valore del campo <strong>Calcolo</strong> non è selezionato).</li>
</ul>
</td>
</tr>
<tr>
<td>
<p>Valore</p>
</td>
<td>
<p>Immettere un valore per il campo. È possibile modificare questo valore solo quando il campo <strong>Calcolo</strong> è impostato su <strong>Manuale</strong>.</p>
</td>
</tr>
<tr>
<td>
<p>Imposta sul reddito</p>
</td>
<td>
<p>Selezionare uno dei seguenti valori:</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Imponibile</strong> &ndash; Il campo dovrebbe rappresentare un imponibile.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Importo imposta </strong>&ndash; Il campo dovrebbe rappresentare un importo dell'imposta.</p>
<p>È possibile modificare questo valore solo quando il campo <strong>Calcolo</strong> è impostato su <strong>Transazioni fiscali</strong>.</p>
</td>
</tr>
<tr>
<td>
<p>Segno</p>
</td>
<td>
<p>Immettere <strong>1</strong> se il valore deve essere rappresentato così com'è. Immettere <strong>-1</strong> se i valori devono essere invertiti.</p>
<p>È possibile modificare questo valore solo quando il campo <strong>Calcolo</strong> è impostato su <strong>Transazioni fiscali o Totale</strong>.</p>
</td>
</tr>
<tr>
<td>
<p>IVA non deducibile</p>
</td>
<td>
<p>Se il <strong>campo Calcolo è impostato su Transazione fiscale </strong>e il <strong>campo Imposta è impostato su Importo imposta, selezionare questa casella di controllo</strong> per ridurre l'importo dell'imposta calcolato in base all'importo dell'imposta non detraibile.</p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>

> [!NOTE]
> Se vengono apportate modifiche nella dichiarazione, è necessario modificare le impostazioni del campo.

10. Per i campi in cui il campo **Calcolo** è impostato su **Transazioni fiscali** nella scheda **Codici imposta selezionati**, selezionare **Nuovo** per aggiungere una riga per ogni codice IVA che deve essere reso disponibile come valore di campo.

    ![Pagina Impostazioni comunicazione annuale imposte, scheda Codici imposta selezionati](media/2_Yearly_tax_communication_setup.png)

11. Selezionare **Eccezioni** per configurare i conti principali che dovrebbero essere esclusi dalla query.

    Creare un numero sufficiente di codici IVA univoci in modo che ciascuno sia collegato a un singolo campo nella dichiarazione annuale. Questo approccio consente di semplificare la configurazione della dichiarazione annuale.

    Se lo stesso codice IVA può essere collegato a più campi, è tuttavia necessario configurare filtri aggiuntivi per la transazione fiscale.

12. Selezionare **Query** e specificare regole di filtro aggiuntive per l'IVA registrata. È ad esempio possibile specificare filtri aggiuntivi per la sezione relativa a direzione IVA o libro IVA.

È possibile effettuare la seguente configurazione aggiuntiva per i campi in cui il campo **Calcolo** è impostato su **Totale**. Il sistema può quindi calcolare automaticamente i valori per i tag che dovrebbero rappresentare un risultato calcolato utilizzando una formula composta dai valori di altri campi (solo i campi in cui il campo **Calcolo** non è impostato su **Totale**).

13. Seleziona la riga in cui il campo **Calcolo** è impostato su **Totale**.
14. Nella scheda **Importo totale** selezionare **Nuovo** per aggiungere righe per tutti i campi da sommare.

    ![Pagina Impostazioni comunicazione annuale imposte, scheda Importo totale](media/3_Yearly_tax_communication_setup.png)

15. Impostare i seguenti campi.

    | Nome campo | Descrizione                                                                                                                 |
    |------------|-----------------------------------------------------------------------------------------------------------------------------|
    | Segno       | Immettere **1** se il valore del campo deve essere accettato così com'è. Immettere **-1** se il valore del campo deve essere invertito. |
    | ID campo   | Selezionare il campo da sommare. I campi in cui il campo **Calcolo** è impostato su **Totale** non possono essere selezionato qui. |

### <a name="formats-of-the-fields"></a>Formati dei campi

I valori dei campi possono in genere essere numerici (formato **NU**) o alfanumerici (formato **UN**).

- **Numerico (NU)** - Questi valori sono importi. Sono allineati a destra e hanno una lunghezza fissa di 16 caratteri. I caratteri di spazio vengono utilizzati come riempimento,
- **Alfanumerico (AN)** - Questi valori sono stringhe. Sono allineati a sinistra e hanno una lunghezza fissa di 16 caratteri. I caratteri di spazio vengono utilizzati come riempimento.

Nella colonna **Formato** è possibile specificare un formato di campo. Oltre a **NU** e **AN**, sono disponibili per la selezione anche i seguenti formati.

| Formattazione | Descrizione                                                                                                                                               | Carattere di spaziatura interna | Esempio                                    |
|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|--------------------------------------------|
| CF     | Codice fiscale (16 caratteri)                                                                                                                               | BARRA SPAZIATRICE             | "XXXXXX11X11X111X"                         |
| PI     | Partita IVA (11 caratteri)                                                                                                                         | BARRA SPAZIATRICE             | "11111111111"                              |
| CN     | Codice fiscale numerico (11 caratteri)                                                                                                                       | BARRA SPAZIATRICE             | "11111111111"                              |
| PN     | Abbreviazione automobilistica per la provincia italiana (ad esempio, la provincia di nascita), un simbolo di spazio e il valore "EE" per paesi o regioni estere | BARRA SPAZIATRICE             | "BO   "                                    |
| Nx     | Come **NU**, ma rappresenta formati come **N1**, **N2** e **N3** nelle linee guida ufficiali                                                             | BARRA SPAZIATRICE             | "            1234"                         |
| CB     | Casella di controllo, dove i valori sono **1** per uno stato selezionato e **0** per uno stato cancellato                                                                  | Non applicabile    | "1"                                        |
| NN     | Importo positivo (11 caratteri) o importo negativo (11 caratteri)                                                                                        | BARRA SPAZIATRICE             | "       1234" "      -1234"                |
| DT     | Data in formato GGMMAAAA format                                                                                                                                   | Non applicabile    | "01012020"                                 |
| DA     | Data in formato AAAA                                                                                                                                       | Non applicabile    | "2020"                                     |
| NP     | Campo numerico positivo                                                                                                                                    | BARRA SPAZIATRICE             | "            1234"                         |
| PC     | Percentuale e tasso, con un massimo di tre posizioni decimali                                                                                           | BARRA SPAZIATRICE             | "   100" "   33,333"                       |
| PR     | Abbreviazione automobilistica per la provincia italiana (ad esempio, la provincia di residenza)                                                                 | BARRA SPAZIATRICE             | "BO   "                                    |
| QU     | Campo numerico con un massimo di cinque posizioni decimali                                                                                                   | BARRA SPAZIATRICE             | "    1000,16234" "   0,99" "   3000000,50" |

## <a name="create-a-yearly-tax-declaration"></a>Creare una dichiarazione fiscale annuale

1. Andare a **Imposta \> Dichiarazioni \> IVA \> Comunicazione annuale imposte**.
2. Selezionare **Creare nuovo** per creare informazioni sull'intestazione per il report **Comunicazione annuale imposte** per l'anno precedente. Il numero di righe create corrisponde al numero di libri IVA italiani.

![Pagina Comunicazione annuale imposte, scheda Panoramica](media/4_Yearly_tax_communication_setup.png)

3. Nella scheda **Generale** rivedere le seguenti informazioni:

    | Campo                | Descrizione                                                                                                                                                                                                                                                                                                                |
    |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | ID comunicazione imposte | Numero di identificazione del report **Comunicazione annuale imposte**.                                                                                                                                                                                                                                                      |
    | Anni                | Anno della comunicazione imposte. Questo campo viene automaticamente impostato sull'anno precedente. Se si crea il report nel 2020, questo campo è ad esempio impostato su **2019**.                                                                                                                                                |
    | Codice ATECOFIN        | Codice imposta associato alla classificazione di possibili attività della società. Questo campo viene compilato dalla pagina **Libri IVA italiani**. Per ulteriori informazioni, vedere [Libri IVA italiani](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-fiscal-books#set-up-sales-tax-books). |
    | Esportato             | Valore che indica se il file con estensione ivc è stato esportato. Questo campo e i due campi successivi vengono impostati automaticamente quando si seleziona **Esporta e genera file**.                                                                                                                                                     |
    | Data di esportazione       | Data in cui è stato esportato il file con estensione .ivc.                                                                                                                                                                                                                                                                                  |
    | Nome file di esportazione     | Nome del file con estensione ivc che è stato esportato.                                                                                                                                                                                                                                                                               |

4. Selezionare la riga richiesta, quindi selezionare **Apri** per aprire la pagina **Comunicazione annuale imposte** che contiene le informazioni sulla dichiarazione selezionata.
5. Nella scheda **Intestazione** rivedere le seguenti informazioni:

<table>
<tbody>
<tr>
<td>
<p><strong>Campo</strong></p>
</td>
<td>
<p><strong>Descrizione</strong></p>
</td>
</tr>
<tr>
<td>
<p><strong>ID comunicazione imposte</strong>, <strong>Codice ATECOFIN</strong> e <strong>Anni</strong></p>
</td>
<td>
<p>Questi campi vengono impostati come descritto nella tabella precedente.</p>
</td>
</tr>
<tr>
<td>
<p>Sezione <strong>Informazioni società</strong></p>
</td>
<td>
<p>Rivedi le informazioni sulla società.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Ragione sociale</strong></p>
</td>
<td>
<p>Nome della società per cui è creato il report <strong>Comunicazione annuale imposte</strong>.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Codice fiscale</strong></p>
</td>
<td>
<p>Codice fiscale della società.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Partita IVA società</strong></p>
</td>
<td>
<p>Partita IVA della società.</p>
</td>
</tr>
<tr>
<td>
<p>Sezione <strong>Dichiarante</strong></p>
</td>
<td>
<p>Immettere le informazioni sul dichiarante.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Tipo di dichiarante</strong></p>
</td>
<td>
<p>Selezionare il tipo di dichiarante.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Registrazione per la stessa persona giuridica</strong></p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong></p>
</td>
</tr>
<tr>
<td>
<p><strong>Codice fiscale CAF</strong></p>
</td>
<td>
<p>Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> immettere il codice fiscale del centro di assistenza fiscale.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Obbligo CAF</strong></p>
</td>
<td>
<p>Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> selezionare uno dei seguenti valori:</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazione preparata da persona giuridica</strong></p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazione preparata dal dichiarante</strong></p>
</td>
</tr>
<tr>
<td>
<p><strong>Numero iscrizione CAF</strong></p>
</td>
<td>
<p>Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> immettere il numero di iscrizione del centro di assistenza fiscale.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Data di trasmissione CAF</strong></p>
</td>
<td>
<p>Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> immetter la data di trasmissione.</p>
</td>
</tr>
<tr>
<td>
<p>Sezione <strong>Dichiarante</strong></p>
</td>
<td>
<p>Specificare le informazioni sul dichiarante, se il dichiarante è diverso dal contribuente.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Dichiarante</strong></p>
</td>
<td>
<p>Selezionare il nome del dipendente.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Codice fiscale dichiarante</strong></p>
</td>
<td>
<p>Immettere il codice fiscale del dichiarante.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Ruolo dichiarante</strong></p>
</td>
<td>
<p>Selezionare il ruolo del dichiarante:</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Rappresentante legale</strong> &ndash; Il dichiarante è un socio gerente.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Amministratore di minorenni</strong> &ndash; Il dichiarante è un amministratore per minori o per persone con disabilità.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Controllore delle merci sequestrate</strong> &ndash; Il dichiarante è un amministratore di beni confiscati.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Rappresentante fiscale</strong> &ndash; Il dichiarante è un rappresentante fiscale per non residenti.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Legatario generale</strong> &ndash; Il dichiarante è un erede della società.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore</strong> &ndash; Il dipendente è l'amministratore di una liquidazione volontaria.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Operatore straordinario</strong> &ndash; Il dipendente è un rappresentante che invia le dichiarazioni fiscali per conto di una società che non esiste più in seguito a una fusione, un'acquisizione o un'altra transazione straordinaria.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Curatore fallimentare</strong> &ndash; Il dichiarante è un curatore fallimentare.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore commissionato</strong> &ndash; Il dipendente è l'amministratore di una liquidazione.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Non residente</strong> &ndash; Il dichiarante è un rappresentante fiscale per non residenti. Il rappresentante fiscale trasferisce gli articoli per conto di un non residente e non paga l'IVA. La società o l'individuo che accetta gli articoli è tenuto a pagare l'IVA. Per maggiori informazio, vedere l'articolo 44, comma 3, del D.L. N. 331/1993.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Tutore legale</strong> &ndash; Il dipendente è tutore di un minore che è erede della società.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore un unico proprietario</strong> &ndash; Il dipendente è un amministratore responsabile della liquidazione delle apparecchiature della società durante una liquidazione volontaria.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Responsabile proprietà</strong> &ndash; Il dichiarante è il responsabile di una proprietà.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Rappresentante pubblico</strong> &ndash; Il dichiarante è un rappresentante che firma le dichiarazioni per conto del governo.</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore pubblico</strong> &ndash; Il dichiarante è un liquidatore che lavora per conto del governo.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Data appuntamento</strong></p>
</td>
<td>
<p>Immettere la data di nomina del dichiarante.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Codice fiscale</strong></p>
</td>
<td>
<p>Immettere il codice fiscale della società dichiarante.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Città o paese straniero di nascita</strong>, <strong>Provincia di nascita</strong>, <strong>Data di nascita</strong>, <strong>Genere</strong>, <strong>Nome</strong>, <strong>Cognome</strong> e <strong>Telefono</strong></p>
</td>
<td>
<p>Immettere informazioni aggiuntive sul dichiarante.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Appuntamenti</strong></p>
</td>
<td>
<p>Specificare le informazioni sull'avvio della procedura e le date di fine.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Data di inizio procedura</strong></p>
</td>
<td>
<p>Immettere una data di inizio della procedura.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Data di fine procedura</strong></p>
</td>
<td>
<p>Immettere una data di fine della procedura.</p>
</td>
</tr>
<tr>
<td>
<p><strong>Correzione</strong></p>
</td>
<td>
<p>Selezionare il tipo di correzione:</p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Correzione</strong></p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazione supplementare</strong></p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazioni aggiuntive</strong></p>
<p>&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazioni aggiuntive (2)</strong></p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>

6. Nella scheda **Righe del report** rivedi o modifica le righe e gli importi configurati in precedenza per il report **Comunicazione annuale imposte** nella pagina **Impostazioni comunicazione annuale imposte**. Per le righe in cui il campo **Calcolo** è impostato su **Manuale**, inserisci manualmente gli importi.
7. Nella scheda **Dettagli** rivedere o modificare i dettagli di ciascuna riga del report **Comunicazione annuale imposte**.
8. Chiudi la pagina **Comunicazione annuale imposte** che contiene le informazioni sulla dichiarazione selezionata.
9. Nella pagina **Comunicazione annuale imposte** che contiene l'elenco delle dichiarazioni, selezionare **Esporta**.
10. Nella finestra di dialogo **Crea file di esportazione** immettere un valore nel campo **Nome file**. Selezionare quindi **OK** per creare ed esportare il file con estensione ivc.
11. Selezionare **Elimina esportazione** per eliminare il file con estensione ivc creato ed esportato.

## <a name="appendix-1-structure-of-the-yearly-vat-declaration"></a>Appendice 1. Struttura della dichiarazione IVA annuale

La tabella seguente fornisce un esempio della struttura della dichiarazione IVA annuale. Questo esempio si basa sulla dichiarazione del 2020. Le sezioni che non sono incluse nell'esempio di configurazione sono riportate in *corsivo*.

<table>
<tbody>
<tr>
<td>
<p><strong>Sezione (EN)</strong></p>
</td>
<td>
<p><strong>Campi</strong></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VA</em></p>
<p><em>INFORMAZIONI E DATI RELATIVI ALL'ATTIVITÀ</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Dati analitici generali</em></p>
</td>
<td>
<p><em>VA001001-VA005004</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Riepilogo dei dati relativi a tutte le attività svolte</em></p>
</td>
<td>
<p><em>VA010001-VA015001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VB</em></p>
<p><em>DATI RELATIVI AI DETTAGLI IDENTIFICATIVI DEI RAPPORTI FINANZIARI</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VB001001-VB007004</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p>PARTE VC</p>
<p>ESPORTATORI E OPERATORI ASSOCIATI</p>
</td>
</tr>
<tr>
<td>
<p>Acquisti e importazioni senza l'applicazione dell'imposta sul valore aggiunto (IVA) relativa a tutte le attività svolte.</p>
</td>
<td>
<p>VC001001-VC014003</p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VD</em></p>
<p><em>CESSIONE DEL CREDITO IVA DA PARTE DI SOCIETÀ DI GESTIONE CESPITI</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Società che effettua la cessione - Elenco delle società o degli enti cessionari</em></p>
</td>
<td>
<p><em>VD001001-VD021002</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Società o enti che effettuano la cessione - Elenco delle società cedenti</em></p>
</td>
<td>
<p><em>VD031001-VD056001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p>PARTE VE</p>
<p>CALCOLO DEL FATTURATO AZIENDALE E DELL'IMPOSTA RELATIVA ALLE OPERAZIONI TASSABILI</p>
<p>(Commento: vendite e IVA a debito sulle vendite)</p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Conferimento di prodotti agricoli e cessioni da parte di agricoltori esenti (in caso di superamento del limite di più di un terzo)</em></p>
</td>
<td>
<p><em>VE001001-VE012002</em></p>
</td>
</tr>
<tr>
<td>
<p>Sezione 2 - Operazioni agricole tassabili e operazioni commerciali o professionali tassabili</p>
</td>
<td>
<p>VE020001-VE023002</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 3 - Totale importo tassabile e imposta</p>
</td>
<td>
<p>VE024001-VE026002</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 4 - Altre operazioni</p>
</td>
<td>
<p>VE030001-VE040001</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 5 - Fatturato aziendale</p>
</td>
<td>
<p>VE050001</p>
</td>
</tr>
<tr>
<td colspan="2">
<p>PARTE VF</p>
<p>OPERAZIONI PASSIVITÀ E IVA AMMISSIBILE IN DETRAZIONE</p>
<p>(Commento: acquisti e IVA a credito sugli acquisti)</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 1 - Importo totale degli acquisti effettuati nel territorio nazionale di acquisti e importazioni intracomunitarie</p>
</td>
<td>
<p>VF001001-VF022001</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 2 - Totale acquisti e importazioni, totale imposte, acquisti intracomunitari, importazioni e acquisti da San Marino</p>
</td>
<td>
<p>VF023001-VF027004</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 3 - Calcolo dell'IVA ammissibile in detrazione</p>
</td>
<td>
<p>VF030001-VF030009</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 3-A - Operazioni esenti</p>
</td>
<td>
<p><em>VF031001-VF033001</em>, VF034001-VF037001</p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 3-B - Azienda agricola (art. 34)</em></p>
</td>
<td>
<p><em>VF038001-VF055001</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 3-C - Casi speciali</em></p>
</td>
<td>
<p><em>VF060001-VF062002</em></p>
</td>
</tr>
<tr>
<td>
<p>Sezione 4 - IVA ammissibile in detrazione</p>
</td>
<td>
<p>VF070001-VF071001</p>
</td>
</tr>
<tr>
<td colspan="2">
<p>PARTE VJ</p>
<p>CALCOLO DELL'IMPOSTA SU ALCUNI TIPI DI OPERAZIONI</p>
<p>(Commento: IVA a debito su reverse charge su acquisti)</p>
</td>
</tr>
<tr>
<td>
<p>&nbsp;</p>
</td>
<td>
<p>VJ001001-VJ019002</p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VI</em></p>
<p><em>DICHIARAZIONI DI INTENTO RICEVUTE</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VI001001-VI006002</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VH</em></p>
<p><em>MODIFICHE DELLE COMUNICAZIONI PERIODICHE</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VH001001-VH017001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VM</em></p>
<p><em>PAGAMENTO PER LE REGISTRAZIONI DI AUTOMOBILI UE</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VM001001-VM012001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VK</em></p>
<p><em>AZIENDA CONTROLLANTE E CONTROLLATA</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 &ndash; Dati generali</em></p>
</td>
<td>
<p><em>VK001001-VK001004</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Calcolo dell'eccedenza fiscale</em></p>
</td>
<td>
<p><em>VK020001-VK028001</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 3 - Cessazione del controllo durante l'anno Dati relativi al periodo di controllo</em></p>
</td>
<td>
<p><em>VK030001-VK036001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VN</em></p>
<p><em>DICHIARAZIONI SUPPLEMENTARI A FAVORE</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VN001001-VN004005</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VQ</em></p>
<p><em>PAGAMENTI PERIODICI OMESSI</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VQ001001-VQ005010</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p>PARTE VL</p>
<p>PAGAMENTO DELL'IMPOSTA ANNUALE</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 1 - Calcolo dell'IVA dovuta o dell'IVA a credito per il periodo fiscale</p>
</td>
<td>
<p>VL001001-VL004001</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 2 - Credito dell'anno precedente</p>
</td>
<td>
<p>VL008001-VL012002</p>
</td>
</tr>
<tr>
<td>
<p>Sezione 3 - Calcolo dell'IVA a debito o a credito relativa a tutte le attività svolte</p>
</td>
<td>
<p>VL020001-VL040001</p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VP</em></p>
<p><em>PAGAMENTO IMPOSTE</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VP001001-VP014002</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VT</em></p>
<p><em>INDICAZIONE SEPARATA DELLE OPERAZIONI EFFETTUATE RIGUARDANTE I CONSUMATORI FINALI E I TITOLARI DI PARTITA IVA</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VT001001-VT022002</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VX</em></p>
<p><em>CALCOLO DELL'IVA DA PAGARE O DEL CREDITO D'IMPOSTA</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Per le persone che presentano il reso con più moduli compilare solo il modulo n. 01</em></p>
</td>
<td>
<p><em>VX001001-VX006002</em></p>
</td>
</tr>
<tr>
<td>
<p><em>RISERVATO ALLE SOCIETÀ PARTECIPANTI AL PAGAMENTO IN FASCIA IVA V</em></p>
</td>
<td>
<p><em>VX007001-VX008001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VO</em></p>
<p><em>COMUNICAZIONE DI OPZIONI E REVOCHE</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Opzioni, rinunce e revoche ai fini dell'IVA</em></p>
</td>
<td>
<p><em>VO001001-VO015002</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Opzioni e revoche ai fini dell'IVA</em></p>
</td>
<td>
<p><em>VO020001-VO026001</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 3 - Opzioni e revoche ai fini dell'IVA e dell'imposta sul reddito</em></p>
</td>
<td>
<p><em>VO030001-VO035001</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 4 - Opzioni e revoca in materia di imposte sull'intrattenimento</em></p>
</td>
<td>
<p><em>VO040001-VO040002</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 5 - Opzioni e revoca in materia di IRAP</em></p>
</td>
<td>
<p><em>VO050001-VO050002</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VG</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Società che partecipano alla compensazione dell'IVA</em></p>
</td>
<td>
<p><em>VG001001-VG004007</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Società che partecipano alla catena di controllo ma non alla compensazione dell'IVA</em></p>
</td>
<td>
<p><em>VG005001-VG007006</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 3 - Revoca</em></p>
</td>
<td>
<p><em>VG008001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VS</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Elenco delle società del gruppo</em></p>
</td>
<td>
<p><em>VS001001-VS012012</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Dati di riepilogo</em></p>
</td>
<td>
<p><em>VS020001-VS022002</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 3 - Garanzie della società controllante</em></p>
</td>
<td>
<p><em>VS030001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VV</em></p>
<p><em>PAGAMENTI IMPOSTE PERIODICI DI GRUPPO</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VV001001-VV017003</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VW</em></p>
<p><em>PAGAMENTO DELL'IMPOSTA ANNUALE DI GRUPPO</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 1 - Calcolo dell'IVA dovuta o dell'IVA a credito per il periodo fiscale</em></p>
</td>
<td>
<p><em>VW001001-VW004001</em></p>
</td>
</tr>
<tr>
<td>
<p><em>Sezione 2 - Calcolo dell'IVA a debito o a credito</em></p>
</td>
<td>
<p><em>VW020001-VW040001</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VY</em></p>
<p><em>CALCOLO DELL'IVA DOVUTA O DEL CREDITO D'IMPOSTA DI GRUPPO</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VY001001-VY006002</em></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><em>PARTE VZ</em></p>
<p><em>ECCEDENZE DI GRUPPO DETRAIBILI (ANNI PRECEDENTI)</em></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><em>VZ001001-VZ002001</em></p>
</td>
</tr>
</tbody>
</table>

### <a name="example"></a>Esempio

Ecco un esempio per la persona giuridica **ITCO**.

1. Andare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA** e configurare i seguenti codici IVA.

    | Codice IVA | Percentuale | Descrizione                                                                              |
    |----------------|------------|------------------------------------------------------------------------------------------|
    | DOMP22         | 22         | Acquisti nazionali con un'aliquota del 22%.                                              |
    | DOMS22         | 22         | Vendite nazionali con un'aliquota del 22%.                                                  |
    | EUP22          | 22         | Acquisti UE con un'aliquota del 22%, dove l'opzione **IVA intracomunitaria** è impostata su **Sì**.    |
    | RC             | 22         | Reverse charge sulle vendite interne per cui l'opzione **Esenzione** è impostata su **Sì**.             |
    | EUS            | 22         | Vendite nell'UE per cui l'opzione **Esenzione** è impostata su **Sì** nella pagina **Fasce IVA**. |

2. Andare a **Imposta** \> **Impostazione** \> **Parametri** \> **Parametri di contabilità generale**.
3. Nella scheda **Sequenze numeriche** selezionare una sequenza numerica per il riferimento **ID comunicazione imposte**.
4. Nella scheda **IVA**, nel campo **Mapping formato** della Scheda dettaglio **Comunicazione annuale imposte** selezionare il formato **Comunicazione annuale imposte (IT)**.
5. Andare a **Imposta** \> **Impostazione** \> **IVA** \> **Impostazioni comunicazione annuale imposte** e aggiungere le seguenti righe.

    | ID campo | Descrizione                                                                                                                                              | Formattazione | Calcolo      | Imposta sul reddito        | Segno | Scheda Codice IVA selezionato | Scheda Totali                   |
    |----------|----------------------------------------------------------------------------------------------------------------------------------------------------------|--------|------------------|------------|------|-----------------------------|------------------------------|
    | VE023001 | Imponibile del 22% delle transazioni fiscali agricole (art. 34, c.1) e delle operazioni professionali                                                                  | NU     | Transazioni fiscali | Imponibile   | 1    | DOMS22                      |                              |
    | VE023002 | Base imponibile del 22% su transazioni fiscali agricole (art. 34, c.1) e operazioni professionali                                                                       | NU     | Transazioni fiscali | Imposta | 1    | DOMS22                      |                              |
    | VE030003 | Vendite intracomunitarie                                                                                                                                    | NU     | Transazioni fiscali | Imponibile   | 1    | EUS                         |                              |
    | VE030001 | Operazioni totali che contribuiscono alla formazione del limite massimo (plafond)                                                                                      | NU     | Totale            |            | 1    |                             | VE030003                     |
    | VE035007 | Vendite di prodotti elettronici                                                                                                                             | NU     | Transazioni fiscali | Imponibile   | 1    | RC                          |                              |
    | VE035001 | Operazioni con applicazione di reverse charge                                                                                                            | NU     | Totale            |            | 1    |                             | VE035007                     |
    | VE050001 | Fatturato aziendale                                                                                                                                        | NU     | Totale            |            | 1    |                             | VE023001, VE030003, VE035007 |
    | VF014001 | Acquisti e importazioni tassabili (22%)                                                                                                                      | NU     | Transazioni fiscali | Imponibile   | 1    | DOMP22, EUP22               |                              |
    | VF014002 | Imposta su acquisti e importazioni (22%)                                                                                                                       | NU     | Transazioni fiscali | Imposta | 1    | DOMP22, EUP22               |                              |
    | VF023001 | Totale ACQUISTI E IMPORTAZIONI                                                                                                                              | NU     | Totale            |            | 1    |                             | VF014001                     |
    | VF023002 | Totale ACQUISTI E IMPORTAZIONI - IMPOSTA                                                                                                                        | NU     | Totale            |            | 1    |                             | VF014002                     |
    | VF025002 | Totale IMPOSTA SU ACQUISTI E IMPORTAZIONI TASSABILI                                                                                                               | NU     | Totale            |            | 1    |                             | VF014002                     |
    | VF026001 | Acquisti intracomunitari - Imponibile                                                                                                                     | NU     | Transazioni fiscali | Imponibile   | 1    | EUP22                       |                              |
    | VF026002 | Acquisti intracomunitari - Imposta                                                                                                                          | NU     | Transazioni fiscali | Imposta | 1    | EUP22                       |                              |
    | VJ009001 | Acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art. 74, commi 7 e 8)        | NU     | Transazioni fiscali | Imponibile   | 1    | EUP22                       |                              |
    | VJ009002 | Imposta su acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art. 74, commi 7 e 8) | NU     | Transazioni fiscali | Imposta | 1    | EUP22                       |                              |
    | VJ019002 | Totale imposta                                                                                                                                                | NU     | Totale            |            | 1    |                             | VJ009002                     |
    | VE024001 | Totale IMPONIBILE per operazioni attive                                                                                                                      | NU     | Totale            |            | 1    |                             | VE023001                     |
    | VE024002 | Totale IMPOSTA su operazioni attive                                                                                                                           | NU     | Totale            |            | 1    |                             | VE023002                     |
    | VE026002 | Totale imposta (VE24 +/- VE25)                                                                                                                                | NU     | Totale            |            | 1    |                             | VE023002                     |
    | VF037001 | IVA ammissibile in detrazione (Sezione 3-A)                                                                                                                  | NU     | Totale            |            | 1    |                             | VF014002                     |
    | VF071002 | IVA ammissibile in detrazione (Sezione 4)                                                                                                                    | NU     | Totale            |            | 1    |                             | VF014002                     |
    | VL001001 | IVA a debito                                                                                                                                               | NU     | Totale            |            | 1    |                             | VJ009002, VE023002           |
    | VL002001 | IVA deducibile                                                                                                                                           | NU     | Totale            |            | 1    |                             | VF014002                     |

> [!NOTE]
> Per visualizzare il modulo "Comunicazione annuale IVA" per l'anno 2020 e le relative istruzioni, vedere [Modello e istruzioni - IVA 2020](https://www.agenziaentrate.gov.it/portale/web/guest/iva-2020/modello-e-istruzioni-imprese).

6. Aggiorna la pagina.
7. Registrare le seguenti transazioni. Ad esempio, per le fatture cliente, andare a **contabilità clienti \> Fatture \> Tutte le fatture a testo libero**. Per le fatture fornitore, andare a **Contabilità fornitori \> Fatture \> Giornale di registrazione fatture**.

    | Data              | Tipo di transazione | Importo netto | Importo IVA | Codice IVA | Campo previsto                                        | Somma prevista            |
    |-------------------|------------------|------------|------------|----------------|-------------------------------------------------------|-------------------------|
    | 1 febbraio 2019  | Fattura fornitore   | 1000       | 220        | DOMP22         | VF014001 VF014002                                     | 1000 220                |
    | 10 febbraio 2019 | Fattura fornitore   | 800        | 176        | EUP22          | VF014001 VF014002 VF026001 VF026002 VJ009001 VJ009002 | 800 176 800 176 800 176 |
    | 2 febbraio 2019  | Fattura cliente | 1000       | 220        | DOMS22         | VE023001 VE023002                                     | 1000 220                |
    | 5 febbraio 2019  | Fattura cliente | 1500       | 0          | EUS            | VE030003                                              | 1500                    |
    | 1 marzo 2019     | Fattura cliente | 500        | 0          | RC             | VE035007                                              | 500                     |

8. Andare a **Imposta \> Dichiarazioni \> IVA \> Comunicazione annuale imposte**.
9. Selezionare **Crea nuovo** per creare un record di comunicazione annuale imposte per l'anno precedente (2019).
10. Selezionare la nuova riga, selezionare **Apri**, quindi rivedere i dati generati per la dichiarazione.

I campi con **Totale** selezionato nel campo **Calcolo** sono contrassegnati in grassetto.

| ID campo     | Valore                      | Descrizione (EN)                                                                                                                                         |
|--------------|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| VE023001     | 1000                       | Imponibile del 22% delle transazioni fiscali agricole (art. 34, c.1) e delle operazioni professionali.                                                                 |
| VE023002     | 220                        | Base imponibile del 22% su transazioni fiscali agricole (art. 34, c.1) e operazioni professionali.                                                                      |
| **VE024001** | 1000                       | Totale IMPONIBILE per operazioni attive.                                                                                                                     |
| **VE024002** | 220                        | Totale IMPOSTA su operazioni attive.                                                                                                                          |
| **VE026002** | 220                        | Totale imposta (VE24 +/- VE25).                                                                                                                               |
| VE030003     | 1500                       | Vendite intracomunitarie.                                                                                                                                   |
| **VE030001** | 1500                       | Operazioni totali che contribuiscono alla formazione del limite massimo (plafond).                                                                                     |
| VE035007     | 500                        | Vendite di prodotti elettronici.                                                                                                                            |
| **VE035001** | 500                        | Operazioni con applicazione di reverse charge.                                                                                                           |
| **VE050001** | 3000 (= 1000 + 1500 + 500) | Fatturato aziendale.                                                                                                                                       |
| VF014001     | 1800                       | Acquisti e importazioni tassabili (22%).                                                                                                                     |
| VF014002     | 396                        | Imposta su acquisti e importazioni (22%).                                                                                                                      |
| **VF023001** | 1800                       | Totale ACQUISTI E IMPORTAZIONI.                                                                                                                             |
| **VF023002** | 396                        | Totale ACQUISTI E IMPORTAZIONI - IMPOSTA.                                                                                                                       |
| **VF025002** | 396                        | Totale IMPOSTA SU ACQUISTI E IMPORTAZIONI TASSABILI.                                                                                                              |
| VF026001     | 800                        | Acquisti intracomunitari - Imponibile.                                                                                                                    |
| VF026002     | 176                        | Acquisti intracomunitari - Imposta.                                                                                                                         |
| **VF037001** | 396 (= 220 + 176)          | IVA ammissibile in detrazione.                                                                                                                               |
| **VF071002** | 396                        | IVA ammissibile in detrazione.                                                                                                                               |
| VJ009001     | 800                        | Acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art. 74, commi 7 e 8).        |
| VJ009002     | 176                        | Imposta su acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art. 74, commi 7 e 8). |
| **VJ019002** | 176                        | Totale imposta.                                                                                                                                               |
| **VL001001** | 396                        | IVA a debito.                                                                                                                                              |
| **VL002001** | 396                        | IVA deducibile.                                                                                                                                          |

## <a name="appendix-2-example-of-the-yearly-tax-communication-setup-for-2020"></a>Appendice 2. Esempio di impostazioni comunicazione annuale imposte per il 2020

Per scaricare l'impostazione di esempio per la dichiarazione 2020, vedere [Impostazione di esempio IVA 2020](https://docs.microsoft.com/dynamics/s-e/ax/ItalianAnnualVATdeclaration_delta). Per accedere al collegamento, è necessario avere accesso a CustomerSource.

1. Andare a **Imposta \> Impostazione \> IVA \> Impostazioni comunicazione annuale imposte**.
2. Selezionare il pulsante **Apri in Microsoft Office**, quindi in **Apri in Excel** selezionare **Impostazioni comunicazione annuale imposte (DEMF)**.

    ![Seleziona di Impostazioni comunicazione annuale imposte (DEFM)](media/6_Export_to_Excel.png)

3. Selezionare **Scarica**.
4. Apri il file scaricato e abilita la modifica.
5. Copiare i dati dal file scaricato in precedenza e incollarli nel file che aperto, quindi selezionare **Pubblica**.

    ![Pulsante Pubblica](media/5_Export_to_Excel.png)

6. Rivedere le impostazioni e apportare gli aggiornamenti necessari. Ad esempio, impostare i codici IVA esistenti nell'applicazione.
7. Considerare le seguenti informazioni. Alcuni totali non sono configurati nell'esempio e devono essere calcolati manualmente utilizzando la formula specificata nelle linee guida ufficiali. Di seguito sono riportati tali totali:

   - VF037001 IVA ammissibile in detrazione (IVA ammessa in detrazione)
   - VF071002 IVA ammissibile in detrazione (IVA ammessa in detrazione)
   - VL032001 IVA dovuta (IVA a debito)
   - VL033001 Credito (IVA a credito)
   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]