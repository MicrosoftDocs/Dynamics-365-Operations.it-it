---
title: Novità o modifiche in Dynamics 365 Human Resources 19 novembre 2021
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources standalone al 19 novembre 2021.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d3e08432a4ce4d73cd67ad839191abe9f6e691a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886075"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Novità o modifiche in Dynamics 365 Human Resources 19 novembre 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive le funzionalità nuove, modificate o future di Microsoft Dynamics 365 Human Resources.

Per ulteriori informazioni sul processo di aggiornamento e pianificazione, vedere [Processo di aggiornamento](hr-admin-setup-update-process.md).

Per ulteriori informazioni sulle nuove funzionalità e sulle relative date di disponibilità generale previste, vedi [Secondo ciclo di rilascio del 2021 di Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>In questa versione

Questa versione include le seguenti correzioni di bug. Le modifiche si applicano alla build 8.1.4591.

### <a name="bug-fixes"></a>Correzioni di bug

Questa versione include le seguenti correzioni di bug.

> [!NOTE]
> Il nostro obiettivo è fornire queste informazioni il prima possibile. Potremmo aggiornare questo articolo per includere le correzioni di bug che sono state inserite nella build dopo che questo articolo è stato inizialmente pubblicato.

| Numero problema | Problema | Description |
|---|---|---|
| 626178 | La navigazione non è presente nei riquadri lavoratore in **Responsabile self-service** | Questo problema è ora risolto. La navigazione è disponibile per vedere i dettagli del report in **Responsabile self-service**. |
| 632573 | Non c'è alcun errore di convalida durante il salvataggio di un **Corso** | Questo problema è ora risolto. Quando si crea un corso con il **Numero minimo di partecipanti** su un valore maggiore di 0 è consentito salvare anche quando il **Numero massimo di partecipanti** è 0. |
| 615955 | Errore "Campo **Scopo** deve essere compilato" quando si crea una nuova posizione di richiesta di reclutamento. | Quando si crea un indirizzo per una nuova sede di richiesta di reclutamento, viene visualizzato l'errore: "Il campo "Scopo" deve essere compilato". Tuttavia il campo **Scopo** non è disponibile nella pagina. |
| 620797 | Errore del campo **Genere** vuoto fuorviante | Quando non viene inserito un sesso per un contatto personale, il report mostra "Fai clic o tocca qui per inserire il testo" – Questo è fuorviante in quanto è possibile non inserire nulla nel campo. |
| 620800 | Il collegamento alla dichiarazione dei benefit è nascosto | La dichiarazione dei benefit non è visualizzabile per impostazione predefinita in **Self-service dipendenti**.  È stato aggiunto un collegamento sul lato destro di **Self-service dipendenti** sotto la sezione **Collegamenti** |
| 629778 | Problema di prestazioni con l'integrazione CDS. | La richiesta relativa all'autorizzazione ha causato problemi di prestazioni. |

## <a name="in-preview"></a>In anteprima

Le seguenti nuove funzionalità sono in anteprima. Per maggiori informazioni su come attivare o disattivare le funzioni, vedi [Gestione delle funzioni](hr-admin-manage-features.md).

| Funzionalità | Piano di rilascio | Documentazione |
|---|---|---|
| Area di lavoro gestione benefit | [Area di lavoro Gestione benefit](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Area di lavoro gestione benefit](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Presto disponibile
Per un elenco completo delle funzionalità pianificate e dei relativi rilasci programmati, vedi [Dynamics 365 e cloud di settore: secondo ciclo di rilascio del 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
