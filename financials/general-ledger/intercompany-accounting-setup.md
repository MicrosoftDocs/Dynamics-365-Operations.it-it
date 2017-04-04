---
title: "Impostazione della contabilità interaziendale"
description: "In questo argomento viene descritto come impostare la contabilità interaziendale per consentire l&quot;utilizzo dei giornali di registrazione interaziendale per le allocazioni contabili e i giornali di registrazione finanziari, ad esempio i giornali di registrazione giornalieri, i giornali di registrazione fatture fornitore e giornali di registrazione pagamenti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Impostazione della contabilità interaziendale

In questo argomento viene descritto come impostare la contabilità interaziendale per consentire l'utilizzo dei giornali di registrazione interaziendale per le allocazioni contabili e i giornali di registrazione finanziari, ad esempio i giornali di registrazione giornalieri, i giornali di registrazione fatture fornitore e giornali di registrazione pagamenti.

I giornali di registrazione interaziendale possono essere create in numerosi scenari, ad esempio per i giornali di registrazione giornalieri, i giornali di registrazione fatture fornitore, le allocazioni contabili e i pagamenti centralizzati. Per attivare questi scenari, è necessario impostare la contabilità interaziendale.

## <a name="define-main-accounts"></a>Definire i conti principali
Innanzitutto, è necessario creare i conti principali interaziendali da utilizzare per le voci contabili Dovuto a e Dovuto da. È consigliabile utilizzare conti principali univoci per ciascuna società in modo da semplificare la riconciliazione e l'eliminazione di voci contabili interaziendali. Se si utilizza una dimensione del partner commerciale o corrispondenti per identificare la parte interaziendale, è possibile definire la dimensione come fisse sul conto principale definito nella contabilità interaziendale. Quando si impostano i conti principali, è necessario impostare ** tipo di conto principale ** il campo su ** lo stato patrimoniale ** ** conti principali ** nella pagina.

## <a name="define-journal-names"></a>Consente di definire i nomi di giornale di registrazione
Quindi, è necessario definire un nome di giornale di registrazione. Impostare ** tipo di giornale di registrazione ** il campo su ** giornaliero ** ** nomi di giornale di registrazione ** nella pagina. È consigliabile utilizzare un nome di giornale di registrazione specifico per contabilità interaziendale.

## <a name="define-intercompany-accounting-setup"></a>Definire l'impostazione della contabilità interaziendale
** Contabilità interaziendale ** la pagina viene utilizzata per creare coppie le persone giuridiche che potrà essere gestito tra loro. L'impostazione della contabilità interaziendale viene diviso, in modo tale che l'impostazione sia visibile da tutte le persone giuridiche. Quando si crea una nuova coppia della persona giuridica, assicurarsi che sia presente della persona giuridica è definita come società di origine rispetto alla società di destinazione. Durante l'immissione di transazioni interaziendali, la transazione deve determinare la persona giuridica è iniziale o producente la transazione. Ad esempio, la contabilità interaziendale è impostata per USMF (nascere) e USSI destinazione (). Se un utente è attivo in USSI e immette una transazione interaziendale con USMF, la transazione non registrata nella contabilità interaziendale viene definita solo per USMF che è l'iniziatore. Se una società può produrre una transazione, sarà necessario creare una seconda coppia della persona giuridica per l'impostazione reciproca. 

Selezionare ** conto in Dare ** (da) e ** conto in Avere dovuto (**) sia per la nascita della persona giuridica di destinazione. Consente di definire ** nome di giornale di registrazione ** verrà utilizzato quando viene creata la transazione nella società di destinazione. Il giornale di registrazione per la società di origine è già noto che ha selezionato dall'utente durante la creazione della transazione interaziendale. 

Infine, selezionare quali persona giuridica riceverà gli importi di supporto rappresentanti, ad esempio lo sconto di cassa o i profitti realizzati/perdite per i pagamenti centralizzati. 

Relazione reciproca può essere impostata in modo semplice ** la contabilità interaziendale ** nella pagina utilizzando ** creare una relazione reciproca ** il pulsante dopo la prima coppia della persona giuridica viene creata. Quando la coppia reciproca viene creata, le informazioni relative alla società di destinazione verranno copiate nella società di origine e viceversa. Il giornale di registrazione definito per la società di destinazione rimarrà. La maggior parte delle organizzazioni utilizzano la stessa convenzione di denominazione per i nomi di giornale di registrazione, in modo che il nome del giornale di registrazione è lo stesso. Se il nome di giornale di registrazione è diverso, un avviso sembrerà nel campo la registrazione del giornale di registrazione non sono presenti e un giornale di registrazione diverso può essere selezionato.


