---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono fornite alcune risposte alle domande frequenti sulla creazione di report finanziari.
author: jinniew
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5e0702864815c630f35e3f5b753ece1cb1daa71
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722298"
---
# <a name="financial-reporting-faq"></a>Domande frequenti sulla creazione di report finanziari

In questo argomento vengono fornite risposte alle domande frequenti sulla creazione di report finanziari.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?

L'esempio seguente mostra come limitare l'accesso a un report utilizzando la sicurezza dell'albero.

La società dimostrativa USMF dispone di un report **stato patrimoniale** che non desidera rendere accessibile a tutti gli utenti dei report finanziari. È possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo specifici utenti possano accedervi.

1. Accedere a Financial Reporter Report Designer.
2. Selezionare **File \> Nuovo \> Definizione di albero** per creare una nuova definizione di albero.
3. Fare doppio tocco o doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.
4. Selezionare **Utenti e gruppi**.
5. Selezionare gli utenti o i gruppi che devono accedere al report.
6. Selezionare **Salva**.
7. Nella definizione di report, aggiungere la nuova definizione di albero.
8. Nella definizione di albero, selezionare **Impostazione**. Quindi, in **Selezione unità gerarchica** selezionare **Includi tutte le unità**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Come identificare quali conti non corrispondono ai saldi?

Se si dispone di un report che non corrisponde ai saldi, utilizzare le seguenti procedure per identificare ciascun conto e scostamento.

### <a name="in-financial-reporter-report-designer"></a>In Financial Reporter Report Designer

1. Creare una nuova definizione di riga.
2. Selezionare **Modifica \> Inserisci righe da dimensioni**.
3. Selezionare **MainAccount**.
4. Selezionare **OK**.
5. Salvare la definizione di riga.
6. Creare una nuova definizione di colonna.
7. Creare una nuova definizione di report.
8. Selezionare **Impostazioni** e deselezionare questa opzione.
9. Generare il report. 
10. Esportare il report in Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>In Dynamics 365 Finance

1. Andare a **Contabilità generale \> Richieste di informazioni e report \> Bilancio di verifica**.
2. Impostare i seguenti campi:

    - **Dal** - Immettere la data di inizio dell'anno fiscale.
    - **Al** - Immettere la data per la quale si sta generando il report.
    - **Dimensione finanziaria** - Impostare questo campo su **Set di conti principali**.

3. Selezionare **Calcola**.
4. Esportare il report in Excel.

Ora si possono copiare i dati dal report di Excel di Financial Reporter nel report **Bilancio di verifica** per confrontare le colonne **Saldo di chiusura**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Quando si progetta un report in Report Designer o quando si genera un report finanziario, viene visualizzato il seguente messaggio: "Impossibile completare l'operazione a causa di un problema nel framework del provider di dati". Come si deve rispondere?

Il messaggio indica che si è verificato un problema quando il sistema ha tentato di recuperare i metadati finanziari dal data mart mentre veniva utilizzato il report finanziario. Ci sono due modi per rispondere a questo problema:

- Rivedere lo stato di integrazione dei dati andando su **Strumenti \> Stato di integrazione** in Report Designer. Se l'integrazione è incompleta, attendere che venga completata. Quindi ripetere l'operazione che si stava facendo quando è stato visualizzato il messaggio.
- Contattare l'assistenza per identificare e risolvere il problema. È possibile che siano presenti dati incoerenti nel sistema. I tecnici dell'assistenza possono aiutare a identificare il problema sul server e a trovare i dati specifici che potrebbero richiedere un aggiornamento.

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>In che modo la selezione della conversione del tasso storico influisce sulle prestazioni del report?

Il tasso storico viene in genere utilizzato con utili non distribuiti, proprietà, impianti e attrezzature e conti capitale netto. Il tasso storico può essere richiesto in base alle linee guida del consiglio per gli standard di contabilità finanziaria (FASB, Financial Accounting Standards Board) o ai principi contabili generalmente accettati (GAAP, Generally Accepted Accounting Principles). Per ulteriori informazioni, vedere [Funzionalità di valuta nei report finanziari](financial-reporting-currency-capability.md).

## <a name="how-many-types-of-currency-rate-are-there"></a>Quanti tipi di tasso di cambio esistono?

Sono disponibili tre tipi:

- **Tasso corrente**: questo tipo viene in genere utilizzato con i conti dello stato patrimoniale. Di solito è conosciuto come il *tasso di cambio corrente* e può essere il tasso dell'ultimo giorno del mese o di un'altra data prestabilita.
- **Tasso medio**: questo tipo viene in genere utilizzato con i conti del conto economico (profitti/perdite). È possibile impostare il tasso medio per calcolare la media semplice o la media ponderata.
- **Tasso storico**: questo tipo viene in genere utilizzato con utili non distribuiti, proprietà, impianti e attrezzature e conti capitale netto. Questi conti potrebbero essere richiesti in base alle linee guida FASB o GAAP.

## <a name="how-does-historical-currency-translation-work"></a>Come funziona la conversione della valuta storica?

I tassi sono specifici della data della transazione. Pertanto, ogni transazione viene convertita individualmente, in base al tasso di cambio più prossimo.

Per la conversione della valuta storica è possibile utilizzare i saldi periodo precalcolati anziché i dettagli delle singole transazioni. Questo comportamento è diverso dal comportamento della conversione del tasso corrente.

## <a name="how-does-historical-currency-translation-affect-performance"></a>In che modo la conversione della valuta storica influisce sulle prestazioni?

Quando i dati presentati nei report vengono aggiornati, potrebbe verificarsi un ritardo poiché gli importi devono essere ricalcolati controllando i dettagli della transazione. Questo ritardo viene attivato ogni volta che i tassi vengono aggiornati o vengono registrate altre transazioni. Ad esempio, se migliaia di conti sono impostati per la conversione storica un paio di volte al giorno, potrebbe verificarsi un ritardo fino a un'ora prima che i dati del report vengano aggiornati. Se invece c'è un numero contenuto di conti specifici, i tempi di elaborazione per gli aggiornamenti dei dati del report possono essere ridotti a pochi minuti.

Allo stesso modo, quando i report vengono generati utilizzando la conversione di valuta per i conti di tipo storico, vengono effettuati calcoli aggiuntivi per ogni transazione. A seconda del numero di conti, il tempo di generazione dei report può più che raddoppiare.

## <a name="what-are-the-estimated-data-mart-integration-intervals"></a>Quali sono gli intervalli di integrazione di data mart stimati?

Financial Reporter utilizza 16 attività per copiare i dati da Dynamics 365 Finance nel database di Financial Reporter. La tabella seguente elenca queste 16 attività e mostra l'intervallo che specifica la frequenza di esecuzione di ciascuna attività. Gli intervalli non possono essere modificati.

| Nome                                                       | Intervallo | Intervallo di tempo |
|------------------------------------------------------------|----------|-----------------|
| Da categorie di conti AX 2012 a Categoria di conti            | 41       | Minuti         |
| Da conti AX 2012 a conto                                | 7        | Minuti         |
| Da società AX 2012 a società                               | 300      | Secondi         |
| Da società AX 2012 all'organizzazione                          | 23       | Minuti         |
| Da combinazioni di dimensioni AX 2012 a combinazione di dimensioni    | 1        | Minuti         |
| Da valori di dimensione AX 2012 a valore di dimensione                | 11       | Minuti         |
| Da dimensioni AX 2012 a dimensione                            | 31       | Minuti         |
| Da tassi di cambio AX 2012 a tasso di cambio                    | 17       | Minuti         |
| Da anni fiscali AX 2012 ad anno fiscale                        | 13       | Minuti         |
| Da transazioni di contabilità generale AX 2012 a fatto                | 1        | Minuti         |
| Da gerarchie organizzative AX 2012 ad albero                   | 3.600    | Secondi         |
| Da scenari AX 2012 a scenario                              | 29       | Minuti         |
| Qualificatori del tipo di transazione AX 2012 al qualificatore del tipo di fatto | 19       | Minuti         |
| Attività di manutenzione                                           | 1        | Minuti         |
| Da definizioni di report MR a report finanziari AX7             | 45       | Secondi         |
| Da versioni di report MR a versioni di report finanziario AX         | 45       | Secondi         |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
