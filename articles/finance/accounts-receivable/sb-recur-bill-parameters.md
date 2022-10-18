---
title: Parametri di fatturazione contratto ricorrente
description: Questo articolo spiega come impostare i valori predefiniti per i programmi di fatturazione creati in Fatturazione contratto ricorrente. Spiega inoltre come creare i gruppi di programmi di fatturazione.
author: JodiChristiansen
ms.date: 11/04/2021
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
ms.openlocfilehash: 64d6e21c2d8c588a64f0f4cf8b7a0bafc853bcab
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644005"
---
# <a name="recurring-contract-billing-parameters"></a>Parametri di fatturazione contratto ricorrente

Usa la pagina **Parametri di fatturazione contratto ricorrente** per impostare i valori predefiniti per i programmi di fatturazione creati in Fatturazione contratto ricorrente. Tutti i programmi di fatturazione creati inizialmente utilizzeranno questi valori predefiniti. Tuttavia, puoi modificare i valori per ogni programma di fatturazione in base alle tue esigenze.

## <a name="general-tab"></a>Scheda Generale

1. Nella pagina **Parametri di fatturazione contratto ricorrente** sulla scheda **Generale** nel campo **Gruppo di programmi di fatturazione** seleziona un gruppo di programmi di fatturazione. Per informazioni su come impostare i gruppi di programmi di fatturazione, vedi la sezione [Impostare gruppi di programmi di fatturazione](#set-up-billing-schedule-groups) più avanti in questo articolo.
2. Nel campo **Tipo di terminazione**, seleziona come viene calcolata la fattura finale al termine di un programma di fatturazione:

    - **Regola il programma** – Interrompi il programma di fatturazione alla data di scadenza, modifica lo stato del programma su **Ultima fatturazione**, e rettifica la relativa programmazione di differimento stornando l'importo che non deve più essere riconosciuto. Se la data di inizio della fatturazione è successiva alla data di terminazione, i periodi di fatturazione rimanenti vengono rimossi.
    - **Fattura rimanente** – Aggiungi gli eventuali importi residui nel programma di fatturazione al periodo di terminazion, modifica lo stato del programma in **Ultima fatturazione** e aggiorna il programma di differimento. Se la data di inizio della fatturazione è successiva alla data di terminazione, l'importo totale di tutti i periodi di fatturazione rimanenti viene aggiunto al periodo di fatturazione e i periodi di fatturazione rimanenti vengono rimossi.
    - **Nessuna rettifica** – Termina il programma di fatturazione alla data di terminazione. Non vengono apportate modifiche al programma di fatturazione.

3. Nel campo **Tipo di programma univoco** seleziona **Nessuno** per specificare che i clienti sono limitati a un unico programma di fatturazione. Seleziona **Per cliente** o **Per utente finale** per specificare che i clienti sono limitati a un programma unico.
4. Imposta l'opzione **Allinea a mese** su **Sì** per allineare le righe dei dettagli del programma di fatturazione alla fine di un mese in cui viene creato o aggiornato un programma di fatturazione. Impostalo su **No** per utilizzare le date incrementali.
5. Imposta l'opzione **Periodi ripartizione parziali** su **sì** per allocare gli importi di fatturazione in base al numero di giorni del periodo. Impostala su **No** per avere un importo uguale in ogni periodo di fatturazione, indipendentemente dal numero di giorni.
6. Se imposti l'opzione **Periodi ripartizione parziali** su **sì**, imposta il campo **Metodo di ripartizione** su **Giornaliero** per distribuire gli importi in base al numero di giorni del periodo. Impostalo su **Mensile** per avere un importo uguale ogni mese.
7. Specifica se i programmi di fatturazione appena creati sono sospesi per impostazione predefinita.

    > [!NOTE]
    > Per rimuovere la sospensione da un programma di fatturazione, l'utente deve far parte di un gruppo di utenti. Seleziona **Sostituzione gruppo di utenti rimozione attesa** per impostare un gruppo di utenti in cui l'opzione **Consenti rimozione attesa** è abilitata.

8. Nel campo **Tipo di transazione fattura**, seleziona il tipo di transazione fattura predefinito per i nuovi programmi di fatturazione.
9. Imposta l'opzione **Allinea differimento a fatturazione** su **sì** per allineare il programma di differimento corrispondente in modo che utilizzi le stesse date del programma di fatturazione. Impostalo su **No** per avere date diverse.
10. Se stai utilizzando la funzione di suddivisione dei ricavi, imposta l'opzione **Crea automaticamente suddivisione ricavi** su **sì** quando gli articoli vengono aggiunti a un programma di fatturazione. La casella di controllo **Suddivisione ricavi** verrà automaticamente selezionata nella riga del programma di fatturazione se l'articolo è impostato come articolo di suddivisione dei ricavi. Imposta l'opzione su **No** per selezionare manualmente la casella di controllo **Suddivisione ricavi**.
11. Imposta l'opzione **Suddivisione clienti** su **sì** per consentire la fatturazione di un piano di fatturazione a clienti diversi. Quando è impostata su **sì** l'opzione **Suddivisione clienti** è disponibile nell'intestazione del programma di fatturazione e nella riga del programma di fatturazione. 
12. Imposta i campi per la creazione dell'ordine cliente:

    - Le fatture possono essere consolidate per periodo, cliente o articolo. Qualsiasi combinazione di valori **sì** e **no** può essere impostata. Le fatture possono anche essere suddivise per gruppo di articoli.
    - Sono disponibili le seguenti opzioni di registrazione per le fatture:

        - **Crea ordine cliente**: crea solo l'ordine cliente.
        - **Mostra registrazione fattura**: Fattura l'ordine cliente e apri una pagina in cui è possibile registrare manualmente la fattura.
        - **Crea fattura a testo libero** – Seleziona questa opzione se stai utilizzando fatture a testo libero.
        - **Registra automaticamente fattura** – Fattura l'ordine cliente e registralo automaticamente.

    - Imposta l'opzione **Aggiungi date di fatturazione alla descrizione articolo** su **sì** per aggiungere una descrizione che includa la data di inizio e la data di fine della fatturazione.
    - Imposta l'opzione **Escludi consumo a zero** su **sì** per escludere le righe del programma di fatturazione che non hanno consumo. Impostala su **No** per includere tali righe nell'ordine cliente.
    - Imposta l'opzione **Non stampare articoli figlio** su **sì** se non vuoi stampare gli articoli figlio di una suddivisione dei ricavi nell'ordine cliente. La fattura mostra solo l'articolo padre. Se l'importo netto degli articoli figlio (nascosti) è una somma diversa da zero, l'importo netto della riga principale mostra un riepilogo delle righe figlio. Imposta l'opzione su **No** per stampare tutti gli articoli figlio sotto l'articolo padre nella fattura di vendita.

12. Imposta i campi per il supporto e i rinnovi:

    - Imposta l'opzione **Abilita supporto e rinnovo automaticamente** su **sì** per utilizzare automaticamente la funzione di supporto e rinnovo su un ordine cliente.
    - Nel campo **Livello supporto e rinnovo** seleziona il livello di supporto e rinnovo predefinito.
    - Nel campo **Quantità supporto e rinnovo** specifica la quantità di supporto e rinnovo.
    - Nel campo **Supporto predefinito e data di inizio rinnovo** specifica la data da utilizzare come data di inizio predefinita per supporto e rinnovi:

        - **Data transazione**: utilizza la data di transazione come data di inizio.
        - **Inizio mese corrente** – Utilizza il primo del mese corrente come data di inizio.
        - **Inizio mese successivo** – Utilizza il primo del mese successivo come data di inizio. Se la data della transazione è il primo del mese, viene utilizzato il primo del mese corrente.
        - **Regola del 15** – Utilizza come data di inizio il primo del mese in corso se la data della transazione è compresa tra il primo e il quindici del mese. Se la data della transazione è il sedici o dopo, usa il primo del mese successivo come data di inizio.

    - Imposta l'opzione **Includi sconto nel calcolo** su **sì** per includere l'importo dello sconto nell'importo del supporto o del rinnovo. Impostala su **No** per escludere l'importo dello sconto.
    - Nei campi **Frequenza supporto** e **Frequenza rinnovo** seleziona la frequenza da utilizzare quando gli articoli di supporto e rinnovo vengono aggiunti a un programma di fatturazione: **Giornaliero**, **Mensile**, **Trimestrale**, **Semestrale**, o **Annuale**.
    - Imposta l'opzione **Allinea per gruppo di articoli** su **sì** per allineare le date di inizio e fine dei nuovi articoli agli articoli esistenti, in base al gruppo di articoli.
    - Imposta l'opzione **Allinea a periodo non fatturato successivo** su **sì** per determinare la data di allineamento per un articolo di rinnovo in base alla data del successivo periodo non fatturato dopo l'inizio del rinnovo.
    - Imposta l'opzione **Copia numero di serie** su **sì** per copiare il numero di serie dell'articolo dalla riga dell'ordine cliente iniziale alla riga del programma di fatturazione corrispondente.

13. Se stai utilizzando l'escalation nel programma di fatturazione, seleziona il metodo utilizzato per il calcolo dell'indice dei prezzi al consumo.
14. Imposta l'opzione **Traccia variazione di prezzo** su **sì** se desideri un record delle variazioni di prezzo nelle righe del programma di fatturazione. Se una riga del programma di fatturazione viene modificata manualmente da standard a forfettario e viene immesso un nuovo prezzo, le informazioni di controllo vengono tracciate nella riga del programma di fatturazione. Imposta l'opzione su **No** se non vuoi dividere tracciare queste modifiche.
15. Specificare se i record vengono filtrati in base alla data di inizio o alla data di fine per impostazione predefinita nella pagina **Genera fattura**.
16. Se usi la funzionalità **Ricavi non fatturati** specifica le opzioni utilizzate:

    - Imposta l'opzione **Registra automaticamente giornale di registrazione generale** su **sì** se vuoi creare e registrare contemporaneamente il giornale di registrazione generale. Impostala su **No** se vuoi creare il giornale di registrazione generale e quindi registrarlo manualmente.
    - Nel campo **Nome giornale di registrazione predefinito** seleziona il nome del giornale di registrazione predefinito da utilizzare quando viene creato il giornale di registrazione generale.
    - Nel campo **Metodo non fatturato a breve termine**, seleziona il metodo non fatturato a breve termine, se ne stai utilizzando uno. Se selezioni **Nessuno**, la funzionalità a breve termine non verrà utilizzata con i ricavi non fatturati. Seleziona **Periodi operativi continui** per utilizzare sempre 12 mesi o **Anno fisso** per utilizzare l'anno fiscale rimanente.

17. Specifica le opzioni utilizzate quando un programma di fatturazione e le relative righe vengono terminate:

    - **Emetti credito** – Crea una nota di credito quando un programma di fatturazione o una riga del programma di fatturazione viene terminato.
    - **Rettifica credito** – Crea una rettifica del credito per un programma di fatturazione quando una riga viene terminata. La rettifica del credito viene visualizzato in un periodo di fatturazione futuro per il programma di fatturazione. La rettifica del credito aggiorna l'importo della fattura per il periodo di fatturazione successivo fino al termine dell'applicazione del credito al programma di fatturazione.
    - **Nessun credito** – Non viene creata una rettifica di credito o una nota di credito quando un programma di fatturazione o una riga del programma di fatturazione viene terminato. Questa opzione è disponibile solo quando l'opzione **Nessuna rettifica** viene usata per terminare un programma di fatturazione.
18. Quando l'opzione **Occasionale può terminare il rimborso** è impostata su **No** e un programma di fatturazione con una frequenza di fatturazione di **Occasionale**, lo stato della riga del programma di fatturazione cambia in **Terminato** una volta che il piano di fatturazione è stato fatturato. Questo programma di fatturazione non può essere terminato e non può essere emesso alcun credito. Quando l'opzione **Occasionale può terminare il rimborso** è impostata su **Sì**, la riga del programma di fatturazione con una frequenza di fatturazione di **Occasionale** avrà lo stato **attivo** dopo che il piano di fatturazione è stato fatturato. È possibile terminare la riga del programma di fatturazione ed elaborare un rimborso. 
19. L'opzione **Ripartizione giornaliera** impostata nei parametri imposta automaticamente la pagina di terminazione di massa e l'intestazione della pianificazione di fatturazione e le finestre di dialogo Termina. Può essere modificata durante il processo di terminazione. Quando è impostata su **sì** l'eventuale importo del rimborso sarà calcolato utilizzando una tariffa giornaliera. Quando è impostata su **No** l'importo verrà accreditato in base alla data di scadenza e alla frequenza di fatturazione. Ad esempio, se si utilizza la frequenza mensile e l'importo di fatturazione è stato $ 100 al mese, l'importo del credito è in incrementi di $ 100. Se la frequenza di fatturazione è una tantum, l'importo del credito è $ 0,00. Devi avere Ripartizione giornaliera impostato su Sì per ottenere un rimborso per la frequenza di fatturazione una tantum. 
20. Imposta l'opzione **Crea differimento per credito** su **sì** per creare un nuovo programma di differimento se si accredita un programma di differimento esistente. Lascia l'opzione impostata su **No** per creare il credito sul piano di differimento esistente.

## <a name="sequence-number-tab"></a>Scheda Sequenza numerica

Usa la scheda **Sequenza numerica** della pagina **Parametri di fatturazione contratto ricorrente** per impostare il valore predefinito per i numeri del programma di fatturazione. I valori predefiniti sono impostati nella pagina **Sequenze numeriche** (**Amministrazione organizzazione \> Sequenze numeriche \> Sequenze numeriche**).

## <a name="set-up-billing-schedule-groups"></a>Impostare i gruppi di programmi di fatturazione

Usa la pagina **Gruppo di programmi di fatturazione** per creare un gruppo di programmi di fatturazione per la fatturazione del contratto ricorrente. Quando viene creata un nuovo programma di fatturazione e ad esso viene applicato un gruppo di programmi di fatturazione, i valori definiti nella pagina **Gruppo di programmi di fatturazione** vengono inseriti come valori predefiniti per il programma di fatturazione. Puoi modificare qualsiasi valore predefinito per il programma di fatturazione specifico che crei. È possibile impostare più gruppi di programmi di fatturazione e quindi assegnarne uno come gruppo di programmi di fatturazione predefinito nella pagina **Parametri di fatturazione contratto ricorrente**.

Per creare un gruppo di programmi di fatturazione per la fatturazione del contratto ricorrente, attieniti alla seguente procedura.

1. Sulla pagina **Gruppo di programmi di fatturazione** seleziona **Nuovo** per creare un gruppo di programmi di fatturazione.
2. Nel campo **Gruppo di programmazioni fatturazione** immetti un identificatore univoco.
3. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Frequenza fatturazione** specifica la frequenza con cui il programma di fatturazione viene fatturato a un cliente: **Una volta**, **Giornaliero**, **Mensile**, **Trimestrale**, **Semestrale**, o **Annuale**.
5. Nel campo **Intervallo di fatturazione** immetti un intervallo di fatturazione. Ad esempio, imposta il campo **Frequenza di fatturazione** su **Mensile** e il campo **Intervallo di fatturazione** su **2** per fatturare ogni due mesi.
6. Nel campo **Metodo di determinazione prezzo**, seleziona il metodo di determinazione del prezzo predefinito per gli articoli nel programma di fatturazione:

    - **Standard** – Calcola il prezzo unitario in base alla quantità totale inserita e utilizza il prezzo standard dalla pagina **Prodotti rilasciati** in Gestione delle informazioni sul prodotto.
    - **Forfettario** – Applica un prezzo forfettario inserito nella riga del programma di fatturazione.
    - **Livello** – Calcola il prezzo unitario utilizzando una quantità fissa per diverse fasce di prezzo. Ogni livello deve essere compilato prima di passare alla fascia di prezzo successiva.
    - **Livello forfettario** – Calcola il prezzo unitario utilizzando una quantità fissa e gli importi di prezzi estesi per diverse fasce di prezzo. Il prezzo addebitato in un periodo di fatturazione utilizza il prezzo esteso che corrisponde al livello in cui esiste la quantità di fatturazione.

7. Nel campo **Tipo di articolo** seleziona il tipo di articolo per il gruppo di fatturazione:

    - **Standard** – Seleziona questo valore se la quantità è statica.
    - **Utilizzo** – Seleziona questo valore per gli articoli a tempo o a consumo. Se selezioni questo valore, imposta il campo **Opzione lettura dell'utilizzo** su **Lettura** per inserire il valore (lettura) per un periodo di fatturazione su un contatore o un dispositivo. Il valore consumato verrà calcolato in base al periodo di fatturazione precedente e alla lettura corrente inserita.
    - **A fasi** – Seleziona questo valore per utilizzare la funzionalità di fatturazione a fasi. Se selezioni questo valore, nel campo **Modello a fasi** seleziona il modello a fasi se ne stai utilizzando uno.
    - **Consumo** – Seleziona questo valore per inserire il valore consumato per un periodo di fatturazione.

8. Imposta l'opzione **Fattura separatamente** su **sì** per creare una combinazione di fatture consolidate e fatture separate per lo stesso cliente. Ad esempio, un cliente ha cinque programmi di fatturazione. Tre di essi verranno consolidati in un'unica fattura, ma ciascuno degli altri due richiede una fattura separata. Imposta l'opzione su **No** per creare una sola fattura consolidata per il cliente.
9. Imposta l'opzione **Rinnova automaticamente** su **sì** per rinnovare automaticamente il programma di fatturazione ricorrente per il periodo di fatturazione successivo al momento della creazione della fattura. Impostala su **No** per rinnovare manualmente il programma di fatturazione. Nel campo **Righe da aggiungere per rinnovo** specifica quante righe aggiungere per ogni rinnovo.
10. Imposta l'opzione **Escalation** su **sì** applicare le *escalation* (aumenti di prezzo) ai programmi di fatturazione associati a questo gruppo di programmi di fatturazione.
