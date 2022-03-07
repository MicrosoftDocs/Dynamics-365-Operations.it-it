---
title: Sospendere e riprendere una transazione nel POS
description: In questo argomento viene illustrato come gli utenti possono sospendere le transazioni in corso e quindi riprenderle successivamente o su un registratore di cassa differente utilizzando Dynamics 365 Commerce.
author: jblucher
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fdb693cb3b7520a9850d3e37dd512fc5b2a847f3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798659"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a>Sospendere e riprendere una transazione nel POS

[!include [banner](includes/banner.md)]


Gli utenti POS possono sospendere le transazioni in corso e quindi riprenderle successivamente o su un registratore di cassa differente. Le transazioni vengono spesso sospese per liberare rapidamente un registro di cassa per un'attività differente senza perdita di dati nella transazione corrente. Ad esempio, un associato di un punto vendita inizia a elaborare la transazione di un cliente su un dispositivo mobile ma deve completarla su un registratore con un cassetto della cassa. In questo caso, l'associato del punto vendita può sospendere la transazione sul dispositivo mobile e quindi richiamarla e riprenderla su un registratore di cassa.

## <a name="configure-suspend-and-resume-functionality"></a>Configurare la funzionalità per sospendere e riprendere una transazione

### <a name="pos-operations"></a>Operazioni POS

Due [Operazioni POS](pos-operations.md) consentono al supporto POS di sospendere e riprendere gli scenari. È possibile assegnare queste operazioni a [griglie di pulsanti](pos-screen-layouts.md) nella pagina delle transazioni o nella pagina di benvenuto.

- 503: Sospendi transazione
- 504: Richiama transazione

### <a name="receipt-template"></a>Modello di ricevuta

Il POS può essere configurato per generare una distinta stampata quando una transazione viene sospesa. Tale distinta può quindi essere utilizzata per identificare e richiamare rapidamente la transazione in seguito.

Per abilitare il POS per la stampa di una distinta, è necessario aggiungere il formato di ricevuta **Transazione sospesa** al profilo di ricevuta del punto vendita. È possibile progettare il formato di ricevuta di modo che includa o non includa specifici dettagli sulla transazione. Ad esempio, il formato può includere un codice a barre per supportare la scansione.

### <a name="receipt-numbering"></a>Numerazione ricevute

Per gli altri tipi di transazione POS che generano una ricevuta stampata, è possibile definire una sequenza numerica per le transazioni sospese nella sezione **Numerazione ricevute** del profilo funzionalità del punto vendita.

### <a name="void-when-closing-shift"></a>Annulla alla chiusura del turno

È possibile utilizzare l'opzione **Annulla alla chiusura del turno** per far sì che gli utenti completino o annullino tutte le transazioni sospese prima di chiudere il proprio turno. Durante l'operazione **Chiudi turno**, il POS richiederà agli utenti di visualizzare o annullare tutte le transazioni sospese.

## <a name="suspend-and-resume-a-transaction"></a>Sospendere e riprendere una transazione

### <a name="suspend-a-transaction"></a>Sospendere una transazione

Gli utenti con privilegi sufficienti e con un layout di schermo che include l'operazione **Sospendi transazione** possono sospendere una transazione e quindi richiamarla successivamente o su un registro di cassa differente.

Le transazioni possono essere sospese solo se **non** contengono i seguenti tipi di righe:

- Righe pagamento attive
- Righe gift card (per emettere una gift card o per un'aggiunta al saldo gift card)

Una transazione sospesa non influisce sulle informazioni relative alle vendite o alla disponibilità delle scorte per il punto vendita.

### <a name="resume-a-suspended-transaction"></a>Riprendere una transazione sospesa

Le transazioni sospese possono essere richiamate e riprese nello stesso punto vendita da qualsiasi utente con privilegi sufficienti e che dispone di un layout che include l'operazione **Richiama transazione**.

Per richiamare rapidamente e facilmente una transazione sospesa, eseguire la scansione del codice a barre sulla distinta stampata durante la visualizzazione dell'elenco delle transazioni dall'operazione **Richiama transazione**.

### <a name="considerations-for-offline-mode"></a>Considerazioni sulla modalità offline

- Qualsiasi transazione sospesa quando il POS è in modalità in linea non può essere ripresa in modalità offline, poiché i dati non vengono sincronizzati al database offline.
- Se si sospende una transazione quando il POS è in modalità offline, è possibile richiamarla in modalità offline purché il POS non sia passato di nuovo alla modalità in linea dopo la sospensione della transazione. Quando il POS passa di nuovo alla modalità in linea, i dati relativi alle transazioni sospese vengono spostati nel database in linea e rimossi dal database offline. Di conseguenza, le transazioni possono essere riprese solo in modalità in linea. Se il POS passa di nuovo alla modalità offline, non sarà possibile riprendere le transazioni sospese, in quanto sono già state rimosse dal database offline.

### <a name="void-a-suspended-transaction"></a>Annullare una transazione sospesa

È possibile annullare le transazioni sospese richiamando la transazione e quindi eseguendo l'operazione **Annulla transazione** oppure selezionando la transazione nell'elenco **Richiama transazione** e quindi **Annulla** sulla barra delle app. In alternativa, il punto vendita può essere configurato affinché gli utenti annullino le transazioni sospese quando chiudono il proprio turno.


[!INCLUDE[footer-include](../includes/footer-banner.md)]