---
title: Generare report Affordable Care Act (ACA)
description: È disponibile una funzionalità che consente ai dipendenti che devono tenere traccia delle informazioni dichiarate sui moduli 1095-B e 1095-C a supporto della parte relativa al mandato del datore di lavoro dell'Affordable Care Act. Questa funzionalità è abilitata solo per le persone giuridiche negli Stati Uniti.
author: andreabichsel
manager: AnnBe
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: f03e414683465e7275d6c48a843306abefbacaf0
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1505843"
---
# <a name="generate-affordable-care-act-aca-reports"></a>Generare report Affordable Care Act (ACA)

[!include [banner](includes/banner.md)]

È disponibile una funzionalità che consente ai dipendenti che devono tenere traccia delle informazioni dichiarate sui moduli 1095-B e 1095-C a supporto della parte relativa al **mandato del datore di lavoro** dell'Affordable Care Act. Questa funzionalità è abilitata solo per le persone giuridiche negli Stati Uniti.

## <a name="getting-started"></a>Introduzione
Quando si inizia a tenere traccia delle informazioni da dichiarare nei moduli 1095-B e 1095-C, è necessario prima creare uno o più gruppi di copertura Affordable Care. Tali gruppi di copertura Affordable Care verranno utilizzati per indicare l'offerta di copertura che è stata fornita a un dipendente, la quota dei dipendenti del premio mensile al costo minimo (se il costo è al di sopra della soglia di povertà federale) nonché il programma Safe Harbor utilizzato dal datore di lavoro, se applicabile. L'utilizzo dei gruppi Affordable Care Act consente di gestire le informazioni relative a questi campi senza dover toccare ciascun record dipendente per il quale le condizioni siano identiche. Inoltre, i gruppi di copertura Affordable Care possono essere assegnati facilmente a uno o più dipendenti utilizzando la funzionalità per l'assegnazione in massa nella pagina.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Gestione di più versioni di un gruppo di copertura
È possibile gestire più versioni di qualsiasi gruppo di copertura, in modo da apportare modifiche per mantenere aggiornate le informazioni del gruppo, senza dover creare un nuovo gruppo e riassegnare ad esso i dipendenti quando qualcosa cambia nell'organizzazione o nei benefit offerti. 

Dopo aver creato i gruppi di copertura Affordable Care necessari, è possibile scegliere di assegnare in massa i gruppi ai dipendenti utilizzando la funzionalità **Assegnazione di massa** della pagina oppure è possibile passare su ciascun dipendente e indicare se le informazioni ACA devono essere registrate e dichiarate per il dipendente nonché assegnare il dipendente a un gruppo di copertura Affordable Care.

Se le informazioni sulla copertura Affordable Care non devono essere registrate o dichiarate per un dipendente, ad esempio se i tratta di un dipendente a tempo parziale, il campo **Copertura del report** potrebbe essere impostato su No. Sebbene ciascun dipendente per cui le informazioni ACA devono essere registrate debba essere assegnato a un gruppo di copertura Affordable Care, è comunque possibile modificare le opzioni **Offerta di copertura**, **Quota costo dipendente** e **Safe Harbor** per qualsiasi mese, o mesi, per cui potrebbe essere necessario impostare valori diversi da quelli specificati nel gruppo di copertura Affordable Care.

Per immettere le eccezioni a uno dei valori di gruppo di copertura Affordable Care, fare clic sul collegamento Copertura Affordable Care Act nella pagina Dettagli lavoratore, che si trova sotto la sezione Informazioni aggiuntive nella scheda Impiego.

## <a name="reporting-health-care-coverage"></a>Report di copertura delle spese mediche
Oltre a tenere traccia di qualsiasi copertura di assicurazione sanitaria offerta a un dipendente a tempo pieno, se il datore di lavoro offre una copertura sanitaria autoassicurata patrocinata dal datore di lavoro per cui il dipendente è iscritto (indipendentemente dal fatto che si tratti di un dipendente a tempo pieno o parziale), le informazioni aggiuntive devono essere dichiarate nel modulo 1095-C. Ciascun dipendente (dipendenti inclusi) coperto dai piani di benefit patrocinati da datore di lavoro deve essere incluso nel report per i mesi per cui sono stati coperti. 

È possibile indicare se si desidera che ciascun piano di benefit debba essere dichiarato selezionando la casella di controllo **Dichiarabile all'ACA**.

Inoltre, se i dipendenti hanno scelto di avere uno dei relativi dipendenti coperti da un benefit, è possibile indicare le date in cui il dipendente era coperto per ciascun dipendente nella pagina Gestisci benefit. Per indicare che il dipendente è coperto dal benefit, scegliere il pulsante Modifica nel riquadro azioni della Scheda dettaglio Dipendenti.

Nella pagina **Gestione date di copertura persone a carico**, è possibile indicare le date in cui il dipendente è stato coperto dal benefit. Immettendo le date in questa pagina verrà automaticamente selezionata la casella di controllo **Coperto** nella pagina **Gestisci benefit**.

## <a name="generate-1095b-and-1095c-forms"></a>Generare i moduli 1095B e 1095C
È inoltre possibile generare i moduli 109-B e 1095-C dal prodotto e distribuirli a ciascuno dei dipendenti. Anche il modulo 1095-C generato elettronicamente e i corrispondenti file di trasmissione 1094-C utilizzabili per inviarlo all'IRS possono essere generati dal sistema.  

Durante la generazione del modulo 1095-C, immettere l'anno fiscale appropriato e indicare se i numeri di previdenza sociale devono essere mascherati. Quando si stampano moduli 1095-C per più di 500 dipendenti, si riceveranno più di un file PDF. Si consiglia di aumentare il valore **Dimensioni massime di file** nella finestra **Parametri di gestione documenti** a 150 MB.

## <a name="viewing-information"></a>Visualizzazione delle informazioni
È possibile utilizzare la pagina **Copertura Affordable Care Act del lavoratore** per visualizzare i dipendenti assegnati a ciascun gruppo di copertura, quelli che non devono essere inclusi in un report e i dipendenti che non sono assegnati.

Se uno qualsiasi dei valori predefiniti del gruppo di copertura Affordable Care viene sovrascritto, un asterisco verrà visualizzato accanto al valore modificato. Se i valori per tutti i 12 mesi sono uguali e non sono stati ignorati, il valore verrà stampato nella colonna **Tutti i 12 mesi**.

È inoltre possibile utilizzare la finestra di richiesta di informazioni per capire quali dipendenti sono stati contrassegnati come non ACA dichiarabili, vale a dire che non è necessario tenere traccia della copertura offerta e non sarà necessario emettere un modulo 1095-C per loro a fine anno. Se si seleziona **Non ACA dichiarabile** nel campo **Filtra per**, è possibile generare un elenco di tutti i dipendenti che sono stati contrassegnati per non ricevere un 1095-C.

Oltre a visualizzare un elenco di dipendenti che non sono ACA dichiarabili, è inoltre possibile visualizzare tutti i dipendenti che non sono assegnati (il campo **Dichiara copertura ACA** è vuoto) o assegnati a un gruppo di copertura Affordable Care che è scaduto per l'anno selezionato nel campo **Anno**.

È possibile esportare gli elenchi di dipendenti generati mediante una delle opzioni di filtro in Excel.

Se è necessario dichiarare i singoli dipendenti coperti in quanto come datore di lavoro si fornisce la copertura autoassicurata, è anche possibile visualizzare tutti i dipendenti coperti dai piani di benefit che sono stati contrassegnati come **ACA dichiarabile** selezionando l'azione Visualizza copertura dipendente della striscia del riquadro azioni.

**Nota:** solo i benefit il piano è stato contrassegnato come **ACA dichiarabile** verranno visualizzati nella finestra di richiesta di informazioni.
