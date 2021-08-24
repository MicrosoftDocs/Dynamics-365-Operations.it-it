---
title: Emissione di fatture elettroniche in Finance e Supply Chain Management
description: Questo argomento spiega come emettere le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management con la fatturazione elettronica.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 24909c2a2505724c159e939535c1d57cb66e48629862bebb32b3d72c0eb06c97
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752128"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Emissione di fatture elettroniche in Finance e Supply Chain Management

[!include [banner](../includes/banner.md)]

Questo argomento spiega come emettere le fatture elettroniche in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management con la fatturazione elettronica.


## <a name="feature-activation"></a>Attivazione della funzionalità

Per emettere fatture elettroniche tramite Fatturazione elettronica, è necessario attivare il Riferimento funzionalità in Finance e Supply Chain Management.

Ogni funzionalità corrisponde a una specifica funzionalità di fatturazione elettronica conforme ai requisiti di fatturazione elettronica per un paese/area geografica.

La tabella seguente mostra l'elenco delle funzionalità supportati da Fatturazione elettronica.

| Nome                                              | Paese/area geografica |
|---------------------------------------------------|----------------|
|Fattura elettronica austriaca                        |Austria         |
|Fattura elettronica belga                         |Belgio         |
|NF-e federale - Fattura elettronica brasiliana       |Brasile          |
|NFS-e - Fattura elettronica del servizio brasiliano (città)|Brasile          |
|Fattura elettronica danese                          |Danimarca         |
|Fattura elettronica egiziana                        |Egitto           |
|Fattura elettronica estone                        |Estonia         |
|Fattura elettronica finlandese                         |Finlandia         |
|Fattura elettronica francese                          |Francia          |
|Fattura elettronica tedesca                          |Germania         |
|PEPPOL - Fattura elettronica globale                 |Globali          |
|Fattura elettronica italiana                         |Italia           |
|CFDI - Fattura elettronica messicana                  |Messico          |
|Fattura elettronica olandese                           |Paesi Bassi     |
|Fattura elettronica norvegese                       |Norvegia          |
|Fattura elettronica spagnola                         |Spagna           |

Quando è presente una funzionalità di fatturazione elettronica legacy supportata dall'ambito di localizzazione di un paese/area geografica, l'attivazione di una di queste funzionalità disattiva la funzionalità legacy e consente l'emissione di fatture elettroniche tramite Fatturazione elettronica.

> [!IMPORTANT]
> Dopo l'abilitazione della funzionalità di integrazione di Fatturazione elettronica, la nuova esperienza di fatturazione elettronica è disattivata per impostazione predefinita. È possibile utilizzare il concetto di funzionalità per abilitare selettivamente nuove esperienze per persone giuridiche che utilizzano funzionalità specifiche per paese/area geografica. L'opzione **Globale** controlla la nuova esperienza per il paese/le aree geografiche rimanenti che non sono specificatamente elencate nella tabella.

## <a name="submit-electronic-documents"></a>Invia documenti elettronici

Il processo di invio dei documenti elettronici rappresenta l'unico punto di comunicazione tra Finance e Supply Chain Management e Fatturazione elettronica. Durante ogni evento di invio, la comunicazione scorre in entrambe le direzioni:

- **Da Finance e Supply Chain Management al componente aggiuntivo per la fatturazione elettronica** - Finance e Supply Chain Management inviano le fatture astratte a Fatturazione elettronica. Come richiesto, inviano anche il contenuto delle variabili che sono state configurate come parte delle funzionalità di fatturazione elettronica.
- **Dal componente aggiuntivo per la fatturazione elettronica a Finance e Supply Chain Management** - A seconda della funzione di fatturazione elettronica, Finance e Supply Chain Management ricevono aggiornamenti da Fatturazione elettronica sui risultati dell'elaborazione delle fatture inoltrate in precedenza. Ricevono anche il contenuto delle variabili che sono state configurate come parte delle funzionalità di fatturazione elettronica.

Per inviare documenti elettronici a Fatturazione elettronica, in Finance e Supply Chain Management, vai a **Amministrazione organizzazione &gt; Periodico &gt; Documenti elettronici &gt; Invia documenti elettronici**.

Il punto di partenza è una fattura registrata. Questa fattura può provenire da origini diverse, ad esempio ordini di vendita, fatture di progetto o fatture a testo libero.

Il processo di invio può essere eseguito manualmente o in background.

- **Esecuzione manuale** - Per l'esecuzione manuale, è necessario utilizzare l'opzione **Filtro** per definire l'intervallo di documenti che devono essere inviati. Nella pagina **Filtri** puoi configurare la query per selezionare le fatture registrate da inviare. Dopo aver effettuato la selezione, è necessario avviare manualmente l'esecuzione dell'elaborazione e attendere che termini l'esecuzione. Quando l'elaborazione è completata, un messaggio nel centro azioni mostra il numero di documenti elettronici che sono stati inviati.
- **Esecuzione in background** - L'esecuzione in background viene eseguita senza richiedere l'accesso o mantenere aperta la finestra di dialogo di invio. Puoi pianificare l'esecuzione del processo e definire la frequenza di esecuzione.

## <a name="view-the-submission-logs"></a>Visualizzare i registri di invio

In Finance e Supply Chain Management, puoi utilizzare i registri di invio per visualizzare i risultati dell'elaborazione dell'invio a Fatturazione elettronica. Vai a **Amministrazione organizzazione &gt; Periodico &gt; Documenti elettronici &gt; Invio documenti elettronici**, e poi, nel campo **Tipo di documento** seleziona un valore per filtrare il tipo di fatture visualizzate nei registri.

Ci sono tre possibili stati di invio:

- **Programmato** - Fatturazione elettronica ha ricevuto l'invio da Finance e Supply Chain Management ed è in corso l'elaborazione della funzione di fatturazione elettronica.
- **Completato** - Fatturazione elettronica ha elaborato correttamente la funzione di fatturazione elettronica così come è stata configurata per eseguirla.
- **Non riuscito** - Fatturazione elettronica ha riscontrato un errore o è stato interrotto da un'eccezione durante l'elaborazione della funzione di fatturazione elettronica.

> [!IMPORTANT]
> Lo stato di invio si riferisce allo stato dell'elaborazione che Fatturazione elettronica esegue sulla funzione di fatturazione elettronica. Non si riferisce allo stato finale della fattura elettronica stessa.
>
> Ad esempio, se una fattura elettronica deve essere inviata a un servizio Web esterno per l'approvazione, lo stato di invio potrebbe essere **Completato**, ma lo stato della fattura elettronica potrebbe essere **Rifiutato**. In questo caso, Fatturazione elettronica ha elaborato correttamente la funzione di fatturazione elettronica così come è stata configurata per eseguirla. Tuttavia, la fattura elettronica è stata rifiutata perché non soddisfaceva i criteri stabiliti dal servizio Web per l'approvazione della fattura.

I registri di invio includono le seguenti funzioni aggiuntive:

- **Dettagli invio** - Visualizza i dettagli dell'invio principale. La visualizzazione mostra il registro di esecuzione completo delle azioni configurate nella funzione di fatturazione elettronica. Consente inoltre agli utenti di scaricare i file creati durante l'elaborazione. Negli scenari in cui la fattura deve essere approvata da un servizio Web esterno, consente agli utenti di visualizzare lo stato della fattura.
- **Invii correlati** - Visualizza i dettagli degli invii secondari.
- **Annulla invii** - Questa funzione abilita un processo di invio speciale in scenari in cui la fattura elettronica deve essere approvata da un servizio web esterno. Indica a Fatturazione elettronica di inviare al servizio Web un messaggio specifico che ha lo scopo di annullare lo stato di una fattura elettronica approvata nel database del servizio Web.
- **Invia di nuovo documento** - Invia nuovamente un documento elettronico che è già stato inviato a Fatturazione elettronica. Viene creato un registro nuovo nella pagina **Dettagli invio**.
- **Esegui invio correlato**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
