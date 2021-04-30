---
title: Collaborare con i fornitori tramite il portale fornitori
description: In questo argomento viene illustrato come gli addetti agli acquisti possono utilizzare il portale fornitori per collaborare con i fornitori esterni durante il processo di conferma dell'ordine fornitore. Queste informazioni si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceffa7028f4490a88027a2affdc898877cc2db43
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910067"
---
# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Collaborazione con i fornitori tramite il portale fornitori

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come gli addetti agli acquisti possono utilizzare il portale fornitori per collaborare con i fornitori esterni durante il processo di conferma dell'ordine fornitore. Queste informazioni si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX.

Le informazioni in questo argomento si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX. Per ulteriori informazioni sulle nuove funzionalità di collaborazione fornitore, vedere [Collaborazione fornitore con i fornitori esterni](vendor-collaboration-work-external-vendors.md).  

Il portale fornitori è destinato ai fornitori che non dispongono dell'integrazione EDI (Electronic Data Interchange) con Microsoft Dynamics AX per scambiare le informazioni sugli ordini fornitore. Il portale consente agli addetti agli acquisti di inviare un ordine al fornitore e di ricevere una risposta di conferma o rifiuto direttamente in Dynamics AX.  

Il processo può essere configurato in modo che una conferma del fornitore confermi automaticamente l'ordine. In questo caso, il follow-up è necessario solo occasionalmente, quando un ordine viene rifiutato o quando la conferma del fornitore viene registrata come risposta ma lo stato dell'ordine fornitore non viene aggiornato a **Confermato** a causa di un problema nel processo di conferma.

## <a name="po-confirmation-and-rejection"></a>Conferma e rifiuto dell'ordine fornitore
Gli ordini fornitore vengono preparati in Dynamics AX. Se si dispone di un ordine fornitore con uno stato **Approvato**, lo si invia al fornitore generando una richiesta di conferma. Se si desidera richiamare l'attenzione del fornitore su un nuovo ordine fornitore, è anche possibile utilizzare il sistema di gestione stampa per inviare l'ordine per e-mail. L'ordine fornitore viene visualizzato nel portale fornitori e include un'opzione che il fornitore può utilizzare per confermarlo o rifiutarlo. Il fornitore può anche aggiungere commenti per comunicare informazioni come modifiche all'ordine fornitore.  

Nel portale fornitori il fornitore può visualizzare le righe dell'ordine. Queste righe includono informazioni come il numero prodotto esterno, le dimensioni, le informazioni sul prezzo, la quantità, la data di consegna e l'indirizzo di consegna. Il fornitore può generare un report che mostra le informazioni sull'ordine fornitore e il prezzo totale. Le spese rilevanti al fornitore vengono visualizzate se il fornitore fa clic sul pulsante **Spese** nell'intestazione o nelle righe. I fornitori possono importare le informazioni dell'ordine fornitore nel proprio sistema utilizzando la funzionalità **Esporta in Excel**.  

Nella tabella seguente viene mostrato lo scambio tipico di informazioni, a seconda del modo in cui il fornitore risponde quando riceve un ordine fornitore per la conferma.

| Tipo di risposta                                                                                                  | Risultato                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il fornitore conferma l'ordine. Il sistema è configurato per confermare automaticamente gli ordini fornitore quando il fornitore conferma.    | Lo stato dell'ordine viene aggiornato a **Confermato**. Se qualcosa impedisce l'aggiornamento dell'ordine, la risposta del fornitore viene comunque registrata come **Confermata** ma lo stato dell'ordine fornitore rimane **In revisione esterna**.                                                                       |
| Il fornitore conferma l'ordine. Il sistema non è configurato per confermare automaticamente gli ordini fornitore quando il fornitore conferma. | La risposta del fornitore viene registrata come **Confermata**, ma lo stato dell'ordine fornitore rimane **In revisione esterna**.                                                                                                                                                                                      |
| Il fornitore rifiuta l'ordine.                                                                                     | La risposta del fornitore viene registrata come **Rifiutata** e lo stato dell'ordine fornitore rimane **In revisione esterna**. Il rifiuto viene ricevuto insieme al motivo e alle modifiche suggerite, ad esempio una data di consegna alternativa. Aggiornare l'ordine fornitore e inviare una nuova versione per la conferma. |

## <a name="changes-to-a-po"></a>Modifiche a un ordine fornitore
Quando è necessario modificare un ordine fornitore già confermato, è possibile inviarne uno nuovo al fornitore tramite il portale. Il nuovo ordine fornitore presenterà un suffisso versione per indicare che si tratta di una versione modificata di un ordine fornitore comunicato in precedenza. Il portale fornitori consente ai fornitori di tenere traccia dello storico di ciascun ordine. La versione confermata in precedenza dell'ordine fornitore rimarrà nell'elenco di ordini confermati finché non viene confermato il nuovo ordine.  

Quando si annulla un ordine fornitore, lo stato torna **Approvato**. È necessario inviare nuovamente l'ordine al fornitore tramite il portale in modo che possa confermare o rifiutare l'annullamento. Dopo la conferma dell'annullamento, l'ordine fornitore viene visualizzato nell'elenco dell'elenco del fornitore degli ordini come **Annullato**.

## <a name="versions-status-transitions-and-change-management"></a>Versioni, transizione dello stato e gestione delle modifiche
Quando un ordine fornitore viene inviato al fornitore, viene registrato nel sistema come una versione specifica e lo stato passa da **Approvato** a **In revisione esterna**. Se l'ordine fornitore viene modificato in un momento successivo, viene creata una nuova versione dell'ordine e lo stato torna a essere **Approvato** (oppure **Bozza** se la gestione modifiche è abilitata).  

Nella tabella seguente è riportato un esempio delle modifiche dello stato e della versione a cui potrebbe essere sottoposto un ordine fornitore.

| Azione                                                   | Stato e versione                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| La versione iniziale dell'ordine fornitore viene creata in Dynamics AX. | Lo stato è **Approvato**.                                                                           |
| L'ordine fornitore viene inviato al portale fornitori.                     | Una versione viene registrata nel portale e lo stato passa a **In revisione esterna**.    |
| Si apportano alcune modifiche richieste dal fornitore.  | Lo stato torna a essere **Approvato**.                                                            |
| Si invia la nuova versione dell'ordine fornitore nel portale fornitori. | Una nuova versione viene registrata nel portale e lo stato passa a **In revisione esterna**. |
| Il fornitore approva la nuova versione dell'ordine.           | Lo stato viene modificato in **Confermato**.                                                                |

Per visualizzare le versioni dell'ordine fornitore che sono state inviate al fornitore e le relative risposte, fare clic su **Giornali di registrazione** &gt; **Richieste di conferma** dall'ordine fornitore.  

Gli ordini inviati al fornitore per una risposta e con stato **In revisione esterna** verranno visualizzati nell'elenco **Ordini fornitore inviati al portale fornitori e in attesa di risposta** o **Ordini fornitore inviati al portale fornitori e per cui la risposta richiede un'azione**. Quando si modifica un ordine che è stato inviato al fornitore, in modo che lo stato torni nuovamente ad **Approvato**, l'ordine non viene più visualizzato in questi elenchi. Per verificare se in precedenza è stata emessa una risposta all'ordine dal fornitore, fare clic su **Giornali di registrazione** &gt; **Richieste di conferma**.  

I fornitori non devono confermare l'ordine nel portale fornitori. Possono anche inviare un messaggio di posta elettronica o comunicare l'accettazione di un ordine attraverso altri canali. È quindi possibile confermare l'ordine manualmente in Dynamics AX. In questo caso, viene visualizzato un avviso che l'ordine sta per essere confermato anche in assenza di risposte dal fornitore. L'ordine fornitore viene visualizzato nello storico di conferma nel portale fornitori come ordine confermato aperto che non dispone di risposte. Il fornitore non ha più la possibilità di rifiutare o confermare l'ordine fornitore.  

**Nota:** la versione dell'ordine fornitore disponibile ad altri processi in Dynamics AX è sempre la versione più recente, anche se tale versione non è ancora stata registrata.

### <a name="change-management"></a>Gestione delle modifiche

Se è stata abilitata la gestione delle modifiche di un ordine fornitore, l'ordine deve superare un flusso di lavoro di approvazione per ottenere lo stato **Approvato**. Questo processo non è visibile al fornitore.  

Se la gestione delle modifiche è abilitata per un ordine fornitore, la versione viene registrata quando l'ordine viene approvato, non quando viene inviato al fornitore o confermato.  

Nella tabella riportata di seguito viene mostrato un esempio di modifica allo stato e alla versione a cui l'ordine potrebbe essere sottoposto quando la gestione delle modifiche è abilitata.


|                                                    Azione                                                     |                                                                                                                                                                                                                      Stato e versione                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           La versione iniziale dell'ordine fornitore viene creata in Dynamics AX.                            |                                                                                                                                                                                                            Lo stato è <strong>Bozza</strong>.                                                                                                                                                                                                             |
| L'ordine fornitore viene inviato al processo di approvazione. (Si tratta di un processo interno che non coinvolge il fornitore). |                                                                                                                        Lo stato viene modificato da <strong>Bozza</strong> a <strong>In revisione</strong> ad <strong>Approvazione</strong> se l'ordine non viene rifiutato durante il processo di approvazione. L'ordine fornitore approvato viene registrato come una versione.                                                                                                                        |
|                                      L'ordine fornitore viene inviato al portale fornitore                                      |                                                                                                                                                                      La versione viene registrata nel portale e lo stato passa a <strong>In revisione esterna</strong>.                                                                                                                                                                       |
|                            Si apportano alcune modifiche richieste dal fornitore.                            |                                                                                                                                                                                                    Lo stato torna a essere <strong>Bozza</strong>.                                                                                                                                                                                                     |
|                              L'ordine fornitore viene nuovamente inviato al processo di approvazione.                               | Lo stato viene modificato da <strong>Bozza</strong> a <strong>In revisione</strong> ad <strong>Approvazione</strong> se l'ordine non viene rifiutato durante il processo di approvazione. In alternativa, il sistema può essere configurato in modo che modifiche specifiche ai campi non richiedano una nuova approvazione. In questo caso, lo stato viene inizialmente modificato in <strong>Bozza</strong> e quindi automaticamente aggiornato ad <strong>Approvato</strong>. L'ordine fornitore approvato viene registrato come nuova versione. |
|                           Si invia la nuova versione dell'ordine fornitore nel portale fornitori.                            |                                                                                                                                                                    La nuova versione viene registrata nel portale e lo stato passa a <strong>In revisione esterna</strong>.                                                                                                                                                                     |
|                                Il fornitore approva la nuova versione dell'ordine.                                 |                                                                                                                                                     Lo stato viene modificato in <strong>Confermato</strong> automaticamente o quando si riceve la risposta dal fornitore e quindi si conferma l'ordine.                                                                                                                                                     |

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Sicurezza degli utenti del portale fornitori](configure-security-vendor-portal-users.md)

[Area di lavoro fatturazione di collaborazione fornitore](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]