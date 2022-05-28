---
title: Impostazione ed elaborazione dei pagamenti provvisori
description: Questo argomento descrive come impostare ed elaborare i pagamenti provvisori del cliente. Un pagamento provvisorio è un pagamento che viene registrato nella contabilità generale in due passaggi.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca93d99ce04e607b137a2755d507022a33ab1be8
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734193"
---
# <a name="set-up-and-process-bridged-payments"></a>Impostazione ed elaborazione dei pagamenti provvisori

[!include [banner](../includes/banner.md)]

Un pagamento provvisorio è un pagamento che viene registrato nella contabilità generale in due passaggi. In genere, questo approccio viene utilizzato quando il metodo di pagamento è impostato su **Banca** e devi registrare le transazioni sul conto bancario solo quando la transazione ha autorizzato la banca. Tuttavia, puoi anche usarlo per un conto CoGe. In questo caso, il sistema sposta l'importo da un conto principale a un altro conto principale durante l'elaborazione della registrazione provvisoria.

È possibile creare pagamenti provvisori da Contabilità fornitori o Contabilità clienti. Sebbene questo argomento spieghi come configurare la registrazione provvisoria per la contabilità fornitori, i passaggi per le transazioni di contabilità fornitori sono simili.

## <a name="set-up-bridging-posting"></a>Impostare la registrazione provvisoria

Per utilizzare la pubblicazione provvisoria, devi impostare uno o più metodi di pagamento in modo che utilizzino il medoto **Registrazione provvisoria**. È quindi necessario selezionare un conto provvisorio.

1. Vai a **Contabilità clienti &gt; Impostazione pagamenti &gt; Metodi di pagamento**.
2. Seleziona un metodo di pagamento esistente per cui abilitare la registrazione provvisoria. In alternativa, crea un nuovo metodo di pagamento.
3. Seleziona la casella di controllo **Registrazione provvisoria**.
4. Nel campo **Conto provvisorio** seleziona il conto principale su cui devono essere registrati i pagamenti prima che vengano liquidati sul conto bancario.
5. Chiudi la pagina.

## <a name="process-and-transfer-bridging-posting"></a>Elaborare e trasferire la registrazione provvisoria

Per creare ed elabobrare una registrazione provvisoria attieniti alla procedura seguente.

1. Vai a **Contabilità clienti &gt; Pagamenti &gt; Giornale di registrazione pagamenti cliente**.
2. Seleziona **Nuovo** per creare un giornale di registrazione.
3. Nel campo **Nome** seleziona un nome.
4. Aggiungi le righe al giornale di registrazione pagamenti cliente e seleziona il metodo di pagamento configurato per la registrazione provvisoria.
5. Registra il giornale. Le transazioni verranno registrate sul conto principale selezionato nel campo **Conto provvisorio** nella procedura precedente.

Quando le transazioni hanno autorizzato la banca e vuoi trasferire il pagamento dal conto provvisorio al conto di pagamento specificato per il metodo di pagamento, attieniti alla seguente procedura.

1. Fare clic su **Contabilità generale &gt; Inserimenti nel giornale di registrazione &gt; Giornali di registrazione generali**.
2. Seleziona **Nuovo** per creare un giornale di registrazione.
3. Nel campo **Nome** seleziona un nome.
4. Seleziona **Righe** per aprire i dettagli del giornale di registrazione.
5. Seleziona **Funzioni &gt; Seleziona transazioni provvisorie**.
6. Contrassegna ogni pagamento che è stato cancellato, quindi seleziona **Accetta**.
7. Registra il giornale.
