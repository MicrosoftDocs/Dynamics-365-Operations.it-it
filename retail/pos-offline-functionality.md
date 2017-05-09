---
title: "Funzionalità offline POS"
description: "Questo articolo fornisce informazioni sulla modalità offline per Retail Modern POS, in cui i dispositivi POS passano automaticamente dal database del canale al database offline se il server Retail non è disponibile. Questo articolo include le informazioni generali di impostazione per la modalità offline e illustra la sincronizzazione dei dati tra il database offline e il database del canale."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>Funzionalità offline POS

[!include[banner](includes/banner.md)]


Questo articolo fornisce informazioni sulla modalità offline per Retail Modern POS, in cui i dispositivi POS passano automaticamente dal database del canale al database offline se il server Retail non è disponibile. Questo articolo include le informazioni generali di impostazione per la modalità offline e illustra la sincronizzazione dei dati tra il database offline e il database del canale.

<a name="overview"></a>Panoramica
--------

In Retail Modern POS, un dispositivo POS entra in modalità offline ogni volta che il server vendita al dettaglio non è disponibile. Pertanto, se la connessione con il server vendita al dettaglio viene persa, Retail Modern POS passa automaticamente al database offline. Durante la transazione di vendita, se una richiesta di dati non ha esito positivo nell'intervallo di timeout configurato nel profilo offline, Retail Modern POS automaticamente passa al database offline e continua la transazione di vendita. Mentre il dispositivo POS è in modalità offline, Retail Modern POS tenta di riconnettersi al server vendita dettaglio dopo l'intervallo di tentativo di riconnessione configurato nel profilo offline. Il tentativo di riconnessione viene effettuato solo all'inizio di una transazione.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Determinazione della modalità di connessione di Retail Modern POS

L'intestazione dello stato di Retail Modern POS indica lo stato corrente della connessione e la finestra **Stato connessione** mostra lo stato dell'ultimo tentativo di sincronizzazione con il database offline. [![Stato connessione](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Creazione di un pulsante per passare manualmente tra le modalità online e offline

È possibile aggiungere un pulsante a Retail Modern POS per passare manualmente tra le modalità online e offline. Creare un pulsante per l'operazione POS **917 Stato di connessione al database**. Il nome del pulsante è **Disconnetti** quando Retail Modern POS è connesso al server vendita al dettaglio e **Connetti** quando è disconnesso. È possibile utilizzare questo pulsante per visualizzare la connessione e per disconnettersi dal server vendita dettaglio o connettersi a esso. [![Pulsante Disconnetti in Retail Modern POS](./media/details-1024x537.png)](./media/details.png)

## <a name="setup"></a>Impostazione
Per abilitare il supporto offline per un dispositivo POS (registratore di cassa), impostare l'opzione **Supporta offline** su **Sì** nella pagina **Registratore di cassa**. Una nuova entità database di canale viene creata e aggiunta al gruppo di dati del canale del punto vendita. Quindi eseguire tutte le programmazioni di distribuzione richieste per generare i pacchetti dati del database offline. Dopo, installare la versione offline del Retail Modern POS. Il processo di installazione crea il database offline. Inoltre, installare Microsoft SQL Server 2014 Express se necessario. La sincronizzazione dei dati offline inizia dopo il primo accesso a Retail Modern POS.

## <a name="data-synchronization"></a>Sincronizzazione dati
Retail scheduler viene utilizzato per inviare i dati master al database offline. Per impostazione predefinita, quando una programmazione di distribuzione viene eseguita, le modifiche ai dati vengono inviate al database del canale e al database offline. Retail Modern POS include la libreria async sync, che scarica tutti i pacchetti dati disponibili e li inserisce nel database offline. Se le transazioni sono create offline, Retail Modern POS le carica nel server vendita al dettaglio, in modo che possano essere immesse nel database del canale. La sincronizzazione dei dati offline può verificarsi solo se Retail Modern POS è in esecuzione. [![Sincronizzazione non in linea](./media/offline-sync-1024x521.png)](./media/offline-sync.png)




