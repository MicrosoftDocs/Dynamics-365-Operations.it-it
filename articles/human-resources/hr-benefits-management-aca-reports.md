---
title: Genera rapporti Affordable Care Act nella gestione dei vantaggi
description: Questo argomento descrive come la gestione dei benefici ti aiuta a tenere traccia delle informazioni riportate nel modulo 1.095-B e nel modulo 1.095-C per il mandato del datore di lavoro Affordable Care Act (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 24df18f428e4ca14859bc34048a6bda5e03d1b2f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464376"
---
# <a name="generate-aca-reports-in-benefits-management"></a>Genera rapporti ACA nella gestione dei vantaggi

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La gestione dei benefici ti aiuta a tenere traccia delle informazioni riportate nel modulo 1.095-B e nel modulo 1.095-C per il mandato del datore di lavoro Affordable Care Act (ACA). Come la capacità di reporting ACA nella vecchia area di lavoro **Benefici**, questa funzionalità si applica solo alle persone giuridiche negli Stati Uniti.

Per utilizzare questa funzionalità, è necessario prima attivarla in **Gestione avanzata dei vantaggi**. Per ulteriori informazioni, comprese importanti avvertenze sulla gestione dei vantaggi, vedi [Abilita o disabilita la gestione dei vantaggi](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Puoi utilizzare il reporting ACA solo dall'area di lavoro **Gestione dei vantaggi** o dalla vecchia area di lavoro **Benefici**, non da entrambe. Ad esempio, se si è passati alla gestione dei vantaggi, il reporting ACA è disponibile solo dall'area di lavoro **Gestione dei vantaggi**, non dalla vecchia area di lavoro **Benefici**.
>
> Se si passa alla gestione dei benefici nel mezzo di un anno di iscrizione, è necessario configurare correttamente i dati dei dipendenti per l'intero anno nella gestione dei vantaggi. In questo modo, ti assicuri di ricevere informazioni accurate sui rapporti per l'intero anno.

## <a name="getting-started"></a>Introduzione

Per tenere traccia delle informazioni per i moduli 1.095, creare prima uno o più gruppi di copertura Affordable Care. Questi gruppi indicano le seguenti informazioni:

- L'offerta di copertura fornita a un dipendente
- La quota del dipendente del premio mensile più basso, se il costo è superiore alla soglia di povertà federale
- L'approdo sicuro utilizzato dal datore di lavoro, se applicabile

I gruppi di copertura Affordable Care ti aiutano a gestire queste informazioni per più record di dipendenti che hanno le stesse condizioni. Puoi facilmente assegnare gruppi a uno o più dipendenti.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Crea o modifica un gruppo di copertura Affordable Care

1. Nell'area di lavoro **Gestione dei vantaggi**, seleziona **Gruppo di copertura Affordable Care**.

    ![Selezione del gruppo di copertura Affordable Care](./media/hr-benefits-management-aca-coverage-group.png)

2. Seleziona **Nuovo** per creare un nuovo gruppo di copertura Affordable Care o **Modifica** per modificare un gruppo esistente.

    ![Selezione di Nuovo o Modifica](./media/hr-benefits-management-aca-new.png)

3. Impostare i seguenti campi.

    | Campo | Descrizione |
    |---|---|
    | Nome | Immetti un nome per il gruppo. |
    | Descrizione | Immettere una descrizione del gruppo. |
    | Offerta di copertura | La copertura offerta ai dipendenti, al loro coniuge o partner e ai loro dipendenti. |
    | Quota costo dipendente | L'importo di cui il dipendente è responsabile. |
    | Sezione applicabile 4980H Safe Harbor | 4980H Safe Harbor o codice sblocco transizione. |
    | Mese iniziale piano | Seleziona il mese di calendario in cui inizia l'anno del tuo piano di benefit. |
    | Gruppo valido da | La prima data in cui questo record è valido. |
    | Gruppo valido fino a | L'ultima data in cui questo record è valido. Se non c'è una data di scadenza, inserisci **Mai**. |

    ![Creazione di un gruppo di copertura](./media/hr-benefits-management-aca-new-group.png)

4. Selezionare **Salva**.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Assegna più dipendenti a un gruppo di copertura Affordable Care

1. Nell'area di lavoro **Gestione dei vantaggi**, seleziona **Gruppo di copertura Affordable Care**.
2. Seleziona il gruppo a cui assegnare i dipendenti.
3. Seleziona **Assegnazione di massa**.

    ![Selezione dell'assegnazione di massa](./media/hr-benefits-management-aca-mass-assignment.png)

4. Seleziona i dipendenti nell'elenco, quindi seleziona **Assegna**.

    ![Assegnazione dei dipendenti selezionati a un gruppo](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Mantenimento di più versioni di opzioni di copertura

Puoi mantenere più versioni di qualsiasi gruppo di copertura. Quando qualcosa cambia nella tua organizzazione o nei vantaggi offerti, puoi mantenere aggiornate le informazioni del gruppo senza dover creare un nuovo gruppo e riassegnarvi i dipendenti.

Dopo aver creato i gruppi di copertura Affordable Care, puoi assegnarvi i dipendenti in massa. Puoi anche assegnare individualmente i dipendenti a gruppi e indicare se le informazioni ACA vengono tracciate e riportate.

Se non è necessario tenere traccia e segnalare le informazioni ACA per un dipendente, puoi impostare l'opzione **Copertura del rapporto** su **No**. Ad esempio, potresti avere dipendenti part-time che non richiedono rapporti ACA.

### <a name="override-default-values-for-an-employee"></a>Sostituisci i valori predefiniti per un dipendente

Per i dipendenti assegnati a un gruppo di copertura Affordable Care, è possibile modificare le seguenti opzioni per tutti i mesi che richiedono valori diversi:

- Offerta di copertura
- Quota costo dipendente
- Sezione applicabile 4980H Safe Harbor

> [!NOTE]
> Per i rapporti ACA 2020, devi segnalare sia i codici di avviamento postale di lavoro che quelli di casa nel modulo 1.095-C. I valori vengono inseriti automaticamente, in base alle posizioni attive correnti. Se una delle due località era diversa durante qualsiasi parte dell'anno, è necessario sostituire il valore. Il campo **CAP** (riga 17) del report 1.095-C è riempita solo se il codice **Offerta di copertura** contiene **1L** tramite **1Q**, come segue:
>
> - **1L, 1M o 1N:** il codice CAP della residenza principale
> - **1O, 1P, 1Q:** il CAP del luogo di lavoro principale

Per inserire eccezioni per qualsiasi valore di un gruppo di copertura Affordable Care, segui questi passaggi.

1. Nell'area di lavoro **Gestione personale**, selezionare **Collegamenti**, quindi selezionare **Lavoratori**.
2. Selezionare il dipendente dall'elenco.
3. Nella scheda **Impiego**, nella sezione **Ulteriori informazioni**, seleziona **Copertura Affordable Care**.

    ![Modifica delle opzioni per un dipendente](./media/hr-benefits-management-aca-change-single-employee.png)

4. Seleziona **Modifica**.
5. Per ogni mese che richiede modifiche, seleziona la casella di controllo **Ignora predefinito**, quindi modifica gli altri valori come richiesto.

    ![Sovrascrittura dei valori predefiniti](./media/hr-benefits-management-aca-override-default.png)

6. Selezionare **Salva**.

## <a name="report-health-care-coverage"></a>Report di copertura delle spese mediche

Devi tenere traccia di qualsiasi copertura sanitaria autoassicurata e sponsorizzata dal datore di lavoro per i dipendenti a tempo pieno e part-time. Includere ogni dipendente, insieme alle persone a carico, nel report 1.095-C per i mesi in cui sono stati coperti.

Per indicare se è necessario segnalare un piano di benefit, attieniti alla seguente procedura.

1. Nell'area di lavoro **Gestione benefit**, seleziona **Piani di benefit**.
2. Seleziona il piano di benefit da segnalare.
3. Seleziona **Modifica**.
4. Impostare l'opzione **Segnalato in Affordable Care Act** su **Sì**.

    ![Report di copertura delle spese mediche](./media/hr-benefits-management-aca-report-coverage.png)

5. Selezionare **Salva**.

Se un dipendente sceglie la copertura sanitaria per un dipendente, il periodo di copertura del dipendente è determinato dalla data in cui il dipendente è stato iscritto o rimosso. Le date di copertura per le persone a carico vengono calcolate automaticamente in base al periodo in cui la persona a carico era idonea e attiva in un piano durante l'anno di iscrizione.

## <a name="generate-1095-b-and-1095-c-forms"></a>Genera moduli 1095-B e 1095-C

Puoi inoltre generare i moduli ACA 1.095-B e 1.095-C, quindi distribuirli a ciascuno dei dipendenti. Puoi inoltre generare elettronicamente il modulo 1.095-C e i file di trasmissione 1.094-C corrispondenti da inviare all'Internal Revenue Service (IRS).

1. Nell'area di lavoro **Gestione dei benefit**, seleziona **Modulo ACA 1.095-B** o **Modulo ACA 1.095-C**.
2. Modifica i parametri in base alle esigenze, quindi seleziona **OK**.

    > [!NOTE]
    > Quando si stampano moduli 1.095-C per più di 500 dipendenti, si riceveranno più di un file PDF. Ti consigliamo di aumentare il valore del campo **Dimensioni massime del file in megabyte** nella pagina **Parametri di gestione dei documenti** su **150**. Per aprire rapidamente quella pagina, puoi utilizzare il campo di ricerca sulla barra di navigazione.
    >
    > ![Modifica delle dimensioni massime del file](./media/hr-benefits-management-aca-maximum-file-size.png)

3. Per controllare lo stato dei tuoi report e visualizzarli, utilizza il campo di ricerca sulla barra di navigazione per aprire la pagina **Processi di creazione report elettronici**.

    ![Ricerca della pagina dei lavori di creazione di report elettronici](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Seleziona il report da visualizzare, quindi seleziona **Visualizza file**.

    ![Visualizzazione dei file](./media/hr-benefits-management-aca-show-files.png)

5. Selezionare **Apri**.

    ![Apertura di un file](./media/hr-benefits-management-aca-open-file.png)

6. Dalla barra di notifica che appare nella parte inferiore della finestra del browser, apri il file zip, quindi seleziona il report. Puoi visualizzare o stampare il file PDF.

    ![Modulo 1.095-C di esempio](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>Visualizza le informazioni sulla copertura ACA

La pagina **Copertura Affordable Care del lavoratore** visualizza le seguenti informazioni:

- Dipendenti assegnati a ciascun gruppo di copertura
- Dipendenti che non devono essere inclusi in un report
- Dipendenti non assegnati

Per visualizzare queste informazioni, attenersi alla seguente procedura.

1. Nell'area di lavoro **Gestione dei vantaggi**, seleziona **Copertura Affordable Care del lavoratore**.
2. Nel campo **Nome gruppo** seleziona un gruppo.

    ![Visualizzazione della copertura ACA](./media/hr-benefits-management-aca-view-coverage.png)

Se uno qualsiasi dei valori predefiniti del gruppo di copertura Affordable Care viene sovrascritto, un asterisco verrà visualizzato accanto al valore modificato. Se i valori per tutti i 12 mesi sono uguali e non sono stati ignorati, il valore verrà visualizzato nella colonna **Tutti i 12 mesi**.

Puoi visualizzare i dipendenti contrassegnati come non soggetti a report ACA e che non richiedono un modulo 1.095-C. Nel campo **Filtra per**, seleziona **Non segnalabile ACA**.

Puoi visualizzare i dipendenti che non sono assegnati a un gruppo o che sono assegnati a un gruppo scaduto. Nel campo **Filtra per**, seleziona **Gruppo non assegnato o scaduto**.

### <a name="export-to-excel"></a>Esporta in Excel

Per esportare uno qualsiasi degli elenchi in Microsoft Excel, segui questi passaggi.

1. Selezionare il pulsante **Apri in Microsoft Office**.
2. Seleziona **Tabella temporanea di Human Resources HCM per uso interno**.
3. Selezionare **Scarica**.

### <a name="view-aca-reportable-dependents"></a>Visualizza i dipendenti segnalabili da ACA

Se devi segnalare le persone coperte perché fornisci una copertura autoassicurata, puoi visualizzare le persone a carico che sono coperte da piani di benefit che sono contrassegnati come **ACA segnalabile**. Nel riquadro azioni, seleziona **Visualizza copertura dipendente**.

![Visualizzazione della copertura dipendente](./media/hr-benefits-management-aca-view-dependent-coverage.png)

Vengono visualizzate le informazioni sulla copertura per le persone a carico del dipendente.

![Copertura dei dipendenti](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> La pagina mostra solo i piani di benefit contrassegnati come **Segnalabile ACA**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]