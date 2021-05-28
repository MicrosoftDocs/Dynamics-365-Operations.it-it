---
title: Calcolo imposte (anteprima)
description: In questo argomento vengono illustrati l'ambito e le funzionalità generali di Calcolo imposte.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b26472e195d9bdbba340a118c106de1a4dc79b34
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021934"
---
# <a name="tax-calculation-preview"></a>Calcolo imposte (anteprima)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Calcolo imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte. Il motore fiscale è completamente configurabile. Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta. Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.

Calcolo imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.

Calcolo imposte è un motore fiscale basato su microservizi che offre scalabilità esponenziale. Ti consente di eseguire le attività descritte di seguito:

- Configura Calcolo imposte tramite Regulatory Configuration Service (RCS). RCS è una versione avanzata dello strumento di progettazione per la creazione di report elettronici (ER) ed è disponibile come servizio autonomo.
- Configura la matrice fiscale per determinare automaticamente i codici e le aliquote fiscali.
- Configura la matrice fiscale per determinare automaticamente la partita IVA.
- Configura lo strumento di progettazione del calcolo delle imposte per definire le formule e le condizioni.
- Condividi la determinazione delle imposte e la soluzione di calcolo tra le persone giuridiche.

Per utilizzare il servizio di calcolo delle imposte, installa il componente aggiuntivo del servizio di calcolo delle imposte dal progetto in Microsoft Dynamics Lifecycle Services (LCS). Quindi completa la configurazione in RCS e abilita il servizio di calcolo delle imposte in Finance and Supply Chain Management. Per altre informazioni, vedi [Introduzione al servizio per le imposte](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilità

Calcolo imposte è disponibile solo in ambienti sandbox e per clienti selezionati, attraverso un programma di anteprima pubblica. Alla fine, diventerà generalmente disponibile per tutti i clienti e negli ambienti di produzione.

In seguito, verranno fornite continuamente nuove funzionalità, pertanto assicurati di controllare spesso la documentazione più aggiornata per conoscere la copertura e l'ambito delle funzionalità supportate.

Calcolo imposte viene distribuito nelle seguenti aree geografiche di Azure. Verrà inoltre distribuito in più aree geografiche di Azure, in base alle esigenze del cliente:

- Stati Uniti
- Europa

> [!NOTE]
> Calcolo imposte non supporta le distribuzioni locali di Dynamics 365. Inoltre non supporta le versioni precedenti, come Dynamics AX 2012.

## <a name="feature-highlights"></a>Caratteristiche principali

- Una matrice fiscale configurabile per determinare automaticamente e calcolare le imposte
- Supporto per più partite IVA
- Supporto dell'ordine di trasferimento per la determinazione e il calcolo delle imposte
- Supporto per ordini di trasferimento per la determinazione di più partite IVA

## <a name="supported-transactions"></a>Transazioni supportate

Calcolo imposte può essere abilitato per persona giuridica e transazione. Sono supportate le transazioni che seguono:

- Processo di vendita

    - Offerta di vendita
    - Ordine cliente
    - Conferma
    - Distinta di prelievo
    - Documento di trasporto
    - Fattura di vendita
    - Nota di accredito
    - Ordine di reso
    - Spese varie intestazione
    - Spese varie riga

- Processo di acquisto

    - Ordine fornitore
    - Conferma
    - Elenco entrate
    - Entrata prodotti
    - Fattura acquisto
    - Spese varie intestazione
    - Spese varie riga
    - Nota di accredito
    - Ordine di reso
    - Richiesta di acquisto
    - Spese varie riga di richiesta di acquisto
    - Richiesta di offerta
    - Spese varie intestazione richiesta di offerta
    - Spese varie riga richiesta di offerta

- Processo magazzino

    - Ordine di trasferimento - spedizione
    - Ordine di trasferimento - ricezione

## <a name="related-resources"></a>Risorse correlate

[Introduzione al servizio per le imposte](./global-get-started-with-tax-calculation-service.md)

[Più numeri di registrazione IVA](./emea-multiple-vat-registration-numbers.md)

[Supporto della funzione fiscale per l'ordine di trasferimento](./tasks/tax-feature-support-for-transfer-order.md)

[Come creare l'estensione nel servizio per le imposte](./tax-service-add-data-fields-tax-integration-by-extension.md)