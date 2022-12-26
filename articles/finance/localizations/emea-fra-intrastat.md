---
title: Intrastat francese
description: Questo articolo contiene informazioni sulla creazione della dichiarazione Intrastat in Francia.
author: anasyash
ms.date: 11/30/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 2076649c7fff9f47b9c1fda62a103168b19bb973
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831807"
---
# <a name="french-intrastat"></a>Intrastat francese

[!include[banner](../includes/banner.md)]

Le aziende in Francia che sono registrate per l'imposta sul valore aggiunto (IVA) e che commerciano con altri paesi dell'Unione Europea (UE), devono dichiarare lo scambio di beni e servizi da e verso la Francia. La dichiarazione di commercio di beni (DEB, Declaration d'Exchanges de Biens) è una combinazione dell'elenco vendite UE con il report Intrastat. È necessario inviare questo report mensilmente per tutte le vendite intracomunitarie di beni.

È possibile generare il report DEB in uno dei due formati di file elettronici disponibili: SAISUNIC 330 o INTRACOM.

La tabella seguente mostra i campi che sono inclusi nella dichiarazione Intrastat francese in formato SAISUNIC 330. La tabella indica anche i livelli di report di ogni campo. Un campo può avere i seguenti livelli di report:

- **4** – Dichiarazione fiscale.
- **1** – Risposta statistica.
- **5** – Risposta statistica per spedizione e dichiarazione fiscale.

| Campo                       | Livelli di report |
|-----------------------------|---------------|
| Periodo di riferimento         | 4, 1, 5       |
| Numero di dichiarazione       | 4, 1, 5       |
| Numero di riga                 | 4, 1, 5       |
| Codice ISO paese (FR)       | 4, 1, 5       |
| Codice complementare          | 4, 1, 5       |
| Numero Siren                | 4, 1, 5       |
| Codice IVA del cliente        | 4, 1, 5       |
| Codice direzione              | 4, 1, 5       |
| Tipo di transazione            | 4, 1, 5       |
| Livello di obbligo            | 4, 1, 5       |
| Codice voce doganale              | 1, 5          |
| NGP nazionale                | 1, 5          |
| Provincia (reparto)         | 1, 5          |
| Natura della transazione       | 1, 5          |
| Paese di origine      | 1, 5          |
| Paese di origine - Importazioni | 1, 5          |
| Destinazione finale - Esportazioni | 1, 5          |
| Valore fattura               | 4, 1, 5       |
| Valore statistico           | 1, 5          |
| Peso netto                  | 1, 5          |
| Unità supplementari            | 1, 5          |
| Codice di trasporto              | 1, 5          |

La tabella seguente mostra i campi che sono inclusi nella dichiarazione Intrastat francese in formato INTRACOM. La tabella indica anche i livelli di report di ogni campo. Un campo può avere i seguenti livelli di report:

- **4** – Dichiarazione fiscale.
- **1** – Risposta statistica.
- **5** – Risposta statistica per spedizione e dichiarazione fiscale.

| Campo                       | Livelli di report |
|-----------------------------|---------------|
| Codice direzione              | 4, 1, 5       |
| Numero di dichiarazione       | 4, 1, 5       |
| Numero di riga              | 4, 1, 5       |
| Siren                       | 4, 1, 5       |
| Provincia (reparto)         | 1, 5          |
| Codice di trasporto              | 1, 5          |
| Paese di origine           | 1, 5          |
| Natura della transazione       | 1, 5          |
| Valore fattura               | 4, 1, 5       |
| Modalità di consegna           | 1, 5          |
| Tipo di transazione            | 4, 1, 5       |
| Livello di obbligo            | 4, 1, 5       |
| Codice voce doganale              | 1, 5          |
| NGP nazionale                | 1, 5          |
| Peso netto                  | 1, 5          |
| Valore statistico           | 1, 5          |
| Unità supplementari            | 1, 5          |
| Paese di origine - Importazioni | 1, 5          |
| Destinazione finale - Esportazioni | 1, 5          |
| Codice IVA del cliente        | 4, 1, 5       |
| Codice complementare          | 4, 1, 5       |
| Periodo di riferimento         | 4, 1, 5       |

## <a name="set-up-intrastat"></a>Impostare Intrastat

- In [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), nella raccolta di risorse condivise scarica l'ultima versione delle seguenti configurazioni per la creazione di report elettronici per la dichiarazione Intrastat:

    - Modello Intrastat
    - Report Intrastat
    - INTRACOM Intrastat (FR)
    - SAISUNIC Intrastat (FR)

    Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="set-up-vat-ids"></a>Impostare gli ID IVA

#### <a name="set-up-vat-codes-for-your-company"></a>Impostare i codici IVA per la società

1. Vai a **Imposta** \> **Impostazione** \> **IVA** \> **Partite IVA**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Paese/Area geografica** seleziona **FRA**.
4. Nel campo **Numero esenzione fiscale**, immetti il numero di partita IVA della società.
5. Vai in **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche** e seleziona la tua azienda.
6. Nella scheda dettaglio **Commercio estero e logistica** nella sezione **Intrastat** imposta i campi **Partita IVA esportazione** e **Partita IVA importazione** per il codice creato al passaggio 4.
7. Nella Scheda dettaglio **Registrazione fiscale**, nel campo **Partita IVA**, immetti la partita IVA della società.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Impostare gli ID IVA per i partner commerciali

##### <a name="create-a-registration-type-for-the-company-code"></a>Creare un tipo di registrazione per il codice società

È necessario creare i tipi di registrazione con ID IVA per tutti i paesi o le aree geografiche con cui la tua azienda opera.

1. Vai a **Amministrazione organizzazione** \> **Rubrica globale** \> **Tipi di registrazione** \> **Tipi di registrazione**.
2. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di registrazione per la partita IVA.
3. Nella finestra di dialogo **Immetti dettagli tipo di registrazione**, nel campo **Nome** immettere un nome per il nuovo tipo di registrazione. Ad esempio, immetti **ID IVA**.
4. Nel campo **Paese/Area geografica** seleziona il paese o l'area geografica del partner commerciale.
5. Seleziona **Crea**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Effettuare la corrispondenza tra il tipo di registrazione e la categoria di registrazione

1. Vai a **Amministrazione organizzazione** \> **Rubrica globale** \> **Tipi di registrazione** \> **Categorie di registrazione**.
2. Nel riquadro azioni, seleziona **Nuovo** per creare un collegamento tra un tipo di registrazione e una categoria di registrazione.
3. Per il tipo di registrazione dell'ID IVA, seleziona la categoria di registrazione **ID IVA**.
4. Ripeti i passaggi 2 e 3 per gli altri tipi di registrazione che hai creato per i paesi o le aree geografiche con cui la tua azienda opera.

##### <a name="set-up-the-vat-number-of-a-trading-partner"></a>Impostare il numero di partita IVA di un partner commerciale

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Seleziona un cliente nella griglia.
3. Nel riquadro azioni, nella scheda **Cliente**, nel gruppo **Registrazione**, seleziona **ID registrazione**.
4. Nella scheda dettaglio **ID registrazione** seleziona **Aggiungi** per creare un ID registrazione.
5. Nel campo **Tipo di registrazione**, seleziona un tipo di registrazione creato per il codice società.
6. Nel campo **Numero di registrazione** immetti il numero di partita IVA della società.
7. Nel riquadro azioni seleziona **Salva** e chiudi la pagina.

Per ulteriori informazioni, vedi [ID registrazione](emea-registration-ids.md).

### <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. Vai a **Imposta** \> **Impostazione** \> **Commercio estero** \> **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella scheda dettaglio **Creazione di report elettronici** nel campo **Mapping di formato file** seleziona **Intrastat INTRACOM (FR)** o **Intrastat SAISUNIC (FR)**.
3. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
4. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.
5. Nella scheda dettaglio **Generale** nel campo **Codice transazione** seleziona il codice che viene utilizzato per i trasferimenti di beni.
6. Nel campo **Nota di credito** seleziona il codice che viene utilizzato per i resi di merce.
7. Nel campo **Lavoratore** seleziona il nome della persona di contatto.
8. Nella scheda **Contatto** , aggiungi le informazioni sulla persona di contatto:

    - Nel campo **Telefono** inserisci il numero di telefono della persona di contatto.
    - Nel campo **Fax** inserisci il numero di fax della persona di contatto.

9. Nella scheda **Proprietà paese/area geografica**, nel campo **Paese/area geografica**, elenca tutti i paesi o le aree geografiche con cui la tua società ha relazioni commerciali. Per ogni paese che fa parte della UE, nel campo **Tipo di paese/area geografica**, seleziona **UE**, in modo che il paese appaia nel report Intrastat. Per la Francia, nel campo **Tipo di paese/area geografica** seleziona **Nazionale**.

### <a name="set-up-compression-of-intrastat"></a>Imposta compressione di Intrastat

- Vai a **Imposta** \> **Impostazioni** \> **Commercio estero** \> **Compressione di Intrastat** e seleziona i campi da confrontare quando vengono riepilogati i dati Intrastat. Per l'Intrastat francese, seleziona i seguenti campi:
 
    - Procedura statistiche
    - Paese/Area geografica di origine
    - Trasporto
    - Correzione
    - Paese/area geografica
    - Provincia di origine/destinazione
    - Direzione
    - Paese del mittente
    - Codice transazione
    - Voce doganale

### <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Impostare i parametri di prodotto per la dichiarazione Intrastat

1. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.
2. Seleziona un prodotto nella griglia.
3. Nella Scheda dettaglio **Commercio estero**, nella sezione **Intrastat**, nel campo **Voce doganale** seleziona il codice della voce doganale. Il nome della merce verrà stampato nel campo **Descrizione delle merci** del report Intrastat.
4. Nella sezione **Origine**, nel campo **Paese/area geografica**, selezionare il paese o l'area geografica di origine del prodotto.
5. Nella Scheda dettaglio **Gestione articoli** nel campo **Peso netto** immetti il peso del prodotto in chilogrammi.

### <a name="ngp-codes"></a>Codici NGP

Nel report DEB, la codificazione dei prodotti è composta dai seguenti elementi:

- Il codice CN8 a otto cifre che rappresenta la nomenclatura tariffaria e statistica dell'UE.
- Se applicabile, il codice articolo nazionale a una cifra Nomenclature Générale des Produits (NGP).

Nel 2022, il NGP si applica solo a tre tipi di prodotti:

- Prodotti relativi a mucche, pecore e capre
- Equipaggiamento militare
- Vini francesi

È necessario impostare i codici NGP e assegnarli ai prodotti correlati. Il campo **NGP** viene quindi impostato automaticamente nella pagina **Giornale di registrazione Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Impostare un codice NGP

1. Vai a **Imposta** \> **Impostazioni** \> **Commercio estero** \> **Codici NGP**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **NGP** immetti un codice a una cifra.
4. Nel campo **Descrizione** immetti una descrizione per il codice.

#### <a name="assign-an-ngp-code-to-a-product"></a>Assegnare un codice NGP a un prodotto

1. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.
2. Seleziona un prodotto nella griglia.
3. Nella scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **NGP** seleziona il codice NGP appropriato.

### <a name="set-up-warehouse-parameters-for-the-intrastat-declaration"></a>Impostare i parametri di magazzino per la dichiarazione Intrastat

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Magazzino** \> **Magazzini**.
2. Seleziona un magazzino, quindi, nella Scheda dettaglio **Indirizzi** , seleziona **Aggiungi** o **Modifica**.
3. Nella finestra di dialogo, nel campo **Città**, seleziona la città del magazzino. Lo stato o la provincia della città verrà utilizzato come regione per il tuo report DEB.

### <a name="set-up-the-transport-method"></a>Configurare il metodo di trasporto

1. Vai a **Imposta** \> **Impostazione** \> **Commercio estero** \> **Metodo di trasporto**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Trasporto** immetti un codice univoco. Le aziende in Francia utilizzano codici di trasporto a una cifra.

### <a name="intrastat-journal"></a>Giornale di registrazione Intrastat

Vai a **Imposta** \> **Dichiarazioni** \> **Commercio estero** \> **Intrastat** per gestire le tue transazioni applicabili al commercio estero con i paesi dell'UE. Per ulteriori informazioni, vedere [Panoramica Intrastat](emea-intrastat.md).

La colonna **NGP** è specifica per la Francia e mostra il codice NGP del prodotto. Se il codice NGP non è applicabile a un prodotto, viene visualizzato **0** (zero). Per modificare il codice NGP, seleziona la transazione, e poi, nella scheda **Generale** nella sezione **Codici** nel campo **NGP** seleziona il codice NGP richiesto.

#### <a name="intrastat-transfer"></a>Trasferimento Intrastat

Nella pagina **Intrastat**, nel riquadro azioni, puoi selezionare **Trasferisci** per trasferire automaticamente le informazioni sul commercio intracomunitario da ordini di vendita, fatture a testo libero, ordini di acquisto, fatture fornitore, ricevute di prodotti fornitore, fatture di progetto e ordini di trasferimento. Verranno trasferiti solo i documenti che hanno un paese dell'UE come paese o regione di destinazione (per le spedizioni) o consegna (per gli arrivi).

Poiché il report DEB è una combinazione dell'elenco vendite UE e del report Intrastat, include anche le transazioni *triangolari* in cui viene effettuata una consegna diretta da un paese dell'UE (parte A) a un altro paese dell'UE (parte C) e una persona giuridica francese (parte B) si trova nel mezzo dell'operazione triangolare.

#### <a name="generate-a-deb-intrastat-report"></a>Generare un report DEB (Intrastat)

1. Vai a **Imposta** \> **Dichiarazioni** \> **Commercio estero** \> **Intrastat**.
2. Nel riquadro azioni, seleziona **Output** \> **Report**.
3. Nella finestra di dialogo **Report Intrastat**, imposta i seguenti campi.

    | Campo            | descrizione                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Data di inizio        | Seleziona la data di inizio per il report.                                                                                               |
    | Data di fine          | Seleziona la data di fine per il report.                                                                                                 |
    | Genera file    | Imposta questa opzione su **Sì** per generare un file .txt.                                                                                 |
    | Nome file        | Inserisci il nome del file .txt per il tuo report Intrastat.                                                                          |
    | Genera report  | Imposta questa opzione su **Sì** per generare un file .xml.                                                                                |
    | Nome file report | Immetti il nome richiesto.                                                                                                            |
    | Solo correzioni | Imposta questa opzione su **Sì** per dichiarare solo le correzioni. Impostalo su **No** per dichiarare sia le normali operazioni che le correzioni.         |
    | Direzione        | Seleziona **Arrivi** per un report sugli arrivi intracomunitari. Seleziona **Spedizioni** per un report sulle spedizioni intracomunitarie. |

4. Seleziona **OK** per chiudere la finestra di dialogo **Report Intrastat**.
5. Nella finestra di dialogo **Parametri report elettronico**, nella scheda dettaglio **Parametri**, nel campo **Livello report** , seleziona il livello del report. Il livello del report può essere **1 - risposta statistica**, **4 - dichiarazione fiscale** o **5 - risposta statistica alla spedizione e dichiarazione fiscale**.

## <a name="example"></a>Esempio

L'esempio seguente mostra come impostare Intrastat francese e creare il report DEB. Utilizza la persona giurdica **DEMF**.

### <a name="preliminary-setup"></a>Impostazioni preliminari

1. In [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), nella raccolta di risorse condivise scarica l'ultima versione delle seguenti configurazioni per la creazione di report elettronici per il formato della dichiarazione Intrastat:

    - Modello Intrastat
    - Report Intrastat
    - INTRACOM Intrastat (FR)

2. Imposta una gerarchia di prodotti:

    1. Vai a **Gestione informazioni sul prodotto** \> **Impostazioni** \> **Categorie e attributi** \> **Gerarchie di categorie**.
    2. Nella griglia seleziona **Intrastat**.
    3. Nel riquadro azioni, nella scheda **Gerarchia di categorie**, nel gruppo **Gestisci**, seleziona **Modifica**.
    4. Nel riquadro azioni seleziona **Nuovo nodo di categoria**.
    5. Nel campo **Nome**, immetti **Autres Libournais**.
    6. Nel campo **Codice** immetti **2204 21 42**.
    7. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-vat-ids"></a>Impostare gli ID IVA

#### <a name="set-up-vat-codes-for-your-company"></a>Impostare i codici IVA per la società

1. Vai a **Imposta** \> **Impostazione** \> **IVA** \> **Partite IVA**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Paese/Area geografica** seleziona **FRA**.
4. Il campo **Numero esenzione fiscale** immetti **MS123456**.
5. Vai a **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**, e seleziona **DEMF**.
6. Nella scheda dettaglio **Commercio estero e logistica** nella sezione **Intrastat** imposta i campi **Partita IVA esportazione** e **Partita IVA importazione** per il codice creato al passaggio 4.
7. Nella Scheda dettaglio **Ritenuta d'acconto** nel campo **Numero di registrazione fiscale** immetti **123456789**.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Impostare gli ID IVA per i partner commerciali

##### <a name="create-a-registration-type-for-the-company-code"></a>Creare un tipo di registrazione per il codice società

1. Vai a **Amministrazione organizzazione** \> **Rubrica globale** \> **Tipi di registrazione** \> **Tipi di registrazione**.
2. Nel riquadro azioni selezionare **Nuovo** per creare un tipo di registrazione per la partita IVA.
3. Nella finestra di dialogo **Immetti dettagli tipo di registrazione**, nel campo **Nome**, immetti **ID IVA**.
4. Nel campo **Paese/Area geografica** seleziona **DEU**.
5. Seleziona **Crea**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Effettuare la corrispondenza tra il tipo di registrazione e la categoria di registrazione

1. Vai a **Amministrazione organizzazione** \> **Rubrica globale** \> **Tipi di registrazione** \> **Categorie di registrazione**.
2. Nel riquadro azioni, seleziona **Nuovo** per creare un collegamento tra il tipo di registrazione e la categoria di registrazione.
3. Per il tipo di registrazione **ID IVA** del paese **DEU**, seleziona la categoria di registrazione **ID IVA**.

##### <a name="set-up-the-customers-vat-registration-number"></a>Impostare il numero di registrazione IVA del cliente

1. Selezionare **Contabilità clienti** \> **Clienti** \> **Tutti i clienti**.
2. Nella griglia seleziona **DE-016**.
3. Nel riquadro azioni, nella scheda **Cliente**, nel gruppo **Registrazione**, seleziona **ID registrazione**.
4. Nella scheda dettaglio **ID registrazione** seleziona **Aggiungi** per creare un ID registrazione.
5. Nel campo **Tipo di registrazione** seleziona **ID IVA**.
6. Nel campo **Numero di registrazione** immetti **DE9012**.
7. Nel riquadro azioni seleziona **Salva** e chiudi la pagina.
8. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **IVA**, seleziona **DE9012** nel campo **Numero esenzione fiscale**.

### <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. Vai a **Imposta** \> **Impostazione** \> **Commercio estero** \> **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella scheda dettaglio **Generale** nel campo **Codice transazione** seleziona **11**.
3. Nella scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **INTRACOM Intrastat (FR)**.
4. Nel campo **Mapping di formato report** seleziona **Report Intrastat**.
5. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.
6. Nel campo **Lavoratore** seleziona un record.
7. Nella scheda **Contatto**, nel campo **Telefono** inserisci il numero di telefono del contatto
8. Nel campo **Fax** inserisci il numero di fax del contatto.

### <a name="create-ngp-code"></a>Creare il codice NGP

1. Vai a **Imposta** \> **Impostazioni** \> **Commercio estero** \> **Codici NGP**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **NGP** immetti **8**'.
4. Nel campo **Nome descrizione** immetti **NGP 8**.
5. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-product-information"></a>Impostare le informazioni prodotto

1. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.
2. Nella griglia seleziona **D0001**.
3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **NGP** seleziona **8**.
4. Nel campo **Voce doganale** seleziona **2204 21 42**.
5. Nella sezione **Origine**, nel campo **Paese/Area geografica**, seleziona **FRA**.
6. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure** nel campo **Peso netto** immetti **2**.
7. Nel riquadro azioni seleziona **Salva** e chiudi la pagina.
8. Nella griglia seleziona **D0003**.
9. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **100 200 30**.
10. Nella sezione **Origine**, nel campo **Paese/Area geografica**, seleziona **DEU**.
11. Nella Scheda dettaglio **Gestione articoli** nella sezione **Misure** nel campo **Peso netto** immetti **5**.
12. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-regime-codes"></a>Impostare i codici di regime

1. Vai a **Imposta** \> **Impostazioni** \> **Commercio estero** \> **Procedura statistiche**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Procedura statistiche**, immetti **21**.
4. Nel campo **Testo 1** immetti **Codice regime 21**.

### <a name="change-the-site-address"></a>Modificare l'indirizzo del sito

1. Vai a **Gestione magazzino** \> **Impostazione** \> **Magazzino** \> **Siti**.
2. Nella griglia seleziona **1**.
3. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
4. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **FRA**.
5. Seleziona **OK**.
6. Vai a **Gestione magazzino** \> **Impostazioni** \> **Magazzino** \> **Magazzini** e seleziona un magazzino.
7. Nella Scheda dettaglio **Indirizzi** seleziona **Aggiungi**.
8. Nella finestra di dialogo **Nuovo indirizzo**, nel campo **Paese/area geografica**, seleziona **FRA**.
9. Nel campo **Città** seleziona **Bordeaux**.
10. Selezionare **OK** per chiudere la finestra di dialogo.

### <a name="set-up-a-transport-method"></a>Configurare un metodo di trasporto

1. Vai a **Imposta** \> **Impostazione** \> **Commercio estero** \> **Metodo di trasporto**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Trasporto**, immetti **3**.
4. Nel campo **Descrizione** immetti **Trasporto su strada**.

### <a name="assign-a-transport-mode-to-a-mode-of-delivery"></a>Assegnare una modalità di trasporto a una modalità di consegna

1. Vai ad **Approvvigionamento** \> **Impostazione** \> **Distribuzione** \> **Modalità di consegna**.
2. Nella griglia seleziona **50**.
3. Nella Scheda dettaglio **Commercio estero** nel campo **Trasporto**, seleziona **3**.

### <a name="create-a-sales-order-with-an-eu-customer-that-includes-the-new-product"></a>Creare un ordine di vendita con un cliente EU che includa il nuovo prodotto

1. Andare a **Contabilità clienti** \> **Ordini** \> **Tutti gli ordini cliente**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine cliente** nella sezione **Cliente** nel campo **Conto cliente** seleziona **DE-016**.
4. Nella sezione **Indirizzo** nel campo **Indirizzo di consegna** seleziona il segno più (**+**) per creare un indirizzo.
5. Nella finestra di dialogo **Nuovo indirizzo**, nel campo **Nome della descrizione**, immetti **Germania**.
6. Nel campo **Paese/Area geografica** seleziona **DEU**.
7. Selezionare **OK**.
8. Seleziona **OK** nella finestra di dialogo **Crea ordine cliente**.
9. Nella scheda dettaglio **Righe ordine cliente** nel campo **Codice articolo** seleziona **0001**.
10. Nella Scheda dettagli **Dettagli riga** nella scheda **Commercio estero** nel campo **Procedura statistiche** seleziona **21**.
11. Nel campo **Stato di origine** seleziona **AL**.
12. Nel riquadro azioni selezionare **Salva**.
13. Nella scheda **Intestazione** nella scheda dettaglio **Consegna** nel campo **Modalità di consegna** assicurati che sia selezionato **50**.
14. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
15. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**. Seleziona **OK** per registrare la fattura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Trasferire la transazione al giornale di registrazione Intrastat ed esaminare il risultato

1. Vai a **Imposta** \> **Dichiarazioni** \> **Commercio estero** \> **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**. Selezionare **OK**.
4. Ordina le transazioni per il campo **Data**. La prima transazione è la transazione risultante.

    ![La riga rappresenta l'ordine cliente nella pagina Intrastat.](media/intrastat_fr_1.png)

5. Seleziona la riga della transazione, quindi seleziona la scheda **Generale** per visualizzare maggiori dettagli.

    ![Dettagli dell'ordine cliente nella scheda Generale della pagina Intrastat.](media/intrastat_fr_2.png)

6. Nel riquadro azioni, seleziona **Output** \> **Report**.
7. Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data** seleziona il mese dell'ordine cliente creato.
8. Nella sezione **Opzioni di esportazione** imposta l'opzione **Genera file** su **sì**.
9. Nel campo **Nome file** immetti il nome richiesto.
10. Seleziona **OK** per chiudere la finestra di dialogo **Report Intrastat**.
11. Nella finestra di dialogo **Parametri report elettronico** , nella scheda dettaglio **Parametri** nel campo **Livello report** seleziona **5 - risposta statistica alla spedizione e dichiarazione fiscale** e rivedi il report.

    ![Report Intrastat Intracom sulle spedizioni.](media/intrastat_fr_3.png)

12. Esamina il report di Excel generato.

    ![Report Intrastat sulle spedizioni.](media/intrastat_fr_4.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
