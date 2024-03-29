---
title: Report della distinta di pagamento per l'Europa
description: In questo articolo vengono descritti i report della distinta di pagamento per l'Europa.
author: mrolecki
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMLegalEntities, ProjFormletterParameters, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 264604
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: mrolecki
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 99e06f383c94db6d2a1585d33d9f183b0984f5a3
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689592"
---
# <a name="payment-slip-report-for-europe"></a>Report della distinta di pagamento per l'Europa

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti i report della distinta di pagamento per l'Europa.

La funzionalità per i report della distinta di pagamento è disponibile per le persone giuridiche il cui indirizzo principale si trova in Danimarca, Belgio, Norvegia, Svizzera o Finlandia. Le aziende spesso allegano le distinte di pagamento stampate alle fatture per fornire un riferimento di pagamento per la registrazione e la liquidazione. La distinta di pagamento può essere utilizzata per fatture di progetti o servizi, lettere di sollecito, note d'interesse ed estratti conto, oltre che per fatture di vendita e fatture a testo libero.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Impostare un numero ID creditore (Solo Danimarca)
Seguire questi passaggi per immettere il numero di identificazione (ID) del creditore della società. Questo numero viene fornito dall'istituto finanziario. Viene utilizzato come riferimento quando si ricevono i pagamenti dei clienti tramite istituti finanziari.

1.  Fare clic su **Amministrazione organizzazione** &gt; **Impostazione** &gt; **Organizzazione** &gt; **Persone giuridiche**.
2.  Nella Scheda dettaglio **Informazioni conto bancario**, nel campo **ID creditore IF**, immettere l'ID creditore univoco di otto cifre.
3.  Chiudere il modulo per salvare le modifiche.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Impostare un formato per l'allegato distinta di pagamento per fatture, note d'interesse, lettere di sollecito e rendiconti bancari
Seguire questi passaggi per impostare un formato per gli allegati distinta di pagamento che accompagnano fatture di vendita, fatture a testo libero, note d'interesse, lettere di sollecito ed estratti conto.

1.  Fare clic su **Contabilità clienti** &gt; **Impostazione** &gt; **Moduli** &gt; **Impostazione moduli**.
2.  Nella scheda **Fattura**, nel campo **Allegato pagamento associato su fattura cliente**, selezionare il formato per l'allegato distinta di pagamento.
3.  Nelle schede **Fattura a testo libero**, **Nota d'interesse**, **Lettera di sollecito** ed **Estratto conto** selezionare un formato per la distinta di pagamento per ciascun tipo di documento.
4.  Chiudere il modulo per salvare le modifiche.

Seguire questi passaggi per impostare un formato per gli allegati distinta di pagamento che accompagnano le fatture di progetto.

1.  Fare clic su **Gestione progetti e contabilità** &gt; **Impostazione** &gt; **Moduli** &gt; **Impostazione moduli**.
2.  Nel campo **Allegato pagamento associato** selezionare il formato per la distinta base.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Assegnare un formato di allegato per la distinta di pagamento a un conto cliente
Dopo aver impostato il formato per l'allegato della distinta di pagamento per fatture di vendita, fatture a testo libero, note d'interesse, lettere di sollecito estratti conto e fatture di progetto, è possibile assegnare formati specifici per un cliente selezionato.

1.  Fare clic su **Contabilità clienti** &gt; **Comune** &gt; **Clienti** &gt; **Tutti i clienti**.
2.  Creare un nuovo cliente o selezionarne uno esistente.
3.  Nella Scheda dettaglio **Fattura e consegna**, nei campi **Su fattura cliente**, **Su fattura a testo libero**, **Su nota d'interesse**, **Su lettera di sollecito**, **Su fattura di progetto** e **Su un estratto conto**, selezionare il formato di allegato per le distinte di pagamento che accompagneranno i documenti di ciascun tipo inviati al cliente selezionato.
4.  Chiudere il modulo per salvare le modifiche.


Per ulteriori informazioni sulla configurazione e il mantenimento degli ID di pagamento, fai riferimento a [NO-00002 Pagamento cliente in base all'ID pagamento](tasks/no-00002-customer-payment-based-payment-id.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
