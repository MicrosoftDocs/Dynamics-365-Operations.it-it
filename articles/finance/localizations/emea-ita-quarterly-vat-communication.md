---
title: Report di comunicazione IVA trimestrale
description: Questo argomento fornisce informazioni sul report di comunicazione IVA trimestrale in Italia.
author: LizaGolub
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: elgolu
ms.openlocfilehash: 2ea1dfb30e140b9ade37aefeaee6c85c9b527ab1be34d047b411e8be5c52de2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760647"
---
# <a name="quarterly-vat-communication-report"></a>Report di comunicazione IVA trimestrale

[!include [banner](../includes/banner.md)]

Ai sensi del Decreto Legislativo n. 127/2015, articolo 1, e Decreto Legge 78/2010, articolo 21, **Comunicazione periodica del pagamento dell'IVA** (**Comunicazione IVA periodica con prospetto di liquidazione, LIPE**) le informazioni devono essere trasmesse elettronicamente in formato XML alle autorità fiscali italiane.

## <a name="set-up-the-quarterly-vat-communication-lipe-report"></a>Configurare il report di comunicazione IVA trimestrale (LIPE)

### <a name="prerequisites"></a>Prerequisiti

Prima di configurare il report **Comunicazione IVA trimestrale (LIPE)** segui questi passaggi.

1. Andare ad **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**.
2. Nella Scheda dettaglio **Numeri di registrazione**, nella sezione **Italia** nel campo **Codice fiscale** immetti il codice fiscale della persona giuridica della tua organizzazione. (Questo codice ha tra 11 e 16 cifre.)
3. Nella scheda dettaglio **Registrazione fiscale** nel campo **Numero di esenzione fiscale** inserisci il numero di esenzione fiscale della tua organizzazione. (Questo numero ha 11 cifre.)

### <a name="create-a-number-sequence"></a>Creare una sequenza numerica

In base ai requisiti, il nome del report **Comunicazione trimestrale IVA (LIPE)** deve essere composto da più componenti:

- Codice paese International Organization for Standardization (ISO) 3166-1 alpha-2
- Un codice di 11 o 16 caratteri, seguito da un trattino basso (_)
- Un tipo di file (**LI**), seguito da un trattino basso (_)
- Un numero progressivo di cinque caratteri composto solo da lettere minuscole a – z, lettere maiuscole A – Z o numeri da 0 a 9

Di seguito sono riportati alcuni esempi.

- ITAAABBB99T99X999W_LI_00001.xml
- IT99999999999_LI_00002.xml

Per il numero progressivo viene utilizzata una sequenza numerica di sistema. Vai a **Amministrazione organizzazione** \> **Sequenze numeriche** \> **Sequenze numeriche** e crea una sequenza numerica. Questa sequenza numerica deve essere continua e lunga cinque caratteri e alfanumerica (ovvero, deve essere composta solo da lettere minuscole a – z, lettere maiuscole A – Z e numeri da 0 a 9).

Ad esempio:

   ![Impostare una sequenza numerica per il report Comunicazione trimestrale IVA (LIPE).](./media/num-seq.png)

Per ulteriori informazioni su come impostare le sequenze numeriche vedi la sezione [Impostare sequenze numeriche](/dynamicsax-2012/appuser-itpro/set-up-number-sequences).

### <a name="import-and-update-electronic-reporting-configurations"></a>Importare e aggiornare configurazioni per la creazione di report elettronici

1. Importa le versioni più recenti delle seguenti configurazioni per la creazione di report elettronici (ER) per il formato **Comunicazione IVA trimestrale**.

    | Nome configurazione                        | Tipo             | Descrizione                                                                                                                             |
    |-------------------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
    | Modello dei report fiscali italiani                 | Modello            | Il modello di dati comune per le dichiarazioni fiscali italiane.                                                                                          |
    | Mapping del modello Comunicazione IVA trimestrale | Mapping modello    | Il mapping del modello per la raccolta dei dati da Microsoft Dynamics 365 Finance al report **Comunicazione IVA trimestrale (LIPE)**. |
    | Comunicazione IVA Trimestrale               | Formato di esportazione | Il formato ER per il report **Comunicazione IVA trimestrale italiana (LIPE)** in formato XML.                                              |

    Per ulteriori informazioni, vedi [Scaricare configurazioni ER dall'archivio globale](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

    > [!IMPORTANT]
    > Assicurati di importare le versioni più recenti di queste configurazioni. La descrizione di ciascuna versione include in genere il numero dell'articolo della Microsoft Knowledge Base (KB) che spiega le modifiche introdotte in quella versione.

2. Dopo aver importato tutte le configurazioni ER dalla tabella precedente, imposta l'opzione **Predefinito per mapping di modello** su **Sì** per la configurazione **Mapping del modello Comunicazione IVA trimestrale**.
3. Vai a **Aree di lavoro** \> **Creazione di report elettronici**.
4. Seleziona **Modello dei report fiscali italiani** \> **Comunicazione IVA trimestrale** e quindi, nel riquadro azioni, seleziona **Crea configurazione**.
5. Nella finestra di dialogo a discesa, seleziona l'opzione **Deriva da nome: Comunicazione IVA trimestrale**, immetti un nome e una descrizione per il nuovo formato, quindi seleziona **Crea configurazione**.

    ![Derivare il formato ER per creare il formato per l'azienda.](./media/derive-er-format.png)

    Il nuovo formato include tutti i campi e mapping dell'originale. Nel nuovo formato è possibile apportare modifiche per soddisfare i requisiti della propria azienda.

6. Seleziona il nuovo formato e quindi, nel riquadro azioni, seleziona **Progettazione**.

    La pagina **Progettazione formato** è divisa in due parti. Il lato sinistro mostra una struttura di formato (schema XML) e il lato destro mostra un modello di dati (dati).

    Per ulteriori informazioni su ER, vedi [Panoramica dello strumento di creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)

    I valori per i seguenti tag del report vengono raccolti dalle transazioni fiscali registrate nel sistema. I valori considerano i codici imposte specifici utilizzati dalla società e le indicazioni fiscali applicabili alle operazioni della società.

    - TotaleOperazioniAttive
    - TotaleOperazioniPassive
    - IvaEsigibile
    - IvaDetratta

    Per impostare i codici imposta per il report, nella pagina **Progettazione formato** nella scheda **Mapping** espandi **Modello** \> **AccountingData** \> **MonthlyData**, seleziona il nodo **ActiveVATOperations** quindi seleziona **Modifica**.

    ![Modificare la formula per operazioni IVA attive.](./media/edit-formula-active-vat-operations.png)

7. Nella finestra di dialogo **Proprietà origine dati "campo calcolato"** seleziona **Modifica formula**.
8. Aggiorna la formula con i codici imposte utilizzati dalla società e le indicazioni fiscali applicabili alle operazioni della società. Definisci manualmente i codici imposta come valori stringa. Per le indicazioni fiscali, seleziona i valori dall'origine dati **TaxDirection_Type** sul lato sinistro della pagina **Progettazione formula**.

   ![Aggiungere i codici imposta dell'azienda in progettazione formule.](./media/formula-designer.png)

   Quando il report viene generato, il sistema utilizzerà le condizioni definite per il nodo **ActiveVATOperations** per calcolare i valori per i tag **TotaleOperazioniAttive** e **IvaEsigibile** del report.

9. Quando hai finito di modificare la formula, salva le modifiche, chiudi la pagina **Progettazione formula** e seleziona **OK** nella finestra di dialogo **Proprietà origine dati "campo calcolato"**.
10. Nella pagina **Progettazione formato** nella scheda **Mapping** espandi **Modello** \> **AccountingData** \> **MonthlyData**, seleziona il nodo **PassiveVATOperations** quindi seleziona **Modifica**.
11. Nella finestra di dialogo **Proprietà origine dati "campo calcolato"** seleziona **Modifica formula**.
12. Aggiorna la formula con i codici imposta utilizzati dalla tua azienda e le indicazioni fiscali applicabili alle operazioni della tua azienda, come hai fatto per il nodo **ActiveVATOperations** per definire le condizioni che il sistema utilizzerà calcolare i valori per i tag **TotaleOperazioniPassive** e **IvaDetratta** del report.
13. Per specificare la sequenza numerica che il sistema deve utilizzare per i numeri progressivi inclusi nel nome file per il file report, nella pagina **Progettazione formato** nella scheda **Mapping**, seleziona **Aggiungi radice**.
14. Nella finestra di dialogo a discesa, espandi **Dynamics 365 for Operations** e quindi seleziona **Sequenza numerica**.

      ![Aggiungere la sequenza numerica al formato.](./media/add-num-seq.png)

15. Immetti un nome, seleziona la sequenza numerica creata in precedenza, quindi seleziona **OK** per creare la sequenza numerica.

       ![Specificare un nome per la sequenza numerica in formato ER.](./media/num0seq-name.png)

16. Nella pagina **Progettazione formato** seleziona **File** sul lato sinistro, e poi, nella scheda **Mapping**, seleziona il pulsante **Modifica** (simbolo della matita) per il campo **Nome file**.

    ![Modificare la formula per il nome del file con il nome della sequenza numerica.](./media/file-name-edit.png)

17. Aggiorna **"IT"&model.Frontispiece.FiscalCode&"_LI_00000"** con una formula che include un collegamento alla nuova sequenza numerica:
    
      - **"IT"&model.Frontispiece.FiscalCode&"_LI_"&LIPE_file_num**. Qui, **LIPE_file_num** è il nome che hai dato alla sequenza numerica. Per aggiungere **LIPE_file_num** alla formula, fai clic su **Aggiungi origine dati**. Al termine, selezionare **Salva**.

      ![Modificare la formula per il nome file con il nome della sequenza numerica.](./media/file-name-formula-designer.png)

18. Salva le modifiche nel formato ER e completa la configurazione.

### <a name="update-input-parameters"></a>Aggiornare i parametri di input

I valori di alcuni tag di formato devono essere inseriti manualmente. I tag sono inclusi nella finestra di dialogo del report in modo da poter impostare i valori.

Per impostazione predefinita, il formato **Comunicazione IVA trimestrale** include tutti i parametri possibili. Per aggiungere, eliminare o aggiornare i parametri nella finestra di dialogo del report, nella pagina **Progettazione formato** nella scheda **Mapping** passa a **Vista gruppo**, quindi seleziona l'elemento **Contenitori vuoti**.

   ![Contenitori vuoti.](./media/empty-containers.png)

L'elemento **Contenitori vuoti** include tutti i parametri di input per il report. Prima di eliminare un parametro di input, è necessario svincolarlo o aggiornare il mapping per il campo corrispondente. Espandi l'albero della struttura del formato sul lato sinistro della pagina **Progettazione formato** trova il campo corrispondente ed elimina o aggiorna l'associazione.

Per aggiungere un parametro di input, aggiungilo nel nodo corrispondente nell'elemento **Contenitori vuoti**, seleziona un tag nella struttura ad albero del formato, quindi seleziona **Associa**.

   ![Associare un parametro di input.](./media/binding.png)

Quando hai finito di aggiornare il formato, salvalo, chiudilo e completalo.

### <a name="set-up-general-ledger-parameters"></a>Impostazione dei parametri di Contabilità generale

Una nuova voce di menu per il report **Comunicazione IVA trimestrale (LIPE)** deve essere associata al formato creato e aggiornato per la persona giuridica.

1. Andare a **Imposta** \> **Impostazione** \> **Parametri** \> **Parametri di contabilità generale**.
2. Nella scheda **IVA**, nel campo **Mapping formato** della Scheda dettaglio **Comunicazione IVA trimestrale** seleziona il formato **Comunicazione IVA trimestrale** creato.

    ![Impostare il formato di comunicazione IVA trimestrale nei parametri di contabilità generale.](./media/gl-parameters-er-format.png)

## <a name="generate-a-quarterly-vat-communication-lipe-report"></a>Generare un report di comunicazione IVA trimestrale (LIPE)

1. Vai a **Imposta** \> **Dichiarazioni** \> **IVA** \> **Comunicazione IVA trimestrale**.
2. Nella finestra di dialogo **Parametri del report elettronico** imposta i parametri descritti nella tabella seguente.

    | Campo                    | Descrizione                                                                                                                                                                                                                                                                                                                                       | Valore di esempio    |
    |--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|
    | Anno                     | Immetti l'anno per cui generare il report.                                                                                                                                                                                                                                                                                                        | 2018             |
    | Periodo di liquidazione  | Seleziona il periodo di liquidazione IVA per cui generare il report.                                                                                                                                                                                                                                                                                | LUN              |
    | Trimestre                | Seleziona il trimestre per cui generare il report.                                                                                                                                                                                                                                                                                                    | IV               |
    | Mese o Trimestre         | Consente di selezionare una delle opzioni indicate di seguito.                                                                                                                                                                                                                                                                                                              | Mese            |
    | CodiceFiscaleDichiarante | Immetti il codice fiscale del dichiarante. Il codice fiscale è un valore alfanumerico di 16 caratteri. Se questo campo non è applicabile alla tua azienda, lascialo vuoto. Se inserisci un valore in questo campo, devi anche selezionare un valore nel campo **CodiceCarica**.                                                                                     | 1234567891234567 |
    | CodiceCarica             | Se hai inserito un valore nel campo **CodiceFiscaleDichiarante** seleziona il codice posizione che corrisponde a quel codice fiscale.                                                                                                                                                                                                                  | 1                |
    | PIVAControllante         | Immetti il numero di partita IVA della società o autorità che esegue i controlli in caso di pagamento o liquidazione di gruppo. Il numero di partita IVA è un valore alfanumerico di 11 caratteri. Se questo campo non è applicabile alla tua azienda, lascialo vuoto. (Riferimento di legge: ultima clausola dell'articolo 73)                                   | 12345678912      |
    | UltimoMese               | Immetti uno dei seguenti valori per specificare l'ultimo mese di controllo in caso di interruzione del pagamento di gruppo: **1**, **2**, **3**, **4**, **5**, **6**, **7**, **8**, **9**, **10**, **11**, **13**, o **99**. Se questo campo non è applicabile alla tua azienda, seleziona **Non applicabile**. (Riferimento di legge: ultima clausola dell'articolo 73) | 1                |
    | LiquidazioneGruppo       | Se la comunicazione è relativa ad un'interruzione del pagamento di gruppo, inserisci **1**. Se non è relativa ad un'interruzione del pagamento di gruppo, inserisci **0**. Se questo campo non è applicabile alla tua azienda, seleziona **Non applicabile**. (Riferimento di legge: ultima clausola dell'articolo 73)                                                                    | 1                |
    | CFDichiarante            | Inserisci il codice fiscale del dichiarante che effettua la comunicazione. Il codice fiscale è un valore alfanumerico di 16 caratteri. Se questo campo non è applicabile alla tua azienda, lascialo vuoto.                                                                                                                                                   | 1234567891234567 |
    | CodiceCaricaDichiarante  | Immetti il codice posizione del soggetto dichiarante. Il codice posizione è un valore numerico. Se questo campo non è applicabile alla tua azienda, lascialo vuoto.                                                                                                                                                                                           | 1                |
    | CodiceFiscaleSocieta     | Immetti il codice imposta della società dichiarante. Il codice imposta è un valore alfanumerico di 11 caratteri. Sebbene di solito sia uguale al numero di partita IVA, in alcuni casi può differire. Se questo campo non è applicabile alla tua azienda, lascialo vuoto.                                                                                                   | 12345678901      |
    | FirmaDichiarazione       | Se la comunicazione è firmata dal contribuente, seleziona **0**. Se è firmata dalla persona che ha il potere di rappresentanza legale o contrattuale, seleziona **1**.                                                                                                                                                                                   | 0                |
    | CFIntermediario          | Inserisci il codice fiscale dell'intermediario incaricato della trasmissione. Il codice fiscale è un valore alfanumerico di 16 caratteri. Se questo campo non è applicabile alla tua azienda, lascialo vuoto. Se inserisci un valore in questo campo, devi anche inserire valori nei campi **DataImpegno** e **FirmaIntermediario**.                       | 1234567891234567 |
    | ImpegnoPresentazione     | Se la comunicazione è preparata dal contribuente, seleziona **1**. Se è preparato dal mittente, seleziona **2**. Se questo campo non è applicabile alla tua azienda, seleziona **Non applicabile**.                                                                                                                                                       | 1                |
    | DataImpegno              | Se hai inserito un valore nel campo **CFIntermediario** immetti la data corrispondente nel formato ggMMaaaa.                                                                                                                                                                                                                                     | 31012019         |
    | FirmaIntermediario       | Se hai inserito un valore nel campo **CFIntermediario** inserisci **1** se è presente la firma dell'intermediario. Se non è presente, immetti **0**.                                                                                                                                                                                                | 0                |
    | FlagConferma             | Se intendi trasmettere una comunicazione anche se non supera alcun controllo di conformità, seleziona **1**. Se non intendi trasmettere una comunicazione in questa situazione, seleziona **0**.                                                                                                                                                            | 0                |

    - **Trimestre**: Genera un file XML che contiene uno blocco **Modulo** relativo al trimestre selezionato.
    - **Mese**: Genera un file XML che contiene tre blocchi **Modulo** ciascuno dei quali è relativo a un mese del trimestre selezionato.

3. Per i parametri descritti nella tabella seguente, se è stato selezionato **Mese** nel campo **Mese o Trimestre** nel passaggio precedente, immetti i valori per **Mese1**, **Mese2** e **Mese3**, che corrispondono ai mesi del trimestre selezionato. Se hai selezionato **Trimestre** nel campo **Mese o Trimestre** immetti i valori per **Trimestre**, che corrisponde al trimestre selezionato.

    | Campo                                                  | Descrizione                                                                                                                                                       | Valore di esempio |
    |--------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
    | Subfornitura                                           | Se il contributore ha utilizzato i vantaggi forniti, seleziona **1**. Se il contributore non li ha usati, seleziona **0**. (Riferimento di legge: articolo 74, clausola 5)              | 0             |
    | EventiEccezionali                                      | Questo campo è riservato ai soggetti che hanno usufruito dei benefici fiscali IVA nel periodo di riferimento. I valori possibili sono **1** e **9**.                           | 1             |
    | VersamentiAutoUE                                       | Immetti il deposito fiscale totale per il primo trasferimento interno del veicolo. Immetti il valore in formato numerico e utilizza una virgola (,) come separatore decimale.             | 10000,98      |
    | CreditiImposta                                         | Immetti il totale dei crediti d'imposta specifici utilizzati durante il periodo di riferimento. Immetti il valore in formato numerico e utilizza una virgola (,) come separatore decimale. | 10000,98      |
    | InteressiDovuti                                        | Immetti il totale interessi per il pagamento trimestrale. Immetti il valore in formato numerico e utilizza una virgola (,) come separatore decimale.                              | 10000,98      |
    | Acconto                                                | Inserisci l'importo totale dell'acconto, anche se non è stato effettivamente depositato. Immetti il valore in formato numerico e utilizza una virgola (,) come separatore decimale.              | 10000,98      |
    | Metodo                                                 | Seleziona il codice per il metodo utilizzato per determinare l'acconto:                                                                                        | 1             |
    | Operazioni straordinarie                               | Per i casi che comportano operazioni straordinarie, immetti **1**. Altrimenti, immetti **0**.                                                                             | 0             |
    | TotaleOperazioniPassive include importo non detraibile | Seleziona questa casella di controllo se l'importo imponibile nel campo **TotaleOperazioniPassive** include un importo non detraibile.                                            | Selezionate      |

    - **1**: Storico
    - **2**: Previsione
    - **3**: Analitico - valido
    - **4**: Entità che operano in settori quali telecomunicazioni, approvvigionamento idrico, elettricità, raccolta rifiuti e smaltimento

4.  Scegliere **OK** per generare il report.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]