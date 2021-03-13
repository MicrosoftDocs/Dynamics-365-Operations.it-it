---
title: Emissione di fatture elettroniche in Finance e Supply Chain Management
description: Questo argomento spiega come emettere le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management con il componente aggiuntivo per la fatturazione elettronica.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 187f5a20d088b4fcd7af2a6576357a69c2efc2c6
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104399"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Emissione di fatture elettroniche in Finance e Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Questo argomento spiega come emettere le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management con il componente aggiuntivo per la fatturazione elettronica.


## <a name="feature-activation"></a>Attivazione della funzionalità

Per iniziare a emettere fatture elettroniche tramite il componente aggiuntivo Fatturazione elettronica, è necessario attivare il Riferimento funzionalità in Finance e Supply Chain Management.

Ogni riferimento alla funzionalità corrisponde a una specifica funzionalità di fatturazione elettronica conforme ai requisiti di fatturazione elettronica di un paese/area geografica.

La tabella seguente mostra l'elenco dei riferimenti alle funzionalità supportati dal componente aggiuntivo Fatturazione elettronica.

| Riferimento funzionalità | Nome                                              | Paese/area geografica |
|-------------------|---------------------------------------------------|----------------|
| BR-00053          | NF-e federale - Fattura elettronica brasiliana       | Brasile         |
| BR-00095          | Fatture elettroniche brasiliane NFS-e               | Brasile         |
| DK-00001          | Fatturazione elettronica al settore pubblico (OIOUBL) - DK    | Danimarca        |
| EG-00008          | Fatturazione elettronica per l'Egitto                             | Egitto          |
| ES-00025          | Fattura elettronica per il settore pubblico           | Spagna          |
| EUR-00023         | Fatturazione elettronica Unione Europea per il settore pubblico       | Europa         |
| ITA-00036         | IT - Fattura elettronica a settore pubblico (FatturaPA) | Italia          |
| MX-00010          | Fatturazione elettronica CFDI                                  | Messico         |
| MX-00016          | Fatturazione elettronica CFDI - Processo di annullamento           | Messico         |

Nei casi in cui è presente una funzionalità di fatturazione elettronica legacy, supportata dall'ambito di localizzazione del paese, l'attivazione del Riferimento funzionalità consente l'emissione di fatture elettroniche tramite il componente aggiuntivo Fatturazione elettronica e disattiva la funzionalità precedente.

## <a name="submit-electronic-documents"></a>Invia documenti elettronici

Il processo di invio dei documenti elettronici rappresenta l'unico punto di comunicazione tra Finance e Supply Chain Management e il componente aggiuntivo Fatturazione elettronica. Durante ogni evento di invio, la comunicazione scorre in entrambe le direzioni:

- **Da Finance e Supply Chain Management al componente aggiuntivo per la fatturazione elettronica** - Finance e Supply Chain Management inviano le fatture astratte al componente aggiuntivo Fatturazione elettronica. Come richiesto, inviano anche il contenuto delle variabili che sono state configurate come parte delle funzionalità di fatturazione elettronica.
- **Dal componente aggiuntivo per la fatturazione elettronica a Finance e Supply Chain Management** - A seconda della funzione di fatturazione elettronica, Finance e Supply Chain Management ricevono aggiornamenti dal componente aggiuntivo Fatturazione elettronica sui risultati dell'elaborazione delle fatture inoltrate in precedenza. Ricevono anche il contenuto delle variabili che sono state configurate come parte delle funzionalità di fatturazione elettronica.

Per inviare documenti elettronici al componente aggiuntivo Fatturazione elettronica, in Finance e Supply Chain Management, vai a **Amministrazione organizzazione &gt; Periodico &gt; Documenti elettronici &gt; Invia documenti elettronici**.

Il punto di partenza è una fattura registrata. Questa fattura può provenire da origini diverse, ad esempio ordini di vendita, fatture di progetto o fatture a testo libero.

Il processo di invio può essere eseguito manualmente o in background.

- **Esecuzione manuale** - Per l'esecuzione manuale, è necessario utilizzare l'opzione **Filtro** per definire l'intervallo di documenti che devono essere inviati. Nella pagina **Filtri** puoi configurare la query per selezionare le fatture registrate da inviare. Dopo aver effettuato la selezione, è necessario avviare manualmente l'esecuzione dell'elaborazione e attendere che termini l'esecuzione. Quando l'elaborazione è completata, un messaggio nel centro azioni mostra il numero di documenti elettronici che sono stati inviati.
- **Esecuzione in background** - L'esecuzione in background viene eseguita senza richiedere l'accesso o mantenere aperta la finestra di dialogo di invio. Puoi pianificare l'esecuzione del processo e definire la frequenza di esecuzione.

## <a name="view-the-submission-logs"></a>Visualizzare i registri di invio

In Finance e Supply Chain Management, puoi utilizzare i registri di invio per visualizzare i risultati dell'elaborazione dell'invio al componente aggiuntivo Fatturazione elettronica. Vai a **Amministrazione organizzazione &gt; Periodico &gt; Documenti elettronici &gt; Invio documenti elettronici**, e poi, nel campo **Tipo di documento** seleziona un valore per filtrare il tipo di fatture visualizzate nei registri.

Ci sono tre possibili stati di invio:

- **Programmato** - Il componente aggiuntivo Fatturazione elettronica ha ricevuto l'invio da Finance e Supply Chain Management ed è in corso l'elaborazione della funzione di fatturazione elettronica.
- **Completato** - Il componente aggiuntivo Fatturazione elettronica ha elaborato correttamente la funzione di fatturazione elettronica così come è stata configurata per eseguirla.
- **Non riuscito** - Il componente aggiuntivo Fatturazione elettronica ha riscontrato un errore o è stato interrotto da un'eccezione durante l'elaborazione della funzione di fatturazione elettronica.

> [!IMPORTANT]
> Lo stato di invio si riferisce allo stato dell'elaborazione che il componente aggiuntivo Fatturazione elettronica esegue sulla funzione di fatturazione elettronica. Non si riferisce allo stato finale della fattura elettronica stessa.
>
> Ad esempio, se una fattura elettronica deve essere inviata a un servizio Web esterno per l'approvazione, lo stato di invio potrebbe essere **Completato**, ma lo stato della fattura elettronica potrebbe essere **Rifiutato**. In questo caso, il componente aggiuntivo Fatturazione elettronica ha elaborato correttamente la funzione di fatturazione elettronica così come è stata configurata per eseguirla. Tuttavia, la fattura elettronica è stata rifiutata perché non soddisfaceva i criteri stabiliti dal servizio Web per l'approvazione della fattura.

I registri di invio includono le seguenti funzioni aggiuntive:

- **Dettagli invio** - Visualizza i dettagli dell'invio principale. La visualizzazione mostra il registro di esecuzione completo delle azioni configurate nella funzione di fatturazione elettronica. Consente inoltre agli utenti di scaricare i file creati durante l'elaborazione. Negli scenari in cui la fattura deve essere approvata da un servizio Web esterno, consente agli utenti di visualizzare lo stato della fattura.
- **Invii correlati** - Visualizza i dettagli degli invii secondari.
- **Annulla invii** - Questa funzione abilita un processo di invio speciale in scenari in cui la fattura elettronica deve essere approvata da un servizio web esterno. Indica al componente aggiuntivo Fatturazione elettronica di inviare al servizio Web un messaggio specifico che ha lo scopo di annullare lo stato di una fattura elettronica approvata nel database del servizio Web.
- **Invia di nuovo documento** - Invia nuovamente un documento elettronico che è già stato inviato al componente aggiuntivo Fatturazione elettronica. Viene creato un registro completamente nuovo nella pagina **Dettagli invio**.
- **Esegui invio correlato**
