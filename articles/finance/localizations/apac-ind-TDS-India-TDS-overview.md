---
title: Panoramica sull'imposta dedotta all'origine (TDS) indiana
description: Questo argomento fornisce informazioni dettagliate sull'imposta dedotta all'origine (TDS) indiana. La documentazione TDS copre la funzionalità di questa capacità.
author: kailiang
ms.date: 03/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 27263ad2b158aa609167ad593fe9e0542f1227a5
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408148"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Panoramica sull'imposta dedotta all'origine (TDS) indiana

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni dettagliate sull'imposta dedotta all'origine (TDS) indiana.

La documentazione TDS copre la funzionalità di questa capacità. Descrive inoltre come eseguire l'impostazione di base per la TDS, calcolare la TDS sulle transazioni, completare il processo di liquidazione della TDS, registrare i numeri di certificato TDS e generare richieste TDS, dichiarazioni TDS e certificati TDS. La documentazione include i seguenti argomenti:

- [Impostazione di base per TDS](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [Designer formula e funzionalità del limite di soglia utilizzati per il calcolo della TDS](apac-ind-TDS-Formula-designer.md)
- [Calcolo della TDS su fatture, pagamenti, effetti passivi e transazioni interaziendali](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [Processo di liquidazione TDS periodico e liquidazione degli importi TDS ai fornitori dell'autorità TDS](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [Registrazione e aggiornamento delle date e dei numeri di certificato TDS](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Introduzione a TDS

Conformemente all'Income tax Act del 1961, l'imposta sul reddito viene dedotta alla fonte dal beneficiario del servizio al momento del pagamento anticipato o della contabilizzazione del credito, a seconda di quale si verifica per primo. La persona che effettua il pagamento deve detrarre l'importo dell'imposta e pagare solo il saldo netto al fornitore del servizio. La TDS viene applicata ai servizi specificati dal governo e l'imposta viene detratta utilizzando le aliquote specificate dal governo relative a un periodo. Il tasso di detrazione si basa sullo stato dell'entità che riceve il pagamento o fornisce il servizio. Gli stati sono **Persona fisica**, **Famiglia hindu completa** (**HUF**), **Società**, **Ditta**, **Associazione di persone** (**AOP**), **Corpo di individui** (**BOI**) e **Autorità locale**.

Le sezioni seguenti elencano i servizi a cui viene applicata la TDS, come specificato dal governo indiano.

**Residenti**

- Reddito da stipendi (sezione 192)
- Reddito da interessi su titoli (sezione 193)
- Reddito da dividendi (sezione 194)
- Reddito da interessi (sezione 194A)
- Reddito da lotterie o giochi (sezione 194B)
- Vincite da corse di cavalli ecc. (sezione 194BB)
- Appaltatori e subappaltatori (sezione 194C)
- Commissione assicurativa (sezione 194D)
- Reddito da depositi nel quadro di un regime di risparmio nazionale (sezione 194EE)
- Reddito da fondi comuni di investimento o UTI (sezione 194F)
- Commissioni, remunerazioni, premi ecc., per vendita o lotteria (sezione 194G)
- Pagamento di commissioni o intermediazione (sezione 194H)
- Affitto (sezione 194I)
- Servizio professionale (sezione 194J)
- Reddito da unità (sezione 194K)
- Pagamento di compensazioni per l'acquisizione di determinati beni immobili (sezione 194LA)

**Non residenti**

- Pagamenti a sportivi o associazioni sportive non residenti (sezione 194E)
- Altre somme (sezione 195)
- Reddito relativo a unità di non residenti (sezione 196A)

    - Reddito da obbligazioni o azioni in valuta estera della Indian Company (sezione 196C)
    - Redditi di investitori istituzionali esteri da titoli (sezione 196D)
    - Stipendio e tutti gli altri redditi positivi sotto qualsiasi reddito nominale (sezione 192)
    - Interessi su titoli (sezione 193)
    - Interessi diversi da interessi su titoli (sezione 194A)
    - Pagamenti ad appaltatori e subappaltatori (sezione 194C)
    - Vincite da lotterie o cruciverba (sezione 194B)
    - Vincite da corse di cavalli (in virtù della sezione 194BB)
    - Commissione assicurativa che copre tutti i pagamenti per l'acquisizione di attività assicurative (sezione 194D)
    - Qualsiasi interesse diverso dagli interessi su titoli pagabili a non residenti che non sono una società o una società estera (sezione 195)
    - Pagamento a uno sportivo non residente compreso un'atleta o un'associazione o un ente sportivo. In caso di sportivo non residente, sono inclusi pagamenti relativi a pubblicità e articoli su qualsiasi gioco/sport in India in giornali, riviste e così via (sezione 194E)
    - Pagamento in relazione a depositi sotto NSS \[Programma di risparmio nazionale\] (sezione 194EE)
    - Pagamento a seguito di riacquisto di unità da parte di un Fondo Comune o UTI (sezione 194F)
    - Pagamento per commissioni o intermediazione (sezione 194H)
    - Pagamento di affitto (sezione 194I)
    - Pagamento di compensi per servizi professionali o tecnici (sezione 194J)
    - Commissione a stocchisti, distributori, acquirenti e venditori di biglietti della lotteria, inclusa la remunerazione o il premio di tali biglietti (sezione 194G)
    - Reddito da unità acquistate in valuta estera o plusvalenza a lungo termine derivante dal trasferimento di tali unità acquistate in valuta estera (sezione 196B)
    - Pagamento di qualsiasi reddito a non residenti in relazione a interessi o dividendi su obbligazioni e azioni (sezione 196C)

La TDS viene calcolata su acquisti, vendite, resi di vendita, note di accredito, acquisizioni di cespiti, pagamenti anticipati, effetti passivi, imposte su lavori e transazioni interaziendali.

> [!NOTE]
> Nello scenario fiscale indiano attuale, la TDS non viene calcolata sulle transazioni di vendita. Tuttavia, il sistema include una disposizione per calcolare la TDS recuperabile su transazioni di vendita, in particolare per le transazioni interaziendali.

Il calcolo della TDS prende sempre in considerazione la soglia e la soglia di eccezione definite per il componente TDS.

È necessario eseguire il processo di liquidazione periodica della TDS e i pagamenti della TDS devono essere liquidati ai fornitori dell'autorità TDS.

Le date e i numeri dei certificati TDS ricevuti da fornitori o clienti possono essere registrati e aggiornati. Inoltre, le dichiarazioni trimestrali con moduli 26Q e 27Q e il certificato con modulo 16A per la TDS possono essere generati in Finance.

## <a name="setting-up-and-working-with-tds"></a>Impostazione e utilizzo della TDS

Di seguito è riportata una panoramica del processo di impostazione e utilizzo della TDS:

1. **Impostazione TDS**

    - Impostazione dei parametri:

        - In Parametri di contabilità generale, attiva i parametri correlati alla TDS.
        - In Parametri di contabilità generale, imposta la sequenza numerica per i pagamenti della ritenuta d'acconto.
        - Imposta i parametri in Contabilità fornitori e Contabilità clienti.

    - Impostazione di base:

        - Imposta i numeri di registrazione TDS per un'azienda, clienti e fornitori.
        - Imposta gruppi di componenti TDS.
        - Imposta componenti TDS, associaci gruppi di componenti TDS e definisci la soglia e la soglia di eccezione per gli stessi.
        - Imposta le autorità TDS.
        - Imposta i periodi di liquidazione TDS.
        - Imposta i codici imposta TDS e associaci i componenti TDS.
        - Imposta i gruppi di imposte TDS e associaci i codici imposta TDS.
        - In Designer formula, definisci una formula per calcolare la TDS per un gruppo TDS.
        - Registra i numeri di certificato delle concessioni TDS.

    - Impostazione di conti CoGe e società:

        - Imposta i conti CoGe TDS a debito e a credito.
        - Imposta una detrazione fiscale e un numero di conto imposta (TAN) nonché una categoria di tipo di detrazione per la società.

    - Altre impostazioni:

        - Imposta uno scadenziario pagamenti che includa l'allocazione TDS.
        - Imposta un tipo di commissione pagamento per i pagamenti all'autorità TDS.
        - Imposta le informazioni su gruppi TDS, numeri di conto permanenti (PAN) e TAN per fornitori e clienti.

2. **Calcolo della TDS nelle transazioni:**

    - Fatture e pagamenti
    - Effetti passivi
    - Pagamenti anticipati
    - Anticipi

3. **Liquidazione TDS:**

    - Processo di liquidazione TDS periodico
    - Liquidazione di pagamenti TDS ai fornitori dell'autorità TDS e generazione del challan TDS

4. **Richieste, dichiarazioni e certificati TDS:**

    - Registra e aggiorna date e numeri di certificati TDS.
    - Genera una richiesta TDS e una richiesta TDS registrata.
    - Genera dichiarazioni trimestrali TDS e e-TDS con modulo 27A, modulo 26Q e modulo 27Q.
    - Genera un certificato TDS con modulo 16A.
