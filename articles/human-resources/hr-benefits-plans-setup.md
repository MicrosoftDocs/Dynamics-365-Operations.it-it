---
title: Creare un piano di benefit
description: Questo argomento mostra come impostare i piani di benefici in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cf5f2443b1fc070d2b3030000f2980e92ef3004c
ms.sourcegitcommit: 4f9c889e5cf72f34dd9746a322f8c0d6b983037b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2021
ms.locfileid: "7417528"
---
# <a name="create-a-benefit-plan"></a>Creare un piano di benefit

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento mostra come impostare i piani di benefici in Dynamics 365 Human Resources.

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Selezionare **Nuovo**.

3. Nella scheda **Generale** specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Pianifica** | Identificatore univoco per il piano. |
   | **Descrizione** | Descrizione del piano. |
   | **Tipo di piano** | Quando si crea un nuovo piano, è necessario specificare il tipo di piano. Un tipo di piano è un raggruppamento di alto livello di specifici tipi di benefit. Ogni tipo di piano specifica se un dipendente può iscriversi a più piani di quel tipo, se i contatti sono beneficiari o persone a carico e definisce le opzioni di copertura. È possibile creare nuovi tipi di piano personalizzati per soddisfare le esigenze delle offerte di benefit. I principali tipi di piano di benefit sono: <ul><li>401.000</li><li>ADD</li><li>Dentale</li><li>Fitness</li><li>FSA</li><li>Reale</li><li>LTD</li><li>Medico</li><li>PTO</li><li>STD</li><li>Visione</li></ul> |
   | **Codice tipo di piano** | Codice del tipo di piano. |
   | **Programma** | Specifica un programma a cui assegnare facoltativamente il piano. |
   | **Pacchetto** | Specifica un pacchetto a cui assegnare facoltativamente il piano. |
   | **Generale** | Specifica se il piano è il piano generale dell'aggregazione a cui è assegnato. |
   | **Ora e data di inizio validità** | Data e ora di inizio validità del piano. Il valore predefinito è la data di sistema corrente. |
   | **Ora e data di fine validità** | Data e ora di fine validità del piano. 31/12/2154 (che significa mai) è il valore predefinito. |

4. Nella scheda **Configurazione**, specificare i valori per i seguenti campi, a seconda del tipo di piano che si sta creando:

   | Tipo di piano | Campo | Descrizione |
   | --- | --- | --- |
   | Medico (medico, dentale, visione, HMO) | COBRA | Specifica se il piano è idoneo per COBRA (Consolidated Omnibus Budget Reconciliation Act). |
   | Medico (medico, dentale, visione, HMO) | HIPAA | Specifica se il piano è idoneo per HIPAA (Health Insurance Portability and Accountability Act). |
   | Medico (medico, dentale, visione, HMO)<br><br>Altro (PTO, Fitness)<br><br>Altro<br><br>Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria)<br><br>Risparmio (ad esempio, 401(k))<br><br>FSA | Lordo di imposte idoneo | Specifica se è possibile versare contributi per il piano prima dell'applicazione delle imposte. |
   | Medico (medico, dentale, visione, HMO)<br><br>Altro (PTO, Fitness)<br><br>Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria)<br><br>Risparmio (ad esempio, 401(k))<br><br>FSA | Netto di imposte idoneo | Specifica se è possibile versare contributi per il piano dopo l'applicazione delle imposte. |
   | Medico (medico, dentale, visione, HMO)<br><br>Altro (PTO, Fitness)<br><br>Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria)<br><br>Risparmio (ad esempio, 401(k))<br><br>FSA | Collaboratore | Specifica chi versa contributi per il piano: il dipendente, il datore di lavoro o entrambi. |
   | Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Copertura minima | L'importo minimo di copertura assicurativa richiesto per il piano. |
   | Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Copertura massima | L'importo massimo di copertura assicurativa richiesto per il piano. |
   | Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Usa incrementi di copertura | Specifica se convalidare che l'importo di copertura corrisponde a un importo incrementale valido. |
   | Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Importo incrementale | L'importo incrementale della copertura assicurativa per il piano. Ad esempio, se l'importo incrementale è 1.000, un dipendente non può avere $200.500 di assicurazione; il valore deve essere arrotondato a $201.000 o a $200.000. |
   | Disabilità a lungo termine<br><br>ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Direzione incrementale | Specifica la direzione di arrotondamento (per eccesso o difetto) quando l'importo di copertura non soddisfa il valore dell'importo incrementale. |
   | ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Prova di assicurabilità | Specifica se un dipendente deve fornire una prova di assicurabilità. |
   | ADD (assicurazione sulla vita di base, assicurazione sulla vita volontaria) | Periodo | Importo nella valuta di contabilizzazione. Questo campo è attivo solo se è selezionata la casella di controllo Prova di assicurabilità. |
   | Risparmio (ad esempio, 401(k))<br><br>FSA | Contribuzione annuale minima | L'importo di contribuzione minimo richiesto per il piano. |
   | Risparmio (ad esempio, 401(k))<br><br>FSA | Contribuzione annuale massima | L'importo di contribuzione massimo richiesto per il piano. |
   | Risparmio (ad esempio, 401(k)) | Importo annuale massimo datore di lavoro | L'importo massimo che un datore di lavoro può versare per un piano di risparmio dei dipendenti durante un periodo di benefit. È necessario selezionare la casella di controllo Corrispondenza datore di lavoro per utilizzare questo campo. |
   | Risparmio (ad esempio, 401(k)) | Corrispondenza datore di lavoro | Specifica se il datore di lavoro versa contributi per un piano di risparmio dei dipendenti. |
   | Risparmio (ad esempio, 401(k)) | Percentuale corrispondenza datore di lavoro | La percentuale dei contributi di un dipendente che il datore di lavoro corrisponderà. |
   | Risparmio (ad esempio, 401(k)) | Limite dati corrispondenza datore di lavoro | La percentuale massima che il datore di lavoro corrisponderà. Ad esempio, se un datore di lavoro corrisponderà il 100% delle contribuzioni del dipendente fino al 6% della retribuzione del dipendente, il limite di corrispondenza del datore di lavoro è del 6%. |

5. Nella scheda **Impostazione** specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Consenti/continua iscrizione** | Specifica se i dipendenti possono iscriversi al piano se soddisfano i requisiti di idoneità.</br></br>Se impostato su No, il piano non sarà disponibile per i dipendenti durante l'elaborazione dell'idoneità. |
   | **Iscrizione automatica dall'anno precedente** | Specifica se iscrivere automaticamente nel piano un dipendente idoneo iscritto durante l'anno precedente. |
   | **Iscrizione automatica per impostazione predefinita** | Specifica se selezionare il piano per l'iscrizione per impostazione predefinita. Il piano non è obbligatorio, quindi il dipendente può modificare la selezione predefinita. |
   | **Chiuso per nuove iscrizioni** | Specifica se limitare il piano solo ai dipendenti idonei iscritti al piano l'anno precedente. |
   | **Piano obbligatorio** | Specifica se iscrivere automaticamente i dipendenti al piano. I dipendenti non possono modificare la selezione. |
   | **Data di inizio validità** | La data in cui il piano è stato creato nella società. |
   | **Conto fornitore** (fornitore benefit) | Il fornitore a cui l'azienda paga i premi per il piano. |
   | **Nome** (fornitore benefit) | Nome del fornitore. |
   | **Riferimento fornitore** (fornitore benefit) | Il riferimento del fornitore per il piano. Ad esempio, il numero del piano di gruppo dell'azienda. |
   | **Altro riferimento** (fornitore benefit) | Un altro riferimento del fornitore per il piano. Ad esempio, il numero di conto dell'azienda. |
   | **Valuta** (fornitore benefit) | La valuta utilizzata per pagare i premi al fornitore. |
   | **Conto spese** (fornitore benefit) | Il conto di contabilità generale utilizzato come conto spese per i premi del piano. |
   | **Conto fornitore** (amministratore benefit) | Il fornitore retribuito dall'azienda per amministrare il piano. Se il piano è auto-amministrato, lasciare vuoto il campo. |
   | **Nome** (amministratore benefit) | Nome del fornitore amministratore dei benefit. |
   | **Riferimento fornitore** (amministratore benefit) | Il riferimento del fornitore amministratore per il piano. |
   | **Altro riferimento** (amministratore benefit) | Un altro riferimento del fornitore amministratore per il piano. |
   | **Valuta** (amministratore benefit) | La valuta utilizzata per pagare l'amministratore dei benefit. |
   | **Conto spese** (amministratore benefit) | Il conto di contabilità generale utilizzato come conto spese per i costi associati all'amministrazione del piano. |

6. Nella scheda **Filtri**, filtrare come necessario. È possibile filtrare in base ai seguenti campi:

   - **Business Unit**
   - **Reparto**
   - **Persona giuridica**
   - **Ubicazione**
   - **Posizione**

7. Nella scheda **Regole di idoneità** specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **Numero riga** | Numero di riga della regola di idoneità. |
   | **Regola di idoneità** | Una regola di idoneità da applicare al piano di benefit. Questa regola di idoneità verrà applicata al tipo di azione corrispondente e associata al periodo di attesa e alle detrazioni specificati per la copertura. |
   | **Tipo di azione** | L'azione per applicare la regola di idoneità a: iscrizione a benefit o scadenza dei benefit. |
   | **Periodo di attesa copertura** | Un valore dal modulo Periodi di attesa. Il periodo di attesa della copertura determina il numero di giorni o mesi di attesa di un dipendente per la copertura o la scadenza dei benefit in base ai criteri della regola di idoneità e al tipo di azione. |
   | **Periodo di attesa detrazione** | Un valore dal modulo Periodi di attesa. Il periodo di attesa della detrazione determina il numero di giorni o mesi di attesa di un dipendente per le detrazioni dei benefit dalla busta paga in base ai criteri della regola di idoneità e al tipo di azione. |

8. Selezionare **Salva**.

## <a name="view-enrolled-workers"></a>Visualizzare i lavoratori iscritti

È possibile visualizzare i lavoratori che sono iscritti a un piano di benefit selezionato.

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Nella scheda **Benefit** nella barra di spostamento seleziona **Lavoratori iscritti**.

## <a name="attach-coverage-options"></a>Collega opzioni di copertura

È possibile aggiungere opzioni di copertura al piano di benefit selezionato. L'associazione delle opzioni di copertura raggruppa il tasso e la detrazione per un'opzione di copertura.  Esempio: per un piano medico, l'utente selezionerebbe un'opzione di copertura familiare.  Dovrebbe quindi selezionare il tasso Famiglia per il piano associato (impostato in Impostazione tasso) e la detrazione per il piano associato (impostato in Impostazione tasso). Ciò fornisce il costo per il datore di lavoro e il dipendente per una copertura selezionata. Successivamente si ripeterebbe il processo per una copertura Dipendente+1 o una copertura Dipendente.

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Nella scheda **Benefit** nella barra di spostamento seleziona **Collega opzioni di copertura**.

## <a name="override-eligibility-rules"></a>Sostituire le regole di idoneità

È possibile aggiungere lavoratori a un piano come eccezioni alle regole di idoneità. Ogni lavoratore aggiunto sarà idoneo per il piano di benefit.

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Nella scheda **Benefit** nella barra di spostamento seleziona **Sostituzione regole di idoneità**.

## <a name="view-attached-periods"></a>Visualizzare i periodi associati

È possibile visualizzare un elenco dei periodi di benefit disponibili.

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Seleziona la scheda **Periodi** nella barra di spostamento.

## <a name="view-plan-description"></a>Visualizzare la descrizione del piano

È possibile fornire una descrizione del piano per aiutare i dipendenti a scegliere i benefit. La descrizione del piano immessa qui è visualizzata in Dipendente self-service quando si passa il mouse nell'elenco delle opzioni di copertura.

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Nella scheda **Benefit** nella barra di spostamento seleziona **Descrizione piano**.

## <a name="view-flex-credit-programs"></a>Visualizza programmi di crediti flessibili

1. Nell'area di lavoro **Gestione benefit**, sotto **Piani**, selezionare **Piani di benefit**.

2. Nella scheda **Benefit** nella barra di spostamento seleziona **Programmi di crediti flessibili**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
