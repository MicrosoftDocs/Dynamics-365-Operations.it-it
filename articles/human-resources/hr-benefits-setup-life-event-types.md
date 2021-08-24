---
title: Configurare i tipi di eventi reali
description: Microsoft Dynamics 365 Human Resources utilizza tipi di eventi reali per definire eventi in cui è valido aggiornare l'iscrizione ai benefit per i dipendenti.
author: andreabichsel
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44a6848b4a3ed6d5dd00ade27d18cce405f09f94284de4bd39c4c9441abfcd8a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732827"
---
# <a name="configure-life-event-types"></a>Configurare i tipi di eventi reali

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources utilizza tipi di eventi reali per definire eventi in cui è valido aggiornare l'iscrizione ai benefit per i dipendenti, ad esempio sposarsi o avere un figlio. Ogni ID tipo evento reale può essere associato a un solo tipo di evento reale. Ad esempio, se si crea un ID evento reale denominato Cambio indirizzo che è associato al tipo di evento reale Modifica indirizzo dipendente, non è possibile creare un altro ID denominato Modifica indirizzo dipendente e associarlo al tipo di evento reale Modifica indirizzo dipendente. Se un tipo di evento reale non è associato a un tipo di piano, il tipo di evento reale non attiverà un evento reale. Per ulteriori informazioni, vedere [Creazione tipi di piani](hr-benefits-setup-plan-types.md).

## <a name="create-a-life-event-type"></a>Creare un tipo di evento reale

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tipi di eventi reali**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | **ID tipo di evento reale** | Identificatore univoco del tipo di evento reale. |
   | **Descrizione** | Descrizione del tipo di evento reale. |
   | **Tipo di evento reale** | Catalizzatore per l'aggiornamento dell'iscrizione ai benefit di un dipendente. Per un elenco di eventi reali, vedere [Eventi reali](hr-benefits-setup-payment-frequencies.md?life-events) di seguito. |

4. Selezionare **Salva**.

## <a name="view-attached-plans"></a>Visualizzare i piani associati

È possibile visualizzare un elenco dei piani associati al tipo di evento reale selezionato. Gli eventi reali sono associati a un tipo di piano e i tipi di piano sono associati a un piano.

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tipi di eventi reali**.

2. Selezionare **Azioni**.

3. Selezionare **Piani associati**.

## <a name="life-events"></a>Eventi reali

È possibile scegliere tra i seguenti eventi reali quando si crea un tipo di evento reale:

| Evento reale | Ubicazione | Attivazione |
| --- | --- | --- |
| **Modifica stato civile** | Lavoratore> Profilo> Informazioni personali> Stato civile| Modifica dello stato civile |
| **Modifica stato impiego** | Lavoratore > Impiego<br>Pagina Storico esperienze lavorative | Per un lavoratore con un dettaglio di impiego esistente, la creazione di un nuovo dettaglio di impiego con uno status di impiego diverso attiverà un evento reale.  Anche l'aggiornamento di un dettaglio di impiego esistente con uno stato di impiego diverso attiverà un evento reale.  |
| **Modifica indirizzo dipendente** | Lavoratore > Profilo> Indirizzi<br>Lavoratore > Informazioni personali > Contatti personali > Indirizzo | Cambio di indirizzo. L'indirizzo deve essere primario per attivare un evento reale. |
| **Modifica parte dipendente** | Lavoratore > Profilo > Informazioni personali > Contatti personali<br>Dipendente self-service | Aggiungi un contatto personale specificandolo come persona a carico e definendo **Data di inizio validità**. Aggiorna l'informazione **Data di fine validità** della persona a carico del contatto. La relazione del contatto personale deve essere figlio, coniuge, convivente o ex coniuge.  |
| **Nascita o adozione (persona a carico)** | Lavoratore > Profilo > Informazioni personali > Contatti personali<br>Self service dipendenti> Modifica dettagli personali> Contatti personali | **Data di nascita** o **Data di adozione** vengono aggiunti o aggiornati. È richiesta la **data di nascita** del bambino. |
| **Perdita di copertura (coniuge/convivente)** | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Perdita copertura | **Perdita copertura** selezionato per un contatto personale, insieme a **Data di validità** |
| Modifica impiego convivente | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Assunto | Creazione di un contatto personale e impostazione di **Assunto** su **Sì**. Aggiornamento di un contatto personale e modifica di **Assunto**.  |
| **Congedo (coniuge/convivente)** | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Congedo | Contatto personale creato e **Data di decorrenza del congedo** è definito. **Congedo** del contatto personale è aggiornato. **Data di decorrenza del congedo** del contatto personale è aggiornato.  |
| **Modifica copertura (Posizione)** | Lavoratore -> Assegnazione di posizione -> Assegnazioni di posizione lavoratore<br>Posizioni > Posizioni | Modifica della posizione nei record di assegnazione della posizione del lavoratore. Modifica dell'assegnazione del lavoratore nella posizione |
| **Modifica copertura (retribuzione)** | Lavoratore > Retribuzione > Piano fisso<br>Lavoratore > Informazioni personali> Retribuzione annuale benefit | Se Gestione benefit > Parametri condivisi Risorse umane > Benefit > Retribuzione annuale benefit non è abilitato, l'aggiornamento di Lavoratore > Retribuzione> Piano fisso creerà un evento reale. Se Gestione benefit > Parametri condivisi Risorse umane > Benefit > Retribuzione annuale benefit è abilitato, l'aggiornamento di Lavoratore > Informazioni personali > Retribuzione annuale benefit creerà un evento reale. |
| **Assistenza sanitaria per anziani (dipendente/persona a carico)** | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Data di validità assistenza sanitaria per anziani | Aggiunta o aggiornamento della **Data di validità assistenza sanitaria per anziani** per un contatto personale crea questo evento reale. |
| **Sostegno ordinato dal tribunale** | Lavoratore> Profilo> Informazioni personali> Contatti personali> Persona a carico > Sostegno ordinato dal tribunale (QMSCO / QDRO e date di validità) | Quando si crea un contatto personale, verrà creato un evento reale se **Sostegno ordinato dal tribunale** è **Sì**. Anche l'aggiornamento di **Sostegno ordinato dal tribunale** o **Data di scadenza ordinata dal tribunale** attiverà un evento reale. |
| **Decesso** | Lavoratore> Profilo> Informazioni personali> Data di decesso | Viene immessa o aggiornata una data di decesso |
| **Prova di assicurazione** | Lavoratore > Lavoratore > Versioni > Storico esperienze lavorative > Gestione date > Dettagli del benefit | **Prova di assicurabilità** è impostato su **Sì**. **Data di verifica prova di assicurabilità** è definito. |
| **Beneficiario** | Lavoratore > Profilo > Informazioni personali > Contatti personali | Viene aggiunto un contatto personale e la casella **Beneficiario** e **Data di validità** vengono riempiti. Il contatto personale deve essere di tipo **Bambino**, **Coniuge**, **Convivente**, **Fratello**, **Contatto familiare**, **Altro contatto**, **Genitore**. |
| **Assistenza sanitaria per anziani a carico del dipendente** | Lavoratore > Lavoratore > Versioni > Storico esperienze lavorative > Gestione date > Dettagli del benefit | **Idoneo assistenza sanitaria per anziani** è impostato su **Sì**. **Data idoneità assistenza sanitaria per anziani** è cambiato. |
| **Compleanno** | Gestione benefit > Elaborazione modifiche a eventi reali | Questi eventi reali sono creati da **Elaborazione modifiche a eventi reali**. Il processo analizza il periodo e la persona giuridica scelti e trova i lavoratori associati. Calcola il loro ultimo compleanno e crea un evento reale compleanno se non ne è già stato creato uno. |
| **Modifica idoneità lavoratore (non specifica agli Stati Uniti)** | Lavoratore > Impiego<br>Lavoratore > Lavoratore > Versioni > Storico esperienze lavorative | Crea un tipo di evento reale quando:<br><ul><li>Si crea un nuovo impiego e c'è un precedente impiego e il tipo di lavoratore cambia.</li><li>Si crea un nuovo dettaglio di impiego e c'è un precedente dettaglio di impiego e il tipo o la categoria di impiego cambia.</li><li>Si aggiorna un record di impiego e un diverso tipo di lavoratore è definito.</li><li>Si aggiorna un record di dettaglio di impiego e un diverso tipo o categoria di impiego è specificato.</li></ul> |
| **Nuova sostituzione regole di idoneità (non specifica agli Stati Uniti)** | Risorse umane avanzate > Benefit > Piani > Benefit > Sostituzione regole di idoneità | Utilizzo dell'elaborazione di eventi reali<br>La creazione di una sostituzione di idoneità al piano di benefit per un lavoratore attiva questo evento reale.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Modifica sostituzione regole di idoneità (non specifica agli Stati Uniti)** | Risorse umane avanzate > Benefit > Piani > Benefit > Sostituzione regole di idoneità | L'aggiornamento di **Data di inizio validità** o **Data di fine validità** per una sostituzione di idoneità a un piano di benefit attiva questo evento reale. |
| **Scadenza sostituzione regole di idoneità (non specifica agli Stati Uniti)** | Gestione benefit > Elaborazione modifiche a eventi reali  | Questi eventi reali sono creati da **Elaborazione modifiche a eventi reali**. Il processo analizza il periodo e la persona giuridica scelti e trova le sostituzioni di idoneità al piano di benefit associate. Crea eventi reali se le sostituzioni sono scadute. |
| **Nuovo piano di benefit (non specifico agli Stati Uniti)** | Risorse umane avanzate > Benefit > Piani > Nuovo | Le opzioni di idoneità sono aggiunte a un piano corrente. Viene aggiunto un nuovo piano con opzioni di idoneità associate.</br></br>Il personale delle risorse umane deve eseguire l'elaborazione dell'idoneità a eventi reali. |
| **Modifica regole di idoneità (non specifica agli Stati Uniti)** | Gestione benefit > Regole di idoneità | Utilizzo dell'elaborazione dell'idoneità a eventi reali. Registrato quando vengono modificati i seguenti valori dei record **BenefitEligibilityRule**: **UseEmplCategory**, **UseEmplStatus** o **UseEmplType**. Aggiorna solo le transazioni di eventi reali già esistenti per una regola o criteri di idoneità modificati. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]