---
title: Report block list italiano
description: Ottenere come impostare e gestire il report list italiano.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261414
ms.assetid: 6816ee1b-cb27-4653-8254-19e229934e6f
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: cf8dd44520bf35c0aecb37c83599ccacee2a9119
ms.lasthandoff: 03/31/2017


---

# <a name="italian-black-list-report"></a>Report block list italiano

Ottenere come impostare e gestire il report list italiano.

Report black list italiano fornisce un elenco di transazioni tassabili con società situate in paesi con regimi fiscali privilegiati. Questi paesi sono indicati come "elencati list" dal governo italiano e presentano un rischio elevato da una prospettiva VAT. Questo report deve essere inviato agli uffici VAT italiani e in genere viene utilizzato dai responsabili, dai responsabili delle riscossioni, per il dipendente Contabilità clienti, dai responsabili della contabilità clienti, ai prezzi di vendita per il dipendente di vendita. È necessario impostare alcune considerazioni poter generare ** list italiano ** lo possibile ed esportarlo nel formato richiesto.

-   Selezionare una sequenza numerica per ** nera identificazione del report elenco ** il riferimento della sequenza numerica ** parametri per il commercio estero ** nella pagina.
-   Impostare il formato di report di mapping per ** annerisca l'elenco ** riferimento specificando i riferimenti alle configurazioni dichiarazioni elettroniche nel annerisca ** l'elenco ** ** parametri per il commercio estero ** nella pagina.
-   Impostare un paese come "black elencata".
-   Impostare la natura giuridica di una persona giuridica.
-   Impostare il paese di residenza di un cliente/fornitore estero.
-   Impostare il tipo di VAT per un codice VAT.

## <a name="set-up-a-country-or-region-as-black-listed"></a>Impostare un paese come "black list"
Scheda di utilizzo ** proprietà paese ** ** parametri per il commercio estero ** nella pagina per identificare un paese come "black list":

-   In ** codice IT di tre cifre ** sistemi, impostare il codice paese numerico come indicato nelle istruzioni del report dal governo italiano.
-   Selezionare ** black list paese/regione ** la casella di controllo.

** La provincia ** la scheda ** indirizzo ** impostato nella pagina nella Rubrica globale per specificare ** italiano codice provincia **.

## <a name="set-up-the-legal-nature-of-a-legal-entity"></a>Impostare la natura giuridica di una persona giuridica
Utilizzare ** numeri di registrazione ** la sezione ** persone giuridiche ** la finestra per specificare il numero di conto e la natura giuridica di una persona giuridica. La natura giuridica è la struttura legale cui viene registrato presso le autorità fiscali, ad esempio ** associazioni limitate ** della società, ** limitata a responsabilità (). s.r.l **, o ** società per azioni (STAZIONE TERMALE **).

## <a name="set-up-the-countryregion-of-residence-for-a-foreign-customervendor"></a>Impostare il paese di residenza di un cliente/fornitore straniero
Utilizzare ** i dati demografici di vendita ** la sezione ** clienti/fornitori ** pagine per impostare il paese di residenza di un cliente in un paese straniero e specificare le informazioni sul contatto primario, ad esempio il contatto, il luogo di nascita e la provincia di nascita primari. Solo le transazioni fatture con persone giuridiche situate in paesi con regimi fiscali privilegiati (paesi" black list") vengono incluse ** list italiano ** nel report. Se il cliente è anche un fornitore, le transazioni di vendita e acquisto vengono riepilogate come record ** list italiano ** nel report.

## <a name="set-up-the-vat-type-for-a-sales-tax-code"></a>Impostare il tipo di IVA per un codice IVA
Utilizzare ** codici VAT (** ** imposta ** &gt; ** imposte indirette ** &gt; ** VAT **) pagina per impostare il tipo di VAT da calcolare per ** list italiano ** il report. Il tipo di IVA specificato determina la categoria in cui gli importi netto e IVA per le fatture vengono stampati nel report e la posizione in cui si trovano nel file. Se l'importo netto o IVA fatturato in un periodo è negativo per un tipo di IVA specifico, viene visualizzato come accredito per il periodo precedente o l'anno precedente se il periodo inizia a gennaio. Utilizzare la seguente procedura per generare un report. È inoltre possibile visualizzare e aggiornare le transazioni prima di generare il report.

## <a name="generate-the-italian-black-list-report"></a>Generare il report list italiano
Utilizzare ** report list italiano ** la pagina per creare un nuovo report e le transazioni di trasferimento ** list italiano ** al report:

-   Specificare le informazioni ** dettagli relativi all'identificazione ** nell'area.
-   Utilizzato ** trasferimento ** trasferire le transazioni fatture fornitore e cliente ** transazioni ** la sezione in base ai criteri specificati ** dettagli relativi all'identificazione ** nell'area. Nel report vengono visualizzate solo le transazioni associate a un codice IVA. Verificare le transazioni e apportare eventuali modifiche, se necessario.
-   Utilizzato ** applicare la soglia ** escludere le fatture da ** list italiano ** report che con valore all'importo soglia specificato in ** importo soglia ** sistemi ** dettagli relativi all'identificazione ** nell'area.
-   Utilizzato ** report ** generare ed esportare il report come file.



