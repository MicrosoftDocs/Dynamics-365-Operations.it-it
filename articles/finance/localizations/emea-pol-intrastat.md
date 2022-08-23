---
title: Intrastat polacco
description: Questo articolo contiene informazioni sulla creazione di report Intrastat in Polonia.
author: AdamTrukawka
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 473581fa4f3f1e8cac06d5748f28116e6615215e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281644"
---
# <a name="polish-intrastat"></a>Intrastat polacco

[!include[banner](../includes/banner.md)]

La pagina **Intrastat** viene usata per generare e visualizzare le informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE). La dichiarazione Intrastat polacca contiene informazioni sul commercio di merci per il reporting.

I seguenti campi sono inclusi nella dichiarazione Intrastat polacca. Tutti i campi sono inclusi negli arrivi e nelle spedizioni tranne **RodzajTransportu** (la modalità di trasporto) e **KrajPochodzenia** (il paese o l'area geografica di origine) che non sono inclusi nelle spedizioni, e **IdKontrahenta** (la partita IVA estera del cliente) che non è inclusa negli arrivi.

| Nome campo | Description |
|-------------------------|-------------------------|
| Dati Deklaracja | Data in cui è stato creato il documento. |
| Miesiac | Mese di riferimento della dichiarazione. |
| Rok | Anno di riferimento della dichiarazione. |
| Numero | Il numero della dichiarazione nel periodo di riferimento. |
| Wersja | Numero di versione della dichiarazione. |
| NrWlasny | Identificatore della dichiarazione. Il valore viene generato automaticamente. |
| Typ | La direzione del report.</br><li>Per gli arrivi, viene stampata la "P".</li><li>Per le spedizioni, viene stampata la "W".</li> |
| Rodzaj | Tipo di dichiarazione. Il valore indica se il report è la dichiarazione originale o una dichiarazione di correzione. |
| UC | Il codice unità a cui è indirizzata la dichiarazione Intrastat. Il valore è specificato nel campo **Numero esenzione fiscale** della sezione **IVA** della scheda **Agente** nella paginsa **Parametri per il commercio estero**. |
| Nazwa | Nome dell'azienda. |
| Miejscowosc, UlicaNumer, KodPocztowy | Indirizzo completo della persona giuridica. |
| Nip | Il numero di identificazione fiscale polacco (ID IVA [IVA]). |
| Regon | Il numero di identificazione statistica polacco (numero di impresa). |
| LacznaWartoscFaktur | La somma dei valori della fattura. |
| LacznaWartoscStatystyczna | La somma dei valori statistici. |
| LacznaLiczbaPozycji | Numero totale di articoli della merce. |
| PozId | Il numero consecutivo di un determinato articolo di merce. |
| OpisTowaru | Nome commerciale della voce doganale. |
| KrajPochodzeniaWysylki | Codice ISO (International Organization for Standardization) per il paese o l'area geografica della controparte. |
| WarunkiDostawy | Il codice Intrastat per i termini di consegna. |
| RodzajTransakcji | Il codice che indica la natura della transazione. Le aziende in Polonia utilizzano codici di transazione a due cifre. |
| KodTowarowy | Il codice voce doganale di otto cifre secondo la nomenclatura combinata. |
| RodzajTransportu | Il codice Intrastat per la modalità di trasporto. |
| KrajPochodzenia | Il codice ISO per il paese o l'area geografica in cui sono stati prodotti o fabbricati i prodotti. |
| MasaNetto | La massa netta in chilogrammi interi. |
| IloscUzupelniajacaJm | La quantità nell'unità di misura supplementare, in numeri interi. |
| WartoscFaktury | Il valore della fattura di tutte le transazioni coperte da un articolo. |
| WartoscStatystyczna | Valore statistico. |
| Wypelniajacy: NazwiskoImie, Telefon, Faks, Email | Nome e cognome, numero di telefono, numero di fax e indirizzo e-mail della persona che presenta la dichiarazione. |
| IdKontrahenta | La partita IVA estera del cliente in uno stato membro dell'UE. |


## <a name="set-up-intrastat"></a>Impostare Intrastat

Nell'archivio globale, importa l'ultima versione delle configurazioni ER seguenti:

   - Modello Intrastat
   - Report Intrastat
   - Intrastat (PL)

Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configura una partita IVA e un numero aziendale per la tua azienda

### <a name="create-registration-types-for-company-codes"></a>Creare tipi di registrazione per i codici azienda

È necessario creare due tipi di registrazione per i codici azienda: uno per la partita IVA (codice NIP) e uno per il numero azienda (codice regionale).

1. Vai a **Amministrazione organizzazione** > **Rubrica globale** > **Tipi di registrazione** > **Tipi di registrazione**.
2. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di registrazione per la partita IVA.
3. Nella finestra di dialogo **Immetti dettagli tipo di registrazione**, nel campo **Nome** immettere un nome per il nuovo tipo di registrazione. Ad esempio, immettere **NIP**.
4. Nel campo **Paese/Area geografica** seleziona **POL**.
5. Selezionare **Crea**.
6. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di registrazione per il numero di impresa.
7. Nella finestra di dialogo **Immetti dettagli tipo di registrazione**, nel campo **Nome** immettere un nome per il nuovo tipo di registrazione. Ad esempio, immettere **Area geografica**.
8. Nel campo **Paese/Area geografica** seleziona **POL**.
9. Selezionare **Crea**.

### <a name="match-the-registration-types-with-registration-categories"></a>Effettuare la corrispondenza tra i tipi di registrazione e le categorie di registrazione

1. Scegliere **Amministrazione organizzazione** > **Rubrica globale** > **Tipi di registrazione** > **Categorie di registrazione**.
2. Nel riquadro azioni, selezionare **Nuovo** per creare un collegamento tra ogni tipo di registrazione creato e una categoria di registrazione.

    - Per il tipo di registrazione della partita IVA (codice NIP), selezionare la categoria di registrazione **Partita IVA** categoria di registrazione.
    - Per il tipo di registrazione del numero di impresa (codice Regon), selezionare la categoria di registrazione **ID azienda (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configura una partita IVA e un numero aziendale per la tua azienda

1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Seleziona l'azienda nella griglia.
3. Nel riquadro azioni, seleziona **ID registrazione**.
4. Nella Scheda dettaglio **ID registrazione** selezionare **Aggiungi**.
5. Nel campo **Tipo di registrazione**, selezionare uno dei tipi di registrazione creato in precedenza.
6. Immettere la partita IVA dell'azienda (codice NIP) o il numero dell'azienda (codice Regon), a seconda del tipo di registrazione selezionato nel passaggio precedente.
7. Ripetere i passaggi da 4 a 6 per l'altro tipo di registrazione creato in precedenza.

## <a name="set-up-a-company-address"></a>Configurare un indirizzo aziendale

1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Seleziona l'azienda nella griglia.
3. Nella scheda **Indirizzi** seleziona **Modifica**.
4. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Codice postale (CAP)**, seleziona il CAP della tua azienda.
5. Nel campo **Via** immetti il tuo indirizzo e-mail.
6. Nel campo **Città** seleziona la tua città.

## <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. Vai a **Imposta** > **Configura** > **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **Intrastat (PL)**.
3. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
4. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.
5. Nel campo **Codice transazione**, seleziona il codice transazione per i trasferimenti di proprietà. Utilizzi questo codice per le transazioni che producono trasferimenti effettivi o pianificati di proprietà dietro compensazione (finanziaria o di altro tipo). Lo usi anche per le correzioni. Le aziende in Polonia utilizzano codici di transazione a due cifre.
6. Nel campo **Nota di accredito**, seleziona il codice transazione per il reso della merce.
7. Nella scheda **Proprietà paese/area geografica**, nel campo **Paese/area geografica**, elenca tutti i paesi o le aree geografiche con cui la tua società ha relazioni commerciali. Per ogni paese che fa parte della UE, nel campo **Tipo di paese/area geografica**, seleziona **UE**, in modo che il paese appaia nel report Intrastat. Per la Polonia, nel campo **Tipo di paese/area geografica** seleziona **Nazionale**.
8. Nella scheda **Agente**, nella Scheda dettaglio **Agente** della sezione **IVA**, nel campo **Numero esenzione fiscale**, immetti **420000** per indicare il codice dell'unità a cui è indirizzata la dichiarazione Intrastat.
9. Nella scheda **Contatto**, immetti il nome, numero di telefono, numero di fax e indirizzo e-mail della persona che presenta la dichiarazione.
10. Nella scheda **Sequenze numeriche**, nel campo **Codice sequenza numerica** per il riferimento **Numero file XML**, specifica una sequenza numerica non continua che abbia un massimo di nove caratteri. Questo campo viene utilizzato per generare automaticamente un valore per il campi **Identificatore della dichiarazione** del report Intrastat.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Impostare i parametri di prodotto per la dichiarazione Intrastat

1. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
2. Seleziona un prodotto nella griglia.
3. Nella Scheda dettaglio **Commercio estero**, nella sezione **Intrastat**, nel campo **Voce doganale** seleziona il codice della voce doganale. Il nome della merce verrà stampato nel campo **Descrizione delle merci** del report Intrastat.
4. Nella sezione **Origine**, nel campo **Paese/area geografica**, selezionare il paese o l'area geografica di origine del prodotto.
5. Nella Scheda dettaglio **Gestione articoli** nel campo **Peso netto** immetti il peso del prodotto in chilogrammi.

## <a name="set-up-compression-of-intrastat"></a>Imposta compressione di Intrastat

-   Seleziona **Imposta** > **Impostazioni** > **Commercio estero** > **Compressione di Intrastat** e seleziona i campi da confrontare quando vengono riepilogati i dati Intrastat. Per l'Intrastat polacca, seleziona i seguenti campi:

    - Voce doganale
    - Codice transazione
    - Paese/Area geografica di origine
    - Trasporto
    - Termini di consegna
    - Paese del mittente
    - Paese
    - Correzione
    - Numero esenzione fiscale
    - Direzione
    - Fattura

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Configurare il metodo di trasporto e i termini di consegna

1.  Impostare i codici di trasporto.

    1. Vai a **Imposta** > **Impostazione** > **Commercio estero** > **Metodo di trasporto**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nel campo **Trasporto** immetti un codice univoco. Le aziende in Polonia utilizzano codici di trasporto a una cifra.

2.  Configura i codici Intrastat della modalità di consegna.

    1. Seleziona **Approvvigionamento** > **Impostazione** > **Distribuzione** > **Termini di consegna**.
    2. Nella griglia, seleziona un set di termini di consegna.
    3. Nella Scheda dettaglio **Generale**, nel campo **Codice Intrastat** immetti il codice univoco.

## <a name="intrastat-transfer"></a>Trasferimento Intrastat

Nella pagina **Intrastat**, nel riquadro azioni, puoi selezionare **Trasferisci** per trasferire automaticamente le informazioni sul commercio intracomunitario da ordini di vendita, fatture a testo libero, ordini di acquisto, fatture fornitore, ricevute di prodotti fornitore, fatture di progetto e ordini di trasferimento. Verranno trasferiti solo i documenti che hanno un paese dell'UE come paese o area geografica di destinazione o consegna.

Puoi anche inserire manualmente le transazioni selezionando **Nuovo** nel riquadro azioni.

### <a name="generate-an-intrastat-report"></a>Generare un report Intrastat

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni, seleziona **Output** &gt; **Report**.
3. Nella finestra di dialogo **Report Intrastat**, imposta i seguenti campi.

    | Campo | Description |
    |-------------------------|-------------------------|
    | Data iniziale | Seleziona la data di inizio per il report. |
    | Genera file | Imposta questa opzione su **Sì** per generare un file .xml per il report Intrastat. |
    | Nome file | Immetti il nome del file .xml. |
    | Genera report | Imposta questa opzione su **Sì** per generare un file .xlsx per il report Intrastat. |
    | Nome file report | Immetti il nome del file .xlsx. |
    | Direzione | Seleziona **Arrivi** per un report sugli arrivi intracomunitari.</br>Seleziona **Spedizioni** per un report sulle spedizioni intracomunitarie. |
    | Identificatore della dichiarazione | L'ID documento viene generato automaticamente e può essere aggiornato. |
    | Tipo di dichiarazione | Seleziona **Dichiarazione** per una dichiarazione originale.</br>Seleziona **Correzione della dichiarazione – sostituzione** per una dichiarazione di rettifica destinata a sostituire completamente un originale o una dichiarazione di rettifica esistente precedentemente presentata. |
    | Città di creazione del documento | Immetti il valore che deve essere stampato nel campo **Miejscowosc** della dichiarazione Intrastat. |
    | Data di creazione del documento | Immetti il valore che deve essere stampato nel campo **Deklaracja Data** della dichiarazione Intrastat. |
    | N. documento | Immetti il valore che deve essere stampato nel campo **Numer** della dichiarazione Intrastat. |
    | Versione documento | Immetti il valore che deve essere stampato nel campo **Wersja** della dichiarazione Intrastat. |

4. Seleziona **OK** ed esamina i report generati.

## <a name="example"></a>Esempio

Questo esempio mostra come registrare arrivi e spedizioni per Intrastat utilizzando la persona giuridica **DEMF**.

### <a name="preliminary-setup"></a>Impostazioni preliminari

Importa l'ultima versione delle seguenti configurazioni per la creazione di report elettronici:

   - Modello Intrastat
   - Report Intrastat
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>Configurare un indirizzo aziendale

1. Scegli **Amministrazione organizzazione** > **Rubrica globale** > **Indirizzi** > **Impostazione indirizzo**.
2. Nella scheda **Città**, seleziona **Nuovo**.
3. Nel campo **Paese/Area geografica** seleziona **POL**.
4. Nel campo **Città** immetti **Varsavia**.
5. Nella scheda **Codice postale (CAP)**, seleziona **Nuovo**.
6. Nel campo **Paese/Area geografica** seleziona **POL**.
7. Nel campo **Città** seleziona **Varsavia**.
8. Nel campo **Codice postale (CAP)**, immetti **00-844**.
9. Vai a **Amministrazione organizzazione** > **Organizzazione** > **Persone giuridiche** e seleziona la persona giuridica **DEMF**.
10. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
11. Nel campo **Paese/Area geografica** seleziona **POL**.
12. Nel campo **Codice postale (CAP)**, seleziona **31-111**.
13. Nel campo **Via** immetti **Statystyczna 22/1**.
14. Nel campo **Città** seleziona **Varsavia**.
15. Seleziona **OK**.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Configurare una partita IVA e un codice numero aziendale per la tua azienda

### <a name="create-registration-types-for-company-codes"></a>Creare tipi di registrazione per i codici azienda

1. Vai a **Amministrazione organizzazione** > **Rubrica globale** > **Tipi di registrazione** > **Tipi di registrazione**.
2. Nel riquadro azioni seleziona **Nuovo** per creare un tipo di registrazione per la partita IVA (codice NIP).
3. Nella finestra di dialogo **Immetti dettagli tipo di registrazione**, nel campo **Nome**, immetti **NIP**.
4. Nel campo **Paese/Area geografica** seleziona **POL**.
5. Selezionare **Crea**.
6. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di registrazione per il numero di impresa (codice Regon).
7. Nella finestra di dialogo **Immetti dettagli tipo di registrazione**, nel campo **Nome**, immetti **Regon**.
8. Nel campo **Paese/Area geografica** seleziona **POL**.
9. Selezionare **Crea**.

### <a name="match-the-registration-types-with-registration-categories"></a>Effettuare la corrispondenza tra i tipi di registrazione e le categorie di registrazione

1. Scegliere **Amministrazione organizzazione** > **Rubrica globale** > **Tipi di registrazione** > **Categorie di registrazione**.
2. Nel riquadro azioni, selezionare **Nuovo** per creare un collegamento tra ogni tipo di registrazione creato e una categoria di registrazione.

    - Per il tipo di registrazione della partita **NIP**, seleziona la categoria di registrazione **Partita IVA**.
    - Per il tipo di registrazione **Regon**, seleziona la categoria di registrazione **ID azienda (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configura una partita IVA e un numero aziendale per la tua azienda

1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Nella griglia seleziona **DEMF**.
3. Nel riquadro azioni, seleziona **ID registrazione**.
4. Nella Scheda dettaglio **ID registrazione** selezionare **Aggiungi**.
5. Nel campo **Tipo di registrazione** seleziona **NIP**.
6. Nel campo **Numero di registrazione** immetti **1234567890**.
7. Seleziona **Aggiungi**.
8. Nel campo **Tipo di registrazione** seleziona **Regon**.
9. Nel campo **Numero di registrazione** immetti **12345678901234**.

### <a name="set-up-a-number-sequence-code"></a>Impostare un codice sequenza numerica

1. Vai a **Amministrazione organizzazione** > **Sequenze numeriche** > **Sequenze numeriche**.
2. Nella scheda **Sequenza numerica** del riquadro azioni, nel gruppo **Nuovo**, seleziona **Sequenza numerica**.
3. Nella Scheda dettaglio **Identificazione**, nel campo **Codice sequenza numerica**, immetti **XML\_file**.
4. Nella Scheda dettaglio **Parametri di ambito**, nel campo **Ambito**, seleziona **Azienda**.
5. Nel campo **Società** seleziona **DEMF**.
6. Nella Scheda dettaglio **Segmenti**, nel campo **Lunghezza** per il segmento **Alfanumerico**, immetti **4**.
7. Nella sezione Scheda dettaglio **Generale**, nella sezione **Impostazione**, imposta l'opzione **Continua** su **No**.
8. Nella sezione **Assegnazione numero**, nel campo **Maggiore**, immetti **9999**.

### <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella Scheda dettaglio **Generale** nel campo **Codice** **transazione** seleziona **11**.
3. Nella Scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file** seleziona **Intrastat (PL)**.
4. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
5. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, verifica che il campo **Gerarchia di categorie** sia impostato su **Intrastat**.
6. Nella scheda **Proprietà paese/area geografica**, seleziona **Nuovo**.
7. Nel campo **Paese/Area geografica della parte** seleziona **POL**. Quindi, nel campo **Tipo di paese/area geografica** seleziona **Nazionale**.
8. Nel campo **Paese/Area geografica della parte** seleziona **DEU**. Quindi, nel campo **Tipo di paese/area geografica** seleziona **UE**.
9. Nella scheda **Agente**, nella Scheda dettaglio **Agente**, nella sezione **IVA**, nel campo **Numero esenzione fiscale**, immetti **420000**.
10. Nella scheda **Contatto** nel campo **Nome** immetti **Manish Chopra**.
11. Nel campo **Telefono**, immetti **425-555-5068**.
12. Nel campo **Numero di fax**, immetti **425-555-5049**.
13. Nel campo **E-mail**, immetti **manishc@contoso.com**.
14. Nella scheda **Sequenze numeriche**, nel campo **Codice sequenza numerica** per il riferimento **Numero file XML**, seleziona **XML\_file**.

### <a name="set-up-product-information"></a>Impostare le informazioni prodotto

1. Vai a **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti** **rilasciati**.
2. Nella griglia seleziona **D0001**.
3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **100 200 30**.
4. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure** nel campo **Peso netto** immetti **2**.
5. Nel riquadro azioni selezionare **Salva**.
6. Nella griglia seleziona **D0003**.
7. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **100 200 30**.
8. Nella sezione **Origine**, nel campo **Paese/Area geografica**, seleziona **DEU**.
9. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure** nel campo **Peso netto** immetti **5**.
10. Nel riquadro azioni selezionare **Salva**.

### <a name="change-the-site-address"></a>Modificare l'indirizzo del sito

1. Vai a **Gestione magazzino** > **Impostazione** > **Magazzino** > **Siti**.
2. Nella griglia seleziona **1**.
3. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
4. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **POL**.
5. Seleziona **OK**.

### <a name="set-up-a-transport-method"></a>Configurare un metodo di trasporto

1. Crea un metodo di trasporto.

    1. Vai a **Imposta** > **Impostazione** > **Commercio estero** > **Metodo di trasporto**.
    2. Nel Riquadro azioni selezionare **Nuovo**.
    3. Nel campo **Trasporto**, immetti **3**.
    4. Nel campo **Descrizione** immetti **Trasporto su strada**.

2. Assegna il nuovo metodo di trasporto predefinito a una modalità di consegna. In questo modo, puoi configurare i valori predefiniti che vengono utilizzati per il metodo di trasporto quando viene selezionata la modalità di consegna corrispondente.

    1. Seleziona **Approvvigionamento** > **Impostazione** > **Distribuzione** > **Modalità di consegna**.
    2. Nella griglia seleziona **10**.
    3. Nella Scheda dettaglio **Commercio estero** nel campo **Trasporto**, seleziona **3**.

3. Seleziona la modalità di consegna predefinita per un cliente.

    1. Vai a **Contabilità clienti** > **Clienti** > **Tutti i clienti**.
    2. Nella griglia seleziona **DE-016**.
    3. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **Modalità di consegna**, seleziona **10**.

4. Seleziona la modalità di consegna predefinita per un fornitore.

    1. Vai a **Contabilità fornitori** > **Fornitori** > **Tutti i fornitori**.
    2. Nella griglia seleziona **DE-001**.
    3. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **Modalità di consegna**, seleziona **10**.

### <a name="set-up-codes-for-terms-of-delivery"></a>Configurare i codici per i termini di consegna

1. Configura un codice Intrastat per i termini di consegna.

    1. Seleziona **Approvvigionamento** > **Impostazione** > **Distribuzione** > **Termini di consegna**.
    2. Nella griglia seleziona **CIF**.
    3. Nella Scheda dettaglio **Generale**, nel campo **Codice Intrastat** immetti **CIF**.

2. Seleziona i termini di consegna predefiniti per un cliente.

    1. Vai a **Contabilità clienti** > **Clienti** > **Tutti i clienti**.
    2. Nella griglia seleziona **DE-016**.
    3. Nella Scheda dettaglio **Fattura e consegna**, nel campo **Termini di consegna**, seleziona **CIF**.

3. Seleziona i termini di consegna predefiniti per un fornitore.

    1. Vai a **Contabilità fornitori** > **Fornitori** > **Tutti i fornitori**.
    2. Nella griglia seleziona **DE-001**.
    3. Nella Scheda dettaglio **Fattura e consegna**, nel campo **Termini di consegna**, seleziona **CIF**.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Verificare un codice numero di esenzione fiscale del cliente UE

1. Vai a **Contabilità clienti** > **Clienti** > **Tutti i clienti**.
2. Nella griglia seleziona **DE-016**.
3. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **IVA**, verifica che il campo **Numero esenzione fiscale** sia impostato su **DE9012**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Creare un ordine cliente con un cliente UE

1. Seleziona **Contabilità clienti** > **Ordini** > **Tutti gli ordini cliente**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine cliente** nella Scheda dettaglio **Cliente**, nella sezione **Cliente**, nel campo **Conto cliente** seleziona **DE-016**.
4. Nella Scheda dettaglio **Generale**, nella sezione **Dimensioni di immagazzinamento**, nel campo **Sito**, seleziona **1**.
5. Nel campo **Magazzino** selezionare **11**.
6. Nella scheda **Indirizzo**, verifica che il campo **Indirizzo** sia impostato su **Teichgasse 12, Kiel, 24103, DEU**, perché il cliente è tedesco.
7. Seleziona **OK**.
8. Nella scheda **Intestazione**, nella Scheda dettaglio **Consegna**, verifica che il campo **Termini di consegna** sia impostato su **CIF**, e il campo **Modalità di consegna** sia impostato su **10**.
9. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine cliente**, nel campo **Codice articolo** seleziona **D0001**. Quindi, nel campo **Quantità** immetti **8**.
10. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Commercio estero**, verifica che il campo **Codice transazione** sia impostato su **11**, il campo **Merce** sia impostato su **100 200 30** e il campo **Paese/area geografica di origine** sia impostato su **POL**.
11. Nel riquadro azioni selezionare **Salva**.
12. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
13. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**.
14. Nella Scheda dettaglio **Impostazione**, nel campo **Data di vendita**, seleziona **10/18/2021** (18 ottobre 2021).
15. Seleziona **OK** per registrare la fattura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Trasferire la transazione al giornale di registrazione Intrastat ed esaminare il risultato

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**.
4. Seleziona **Filtro**.
5. Nella finestra di dialogo **Filtro Intrastat**, nella scheda **Intervallo**, seleziona la prima riga e verifica che il campo **Campo** sia impostato su **Data**.
6. Nel campo **Criteri** seleziona la data corrente.
7. Seleziona **OK** per chiudere la finestra di dialogo **Filtro Intrastat**.
8. Seleziona **OK** per chiudere la finestra di dialogo **Intrastat (trasferimento)** ed esamina il risultato. La riga rappresenta l'ordine cliente creato in precedenza.

    ![La riga rappresenta l'ordine cliente nella pagina Intrastat](media/intrastat_pl_1.png)

9. Seleziona la riga della transazione, quindi seleziona la scheda **Generale** per visualizzare maggiori dettagli.

    ![Dettagli dell'ordine cliente nella scheda Generale della pagina Intrastat](media/intrastat_pl_2.png)

10. Nel riquadro azioni, seleziona **Output** > **Report**.
11. Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data**, nel campo **Data iniziale** seleziona il primo giorno del mese corrente.
12. Nella sezione **Opzioni** **di esportazione** imposta l'opzione **Genera file** su **Sì**. Quindi, nel campo **Nome file** immetti il nome richiesto.
13. Imposta l'opzione **Genera report** su **Sì**. Quindi, nel campo **Nome file report** immetti il nome richiesto.
14. Nel campo **Direzione** seleziona **Spedizioni**.
15. Nella sezione **Mapping di formato file**, verifica che il campo **Tipo di dichiarazione** sia impostato su **Dichiarazione**.
16. Nel campo **Città di creazione del documento**, immetti **Cracovia**.
17. Nel campo **Data di creazione del documento**, seleziona **19/10/2021** (19 ottobre 2021).
18. Nel campo **N. documento** immetti **11**.
19. Nel campo **Versione documento** immetti **22**.
20. Seleziona **OK** ed esamina il report in formato XML che viene generato. Nella seguente tabella sono riportati i valori del report di esempio.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nome campo</strong></p>
    </td>
    <td>
    <p><strong>Descrizione campo</strong></p>
    </td>
    <td>
    <p><strong>Valore</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informazioni sul documento</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Dati Deklaracja</p>
    </td>
    <td>
    <p>Data in cui è stato creato il documento.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Città in cui è stato creato il documento.</p>
    </td>
    <td>
    <p>Cracovia</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Numero totale di articoli.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Valore statistico totale.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Valore totale della fattura.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Codice unità.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Tipo di dichiarazione.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Versione del documento.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numero</p>
    </td>
    <td>
    <p>Numero del documento.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>Mese di riferimento.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>Anno di riferimento.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>La direzione del report.</p>
    </td>
    <td>
    <p>Me</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>Identificatore della dichiarazione.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informazioni sull'azienda</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>Città in cui si trova l'azienda.</p>
    </td>
    <td>
    <p>Varsavia</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>Codice Regon della società.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Codice NIP della società.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Codice postale dell'azienda.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Via in cui si trova l'azienda.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Nome dell'azienda.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informazioni sul prodotto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Valore statistico.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Valore della fattura.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Massa netta.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>Partita IVA del cliente.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Codice voce doganale.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Codice transazione.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Termini della modalità di consegna.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Il codice del paese o dell'area geografica di spedizione/destinazione.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Descrizione della voci doganali.</p>
    </td>
    <td>
    <p>Hardware</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Il numero di articolo.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informazioni contatto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Indirizzo e-mail</p>
    </td>
    <td>
    <p>Indirizzo e-mail del mittente.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Numero di fax del mittente.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Numero di telefono del mittente.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Nome del mittente.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Esamina il report in formato Excel che viene generato.

    ![Report Intrastat sulle spedizioni](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai a **Contabilità fornitori** > **Ordini fornitore** > **Tutti gli ordini fornitore**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine fornitore**, nel campo **Conto fornitore** seleziona **DE-001**.
4. Nel campo **Sito** seleziona **1**.
5. Nel campo **Magazzino** seleziona **11**.
6. Seleziona **OK**.
7. Nella scheda **Intestazione**, nella Scheda dettaglio **Consegna**, verifica che il campo **Modalità di consegna** sia impostato su **10F** e il campo **Termini di consegna** sia impostato su **CIF**.
8. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine fornitore**, nel campo **Codice articolo** seleziona **D0003**. Quindi, nel campo **Quantità** immetti **6**.
9. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Commercio estero**, verifica che il campo **Codice transazione** sia impostato su **11**, il campo **Trasporto** sia impostato su **3**, il campo **Voce doganale** sia impostato su **100 200 30** e il campo **Paese/area geografica di origine** sia impostato su **DEU**.
10. Nel riquadro Azioni, nella scheda **Acquisto**, nel gruppo **Azioni**, seleziona **Conferma**.
11. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
12. Nel riquadro azioni, seleziona **Predefinito da**, quindi, nel campo **Quantità predefinita per le righe**, seleziona **Quantità ordinata**. Selezionare **OK**.
13. Nella Scheda dettaglio **Intestazione fattura fornitore**, nella sezione **Identificazione fattura**, nel campo **Numero** immetti **00010**.
14. Nella sezione **Date fatture**, nel campo **Data fattura** seleziona la data corrente. Questa data sarà utilizzata per il trasferimento Intrastat.
15. Nel campo **Data ricezione documento**, seleziona **18/10/2021** (18 ottobre 2021).
16. Nel riquadro Azioni, seleziona **Registra** per registrare la fattura.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Creare una dichiarazione Intrastat per gli arrivi

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura fornitore** su **Sì**.
4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

    ![La riga rappresenta l'ordine fornitore nella pagina Intrastat](media/intrastat_pl_4.png)

5. Rivedi le informazioni nella scheda **Generale** per l'ordine fornitore.

    ![Dettagli dell'ordine fornitore nella scheda Generale della pagina Intrastat](media/intrastat_pl_5.png)

6. Nel riquadro azioni, seleziona **Output** > **Report**.
7. Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data**, nel campo **Data iniziale** seleziona il primo giorno del mese corrente.
8. Nella sezione **Opzioni** **di esportazione** imposta l'opzione **Genera file** su **Sì**. Quindi, nel campo **Nome file** immetti il nome richiesto.
9. Imposta l'opzione **Genera report** su **Sì**. Quindi, nel campo **Nome file report** immetti il nome richiesto.
10. Nel campo **Direzione** seleziona **Arrivi**.
11. Nella sezione **Mapping di formato file**, verifica che il campo **Tipo di dichiarazione** sia impostato su **Dichiarazione**.
12. Nel campo **Città di creazione del documento**, immetti **Cracovia**.
13. Nel campo **Data di creazione del documento**, seleziona **19/10/2021** (19 ottobre 2021).
14. Nel campo **N. documento** immetti **11**.
15. Nel campo **Versione documento** immetti **22**.
16. Seleziona **OK** ed esamina il report in formato XML che viene generato. Nella seguente tabella sono riportati i valori del report di esempio.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nome campo</strong></p>
    </td>
    <td>
    <p><strong>Descrizione campo</strong></p>
    </td>
    <td>
    <p><strong>Valore</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informazioni sul documento</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Dati Deklaracja</p>
    </td>
    <td>
    <p>Data in cui è stato creato il documento.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Città in cui è stato creato il documento.</p>
    </td>
    <td>
    <p>Cracovia</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Numero totale di articoli.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Valore statistico totale.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Valore totale della fattura.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Codice unità.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Tipo di dichiarazione.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Versione del documento.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numero</p>
    </td>
    <td>
    <p>Numero del documento.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>Mese di riferimento.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>Anno di riferimento.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>La direzione del report.</p>
    </td>
    <td>
    <p>P</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>Identificatore della dichiarazione.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informazioni sull'azienda</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>Città in cui si trova l'azienda.</p>
    </td>
    <td>
    <p>Varsavia</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>Codice Regon della società.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>Codice NIP della società.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Codice postale dell'azienda.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Via in cui si trova l'azienda.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Nome dell'azienda.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informazioni sul prodotto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Valore statistico.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Valore della fattura.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Massa netta.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>Il codice del paese o dell'area geografica di origine.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>Codice della modalità di trasporto.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Codice voce doganale.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Codice transazione.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Termini della modalità di consegna.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Il codice del paese o dell'area geografica di spedizione/destinazione.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Descrizione della voci doganali.</p>
    </td>
    <td>
    <p>Hardware</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Il numero di articolo.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informazioni contatto</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Indirizzo e-mail</p>
    </td>
    <td>
    <p>Indirizzo e-mail del mittente.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Numero di fax del mittente.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Numero di telefono del mittente.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Nome del mittente.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Esamina il report in formato Excel che viene generato.

    ![Report Intrastat sugli arrivi](media/intrastat_pl_6.png)
