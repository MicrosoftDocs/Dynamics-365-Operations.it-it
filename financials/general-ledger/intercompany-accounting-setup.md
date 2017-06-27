---
title: "Configurazione della contabilità interaziendale"
description: "Questo articolo illustra come impostare la contabilità interaziendale in modo da poter utilizzare i giornali di registrazione interaziendali per allocazioni contabili e giornali di registrazione finanziari, ad esempio giornali di registrazione giornalieri, giornali di registrazione fatture fornitore e giornali di registrazione pagamenti."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 506c7958a90bd5a891ea9859c679fcadb64a64d4
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="intercompany-accounting-setup"></a>Configurazione della contabilità interaziendale

[!include[banner](../includes/banner.md)]


Questo articolo illustra come impostare la contabilità interaziendale in modo da poter utilizzare i giornali di registrazione interaziendali per allocazioni contabili e giornali di registrazione finanziari, ad esempio giornali di registrazione giornalieri, giornali di registrazione fatture fornitore e giornali di registrazione pagamenti.

È possibile creare giornali di registrazione interaziendali in diversi scenari, ad esempio per giornali di registrazione giornalieri, giornali di registrazione fatture fornitore, allocazioni della contabilità generale e pagamenti centralizzati. Per attivare questi scenari, è necessario impostare la contabilità interaziendale.

## <a name="define-main-accounts"></a>Definire conti principali
Innanzitutto, è necessario creare i conti principali interaziendali da utilizzare per le voci contabili Dovuto a e Dovuto da. È consigliabile utilizzare conti principali univoci per ciascuna società in modo da semplificare la riconciliazione e l'eliminazione di voci contabili interaziendali. Se si utilizza una dimensione di controparte o partner commerciale per identificare la parte interaziendale, è possibile definire tale dimensione come fissa nel conto principale definito nella contabilità interaziendale. Quando si impostano i conti principali, è necessario impostare il campo **Tipo di conto principale** sul valore **Stato patrimoniale** nella pagina **Conti principali**.

## <a name="define-journal-names"></a>Definire nomi di giornali di registrazione
Quindi, è necessario definire un nome di giornale di registrazione. Impostare il campo **Tipo di giornale di registrazione** sul valore **Giornaliero** nella pagina **Nomi giornale di registrazione**. È consigliabile utilizzare un nome di giornale di registrazione specifico per contabilità interaziendale.

## <a name="define-intercompany-accounting-setup"></a>Definire la configurazione della contabilità interaziendale
La pagina **Contabilità interaziendale** la pagina viene utilizzata per creare coppie di persone giuridiche che possono eseguire transazioni tra loro. La configurazione della contabilità interaziendale è condivisa in modo che sia visibile all'interno di tutte le persone giuridiche. Quando si crea una nuova coppia di persone giuridiche, assicurarsi di conoscere quale persona giuridica è definita come società di origine rispetto alla società di destinazione. Durante l'immissione di transazioni interaziendali, la transazione determina quale persona giuridica inizia o dà origine alla transazione. Ad esempio, la contabilità interaziendale è impostata per USMF (di origine) e USSI (di destinazione). Se un utente è attivo in USSI e immette una transazione interaziendale con USMF, la transazione non verrà registrata perché la contabilità interaziendale viene definita solo se USMF è la società di origine. Se entrambe le società possono dare origine a una transazione, sarà necessario creare una seconda coppia di persone giuridiche per la configurazione reciproca. 

Selezionare **Conto in Dare (dovuto da)** e **Conto in Avere (dovuto a)** per entrambe le persone giuridiche di origine e di destinazione. Definire il **Nome giornale di registrazione** che verrà utilizzato quando viene creata la transazione nella società di destinazione. Il giornale di registrazione per la società di origine è già noto perché è stato selezionato dall'utente durante la creazione della transazione interaziendale. 

Infine, selezionare la persona giuridica che riceverà la contabilità per gli importi di supporto, ad esempio come sconto di cassa o le perdite/i profitti realizzati per i pagamenti centralizzati. 

Una relazione reciproca può essere configurata in modo semplice nella pagina **Contabilità interaziendale** utilizzando il pulsante **Crea relazione reciproca** dopo la creazione della prima coppia di persone giuridiche. Quando la coppia reciproca viene creata, le informazioni relative alla società di destinazione vengono copiate nella società di origine e viceversa. Il giornale di registrazione definito per la società di destinazione rimarrà. La maggior parte delle organizzazioni utilizza la stessa convenzione di denominazione per i propri nomi di giornale di registrazione, in modo che il nome del giornale di registrazione sia lo stesso. Se il nome del giornale di registrazione è diverso, verrà visualizzato un avviso nel campo per segnalare che il giornale di registrazione non esiste e che è possibile selezionare un giornale di registrazione diverso.




