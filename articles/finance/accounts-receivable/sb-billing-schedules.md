---
title: Creare i programmi di fatturazione
description: In questo articolo viene descritto come creare, eliminare e modificare programmi di fatturazione.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 1248799f92dc6cbce8528a53cc8a3012d2a67b3c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903394"
---
# <a name="create-billing-schedules"></a>Creare i programmi di fatturazione

[!include [banner](../includes/banner.md)]

Nella pagina **Programma di fatturazione**, puoi creare, eliminare o modificare programmi di fatturazione. Puoi anche esaminare l'elenco dei programmi di fatturazione. Quando crei un programma di fatturazione, i valori predefiniti dello stesso sono determinati dal gruppo di fatturazione ad esso associato. Ulteriori informazioni sono impostate nella pagina **Parametri di fatturazione ricorrente di contratti**.

## <a name="create-a-billing-schedule"></a>Creare un programma di fatturazione

Per creare un programma di fatturazione, attieniti a questa procedura.

1. Nella pagina **Programma di fatturazione**, seleziona **Nuovo**.
2. Nella finestra di dialogo **Crea programma di fatturazione**, nel campo **Gruppo programmi di fatturazione**, seleziona un gruppo di programmi di fatturazione.
3. Nel campo **Conto cliente** seleziona un conto cliente.
4. Nel campo **Data d'inizio**, seleziona la data di inizio, quindi, nel campo **Numero di periodi**, immetti il numero di periodi. Il campo **Data di fine** viene aggiornato in base al numero di periodi immessi. Se aggiorni il campo **Data di fine fatturazione**, il campo **Numero di periodi** viene aggiornato a **0** (zero).
5. Seleziona **OK**.
6. Nella pagina **Programma di fatturazione**, nella scheda **Generale**, nel campo **Descrizione**, immetti una descrizione del programma di fatturazione.
7. Nel campo **Modello fasi**, seleziona un modello di fasi per **Fatturazione a fasi**.

I campi come **Conto fattura** e **Codice valuta** sono aggiornati con le informazioni del cliente.

I campi **Frequenza di fatturazione** e **Intervallo di fatturazione** vengono impostati automaticamente, in base al gruppo di programmi di fatturazione selezionato.

8. Per creare fatture distinte, imposta l'opzione **Fattura separatamente** su **Sì**.
9. Per rinnovare automaticamente un programma di fatturazione dopo il periodo di fatturazione finale, impostare l'opzione **Rinnova automaticamente** su **Sì**, quindi imposta il campo **Righe da aggiungere per rinnovo**.

I campi **Parametri** vengono impostati automaticamente, in base ai valori della pagina **Parametri di fatturazione ricorrente di contratti**.

10. Per ripartire l'importo di un programma di fatturazione, imposta l'opzione **Ripartisci periodi parziali** su **Sì**.
11. Per allineare le righe dei dettagli del programma di fatturazione con la fine di un mese, imposta l'opzione **Allinea a mese** su **Sì**.
12. Nei campi **Data di inizio contratto** e **Data di fine contratto**, immetti le date di inizio e di fine del contratto. Queste date sono solo a scopo informativo.

Il campo **Pagamento** mostra le informazioni di pagamento del cliente dal cliente. Quando un articolo è sospeso o terminato, le informazioni di pagamento non possono essere modificate.

> [!NOTE]
> Quando consolidi le fatture per articolo, il valore dei campi **Termini di pagamento**, **Metodo** e **Programma di fatturazione** devono corrispondere. In caso contrario, le fatture non possono essere consolidate.

13. Nella scheda **Indirizzo**, puoi esaminare e aggiornare i campi **Indirizzo di consegna** e **Indirizzo di fatturazione**.
14. Nella scheda **Informazioni contatto**, è possibile associare un account utente finale al programma di fatturazione.
15. Nei campi **Informazioni di contatto**, puoi immettere un contatto, un indirizzo e-mail e un indirizzo Internet.
16. Per tenere traccia delle informazioni sulla commissione del partner, imposta i campi **Conto partner** e **Tasso di commissione partner**. Questi campi sono solo a scopo informativo.
17. Nella scheda **Totale**, è possibile visualizzare i vari totali che calcolati per il programma di fatturazione.
18. Nella scheda **Sospensione**, puoi visualizzare le informazioni di controllo su quando il programma di fatturazione è stato sospeso quando la sospensione è stata rimossa.
19. Nella scheda **Terminazione**, è possibile visualizzare una cronologia delle terminazioni applicate al programma di fatturazione o rimosse dallo stesso.
20. Seleziona **Salva**.
21. Nella Scheda dettaglio **Righe programma di fatturazione**, seleziona **Aggiungi riga**.
22. Nel campo **Numero articolo** seleziona il numero di articolo. Se l'articolo aggiunto è un articolo padre in una ripartizione dei ricavi, le righe vengono aggiornate automaticamente con gli articoli figlio. Puoi modificare solo l'articolo principale in una ripartizione dei ricavi. Tutti gli articoli figlio vengono quindi aggiornati di conseguenza.
23. Nel campo **Tipo di articolo** seleziona il tipo di articolo.
24. Aggiorna le date di inizio e di fine.
25. Prima della creazione delle fatture, puoi modificare la frequenza di fatturazione aggiornando il campo **Frequenza di fatturazione**. Dopo aver creato la prima fattura per il programma di fatturazione, la frequenza di fatturazione non può essere modificata.
26. Nel campo **Unità** selezionare l'unità di misura per l'articolo.
27. Nel campo **Metodo di determinazione prezzo**, seleziona il metodo di determinazione del prezzo per l'articolo.

Il campo **Prezzo unitario** viene impostato automaticamente dall'inventario. Tuttavia, puoi aggiornarlo se modifichi il metodo di determinazione del prezzo in **Flat**.

## <a name="remove-a-line-item"></a>Rimuovere un articolo

Per rimuovere un articolo da un programma di fatturazione, attieniti alla seguente procedura.

1. Nella pagina **Programma di fatturazione**, nel campo **Numero di programma**, seleziona il numero del programma di fatturazione da modificare.
2. Nella Scheda dettaglio **Righe programma di fatturazione**, seleziona la voce da eliminare, quindi seleziona **Rimuovi**.
3. Seleziona **Salva**.

Il resto di questo articolo descrive le azioni e i dettagli disponibili per le righe nella Scheda dettaglio **Righe programma di fatturazione**.

## <a name="billing-schedule-line-actions"></a>Azioni delle righe del programma di fatturazione

I pulsanti nella Scheda dettaglio **Righe programma di fatturazione** ti consente di applicare azioni a singole righe+.

| Pulsante | Description |
|--------|-------------|
| Aggiungi riga | Consente di aggiungere una riga al programma di fatturazione. |
| Aggiungi da elenco articoli | Consente di aggiungere più articoli a un programma di fatturazione selezionandoli in un elenco. |
| Rimuovi | <p>Consente di rimuovere la riga selezionata dal programma di fatturazione.</p><p>Per gli articoli che fanno parte di una ripartizione dei ricavi, puoi rimuovere solo l'articolo padre. Tutti gli articoli figlio associati vengono quindi rimossi automaticamente.</p> |
| Visualizza dettagli di fatturazione | Consente di visualizzare i dettagli della fatturazione. |
| Termina | <p>Consente di terminare le righe selezionate. Questo pulsante è disponibile solo quando lo stato delle righe selezionate è **Attivo**.</p><p>Per gli articoli che fanno parte di una ripartizione dei ricavi, puoi terminare solo l'articolo padre.</p> |
| Rimuovi terminazione | <p>Consente di rimuovere la terminazione dalla righe selezionate. Questo pulsante è disponibile solo quando lo stato delle righe selezionate è **Terminata**.</p><p>Per gli articoli che fanno parte di una ripartizione dei ricavi, puoi rimuovere la terminazione solo dall'articolo padre.</p> |
| Metti in attesa | <p>Consente di selezionare i dettagli per sospendere la riga selezionata.</p><p>Per gli articoli che fanno parte di una ripartizione dei ricavi, puoi sospendere solo l'articolo padre.</p> |
| Rimuovi attesa | <p>Consente di rimuovere la sospensione dalla riga selezionata.</p><p>Per gli articoli che fanno parte di una ripartizione dei ricavi, puoi rimuovere la sospensione solo dall'articolo padre.</p> |
| Riassegnazione e sconto | Questo pulsante non è disponibile per gli articoli che fanno parte di una ripartizione dei ricavi, ad eccezione degli articoli padre dove tale ripartizione utilizza il metodo di assegnazione **Importo zero**. |
| Differimenti | <p>Consente di immettere le opzioni di differimento per la riga selezionata.</p><p>Questo pulsante non è disponibile per gli articoli padre in una ripartizione dei ricavi.</p> |
| Allocazione fasi | <p>Consente di esaminare e aggiornare le informazioni sull'allocazione delle fasi per la riga selezionata.</p><p>Questo pulsante è disponibile solo quando l'articolo del programma di fatturazione è un articolo fase.</p> |
| Supporto e rinnovo | <p>Consente di esaminare e aggiornare le informazioni di supporto e rinnovo per la riga selezionata.</p><p>Questo pulsante è disponibile solo quando l'articolo del programma di fatturazione è un articolo di supporto o rinnovo.</p> |
| Visualizza dimensioni | Mostra o nasconde le colonne delle dimensioni visualizzate nella griglia **Righe programma di fatturazione**. |
| Calcola prezzo unitario | <p>Consente di calcolare il prezzo unitario dell'articolo, di modo che il cliente possa pagare l'importo del contratto a rate (ad esempio, giornaliere, mensili, trimestrali, semestrali o annuali). È possibile selezionare il prezzo del contratto e la frequenza del prezzo.</p><p>È possibile visualizzare un audit trail delle modifiche: il prezzo e la frequenza del vecchio contratto, il prezzo e la frequenza del nuovo contratto, l'utente che ha apportato la modifica e la data e l'ora della modifica.</p> |
| Data di allineamento | <p>Specifica la data di allineamento degli articoli di rinnovo.</p><p>Se selezioni un gruppo di articoli nel campo **Gruppo di articoli**, tutti gli articoli utilizzano la data di allineamento del primo articolo nel gruppo di articoli nel programma di fatturazione. Se il campo **Gruppo di articoli** è vuoto, puoi specificare una data di allineamento da utilizzare per tutti gli articoli.</p><p>Questo pulsante è disponibile solo quando il campo **Frequenza di fatturazione** è impostato su **Annuale**.</p> |
| Ricavi non fatturati | <p>Consente di impostare l'articolo per utilizzare la funzionalità ricavi non fatturati. Puoi quindi specificare i conti dei ricavi non fatturati e degli sconti non fatturati per l'articolo.</p><p>Questo pulsante è disponibile solo per gli articoli in cui il campo **Tipo di articolo** è impostato su **Standard**. Non è disponibile per i programmi di fatturazione esistenti o per le righe di programma di fatturazione in cui la fattura è già stata creata.</p> |
| Aggiungi suddivisione ricavi figlio | <p>Consente di selezionare un articolo da aggiungere all'ordine cliente.</p><p>Questo pulsante è disponibile solo per articoli padre in una ripartizione dei ricavi.</p> |
| Opzioni di determinazione prezzo avanzata | Consente di modificare le opzioni di determinazione del prezzo per un articolo. |

## <a name="billing-schedule-line-details"></a>Dettagli delle righe del programma di fatturazione

Quando selezioni una riga nella Scheda dettaglio **Righe programma di fatturazione**, puoi visualizzare dettagli specifici per quella riga. Questi dettagli sono divisi tra varie schede.

### <a name="general-tab"></a>Scheda Generale

Le seguenti informazioni sono disponibili nella scheda **Generale**.

| Campo o sezione | Description |
|------------------|-------------|
| Uso | <p>Questa sezione fornisce informazioni sugli articoli di utilizzo. Include i seguenti campi:</p><ul><li>**Identificatore di utilizzo** – L'identificatore del contatore o dell'articolo di utilizzo.</li><li>**Opzione di lettura** – L'opzione di lettura dell'utilizzo: **Lettura** o **Consumo**.</li><li>**Consumo stimato** – Specificare il consumo stimato per un articolo di utilizzo con periodi in cui la fattura non è stata creata. Nella pagina **Dettaglio fatturazione**, puoi esaminare le righe dei dettagli di fatturazione per il consumo stimato.</li></ul> |
| Riferimenti esterni\* | Questa sezione contiene i campi **Esterno** e **Numero di riga**, dove puoi specificare informazioni di riferimento esterne. |
| Punto cardine | <p>Questa sezione fornisce informazioni su articoli cardine. Include il campo **Data di completamento stimata**, che mostra la data di completamento dell'articolo.</li></ul> |
| Testo | Un commento per la riga. Il testo viene tradotto nella lingua predefinita del cliente o della persona giuridica. |
| Gruppo di articoli | Il gruppo di articoli dell'articolo. |
| Data di allineamento | La data di allineamento del programma di fatturazione. |

\* Quando consolidi le fatture per articolo nella pagina **Genera fattura**, i campi **Riferimento esterno** devono corrispondere. Se anche un solo carattere è diverso, gli articoli non verranno consolidati nella fattura. Nessun controllo di convalida viene eseguito nei campi nella sezione **Riferimento esterno** e il valore nel campo **Numero di riga** deve essere un numero intero positivo.

### <a name="address-tab"></a>Scheda Indirizzo

Le seguenti informazioni sono disponibili nella scheda **Indirizzo**.

| Campo | Description |
|-------|-------------|
| Indirizzo di consegna | <p>Seleziona l'indirizzo di consegna per l'articolo. L'indirizzo di consegna predefinito è l'indirizzo di consegna principale nella Scheda dettaglio **Indirizzo**.</p><p>Quando modifichi l'indirizzo, puoi selezionare le seguenti opzioni relativi agli indirizzi:</p><ul><li>**Indirizzi** – Seleziona un indirizzo per il cliente corrente.</li><li>**In uso** – Seleziona un indirizzo correntemente utilizzato per il cliente corrente.</li><li>**Altro indirizzo** – Seleziona un indirizzo per qualsiasi record cliente.</li></ul><p>Per gli articoli che utilizzano la ripartizione dei ricavi, puoi modificare solo l'indirizzo dell'articolo padre. L'indirizzo degli articoli figlio corrisponde all'indirizzo del padre e non può essere modificato separatamente.</p> |
| Indirizzo di fatturazione | <p>Seleziona l'indirizzo di consegna per l'articolo. L'indirizzo di consegna predefinito è l'indirizzo di consegna principale nella Scheda dettaglio **Indirizzo**. Puoi modificare l'indirizzo secondo le tue esigenze, in base allo scopo degli indirizzi disponibili:</p><ul><li>Se nessuno degli indirizzi ha lo scopo **Fattura**, l'indirizzo di fatturazione predefinito è l'indirizzo principale del cliente, indipendentemente dallo scopo.</li><li>Se uno o più indirizzi hanno lo scopo **Fattura**, l'indirizzo di fatturazione predefinito è l'indirizzo inserito più di recente.</li><li>Se uno o più indirizzi hanno lo scopo **Fattura** e uno degli indirizzi di fatturazione è impostato come indirizzo principale, l'indirizzo di fatturazione predefinito è l'indirizzo con lo scopo **Fattura** ed è impostato come indirizzo principale.</li><li>Per gli articoli che utilizzano la ripartizione dei ricavi, puoi modificare solo l'indirizzo dell'articolo padre. L'indirizzo degli articoli figlio corrisponde all'indirizzo del padre e non può essere modificato separatamente.</li></ul> |

### <a name="product-tab"></a>Scheda Prodotto

Le seguenti informazioni sono disponibili nella scheda **Prodotto**.

| Campo o sezione | Description |
|------------------|-------------|
| Dimensioni di immagazzinamento | <p>Questa sezione mostra le informazioni di archiviazione per l'articolo. Contiene il campo **Numero di serie**, che mostra il numero di serie dell'articolo.</p><p>Il numero di serie viene copiato dall'ordine cliente iniziale durante il processo di supporto e rinnovo. Per gli articoli che utilizzano la ripartizione dei ricavi, il numero di serie dell'articolo padre viene copiato in tutti gli articoli figlio. Il numero di serie viene copiato quando l'opzione **Copia il numero di serie** è impostata su **Sì** nella pagina **Parametri di fatturazione del contratto ricorrenti**.</li></ul> |
| Dimensioni prodotto | I dettagli del prodotto per l'articolo e i valori vengono aggiornati automaticamente, in base al valore **Numero di variante** selezionato per la riga del programma di fatturazione. |

### <a name="account-tab"></a>Scheda Account

Le seguenti informazioni sono disponibili nella scheda **Conto**.

| Campo | Description |
|-------|-------------|
| Conto principale | Il conto principale creato nella riga di vendita. Il valore predefinito proviene dall'ordine cliente. Questo campo non è obbligatorio. |
| Dimensioni finanziarie dell'articolo | <p>I valori predefiniti delle dimensioni finanziarie, basati sul record cliente e articolo.</p><p>Per gli articoli che utilizzano la ripartizione dei ricavi, gli articoli figlio utilizzano i valori delle dimensioni finanziarie dei record cliente e articolo, come descritto in precedenza. Se devi aggiornare i valori delle dimensioni finanziarie degli articoli figlio, puoi importare l'entità dati.</p> |

### <a name="renewals-tab"></a>Scheda Rinnovi

Le seguenti informazioni sono disponibili nella scheda **Rinnovi**.

| Campo | Description |
|-------|-------------|
| Rinnova automaticamente | <p>Un valore che indica se la riga del programma di fatturazione viene rinnovata automaticamente per il periodo di fatturazione successivo.</p><ul><li>**Sì** – La riga del programma di fatturazione viene rinnovata automaticamente per il periodo di fatturazione successivo quando si crea una fattura:</li><li>**No** – La riga del programma di fatturazione non viene rinnovata automaticamente. Devi rinnovare manualmente il programma di fatturazione.</li></ul> |
| Righe da aggiungere per rinnovo | Il numero di righe da aggiungere a un rinnovo del programma di fatturazione. |

Inoltre, i seguenti pulsanti sono disponibili nella scheda **Rinnovi**.

| Pulsante | Description |
|--------|-------------|
| Controllo scrittura contabile ricavi non fatturati | Consente di visualizzare tutte le modifiche per gli articoli che utilizzano la funzionalità ricavi non fatturati. |
| Aggiungi termine di rinnovo | Consente di aggiungere un termine di rinnovo per l'articolo. La data di inizio del nuovo periodo di rinnovo è la data successiva alla data di fine del periodo precedente. I campi **Data di fine rinnovo**, **Data di inizio differimento**, **Data di fine differimento**, **Quantità articolo** e **Prezzo unitario** possono essere aggiornati. |
| Modifica termine di rinnovo | <p>Consente di modificare un termine di rinnovo. Per il periodo iniziale, puoi modificare le date di inizio e fine del differimento prima della creazione della scrittura contabile. Per i termini successivi, la data di inizio non può essere modificata. È sempre la data successiva dopo la fine del termine precedente.</p><p>Se esiste un termine di rinnovo dopo il termine che stai modificando, le date del termine non possono essere modificate. In questo caso, solo i campi **Quantità** e **Prezzo unitario** per l'articolo di rinnovo possono essere aggiornati.</p><p>Ad esempio, esistono tre termini. <ul><li>Il primo termine non può essere modificato perché è già iniziato.</li><li>Per il secondo termine, puoi modificare solo la quantità e il prezzo unitario.</li><li>Per il terzo termine, puoi modificare tutti i valori tranne la data di inizio. Inoltre, l'opzione **Programma da modello** consente di creare un programma di differimento basato sul modello per i ricavi non fatturati. Quando questa opzione è impostata su **Sì**, seleziona il modello di differimento nel campo **Modello** e modifica le date di inizio e fine del differimento come richiesto. I successivi termini di rinnovo utilizzano lo stesso modello di differimento. Tuttavia, il modello di differimento può essere modificato.</p></li></ul> |

### <a name="termination-tab"></a>Scheda Terminazione

Le seguenti informazioni sono disponibili nella scheda **Terminazione**.

| Campo | Description |
|-------|-------------|
| Data fine rapporto | La data in cui la riga del programma di fatturazione viene terminata. Il valore predefinito è quello del campo **Data di terminazione** nell'intestazione. Puoi modificare il valore come necessario. |
| Tipo di terminazione | Il tipo di terminazione. Il valore predefinito è quello del campo **Tipo di terminazione** nell'intestazione. |

### <a name="hold-tab"></a>Scheda Sospensione

Se vengono utilizzati differimenti di ricavi e spese, la scheda **Sospensione** mostra la data di differimento.

### <a name="escalation-and-discount-tab"></a>Scheda Escalation e sconto

Le seguenti informazioni sono disponibili nella scheda **Escalation e sconto**.

| Campo | Description |
|-------|-------------|
| Riassegnazione | <p>Seleziona se sono consentite escalation per la riga del programma di fatturazione. Qualsiasi riga di escalation dell'intestazione viene applicata quando viene creata la riga del programma di fatturazione.</p><ul><li>**Sì** – È possibile applicare escalation alla riga. Quando questa opzione è selezionata, puoi impostare le escalation per le righe del programma di fatturazione nella pagina **Escalation e sconto**.</li><li>**No** – Non è possibile applicare escalation alla riga.</li></ul><p>L'impostazione predefinita è basata sul **gruppo di programmi di fatturazione** selezionato.</p> |

### <a name="price-changes-tab"></a>Scheda Modifiche prezzo

Per le righe il cui prezzo passa da **Standard** a **Flat**, la griglia nella scheda **Modifiche prezzo** include le seguenti colonne:

- Data modifica
- Modificato dall'utente
- Prezzo standard
- Prezzo flat
- Aggiorna prezzo
