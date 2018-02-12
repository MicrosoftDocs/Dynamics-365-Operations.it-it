---
title: Visualizzare e progettare report finanziari
description: L'articolo fornisce esercizi che guidano alla visualizzazione e creazione dire report finanziari per Microsoft Dynamics 365 for Finance and Operations.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReportingSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 86597a81b4dcfb14cbc88667fbb1db214133c6e5
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="view-and-design-financial-reports"></a>Visualizzare e progettare report finanziari

[!include[banner](../includes/banner.md)]


L'articolo fornisce esercizi che guidano alla visualizzazione e creazione dire report finanziari per Microsoft Dynamics 365 for Finance and Operations. I report finanziari sono costituiti da una esperienza di visualizzazione in Finance and Operations e una funzionalità di progettazione report con un solo clic che consente di creare e modificare report finanziari.  

<a name="exercise-1-generate-and-explore-a-default-financial-report"></a>Esercizio 1: generare ed esplorare un report finanziario predefinito
-----------------------------------------------------------

Per questo esercizio verrà generato ed esplorato un report predefinito esistente. Questo report include tutti i conti e contiene anche le proprietà di conto (attributi) per i conti. Verrà eseguito il drill-down dei dettagli delle transazioni, verranno applicati filtri di dimensione e verrà modificata la valuta nel report. Innanzitutto, aggiorneremo l'ordine di visualizzazione delle dimensioni per report finanziari. Ciò consente di scegliere la modalità di visualizzazione delle dimensioni non solo durante la progettazione e la visualizzazione dei report finanziari.

1.  Passare a **Configurazione dimensione finanziaria per integrazione applicazioni** in **Dimensioni del piano dei conti** nella Contabilità generale.
2.  Spostare le dimensioni nel seguente ordine:
    1.  Conto principale
    2.  Business Unit
    3.  Centro di costo
    4.  Reparto

    Nota: le altre dimensioni possono rimanere nell'ordine in cui sono attualmente.
3.  Salvare la configurazione della dimensione. Successivamente, genereremo un report ed esploreremo i dati nel report.
4.  Passare **Report finanziari** in **Richieste di informazioni e report** nella contabilità generale.
5.  Selezionare la riga per il report denominato **Dettagli CoGe - Predefinito**.
6.  Selezionare **Modifica**. Nota: verrà richiesto di scaricare la funzionalità di progettazione report con un solo clic e di accedere. Per accedere, utilizzare le proprie credenziali.
7.  Modificare l'anno di base a 2012 e selezionare **Genera**. Quando un report viene generato mediante la funzionalità di progettazione report, verrà aperto in una nuova scheda del browser. È possibile esplorare il report nella nuova scheda del browser o accedere alla scheda del browser originale e aprire il report da tale posizione selezionandolo dall'elenco **Report finanziari**.
8.  Nel report aperto, selezionare uno degli importi di cui eseguire il drill-down nei dettagli del conto per il report.
9.  Nei dettagli del conto, selezionare un conto con dati ed **eseguire il drill-down a livello di transazione report**. A livello di transazione report è possibile visualizzare le proprietà (attributi) inclusi nella progettazione del report. A seconda della transazione e del conto, è possibile che vengano visualizzati alcuni o tutti gli attributi.
10. Chiudere il livello di transazione report.
11. Selezionare lo stesso conto o un conto diverso e **aprire le transazioni giustificativo**. Le transazioni giustificativo vengono filtrate per periodo, anno e conto + la combinazione di dimensioni del conto selezionato. Dalle transazioni giustificativo è possibile scegliere di esplorare altre informazioni relative alla transazione.
12. Chiudere le transazioni giustificativo. In un report finanziario è possibile scegliere di visualizzare i dati per un periodo e un anno diversi o con diversi attributi e dimensioni applicati. Questa operazione viene effettuata mediante **Opzioni report**.
13. Selezionare **Opzioni report**.
14. Selezionare **Aggiungere un filtro dimensioni** e scegliere **Business Unit**.
15. Digitare 001 nel campo e selezionare **OK**. Il report mostra ora solo i dati per la Business Unit 001. Si tratta di una visualizzazione personalizzata del report e non è disponibile per altri utenti.
16. Chiudere il report filtrato. I report finanziari possono essere visualizzati in qualsiasi valuta aggiunta a Finance and Operations.
17. Selezionare **Valuta**, quindi **EUR**. Il report viene ora visualizzato in euro. Tutti i codici valuta o simboli di valuta inclusi nella progettazione del report vengono ora visualizzati nella valuta applicata. Se per una valuta non viene definito un simbolo di valuta, questo non viene visualizzato.
18. Chiudere il report **Dettagli CoGe**.
19. Chiudere **Progettazione report**.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>Esercizio 2: aggiungere ulteriori proprietà di conto a una struttura del report
In questo esercizio verrà modificato un report predefinito esistente. Verrà aggiornata sia la definizione di riga per includere tutti i conti che la definizione di colonna per includere gli attributi del conto. Una volta completati gli aggiornamenti, verrà generato ed esplorato report appena creato. Cominceremo dall'elenco Report finanziari.

1.  Passare a **Report finanziari** in Richieste di informazioni e report nella contabilità generale.
2.  Selezionare la riga per il report denominato **Bilancio di verifica riepilogativo - Predefinito**.
3.  Selezionare **Modifica**. **Bilancio di verifica riepilogativo - Predefinito** si aprirà nella funzionalità di progettazione report.
4.  Selezionare **File**, quindi **Salva con nome** e denominare il report Bilancio di verifica dettagliato con attributi. Nota: quando un nuovo report viene creato nella funzionalità di progettazione report, l'elenco dei report finanziari viene aggiornato in Finance and Operations.
5.  Dalla definizione di report, selezionare l'icona di definizione di riga per aprire la **definizione di riga Bilancio di verifica - Predefinito**.
6.  Salvare la definizione di riga come **Bilancio di verifica dettagliato con attributi**
7.  Con il cursore sulla riga 50, selezionare **Modifica**, quindi **Inserire le righe delle dimensioni**. L'inserimento di righe dalle dimensioni consente di scegliere le dimensioni che si desidera inserire nella definizione di riga. Per questo esercizio verrà creata la definizione di riga utilizzando il conto principale.
8.  Assicurarsi che **Conto principale** contenga tutte e commerciali, quindi selezionare **OK**. La definizione di riga contiene ora tutti i conti principali per USMF della persona giuridica.
9.  Scorrere verso il basso alla riga 11110 ed eliminarla.
10. Nella riga 11080, selezionare **--- (importi con carattere di sottolineatura)**.
11. Nella riga 11140, digitare **Totale di tutti i conti** nella colonna B.
12. Nella colonna C, selezionare **TOT** dal menu a discesa.
13. Digitare **50:11080** nella colonna D.
14. **Salvare** la definizione di riga. La definizione di riga contiene ora tutti i conti più a una riga di totale per aggiungere tutti i conti insieme. Successivamente, aggiorneremo la definizione di colonna per includere attributi di conto aggiuntivi.
15. Dalla definizione di report **Bilancio di verifica dettagliato con attributi**, selezionare l'icona di definizione di colonna per aprire la definizione di colonna **Bilancio di verifica riepilogativo - Predefinito**.
16. Salvare la definizione di colonna come **Bilancio di verifica dettagliato con attributi**. La definizione di colonna contiene colonne di dati finanziari, una colonna relativa alla descrizione e colonne di calcolo. Aggiungeremo le colonne di attributi alla definizione di colonna per fornire ulteriori dettagli sui conti.
17. Gli attributi seguenti verranno aggiunti alla definizione di colonna:
    -   Numero giornale di registrazione
    -   Descrizione del giornale di registrazione
    -   Data della transazione
    -   Creato da
    -   Autore ultima modifica

18. Nella colonna I, selezionare **ATTR** come tipo di colonna. Quindi, selezionare **Numero giornale di registrazione** come categoria di attributo.
19. Continuare ad aggiungere colonne per gli attributi rimanenti.
20. Nella riga **Intestazione 2**, aggiungere descrizioni per ciascuna nuova colonna aggiunta.
21. Salvare la definizione di colonna. Ora che la definizione di riga e la definizione di colonna sono state aggiornate, dovremo aggiungerle alla definizione di report.
22. Dalla definizione di report **Bilancio di verifica dettagliato con attributi**, selezionare Bilancio di verifica dettagliato con attributi sia per la definizione di riga che per quella di colonna.
23. Modificare l'anno di base in **2012**.
24. **Salvare** la definizione di report e **generare**. Una volta completato il report con la generazione e aperto, è possibile esplorare il report come illustrato nel primo esercizio. Eseguire il drill-down di conti diversi per vedere come vengono visualizzati gli attributi aggiuntivi.
25. Chiudere il report **Bilancio di verifica dettagliato con attributi**.
26. Chiudere **Progettazione report**.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>Esercizio 3: creare un report multidimensionale utilizzando un albero gerarchico
Per questo esercizio verrà modificato un report predefinito esistente. Verrà creata una struttura del report e verrà aggiunta a una definizione di report per produrre un centro di costo/conto economico divisionario. Una volta completati gli aggiornamenti, verrà generato il centro di costo/conto economico divisionario e verrà esplorato il report utilizzando la struttura del report. Cominceremo dall'elenco Report finanziari.

1.  Passare a **Report finanziari** in Richieste di informazioni e report nella contabilità generale.
2.  Selezionare la riga per il report denominato **Conto economico - Predefinito**.
3.  Selezionare **Modifica**. **Conto economico - Predefinito** si aprirà nella funzionalità di progettazione report.
4.  Nel menu **File**, puntare su **Nuovo**, quindi fare clic su **Definizione di albero gerarchico**.
5.  Nel menu **Modifica**, fare clic su **Inserisci unità gerarchiche da dimensioni**...
6.  Deselezionare le caselle di controllo per tutte le dimensioni ad eccezione di **Centro di costo**.
7.  Fare clic sul campo **Da dimensione** per la dimensione Centro di costo, digitare **007**, quindi premere il tasto TAB. Nel campo **A dimensione**, digitare **018**.
8.  **Salvare** la struttura risultante con il nome **Centri di costo per divisione**. Ora che la struttura del report è stata creata, verrà modificata per inserirvi tre nuove unità di rollup: Marketing, Operazioni e Vendita al dettaglio.
9.  Nel menu **Finestra**, fare clic su **Centri di costo per divisione**. (Se la struttura del report è stata chiusa, selezionarla da Definizioni di albero gerarchico nel pannello di navigazione).
10. Fare clic sull'unità numero due, **Fiere commerciali**, quindi fare clic sull'icona **Inserisci unità gerarchica**.
11. Fare doppio clic sulla colonna dell'entità nella riga vuota, quindi selezionare **USMF**.
12. Digitare **Marketing** nelle colonne B e C.
13. Fare clic sull'unità numero cinque, **Operazioni di servizio**, quindi fare clic con il pulsante destro del mouse. **Selezionare Inserisci unità gerarchica**.
14. Ripetere il passaggio 11.
15. Digitare **Operazioni** nelle colonne B e C.
16. Fare clic sull'unità numero dodici, **Outlet**, quindi fare clic con il pulsante destro del mouse. Selezionare **Inserisci unità gerarchica**.
17. Ripetere il passaggio 11.
18. Digitare **Vendita al dettaglio** nelle colonne B e C. Si noti che le unità Marketing, Operazioni e Vendita al dettaglio vengono visualizzate allo stesso livello delle unità di rollup correnti. Le nuove unità vengono organizzate di seguito. Le unità gerarchiche vengono organizzate mediante le opzioni visualizzate con il pulsante destro del mouse, promuovere e abbassare di livello, oppure mediante trascinamento.
19. Verificare che l'unità tre, **Fiere commerciali**, sia attiva e fare clic con il pulsante destro del mouse.
20. Selezionare **Abbassa di livello unità gerarchica**. Si noti che l'unità viene ora visualizzata come elemento figlio di **Marketing**.
21. Fare clic sull'unità quattro, **Marketing** **Campagna**, quindi fare clic con il pulsante destro del mouse.
22. Selezionare **Abbassa di livello unità gerarchica**.
23. Fare clic su **Operazioni di servizio** nella rappresentazione grafica. Tenere premuto il pulsante sinistro del mouse mentre si trascina l'unità fino a **Operazioni**. Rilasciare il pulsante sinistro del mouse per inserire l'unità nel rollup dell'operazione. Ripetere l'operazione per **Produzione, Controllo qualità, Logistica, Approvvigionamento e Amministrazione**.
24. Rendere **Outlet**, **Super**, **Centro commerciale** e **In linea** elementi secondari di **Vendita al dettaglio** abbassandoli di livello o trascinandoli e rilasciandoli.
25. Salvare la riorganizzazione risultante. Ora che la struttura del report è stata creata e organizzata, può essere aggiunta alla definizione di report.
26. Nel menu **Finestra**, selezionare **Conto economico - Predefinito** per aprire la definizione di report.
27. Fare clic sulla freccia a discesa **Tipo di struttura** e selezionare **Struttura report**.
28. Fare clic sulla freccia a discesa della struttura e selezionare **Centri di costo per divisione**.
29. Modificare l'anno di base in **2012**, **salvare** le modifiche e **generare** il report. Una volta generato e aperto il report, è possibile esplorarlo.
30. Selezionare il menu a discesa **Struttura report** per visualizzare le unità del report. In alternativa, è possibile eseguire il drill-down di una riga del report per visualizzare tutti i saldi per tutte le unità della struttura del report.
31. Chiudere **Conto economico - Predefinito**.
32. Chiudere **Progettazione report**.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>Esercizio 4: creare un report consolidato utilizzando una gerarchia organizzativa
Per questo esercizio verrà modificato un report predefinito esistente. Si aggiungerà una gerarchia organizzativa nella definizione di report per generare un conto economico e un conto patrimoniale consolidati. Una volta completati gli aggiornamenti, verrà generato il report consolidato e verrà esplorato il report utilizzando la struttura del report. Cominceremo dall'elenco Report finanziari.

1.  Passare a **Report finanziari** in Richieste di informazioni e report nella contabilità generale.
2.  Selezionare la riga per il report denominato **Conto patrimoniale e conto economico affiancati - Predefinito**
3.  Selezionare **Modifica**. **Conto patrimoniale e conto economico affiancati - Predefinito** si aprirà nella funzionalità di progettazione report.
4.  Selezionare **File** &gt; **Salva con nome** e denominare il report **Conto patrimoniale e conto economico consolidati affiancati**.
5.  Modificare l'anno di base in 2012.
6.  Fare clic sulla freccia a discesa Tipo di struttura, quindi selezionare **Gerarchie organizzative**.
7.  Fare clic sulla freccia a discesa Struttura, quindi selezionare **Disponibilità Contoso**.
8.  Salvare le modifiche e generare il report. Se richiesto, selezionare tutte le unità di report. Una volta generato e aperto il report, è possibile esplorarlo.
9.  Selezionare **Opzioni report**.
10. Selezionare **Aggiungere un filtro dimensioni** e scegliere **Reparto**.
11. Digitare **022** nel campo e selezionare **OK**.
12. Chiudere il report filtrato.
13. Selezionare il menu a discesa **Struttura report** per visualizzare le unità del report. In alternativa, è possibile eseguire il drill-down di una riga del report per visualizzare tutti i saldi per tutte le unità della struttura del report.
14. Chiudere **Conto patrimoniale e conto economico consolidati affiancati**.
15. Chiudere **Progettazione report**.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>Esercizio 5: creare un report di reparto affiancato
In questo esercizio verrà creato un nuovo report. Il report del conto economico di reparto affiancato. Verrà utilizzata una definizione di riga esistente, ma verrà creata una nuova definizione di report e una nuova definizione di colonna che utilizza i filtri di dimensione. Cominceremo dall'elenco Report finanziari.

1.  Passare a **Report finanziari** in Richieste di informazioni e report nella contabilità generale.
2.  Selezionare **Nuovo**. La funzionalità di progettazione report verrà visualizzata con una definizione di report vuota aperta. La prima attività sarà la creazione della definizione di colonna.
3.  Creare una nuova definizione di colonna facendo clic su **File**, quindi su **Nuovo**, quindi su **Definizione di colonna**.
4.  Nella **Colonna A**, selezionare **DESC** per il tipo di colonna.
5.  Nella **Colonna B**, selezionare **FD** per il tipo di colonna.
6.  Fare doppio clic nel campo **Filtro di dimensione**.
7.  Nella finestra **Dimensione**, fare doppio clic sulla colonna **Reparto**.
8.  Nella sezione Singolo o Intervallo della finestra di dialogo, fare clic su **...** per il campo **Da** per visualizzare un elenco di reparti.
9.  Selezionare il reparto **022**, quindi **Vendite e marketing**, quindi fare clic su **OK**.
10. Ripetere i passaggi da 5 a 8 per i reparti 23-25.
11. Nella riga **Intestazione 2** per ogni colonna FD, digitare le seguenti descrizioni di reparto:
    -   Colonna B - Vendite e marketing
    -   Colonna C - Operazioni
    -   Colonna D - Dati finanziari
    -   Colonna E - IT

12. Salvare la definizione di colonna come Reparti affiancati. Poiché stiamo utilizzando una definizione di riga esistente, la definizione di report può ora essere modificata per utilizzare la definizione di colonna appena creata e la definizione di riga esistente.
13. Nel menu **Finestra**, selezionare **Nuova definizione di report** per aprire la definizione di report.
14. Selezionare **Conto economico - Predefinito** come definizione di riga e **Reparti affiancati** come definizione di colonna.
15. Salvare la definizione di report come **Conto economico di reparto affiancato**.
16. Modificare l'anno di base in **2012**.
17. Modificare il livello di dettaglio in **Finanziario, contabile e di transazione**.
18. **Salvare** le modifiche e **generare**. Una volta generato e aperto il report, è possibile esplorarlo.

## <a name="additional-resources"></a>Risorse aggiuntive
[Report finanziari](../../financials/general-ledger/financial-reporting-getting-started.md) 
[Visualizza report finanziari](../../financials/general-ledger/view-financial-reports.md) 
[Blog per i report finanziari di Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




