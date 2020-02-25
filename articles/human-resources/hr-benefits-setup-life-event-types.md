---
title: Configurare tipi di eventi reali
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 93c4285a1918cb625a01b4523195cacdee1170b4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009602"
---
# <a name="configure-life-event-types"></a>Configurare tipi di eventi reali

[!include [banner](includes/preview-feature.md)]

Microsoft Dynamics 365 Human Resources utilizza tipi di eventi reali per definire eventi in cui è valido aggiornare l'iscrizione ai benefit per i dipendenti. Ad esempio, sposarsi o avere un figlio. Ogni ID tipo evento reale può essere associato a un solo tipo di evento reale. Ad esempio, se si crea un ID evento reale denominato Cambio indirizzo che è associato al tipo di evento reale Modifica indirizzo dipendente, non è possibile creare un altro ID denominato Modifica indirizzo dipendente e associarlo al tipo di evento reale Modifica indirizzo dipendente. 

Dopo aver creato tipi di eventi reali, è necessario associarli ai tipi di piano. Per ulteriori informazioni, vedere [Creazione tipi di piani](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > Quando si crea un evento reale, è necessario associarlo a un tipo di piano. Per ulteriori informazioni, vedere [Creazione tipi di piani](hr-benefits-setup-life-event-types.md).

## <a name="create-a-life-event-type"></a>Creare un tipo di evento reale

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tipi di eventi reali**.

2. Selezionare **Nuovo**.

3. Specificare i valori per i seguenti campi:

   | Campo | Descrizione |
   | --- | --- |
   | ID tipo di evento reale | Identificatore univoco del tipo di evento reale. |
   | Descrizione | Descrizione del tipo di evento reale. |
   | Tipo di evento reale | Catalizzatore per l'aggiornamento dell'iscrizione ai benefit di un dipendente. Per un elenco di eventi reali, vedere [Eventi reali](hr-benefits-setup-payment-frequencies.md?life-events) di seguito. |

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
| Modifica stato civile | Lavoratore> Profilo> Informazioni personali> Stato civile| Modifica dello stato civile |
| Modifica stato impiego | <ul><li>Lavoratore > Impiego</li><li>Pagina Storico esperienze lavorative</li></ul> | Modifica della posizione lavorativa |
| Modifica indirizzo dipendente | <ul><li>Lavoratore > Profilo> Indirizzi </li><li>Lavoratore > Informazioni personali > Contatti personali > Indirizzo</li></ul> Indirizzo aggiunto, modificato o eliminato |
| Modifica persona a carico | <ul><li>Lavoratore > Profilo > Informazioni personali > Contatti personali > Aggiungi o elimina persona a carico</li><li>Dipendente self-service</li></ul> | Persona a carico aggiunta o eliminata. La relazione del contatto personale deve essere figlio, coniuge, convivente o ex coniuge. L'aggiornamento del valore **Data di inizio validità** attiva l'evento reale. Se non si aggiorna quella data, non viene attivato alcun evento reale. |
| Nascita o adozione (persona a carico) | <ul><li>Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico</li><li>Dipendente self-service</li></ul> | Campo **Data adozione** riempito. È richiesta la data di nascita del bambino. |
| Perdita di copertura (coniuge/convivente) | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Perdita copertura | **Perdita copertura** selezionato per un contatto personale, insieme a **Data di validità** |
| Modifica impiego convivente | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Impiegato. | <ul><li>Record Dettagli persona a carico creato e casella **Contatto personale impiegato** = Sì</li><li>Casella **Contatto personale impiegato** modificata (Sì o No)</li></ul> |
| Congedo (coniuge/convivente) | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Congedo | <ul><li>Record Dettagli persona a carico creato e **EhrLOAEffectiveDate** riempito</li><li>**personPrivateDetails.EhrIsLOA** modificato (Sì o No)</li><li>**personPrivateDetails.EhrLOAEffectiveDate** modificato</li></ul> |
| Modifica copertura (Posizione) | <ul><li>Lavoratore -> Assegnazione di posizione -> Assegnazioni di posizione lavoratore</li><li>Posizioni > Posizioni</li></ul> | <ul><li>Modifica della posizione nei record di assegnazione della posizione del lavoratore</li><li>Modifica dell'assegnazione del lavoratore nella posizione</li></ul> |
| Modifica copertura (retribuzione) | Lavoratore > Retribuzione > Piano fisso | La retribuzione benefit annuale viene ricalcolata automaticamente quando si modifica la retribuzione |
| Assistenza sanitaria per anziani (dipendente/persona a carico) | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Data di validità assistenza sanitaria per anziani | Non attivata automaticamente quando un contatto personale inserisce una data di validità. |
| Sostegno ordinato dal tribunale | Lavoratore> Profilo> Informazioni personali> Contatti personali> Persona a carico > Sostegno ordinato dal tribunale (QMSCO / QDRO e date di validità) | Non attiva alcun aggiornamento automatico. Non influisce sull'idoneità; registra un evento reale. |
| Decesso | Lavoratore> Profilo> Informazioni personali> Data di decesso | Viene immessa una data di decesso |
| Prova di assicurazione | <ul><li>Lavoratore > Lavoratore > Versioni > Storico esperienze lavorative > Gestione date > Dettagli del benefit</li><li> Lavoratore > Impiego > Dettagli benefit > Data di verifica</li></ul> | <ul><li>Un lavoratore inserisce una data di verifica</li><li>Un lavoratore imposta il campo EvidenceOfInsurability su **Sì**</li></ul> |
| Beneficiario | Lavoratore > Profilo > Informazioni personali > Contatti personali | Viene aggiunto un contatto personale e la casella **Beneficiario** e **Data di validità** vengono riempiti. Il contatto personale deve essere di tipo **Bambino**, **Sposa**, **Convivente**, **Fratello**, **Contatto familiare**, **Altro contatto**, **Genitore**, **Immobili beneficiario**, **Organizzazione beneficiario** o **Fiducia beneficiario**. |
| Assistenza sanitaria per anziani a carico del dipendente | Lavoratore > Lavoratore > Versioni > Storico esperienze lavorative > Gestione date > Dettagli del benefit | <ul><li>**EhrMedicareEligibilityDate** è cambiato</li><li>**MedicareEligibile** è impostato su **Sì**</li></ul> |
| Compleanno | Lavoratore > Profilo > Informazioni personali > Contatti personali > Dettagli persona a carico > Data di nascita | Una data di nascita viene aggiunta o aggiornata (non dopo l'elaborazione delle modifiche all'evento reale). Esempio: se **Opzioni di idoneità per contatti personali** per un bambino è impostato su Età: 26 in Impostazione > Benefit > Opzioni di idoneità per contatti personali e se il personale delle risorse umane esegue l'elaborazione delle modifiche agli eventi reali un giorno qualsiasi dopo che la persona a carico ha compiuto 26 anni, viene visualizzato un messaggio che avvisa che quella persona non ha più diritto alla copertura. |
| Modifica idoneità lavoratore (non specifica agli Stati Uniti) | <ul><li>Lavoratore > Impiego</li><li>Lavoratore > Lavoratore > Versioni > Storico esperienze lavorative</li></ul> | <ul><li>Il tipo di dipendente, la categoria di impiego o i cinque campi di idoneità definibili dall'utente cambiano</li><li>**HcmEmploymentDetail.EhrEmploymentType** cambia (elaborato solo per record di dettagli impiego *modificati*, non elaborato per *nuovi* record di impiego, come riassunzione e fine rapporto)</li></ul> |
| Nuova sostituzione regole di idoneità (non specifica agli Stati Uniti) | Risorse umane avanzate > Benefit > Piani > Benefit > Sostituzione regole di idoneità | Utilizzo dell'elaborazione di eventi reali | EhrBenefitEligibilityRuleOverride.ValidFrom |
| Modifica sostituzione regole di idoneità (non specifica agli Stati Uniti) | Risorse umane avanzate > Benefit > Piani > Benefit > Sostituzione regole di idoneità | Utilizzo dell'elaborazione di eventi reali (rileva solo le modifiche ai campi **ValidFrom** e **ValidTo** per la sostituzione delle regole di idoneità) |
| Scadenza sostituzione regole di idoneità (non specifica agli Stati Uniti) | Risorse umane avanzate > Benefit > Piani > Benefit > Sostituzione regole di idoneità | Utilizzo dell'elaborazione delle modifiche a eventi reali. Ad esempio, se si modifica la scadenza della sostituzione delle regola di idoneità di un piano affinché sia oggi alle 17, in qualsiasi momento dopo le 17 o nei giorni seguenti e quindi si esegue l'elaborazione delle modifiche agli eventi reali, viene visualizzato un messaggio indicante che la sostituzione delle regole di idoneità è scaduta. |
| Nuovo piano di benefit (non specifico agli Stati Uniti) | Risorse umane avanzate > Benefit > Piani > Nuovo | <ul><li>Le opzioni di idoneità sono aggiunte a un piano corrente</li><li>Viene aggiunto un nuovo piano con opzioni di idoneità associate</li></ul></br></br>Il personale delle risorse umane deve eseguire l'elaborazione dell'idoneità a eventi reali. |
| Modifica regole di idoneità (non specifica agli Stati Uniti) | Risorse umane avanzate > Benefit > Regole/opzioni > Regole di idoneità | Utilizzo dell'elaborazione dell'idoneità a eventi reali. Registrato quando vengono modificati i seguenti valori dei record **EhrBenefitEligibilityRule**: **UseEmplCategory**, **UseEmplStatus** o **UseEmplType**. Aggiorna solo le transazioni di eventi reali già esistenti per una regola o criteri di idoneità modificati. |
