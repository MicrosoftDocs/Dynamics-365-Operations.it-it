---
title: Report Modello 770
description: In questo argomento vengono fornite informazioni sul Modello 770 per l'Italia.
author: ilkond
manager: AnnBe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Taxreport770Table_IT
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 07d09512ef612b41bf527b74496fa440f23851fc
ms.openlocfilehash: 257dd7f989eb16c5d7380af8df3887bf0f4650f6
ms.contentlocale: it-it
ms.lasthandoff: 02/14/2018

---

# <a name="modello-770"></a>Modello 770

[!INCLUDE [banner](../includes/banner.md)]

In questo argomento viene descritto come installare, creare ed esportare il Modello 770 utilizzato per dichiarare le ritenute d'acconto.

Il Modello 770 è un report annuale che fornisce informazioni sulle ritenute d'acconto operate da una società quando questa paga terzisti e lavoratori autonomi. Le società rimettono le ritenute d'acconto direttamente al governo durante l'anno. Quindi, a fine anno, la società crea e trasmette il Modello 770. Questo report dettaglia i pagamenti a favore di ciascun terzista e lavoratore autonomo e le imposte che sono state trattenute nei pagamenti. Il Modello 770 contiene informazioni solo sui terzisti e i lavoratori autonomi per i quali sono state trattenute le imposte nei pagamenti.

## <a name="general-settings-that-are-required-for-the-model-770-report"></a>Impostazioni generali richieste per il Modello 770
Completare le attività seguenti prima di creare un Modello 770:

- Impostare i codici, i gruppi, i limiti e i valori di ritenuta d'acconto. Per ulteriori informazioni, vedere [Impostare i codici di ritenuta d'acconto](../general-ledger/tasks/set-up-withholding-tax.md) e [Ritenuta d'acconto per l'Italia](emea-ita-withholding-tax.md).
- Pagare le fatture fornitori e trattenere le imposte nei pagamenti.
- Impostare i libri IVA italiani. Per ulteriori informazioni, vedere [Libri IVA italiani](emea-ita-fiscal-books.md).

## <a name="set-up-address-information"></a>Impostare le informazioni sull'indirizzo
Utilizzare la pagina **Impostazione indirizzo** per impostare il codice paese, il codice dell'area e dello stato e i codici di comune e provincia per un terzista o un lavoratore autonomo da includere nel Modello 770. È necessario impostare le informazioni relative all'indirizzo per tutti i terzisti e i lavoratori autonomi per i quali trattenere le imposte dai pagamenti. Per informazioni sui codici indirizzo, vedere le istruzioni del governo italiano pubblicate per il Modello 770 sul sito Web dell'[Agenzia delle Entrate](http://www.agenziaentrate.gov.it).

1. Selezionare **Amministrazione organizzazione** > **Indirizzi** > **Impostazione indirizzo**.
2. Selezionare **Paese**, quindi nel campo **Paese**, immettere il codice di due lettere dell'organizzazione internazionale per la standardizzazione (ISO, International Organization for Standardization) per l'Italia.
3. Selezionare **Stato/regione o provincia** e quindi immettere il codice identificativo dello stato e il codice regione IT a due cifre per i terzisti o i lavoratori autonomi.

    > [!NOTE]
    > Utilizzare il codice stato numerico, non l'abbreviazione dello stato.

4. Selezionare **Provincia**, quindi nel campo **Codice provincia IT**, immettere il codice provincia a due lettere ISO per i terzisti o i lavoratori autonomi.
5. Selezionare **Città** e quindi, nel campo **Codice comune italiano**, immettere il codice provincia italiano a quattro caratteri per i terzisti o i lavoratori autonomi. Il codice comune è costituito da una lettera e tre numeri.
6. Selezionare il collegamento **Codici postali (CAP)**, quindi nel campo **Codici postali (CAP)**, immettere il codice di avviamento postale italiano.

## <a name="set-up-a-fiscal-code-for-the-legal-entity"></a>Impostare un codice fiscale per la persona giuridica
Il codice fiscale viene incluso nel Modello 770 per consentire al governo italiano di identificare la persona giuridica.

1. Selezionare **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Nella Scheda dettaglio **Numeri di registrazione**, nel campo **Codice fiscale** per l'Italia, immettere il codice fiscale per la persona giuridica.

## <a name="set-up-a-number-sequence-for-the-model-770-report"></a>Impostare una sequenza numerica per il report Modello 770
Utilizzare la pagina **Parametri di contabilità generale** per impostare una sequenza numerica per il Modello 770.

1. Selezionare **Contabilità generale** > **Impostazione contabilità generale** > **Parametri di contabilità generale**.
2. Selezionare il collegamento **Sequenze numeriche**, quindi nel campo **Codice sequenza numerica**, selezionare una sequenza numerica per il riferimento **ID modello**.

## <a name="set-up-related-information-for-vendors"></a>Impostare informazioni correlate per i fornitori
1. Selezionare **Contabilità fornitori** > **Fornitori** > **Tutti i fornitori** e quindi selezionare il fornitore di interesse.
2. Nella Scheda dettaglio **Fattura e consegna**, nel campo **Codice fiscale** per l'Italia, immettere il codice fiscale del fornitore.

    > [!NOTE]
    > Per i lavoratori autonomi per i quali il pagamento dell'IVA non è obbligatorio, immettere il codice fiscale della persona fisica. Se un fornitore deve pagare l'IVA, immettere il numero di partita IVA fornito dall'ufficio IVA italiano come codice fiscale del fornitore.

3. Nella Scheda dettaglio **Fattura e consegna** selezionare la casella di controllo **Calcola ritenuta d'acconto**. Selezionare un gruppo di ritenute d'acconto per attivare il calcolo quando viene immesso un pagamento.
4. Nella Scheda dettaglio **Dati demografici acquisti** selezionare la provincia in cui è nato il fornitore.
5. Se il fornitore è un erede della società, selezionare la casella di controllo **Erede**.

## <a name="set-up-electronic-reporting-parameters"></a>Impostare i parametri per la creazione di report elettronici
Scaricare le *versioni effettive* delle configurazioni delle dichiarazioni elettroniche seguenti:

- **Modello dati:** modello dei report fiscali italiani
- **Formato:** Modello 770 (IT)
 
Per istruzioni su come scaricare le configurazioni dei report elettronici, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="create-and-export-the-model-770-report"></a>Creare ed esportare il Modello 770
Il Modello 770 esporta le informazioni in un file ASCII che sarà inviato agli uffici tributari. Il nome del file ASCII deve essere \[partita IVA della società\] 77S\[*AA*\].77s, dove **AA** corrisponde alle ultime due cifre dell'anno di riferimento. Per ulteriori informazioni sul completamento e la presentazione del Modello 770, vedere il sito Web dell'[Agenzia delle Entrate](http://www.agenziaentrate.gov.it).

1. Selezionare **Imposta** > **Richieste di informazioni e report** > **Report ritenuta d'acconto** > **Ritenuta d'acconto - Modello 770**.
2. Creare un nuovo report Il report viene numerato in base alla sequenza numerica impostata per il riferimento **ID modello** nella pagina **Parametri di contabilità generale**.
3. Nel campo **Anno di presentazione** immettere l'anno di registrazione delle imposte. Ad esempio, se il report è relativo all'anno fiscale 2016 immettere **2017**. Il valore predefinito è l'anno di calendario corrente.
4. Nel campo **Mapping formato report** selezionare la configurazione di formato correlata preliminare scaricata in **Creazione di report elettronici**.
5. Nella Scheda dettaglio **Informazioni report**, nel campo **Codice ATECOFIN**, immettere il codice ATECOFIN della società. Questo codice viene definito nella pagina **Libri IVA italiani**.
6. Nel campo **Tipo di dichiarazione**, selezionare il tipo di dichiarazione del Modello 770:

    - **Integrativa** - È possibile compilare e inviare un nuovo report se è già stato inviato un report che richiede alcune correzioni.
    - **Correttiva** - Il report che si sta creando è una correzione di un report precedente.
    - **Originale** - Il Modello 770 è un report originale.

7. Nel campo **Evento eccezionale** selezionare qualsiasi evento eccezionale definito preliminarmente che la società ha dovuto affrontare nell'anno fiscale.
8. Nel campo **Stato** selezionare lo stato operativo della società:

    - **Regime normale** - La società opera a regime normale. Questa opzione è selezionata per impostazione predefinita.
    - **In liquidazione** - La società è in liquidazione.
    - **In fallimento** - La società è in fallimento. Se si seleziona questa opzione, diventa disponibile il campo **Data fallimento**.
    - **Attività chiusa** - le attività operative della società sono chiuse.

9. Nel campo **Situazione** selezionare il tipo di periodo fiscale:

    - **Periodo fiscale normale** - Il report si riferisce al solito periodo fiscale. Questa opzione è selezionata per impostazione predefinita.
    - **Periodo fiscale liquidazione** - Il report si riferisce al periodo fiscale in cui la società era in liquidazione.
    - **Periodo fiscale dopo il fallimento** - Il report si riferisce al periodo fiscale dopo che la società è stata iscritta al fallimento.
    - **Periodo fiscale al termine della liquidazione** - Il report si riferisce al periodo fiscale quando è terminata la liquidazione della società.
    - **Periodo fiscale trasformazione IRES** - Il report si riferisce al periodo fiscale specificato dall'Imposta sul Reddito delle Società (IRES) o imposta sul reddito aziendale, durante il quale la società ha subito una trasformazione.

10. Nel campo **Commenti editoriali** selezionare la sezione per cui la società deve presentare la ritenuta d'acconto.

    > [!NOTE] 
    > La sezione predefinita è la Sezione II. Selezionare una sezione in base alle istruzioni che il governo italiano ha pubblicato per il Modello 770 sul sito Web dell'[Agenzia delle Entrate](http://www.agenziaentrate.gov.it).

11. Nel campo **Tipo di dichiarante**, specificare il tipo di dichiarante che invia la dichiarazione fiscale all'ufficio tributario:

    - **Registrazione per la stessa persona giuridica** - Si invia il Modello 770 per la stessa persona giuridica per la quale è stata eseguita la transazione ritenuta d'acconto.
    - **Registrazione per un'altra persona giuridica** - Si invia il Modello 770 per conto di un'altra persona giuridica.
    - **Registrazione attraverso il centro di assistenza fiscale (CAF)** - Il Modello 770 viene registrato tramite il centro di assistenza fiscale (CAF).

12. A seconda del valore selezionato nel campo **Tipo di dichiarante**, completare i seguenti campi correlati: **Codice fiscale**, **Numero iscrizione CAF**, **Obbligo CAF**, **Codice fiscale CAF** e **Data di trasmissione CAF**.
13. Nel campo **Firmatario**, selezionare il dipendente che ha firmato il report per conto della società.
14. Nel campo **Ruolo** selezionare il ruolo del dipendente.
15. Nel campo **Prima data nel ruolo** selezionare la data in cui al dipendente è stato assegnato il ruolo selezionato nel campo **Ruolo**.
16. Completare i seguenti campi per specificare i dettagli del firmatario: **Codice fiscale firmatario**, **Provincia di nascita** e **Città o paese straniero di nascita**.
17. Se il dipendente è cittadino straniero selezionare la casella di controllo **Residente estero**.
18. Se la casella di controllo **Residente estero** è selezionata, completare i campi seguenti per specificare i dettagli del dipendente con nazionalità estera: **Paese**, **Stato/regione e provincia esteri**, **Luogo di residenza**, **Indirizzo estero** e **Codice fiscale estero**.
 
    > [!NOTE] 
    > Questi campi sono disponibili solo se è stata selezionata la casella di controllo **Residente estero**.

19. Nella Scheda dettaglio **Indirizzi** immettere i dettagli dell'indirizzo postale e dell'indirizzo fiscale.
20. Nella Scheda dettaglio **Transazioni ritenuta d'acconto**, selezionare **Trasferimento** per trasferire il pagamento fornitore e le transazioni di ritenuta al Modello 770. Verificare le transazioni rispetto ai record e il report **Ritenuta d'acconto - Report annuale**.
21. Selezionare **Convalida** per convalidare i dati impostati per i fornitori e la società.
22. È possibile utilizzare il pulsante **Reimposta** per reimpostare i valori in tutte le schede.
23. Selezionare **Esporta**, quindi nella pagina **Esporta**, nel campo **Nome file**, specificare il nome file compresso per scaricare. Il file compresso contiene il Modello 770 come file ASCII.
24. Selezionare la casella di controllo **Esportazione finale** per avviare il processo di importazione ignorando la logica di convalida nello strumento di importazione del governo. È inoltre possibile selezionare questa casella di controllo se si utilizza un report inviato in precedenza che è stato rifiutato ma che si considera corretto e completo in termini di informazioni disponibili pubblicate sul sito Web dell'[Agenzia delle Entrate](http://www.agenziaentrate.gov.it).
25. Selezionare **OK** per esportare il Modello 770.

