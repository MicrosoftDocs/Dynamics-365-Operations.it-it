---
title: Novità o modifiche in Dynamics 365 Talent (27 febbraio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: afa1044c8adc9566149e20ade57e771b50d9c53f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529140"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-27-2019"></a>Novità o modifiche in Dynamics 365 Talent (27 febbraio 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2163

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Aggiunta opzione Amministrazione sistema al menu Campi personalizzati

Al menu **Campi personalizzati** è stata aggiunta la voce di menu **Amministrazione sistema** per l'accesso a tale area di lavoro.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Rimozione delle opzioni di importazione e creazione per nuove applicazioni mobili

Attualmente, le nuove app per dispositivi mobili non possono essere create in Talent. L'opzione per creare nuove esperienze mobili è stata rimossa dal menu **App per dispositivi mobili**.

### <a name="variable-compensation-award-dmf-entity"></a>Premi retributivi variabili (entità DMF)

In questa versione, un'entità DMF **Premi retributivi variabili** è ora disponibile per l'esportazione.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Indirizzi britannici visualizzati nella pagina di analisi della gestione del personale come indirizzi svizzeri

In questa versione, gli indirizzi sono visualizzati per città. Questa versione corregge i problemi in cui le visualizzazioni erano rappresentate erroneamente nell'ubicazione del dipendente.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>Il report Power BI sulla forza lavoro presenta un errore quando la data di anzianità di un lavoratore è un giorno bisesto

Una correzione è stata effettuata in Microsoft Power BI per le date di anzianità che cadono il 29 febbraio.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>Le opzioni Retribuzione fissa dipendente, Premi retributivi variabili dipendente, Piani variabili dipendenti (iscrizioni) consentono l'uso di campi personalizzati

Campi personalizzati possono essere aggiunti per Retribuzione fissa dipendente, Premi retributivi variabili dipendente e Piani variabili dipendente (iscrizioni). È ora possibile tenere traccia di ulteriori informazioni sui piani di retribuzione fissa e variabile, oltre alle informazioni disponibili per impostazione predefinita. I campi personalizzati possono essere immessi e aggiornati tramite l'interfaccia utente o le entità fornite.

### <a name="other-miscellaneous-bug-fixes"></a>Altre correzioni di bug varie

Questa versione include altre correzioni di bug minori.

## <a name="coming-soon"></a>Presto disponibili

### <a name="advanced-compensation-security-fixed-and-variable"></a>Protezione retribuzione avanzata (fissa e variabile)

In molte organizzazioni, i responsabili retribuzioni e benefit potrebbero accedere solo a specifici record di retribuzione. Questi record potrebbero essere utilizzati da dirigenti o dipendenti regionali. Questa modifica consentirà alle Risorse umane di gestire i piani di retribuzione per differenti popolazioni di dipendenti nell'organizzazione. I ruoli di sicurezza che possono essere assegnati a piani fissi e variabili determineranno l'accesso a tali piani e ai dati dei dipendenti ad essi correlati (ad esempio, informazioni sugli stipendi e record di premi). Solo i ruoli con l'accesso specificato potranno elaborare la retribuzione per quei dipendenti.

### <a name="platform-update-24-for-finance-and-operations"></a>Update 24 della piattaforma per Finance and Operations

Per ulteriori informazioni sull'aggiornamento 24 della piattaforma per Microsoft Dynamics 365 Finance and Operations (marzo 2019), vedere [Funzionalità di anteprima nell'aggiornamento 24 della piattaforma Finance and Operations (marzo 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Rendere la retribuzione fissa dei dipendenti disponibile per assegnazioni di posizione future

È tipico per i dipendenti che entrano a far parte di un'organizzazione avere una data di inizio futura. Questa modifica consentirà di definire la retribuzione fissa dei dipendenti che hanno assegnazioni di posizione future.

## <a name="known-issues"></a>Problemi noti

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance"></a>Modifiche al modello di integrazione Core HR ( Talent Common Data Service in Finance)
Il modello per Core HR è stato aggiornato a un "modello di query avanzate". Pertanto, per impostazione predefinita, la query avanzata sarà disponibile per i progetti creati utilizzando il modello. Inoltre, tutte le funzioni di mapping predefinite saranno visibili solo nell'editor di query avanzate (le funzioni di mapping predefinite vengono visualizzate come "FN" nei mapping).

Per ulteriori informazioni sugli errori di mapping, vedere [Novità o modifiche in Dynamics 365 Talent: Core HR (14 dicembre 2018)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Per utilizzare il nuovo modello, creare un nuovo progetto e selezionare il nuovo modello di integrazione di Talent.

Per aggiornare il modello esistente, effettuare le seguenti operazioni.

1. Aggiornare i mapping seguenti:

    - **Posizioni lavorative a Posizioni**: rimuovere questo mapping.
    - **Assegnazione processo padre Posizioni lavorative a Posizioni**: rimuovere questo mapping.
    - **Posizioni lavorative a Posizione base:** aggiungere un nuovo mapping dall'entità **Posizioni lavorative** di Common Data Service all'entità **Posizione di base** di Finance and Operations. Spostarlo nella posizione 7 nella sequenza.

        [![Mapping Posizioni lavorative a Posizione di base](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Posizioni a Dettagli posizione:** aggiungere un nuovo mapping dall'entità **Posizioni lavorative** di Common Data Service all'entità **Dettagli posizione** di Finance and Operations. Spostarlo nella posizione 8 nella sequenza.

        [![Mapping Posizioni lavorative a Dettagli posizione](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Posizioni a Durate posizione:** aggiungere un nuovo mapping dall'entità **Posizioni lavorative** di Common Data Service all'entità **Durate posizione** di Finance and Operations.

        [![Mapping Posizioni lavorative a Durate posizione](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Posizioni a Gerarchie posizioni:** aggiungere un nuovo mapping dall'entità **Posizioni lavorative** di Common Data Service all'entità **Gerarchie posizioni** di Finance and Operations. Selezionare **Query avanzata** per rendere la query avanzata disponibile per il progetto.

       [![Pulsante Query avanzata](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Aggiungere i mapping seguenti.
    
    [![Mapping](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Selezionare il collegamento **Query avanzata e Filtro avanzato** accanto al campo **Cerca**.  

    3. Trovare la colonna **cdm_parentjobpositionid.cdm_jobpositionnumber** e selezionare il pulsante freccia giù alla destra della stessa.

    4. Nella finestra di dialogo visualizzata, selezionare **Rimuovi vuoti**.

    5. Selezionare **Aggiungi colonna \> Aggiungi colonna condizionale** per aggiungere una conversione del valore predefinito per HIERARCHYTYPENAME.

        [![Comando Aggiungi colonna condizionale](./media/Add-column.png)](./media/Add-column.png)

    6. Nella finestra di dialogo **Aggiungi colonna condizionale**, immettere **HIERARCHYTYPENAME** come nome della nuova colonna.
    7. Nella parte **Se** della condizione, selezionare un campo, utilizzare **uguale a** come relazione e immettere qualsiasi valore. Nelle parti **_Quindi_* e **Altrimenti** della condizione, specificare cosa deve essere il valore predefinito. In questo caso, immettere **Riga** in entrambe le parti.

        [![Finestra di dialogo Aggiungi colonna condizionale](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Selezionare **OK** per chiudere la finestra dialogo **Filtro e query avanzati**.
    9. Nella pagina **Attività mapping**, selezionare la nuova colonna come origine per creare un altro mapping per HIERARCHYTYPENAME.

        [![Mapping](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]