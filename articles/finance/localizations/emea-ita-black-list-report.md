---
title: Report block list italiano
description: Informazioni su come impostare e gestire il report black list italiano.
author: EvgenyPopovMBS
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BlackListTable_IT, IntrastatParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 261414
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 32aaf0d206551b709f6e722f3a3834c8926ad38b77cfd0f362514dd45a01d81d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764222"
---
# <a name="italian-black-list-report"></a>Report block list italiano

[!include [banner](../includes/banner.md)]

Informazioni su come impostare e gestire il report black list italiano.

Questo record fornisce un elenco di transazioni tassabili con società situate in paesi con regimi fiscali privilegiati. Questi paesi sono indicati come *black list* dal governo italiano e presentano un rischio elevato dal punto di vista fiscale. Questo report deve essere inviato agli uffici IVA italiani e in genere viene utilizzato da ragionieri, responsabili delle riscossioni, addetti alla contabilità clienti, responsabili della contabilità clienti, manager delle vendite e addetti alle vendite. È necessario impostare alcuni elementi prima di poter generare il report ed esportarlo nel formato richiesto.

-   Selezionare una sequenza numerica per il riferimento della sequenza numerica di **ID report black list** nella pagina **Parametri per il commercio estero**.
-   Impostare il mapping del formato di report per il report Black list specificando i riferimenti alle configurazioni di report elettronici nella **black list** nella pagina **Parametri per il commercio estero**.
-   Impostare un paese o una regione come "black list".
-   Impostare la natura giuridica di una persona giuridica.
-   Impostare il paese di residenza di un cliente/fornitore straniero.
-   Impostare il tipo di IVA per un codice IVA.

## <a name="set-up-a-country-or-region-as-black-listed"></a>Impostare un paese come "black list"
Utilizzare la scheda **Proprietà paese** nella pagina **Parametri per il commercio estero** per includere un paese nell'elenco:

-   Nel campo **Codice IT di tre cifre**, impostare il codice paese numerico come indicato nelle istruzioni relative al report del governo italiano.
-   Selezionare la casella di controllo **Paese in black list**.

Utilizzare la scheda **Provincia** nella pagina **Impostazione indirizzo** nella Rubrica globale per specificare il **Codice provincia italiana**.

## <a name="set-up-the-legal-nature-of-a-legal-entity"></a>Impostare la natura giuridica di una persona giuridica
Utilizzare la sezione **Numeri di registrazione** nella pagina **Persone giuridiche** per specificare il codice fiscale e la natura giuridica di una persona giuridica. La natura giuridica è la struttura legale della persona giuridica registrata presso le autorità fiscali competenti, ad esempio **Società in accomandita per azioni**, **Società a responsabilità limitata (SRL)** o **Società per azioni (SPA)**.

## <a name="set-up-the-countryregion-of-residence-for-a-foreign-customervendor"></a>Impostare il paese di residenza di un cliente/fornitore straniero
Utilizzare la sezione **Dati demografici vendite** nelle pagine **Clienti/fornitori** per impostare il paese di residenza di un cliente in un paese straniero e specificare le informazioni sul contatto primario, ad esempio il contatto primario, il luogo di nascita e la provincia di nascita. Solo le transazioni fatture con persone giuridiche residenti in paesi con regimi fiscali privilegiati (paesi "black list") sono incluse nel report. Se il cliente è anche un fornitore, le transazioni di vendita e acquisto vengono riepilogate come un solo record nel report.

## <a name="set-up-the-vat-type-for-a-sales-tax-code"></a>Impostare il tipo di IVA per un codice IVA
Utilizzare la pagina **Codici IVA** (**Imposta** &gt; **Imposte indirette** &gt; **IVA**) per impostare il tipo di imposta da calcolare per il report. Il tipo di IVA specificato determina la categoria in cui gli importi netto e IVA per le fatture vengono stampati nel report e la posizione in cui si trovano nel file. Se l'importo netto o IVA fatturato in un periodo è negativo per un tipo di IVA specifico, viene visualizzato come accredito per il periodo precedente o l'anno precedente se il periodo inizia a gennaio. Per generare un report, attenersi alla seguente procedura. È inoltre possibile visualizzare e aggiornare le transazioni prima di generare il report.

## <a name="generate-the-report"></a>Genera il report

Utilizzare la pagina **Report black list italiano** per creare un nuovo report e trasferire le transazioni al report:

-   Specificare le informazioni nella sezione **Generale**.
-   Utilizzare **Trasferimento** per trasferire le transazioni delle fatture cliente e fornitore alla sezione **Transazioni** in base ai criteri che sono specificati nella sezione **Generale**. Nel report vengono visualizzate solo le transazioni associate a un codice IVA. Verificare le transazioni e apportare eventuali modifiche, se necessario.
-   Utilizzare **Applica soglia** per escludere le fatture dal report inferiori all'importo di soglia specificato nel campo **Importo soglia** nella sezione **Generale**.
-   Utilizzare **Report** per generare ed esportare il report come file.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]