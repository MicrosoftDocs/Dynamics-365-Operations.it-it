---
title: Pronto per il pagamento
description: Questo articolo mostra come contrassegnare un dipendente come pronto per il pagamento in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 81c73584e3567d620292227ce4a24c3c0945fa96
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862861"
---
# <a name="ready-to-pay"></a>Pronto per il pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> Se vuoi contrassegnare un dipendente come pronto per il pagamento, devi prima abilitare la funzionalità **(Anteprima) Integrazione retribuzioni** nella gestione delle funzionalità. Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

Questa funzionalità consente ai professionisti delle risorse umane di capire quali dipendenti sono pronti per l'elaborazione delle retribuzioni e quali richiedono un'azione prima di essere utilizzati da un fornitore di retribuzioni di terze parti.

## <a name="mark-employee-as-ready-to-pay"></a>Contrassegnare il dipendente come pronto per il pagamento

La raccolta e la convalida delle informazioni sui dipendenti può richiedere molto tempo ed è soggetta a errori. Fornendo ai professionisti delle risorse umane un modo per rivedere e aggiornare facilmente le informazioni sui dipendenti, Dynamics 365 Human Resources aiuta a ridurre il tempo impiegato per prepararsi all'elaborazione delle retribuzioni.

Per contrassegnare un dipendente come Pronto per il pagamento:

1. Apri **Gestione retribuzioni**. Ci sono due riquadri nell'area di lavoro: 
    - **Dipendenti pronti per il pagamento**
    - **Dipendenti non pronti per il pagamento**
    ![Area di lavoro per la gestione retribuzioni.](./media/hr-ready-to-pay-1-workspace.png)

2. Seleziona il riquadro **Dipendenti non pronti per il pagamento**.

3. Seleziona i dipendenti da convalidare. Nella **scheda Retribuzioni**, nel gruppo **Pronto per il pagamento** seleziona **Convalida**.
    ![Convalida i dipendenti.](./media/hr-ready-to-pay-2-validate.png)

4. Per rivedere i risultati, nella **scheda Retribuzioni**, nel gruppo **Pronto per il pagamento** seleziona **Risultati**.

## <a name="validation"></a>Convalida

Prima di contrassegnare un dipendente come pronto per il pagamento viene eseguita una convalida sulla completezza del profilo.

![Convalida i risultati.](./media/hr-ready-to-pay-3-results.png)

| Convalida | Dettagli |
| --- | --- |
| **Parametro tipo di indirizzo** | Convalida se il parametro **Utilizza lo scopo indirizzo retribuzione** è selezionato. |
| **Indirizzo retribuzione** | Convalida se il profilo del lavoratore ha almeno un indirizzo con lo scopo **Luogo di residenza retribuzioni** o **Luogo di lavoro retribuzioni** e c'è un solo indirizzo per scopo. |
| **Impiego** | Verifica se il lavoratore ha almeno un impiego (attuale, precedente o futuro). |
| **Numero di identificazione** | Convalida se il campo **Utilizza tipi di identificazione nell'elaborazione delle retribuzioni** è impostato su **Sì** nella pagina **Parametri di Human Resources** e se il tipo di identificazione indicato nel parametro è compilato nel profilo del lavoratore. |
| **Nome e cognome** | Verifica che i campi **Nome** e **Cognome** sono compilati.|
| **Ubicazione** | Verifica che il lavoratore abbia una posizione assegnata. |
| **Data di nascita** | Verifica che il campo **Compleanno** è compilato. |
| **Retribuzione** | Verifica se il lavoratore è iscritto a un piano di retribuzione fissa. |

Se una di queste convalide non riesce, non puoi contrassegnare il dipendente come pronto per il pagamento.

Se il campo **Pronto per il pagamento** è **No**, indica che è necessario eseguire un'azione per garantire che il profilo del lavoratore sia completo. Ciò non interromperà l'esposizione dei dati nelle entità di dati. 

## <a name="process-automation"></a>Automazione processi

È possibile automatizzare la convalida di tutti i dipendenti utilizzando [Automazione del processo](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation). Nell'area di lavoro **Gestione retribuzioni**, andare a **Collegamenti** \> **Parametri** \> **Automazioni di processo**.

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
