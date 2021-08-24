---
title: Intrastat francese
description: Questo argomento contiene informazioni sulla creazione della dichiarazione Intrastat in Francia.
author: andosip
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: d38169d73caf93a0f81e832293916c9e54855a1848fe6ab409a670a4bf707b7c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713138"
---
# <a name="french-intrastat"></a>Intrastat francese

[!include[banner](../includes/banner.md)]

Le aziende in Francia che sono registrate per l'imposta sul valore aggiunto (IVA) e che commerciano con altri paesi dell'Unione Europea (UE), devono dichiarare lo scambio di beni e servizi da e verso la Francia. La dichiarazione di commercio di beni (DEB, Declaration d'Exchanges de Biens) è una combinazione dell'elenco vendite UE con il report Intrastat. È necessario inviare questo report mensilmente per tutte le vendite intracomunitarie di beni.

È possibile generare il report DEB in uno dei due formati di file elettronici disponibili: SAISUNIC 330 o INTRACOM.

La tabella seguente mostra i campi che sono inclusi nella dichiarazione Intrastat francese in formato SAISUNIC 330.

| **Campo**                   | **Livello report**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (semplificato)** | **1 (completo)** |
| Periodo di riferimento         | X                  | X            |
| Numero di dichiarazione       | X                  | X            |
| Numero riga                 | X                  | X            |
| Codice ISO paese (FR)       | X                  | X            |
| Codice complementare          | X                  | X            |
| Numero Siren                | X                  | X            |
| Codice IVA del cliente        | X                  | X            |
| Codice direzione              | X                  | X            |
| Tipo di transazione            | X                  | X            |
| Livello di obbligo            | X                  | X            |
| Codice voce doganale              |                    | X            |
| NGP nazionale                |                    | X            |
| Provincia (reparto)         |                    | X            |
| Natura della transazione       |                    | X            |
| Paese di origine      |                    | X            |
| Paese di origine - Importazioni |                    | X            |
| Destinazione finale - Esportazioni |                    | X            |
| Valore fattura               | X                  | X            |
| Valore statistico           |                    | X            |
| Peso netto                  |                    | X            |
| Unità supplementari            |                    | X            |
| Codice di trasporto              |                    | X            |

La tabella seguente mostra i campi che sono inclusi nella dichiarazione Intrastat francese in formato INTRACOM.

| **Campo**                   | **Livello report**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (semplificato)** | **1 (completo)** |
| Codice                        | X                  | X            |
| Numero di dichiarazione       | X                  | X            |
| Numero di riga              | X                  | X            |
| Siren                       | X                  | X            |
| Provincia (reparto)         |                    | X            |
| Codice di trasporto              |                    | X            |
| Paese di origine           |                    | X            |
| Natura della transazione       |                    | X            |
| Valore fattura               | X                  | X            |
| Modalità di consegna           |                    | X            |
| Tipo di transazione            | X                  | X            |
| Livello di obbligo            | X                  | X            |
| Codice voce doganale              |                    | X            |
| NGP nazionale                |                    | X            |
| Peso netto                  |                    | X            |
| Valore statistico           |                    | X            |
| Unità supplementari            |                    | X            |
| Paese di origine - Importazioni |                    | X            |
| Destinazione finale - Esportazioni |                    | X            |
| Codice IVA del cliente        | X                  | X            |
| Codice complementare          | X                  | X            |
| Periodo di riferimento         | X                  | X            |

### <a name="set-up-intrastat"></a>Impostare Intrastat

1.  In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), nella raccolta di risorse condivise scarica l'ultima versione delle seguenti configurazioni per la creazione di report elettronici per la dichiarazione Intrastat:

-   Modello Intrastat

-   Report Intrastat

-   INTRACOM Intrastat (FR)

-   SAISUNIC Intrastat (FR)

Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  In Dynamics 365 Finance, vai a **Imposta** &gt; **Impostazioni** &gt; **Commercio estero** &gt; **Parametri commercio estero** e segui questi passaggi:

    1.  Nella scheda **Intrastat** nella scheda dettaglio **Creazione di report elettronici** nel campo **Mapping di formato file** seleziona **Intrastat INTRACOM (FR)** o **Intrastat SAISUNIC (FR)**.

    2.  Nel campo **Mapping di formato report** seleziona **Report Intrastat**.

    3.  Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.

    4.  Nella scheda dettaglio **Generale** nel campo **Codice transazione** seleziona il codice che viene utilizzato per i trasferimenti di beni.

    5.  Nel campo **Nota di credito** seleziona il codice che viene utilizzato per i resi di merce.

    6.  Nel campo **Livello di obbligo per l'esportazione** immetti il livello di dettaglio per il report di esportazione. Il livello selezionato influisce sulle righe visualizzate nel report. Per ulteriori informazioni, vedi le tabelle all'inizio dell'argomento.

3.  Vai in **Amministrazione organizzazione** &gt; **Organizzazioni** &gt; **Persone giuridiche**, seleziona la tua azienda, quindi segui questi passaggi:

    1.  Nella scheda dettaglio **Numeri di registrazione**, nel campo **Codice NAF** inserisci il tuo codice NAF. Per ulteriori informazioni, vedi [Codici FR-00003 NAF e numeri Siret](tasks/fr-00003-naf-codes-siret-numbers.md).

    2.  Nella scheda dettaglio **Commercio estero e logistica** nella sezione **Intrastat** imposta i campi **Partita IVA esportazione** e **Partita IVA importazione**.

    3.  Nella Scheda dettaglio **Registrazione fiscale**, nel campo **Partita IVA**, immetti la partita IVA della società.

4.  Per specificare i codici NAF e i numeri di esenzione fiscale per i clienti, vai a **Contabilità clienti** &gt; **Clienti** &gt; **Tutti i clienti** e segui questi passaggi:

    1.  Seleziona un cliente.

    2.  Nella Scheda dettaglio **Fattura e consegna**, nella sezione **IVA**, nel campo **Numero esenzione fiscale** immetti il numero di esenzione fiscale del cliente.

    3.  Nella scheda dettaglio **Dati demografici di vendita** nel campo **Siret francese** immetti il numero Siret dell'azienda.

    4.  Nel campo **Codice NAF** immetti il codice NAF della società.

    5.  Ripeti questi passaggi per gli altri clienti.

5.  Per specificare i codici NAF e i numeri di esenzione fiscale per i fornitori, vai a **Contabilità fornitori** &gt; **Fornitori** &gt; **Tutti i fornitori** e segui questi passaggi:

    1.  Selezionare un fornitore.

    2.  Nella Scheda dettaglio **Fattura e consegna**, nella sezione **IVA**, nel campo **Numero esenzione fiscale** immetti il numero di esenzione fiscale del fornitore.

    3.  Nella scheda dettaglio **Dati demografici di acquisto** nel campo **Siret francese** immetti il numero Siret dell'azienda.

    4.  Nel campo **Codice NAF** immetti il codice NAF della società.

    5.  Ripeti questi passaggi per gli altri fornitori.

6.  Vai a **Imposta** &gt; **Impostazioni** &gt; **Commercio estero** &gt; **Compressione di Intrastat** e seleziona i campi da confrontare quando vengono riepilogati i dati Intrastat. Per Intrastat francese, seleziona **Procedura statistica**, **Stato di origine**, **Paese/area geografica di origine**, **Termini di consegna**, **Trasporto**, **Correzione**, **Paese/area geografica**, **Provincia di origine/destinazione**, **Direzione**, **Paese/area geografica del mittente**, **Stato del mittente**, **Stato**, **Codice transazione**, e **Voce doganale**.

7.  Vai a **Gestione magazzino** &gt; **Impostazioni** &gt; **Magazzino** &gt; **Magazzini**, seleziona un magazzino, quindi segui questi passaggi:

    1.  Nella Scheda dettaglio **Indirizzi**, seleziona **Aggiungi** o **Modifica**.

    2.  Nella finestra di dialogo, nel campo **Città**, seleziona la città del magazzino. Lo stato della città verrà utilizzato come provincia per il tuo report DEB.

### <a name="ngp-codes"></a>Codici NGP

Nel report DEB, la codificazione dei prodotti è composta dai seguenti elementi:

1.  Il codice CN8 a otto cifre che rappresenta la nomenclatura tariffaria e statistica dell'UE.

2.  Se applicabile, il codice articolo nazionale a una cifra Nomenclature Générale des Produits (NGP).

Nel 2021, il NGP si applica solo a tre tipi di prodotti:

-   Prodotti relativi a mucche, pecore e capre

-   Equipaggiamento militare

-   Vini francesi

È necessario impostare i codici NGP e assegnarli ai prodotti correlati. Il campo **NGP** viene quindi impostato automaticamente nella pagina **Giornale di registrazione Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Impostare un codice NGP

1.  Vai a **Imposta** &gt; **Impostazioni** &gt; **Commercio estero** &gt; **Codici NGP**.

2.  Nel riquadro azioni seleziona **Nuovo** per creare un codice NGP.

3.  Nel campo **NGP** immetti un codice a una cifra.

4.  Nel campo **Descrizione** immetti una descrizione per il codice.

#### <a name="assign-an-ngp-code-to-a-product"></a>Assegnare un codice NGP a un prodotto

1.  Selezionare **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Prodotti rilasciati**.

2.  Seleziona un prodotto nella griglia.

3.  Nella scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **NGP** seleziona il codice NGP appropriato.

## <a name="intrastat-journal"></a>Giornale di registrazione Intrastat

Vai a **Imposta** &gt; **Dichiarazioni** &gt; **Commercio** **estero** &gt; **Intrastat** per gestire le tue transazioni applicabili al commercio estero con i paesi dell'UE. Per ulteriori informazioni, vedere [Panoramica Intrastat](emea-intrastat.md).

La colonna **NGP** è specifica per la Francia. Mostra il codice NGP del prodotto. Se il codice NGP non è applicabile a un prodotto, viene visualizzato **0** (zero). È possibile regolare il codice NGP. Seleziona la transazione, e poi, nella scheda **Generale** nella sezione **Codici** nel campo **NGP** seleziona il codice NGP richiesto.

### <a name="intrastat-transfer"></a>Trasferimento Intrastat

Nella pagina **Intrastat**, nel riquadro azioni, puoi selezionare **Trasferisci** per trasferire automaticamente le informazioni sul commercio intracomunitario da ordini di vendita, fatture a testo libero, ordini di acquisto, fatture fornitore, ricevute di prodotti fornitore, fatture di progetto e ordini di trasferimento. Verranno trasferiti solo i documenti che hanno un paese dell'UE come paese o regione di destinazione (per le spedizioni) o consegna (per gli arrivi).

Poiché il report DEB è una combinazione dell'elenco vendite UE e del report Intrastat, include anche le transazioni *triangolari* in cui viene effettuata una consegna diretta da un paese dell'UE (parte A) a un altro paese dell'UE (parte C) e una persona giuridica francese (parte B) si trova nel mezzo dell'operazione triangolare.

### <a name="generate-a-deb-intrastat-report"></a>Generare un report DEB (Intrastat)

1.  Vai a **Imposta** &gt; **Dichiarazioni** &gt; **Commercio estero** &gt; **Intrastat**.

2.  Nel riquadro azioni, seleziona **Output** &gt; **Report**.

3.  Nella finestra di dialogo **Report Intrastat**, imposta i seguenti campi.

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

## <a name="example"></a>Esempio

L'esempio seguente mostra come impostare e lavorare con i codici NGP. Utilizza la persona giurdica **DEMF**.

1.  In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), nella raccolta di risorse condivise scarica l'ultima versione delle seguenti configurazioni per la creazione di report elettronici per il formato della dichiarazione Intrastat:

-   Modello Intrastat

-   Report Intrastat

-   INTRACOM Intrastat (FR)

2.  In Finance, imposta un codice transazione:

    1.  Vai a **Imposta** &gt; **Impostazioni** &gt; **Commercio estero** &gt; **Codici transazioni**.

    2.  Nel Riquadro azioni selezionare **Nuovo**.

    3.  Nel campo **Codice transazione** immetti **11**.

    4.  Nel campo **Nome**, immetti **Acquisto o vendita**.

    5.  Nel riquadro azioni selezionare **Salva**.

3.  Imposta una gerarchia di prodotti:

    1.  Vai a **Gestione informazioni sul prodotto** &gt; **Impostazioni** &gt; **Categorie e attributi** &gt; **Gerarchie di categorie**.

    2.  Nella griglia seleziona **Intrastat**. Quindi nel riquadro azioni, nella scheda **Gerarchia di categorie**, nel gruppo **Gestisci**, seleziona **Modifica**.

    3.  Nel riquadro azioni seleziona **Nuovo nodo di categoria**.

    4.  Nel campo **Nome**, immetti **Autres Libournais**.

    5.  Nel campo **Codice** immetti **2204 21 42**.

    6.  Nel riquadro azioni selezionare **Salva**.

4.  Vai a **Imposta** &gt; **Impostazioni** &gt; **Commercio estero** &gt; **Parametri commercio estero**, e segui questi passaggi:

    1.  Nella scheda **Intrastat** nella scheda dettaglio **Generale** nel campo **Codice transazione** seleziona **11**.

    2.  Nella scheda dettaglio **Creazione di report elettronici**, nel campo **Mapping di formato file**, seleziona **INTRACOM Intrastat (FR)**.

    3.  Nel campo **Mapping di formato report** seleziona **Report Intrastat**.

    4.  Nella scheda dettaglio **Gerarchia di codici di voce doganale**, nel campo **Gerarchia di categorie** seleziona **Intrastat**.

5.  Imposta un codice NGP:

    1.  Vai a **Imposta** &gt; **Impostazioni** &gt; **Commercio estero** &gt; **Codici NGP**.

    2.  Nel Riquadro azioni selezionare **Nuovo**.

    3.  Nel campo **NGP** immetti **8**'.

    4.  Nel campo **Nome descrizione** immetti **NGP 8**.

    5.  Nel riquadro azioni selezionare **Salva**.

6.  Assegna il codice NGP a un prodotto:

    1.  Selezionare **Gestione informazioni sul prodotto** &gt; **Prodotti** &gt; **Prodotti rilasciati**.

    2.  Nella griglia seleziona **0001**.

    3.  Nel campo **NGP** della Scheda dettaglio **Commercio estero**, seleziona **8**.

    4.  Nel campo **Voce doganale** seleziona **2204 21 42**.

    5.  Nel riquadro azioni selezionare **Salva**.

7.  Crea un ordine di vendita che includa il nuovo prodotto:

    1.  Andare a **Contabilità clienti** &gt; **Ordini** &gt; **Tutti gli ordini cliente**.

    2.  Nel Riquadro azioni selezionare **Nuovo**.

    3.  Nella finestra di dialogo **Crea** **ordine** **cliente** nella sezione **Cliente** nel campo **Conto** **cliente** seleziona **100001**.

    4.  Nella sezione **Indirizzo** nel campo **Indirizzo di consegna** seleziona il segno più (**+**) per creare un indirizzo.

    5.  Nella finestra di dialogo **Nuovo indirizzo**, nel campo **Nome della descrizione**, immetti **Germania**.

    6.  Nel campo **Paese/Area geografica** seleziona **DEU**.

    7.  Selezionare **OK**.

    8.  Seleziona **OK** nella finestra di dialogo **Crea ordine cliente**.

    9.  Nella scheda dettaglio **Righe** **ordine cliente** nel campo **Codice articolo** seleziona **0001**.

    10. Nel riquadro azioni selezionare **Salva**.

    11. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.

    12. Nella finestra di dialogo **Registrazione fattura**, nella scheda dettaglio **Parametri** nella sezione **Parametro** nel campo **Quantità** seleziona **Tutto**. Seleziona **OK** per registrare la fattura.

8.  Crea il report DEB:

    1.  Vai a **Imposta** &gt; **Dichiarazioni** &gt; **Commercio estero** &gt; **Intrastat**:

    2.  Nel riquadro azioni seleziona **Trasferisci**.

    3.  Nella finestra di dialogo **Intrastat (trasferimento)** nella sezione **Parametri** imposta l'opzione **Fattura cliente** su **sì**. Selezionare **OK**.

    4.  Ordina le transazioni per il campo **Data**. La prima transazione è la transazione risultante. Il campo **NGP** viene impostato automaticamente.

    5.  Nel riquadro azioni, seleziona **Output** &gt; **Report**.

    6.  Nella finestra di dialogo **Report Intrastat** nella scheda dettaglio **Parametri** nella sezione **Data** seleziona il mese dell'ordine cliente creato.

    7.  Nella sezione **Opzioni di esportazione** imposta l'opzione **Genera file** su **sì**.

    8.  Nel campo **Nome file** immetti il nome richiesto.

    9.  Seleziona **ok** e rivedi il report.

