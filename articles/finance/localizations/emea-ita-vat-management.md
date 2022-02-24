---
title: Gestione e reporting IVA per data di effettuazione dell'operazione (data del libro IVA)
description: In questo argomento vengono fornite informazioni sulle modifiche alla gestione dell'Imposta sul Valore Aggiunto (IVA) in Italia.
author: LizaGolub
manager: AnnBe
ms.date: 09/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: kfend
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: ''
ms.openlocfilehash: 14c044c1f674e94bdcb8bc1c66d794727898799d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408092"
---
# <a name="vat-management-and-reporting-by-tax-point-date-date-of-vat-register"></a>Gestione e reporting IVA per data di effettuazione dell'operazione (data del libro IVA)

[!include [banner](../includes/banner.md)]

Il 23 ottobre 2018, il Decreto Legge 119 (D.L.119/2018) ha introdotto una modifica nella gestione dell'IVA in Italia. Questa modifica è diventata effettiva il 1° luglio 2019. Di seguito è riportato un riepilogo della modifica:

- I contribuenti IVA possono recuperare l'IVA a credito nella liquidazione IVA mensile quando viene attivata la data di effettuazione dell'operazione IVA. Questo recupero è possibile anche se la fattura di acquisto viene ricevuta e registrata nella contabilità IVA a credito prima del quindicesimo giorno del mese successivo. Questa regola non si applica alle transazioni in cui la data di effettuazione dell'operazione IVA viene attivata in un anno fiscale diverso dall'anno fiscale in cui la fattura di acquisto viene ricevuta.
- Per la fornitura di merci e servizi, la fattura può essere emessa entro il quindicesimo giorno del mese successivo al mese in cui la data di effettuazione dell'operazione IVA è stata attivata. Le fatture emesse e registrate prima del quindicesimo giorno del mese successivo al mese in cui la data di effettuazione dell'operazione IVA è stata attivata devono essere incluse nella liquidazione IVA del mese precedente.
- A partire dal 1° luglio 2019, la fattura può essere emessa entro 10 giorni dalla data di effettuazione dell'operazione IVA. Se la fattura non viene emessa alla data di effettuazione dell'operazione IVA, deve includere un riferimento a tale data oltre alla data di fatturazione.
- Le fatture registrate prima del quindicesimo giorno del mese successivo ma che presentano un riferimento alla liquidazione IVA precedente non devono interrompere la registrazione sequenziale. Se le fatture presentano una data di effettuazione dell'operazione IVA nel mese precedente ma una data di fatturazione nel mese corrente, devono essere registrate in ordine cronologico con le fatture nel mese corrente che presentano un riferimento indicante che tali fatture sono relative alla liquidazione IVA precedente.
- Le società che emettono la fattura di vendita il giorno stesso, senza applicare la modifica introdotta dal D.L.119/2018, sono in regola.

La funzionalità Data del libro IVA supporta le modifiche introdotte dal D.L.119/2018. Questa funzionalità è presente in Microsoft Dynamics 365 for Finance and Operations versione 10.0.6 (novembre 2019) e versioni successive.

Prima di poter utilizzare la funzionalità Data del libro IVA, è necessario attivarla nell'area di lavoro **Gestione funzionalità**. Questa funzionalità introduce un nuovo campo di tipo data, ovvero **Data del libro IVA**, per le transazioni IVA. La data aggiuntiva verrà utilizzata come criterio di determinazione della data di effettuazione dell'operazione IVA per l'inclusione delle transazioni IVA nell'ambito del periodo di liquidazione IVA e del reporting per le dichiarazioni IVA.

> [!NOTE]
> Il sistema non consente la registrazione di una fattura se il valore del campo **Data del libro IVA** della fattura rientra in un intervallo chiuso del periodo di liquidazione IVA.
>
> Inoltre, il sistema non consente l'aggiornamento del campo **Data del libro IVA** con un valore che rientra in un intervallo chiuso del periodo di liquidazione IVA.

Per ulteriori informazioni sulla funzionalità Data del libro IVA, vedere [Data di effettuazione dell'operazione (Data del libro IVA)](emea-tax-point-date.md).

## <a name="effect-of-the-date-of-vat-register-feature-on-vat-settlement-and-reporting"></a>Effetto della funzionalità Data del libro IVA sulla liquidazione IVA e sul reporting IVA

Quando la funzionalità Data del libro IVA è attivata, gli utenti nelle persone giuridiche che hanno l'indirizzo principale in Italia potranno impostare l'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** su **Sì**.

![Pagina Parametri di contabilità generale con campo Data del libro IVA evidenziato nella scheda IVA](./media/date-of-vat-gl-parameter.png)

Quando questa opzione è impostata su **Sì**, il processo **Liquida e registra IVA** e il report **Liquidazione IVA italiana** considereranno le transazioni IVA in base alla data in cui l'IVA è stata registrata anziché in base alla data in cui la transazione è stata registrata.

> [!NOTE]
> Il sistema non consentirà l'esecuzione delle seguenti operazioni: 
> 
> - Impostare l'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** su **Sì** se eventuali transazioni IVA sono state registrate in un intervallo aperto del periodo di liquidazione IVA, ma il valore del campo **Data del libro IVA** rientra in un intervallo chiuso del periodo di liquidazione IVA.
> - Impostare l'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** su **No** se il valore del campo **Data del libro IVA** di qualsiasi transazione IVA rientra in un intervallo chiuso del periodo di liquidazione IVA, ma le transazioni sono state registrate in un intervallo aperto del periodo di liquidazione IVA.
> - Disattivare la funzionalità Data del libro IVA nell'area di lavoro **Gestione funzionalità** se l'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** è impostata su **Sì** in almeno una persona giuridica.

## <a name="sales-tax-transactions-extension-consistency-check"></a>Verifica di coerenza Estensione delle transazioni IVA

Il campo **Data del libro IVA** si trova in una tabella TaxTrans_W. Questa tabella è un'estensione della tabella TaxTrans. Se una società imposta l'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** su **Sì**, il comportamento delle query relative all'origine dati in alcune pagine del sistema cambia. Tali query sono ora incluse nella tabella TaxTrans_W. Di conseguenza, gli utenti potrebbero non vedere le transazioni IVA registrate in un periodo precedente. Questo problema si verifica in quanto la tabella TaxTrans_W non è stata utilizzata in precedenza e di conseguenza non vi sono transazioni corrispondenti nella tabella.

Per evitare tale problema, è possibile eseguire la verifica di coerenza **Estensione delle transazioni IVA**. Selezionare **Amministrazione sistema** \> **Attività periodiche** \> **Database** \> **Verifica coerenza**. Nella finestra di dialogo **Verifica coerenza**, espandere **Programma** \> **Contabilità generale** \> **IVA** e quindi selezionare la casella di controllo **Estensione delle transazioni IVA**. Non è necessario selezionare le caselle di controllo di livello superiore se si desidera eseguire solo la verifica di coerenza **Estensione delle transazioni IVA**.

![ Finestra di dialogo Verifica coerenza con la casella di controllo Estensione delle transazioni IVA evidenziata](./media/date-of-vat-consistency-check.png)

Quando si esegue la verifica di coerenza **Estensione delle transazioni IVA**, impostare le seguenti opzioni:

- **Verifica** - Determina se mancano delle transazioni nella tabella TaxTrans_W. Il sistema notificherà il numero di transazioni presenti nella tabella TaxTrans per le quali non vi sono record corrispondenti nella tabella TaxTrans_W.
- **Correggi** - Compensa i record mancanti nella tabella TaxTrans_W. Il sistema inserirà i record corrispondenti nella tabella TaxTrans_W. Le transazioni IVA registrate in periodi precedenti saranno di nuovo visibili nel sistema. 

Assicurarsi di selezionare la data corretta nel campo **Data iniziale** della finestra di dialogo **Verifica coerenza**. Lasciare vuoto il campo **Data iniziale** se si desidera recuperare tutte le transazioni IVA nel sistema.

La verifica di coerenza **Estensione delle transazioni IVA** è disponibile nella versione build 10.0.234.21 e versioni successive per la versione 10.0.6 dell'applicazione e per la versione 10.0.7 e versioni successive. In queste versioni, è disponibile solo quando la funzionalità Data del libro IVA è abilitata nell'area di lavoro **Gestione funzionalità**.

## <a name="changes-in-the-italian-sales-tax-payment-report"></a>Modifiche nel report Liquidazione IVA italiana

È possibile eseguire il report **Liquidazione IVA italiana** utilizzando uno dei seguenti metodi:

- Selezionare **Imposta** \> **Dichiarazioni** \> **IVA** \> **IVA (Italia)**.
- Selezionare **Imposta** \> **Dichiarazioni** \> **IVA** \> **Report IVA per periodo liquidazione**.
- Selezionare **Imposta** \> **Richieste di informazioni e report** \> **Pagamenti IVA** e quindi **IVA (Italia)**.
- Selezionare **Imposta** \> **Richieste di informazioni e report** \> **Pagamenti IVA** e quindi **Stampa report**. È possibile utilizzare questo metodo solo se un layout di report italiano viene definito per l'ufficio IVA specificato per il periodo di liquidazione IVA della riga di pagamento IVA selezionata.

L'impostazione dell'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** non modifica l'elenco di fatture nelle pagine **Sezionali IVA**. Nel report verranno incluse tutte le fatture registrate nelle relative sezioni del libro IVA durante il periodo selezionato.

Tuttavia, l'impostazione dell'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** ha effetto sul calcolo degli importi IVA risultanti:

- Se l'opzione **Data del libro IVA** è impostata su **Sì**, gli importi IVA vengono calcolati in base alle informazioni nel campo **Data del libro IVA** per le transazioni IVA del periodo.
- Se l'opzione **Data del libro IVA** è impostata su **No**, gli importi IVA vengono calcolati in base alla data di registrazione delle transazioni IVA del periodo.

Quando l'opzione **Data del libro IVA** nella pagina **Parametri di contabilità generale** è impostata su **Sì**, il report **Liquidazione IVA italiana** fornisce le seguenti informazioni:

- Le pagine delle sezioni dei libri IVA includono una nuova colonna **Data di effettuazione dell'operazione (Data del libro IVA)**. Questa colonna rappresenta il valore del campo **Data del libro IVA** per la transazione IVA.
- I totali di ogni sezione del libro IVA sono rappresentati da tre gruppi:

    - Operazioni nel periodo effettivo con una data di competenza nel periodo effettivo
    - Operazioni nel periodo effettivo con una data di competenza nel periodo precedente
    - Operazioni nel periodo successivo con una data di competenza nel periodo effettivo

- I totali per libri acquisti e vendite sono rappresentati da tre righe: 

    - Operazioni totali nel periodo effettivo con una data di competenza nel periodo effettivo
    - Operazioni totali nel periodo effettivo con una data di competenza nel periodo precedente
    - Operazioni totali nel periodo successivo con una data di competenza nel periodo effettivo

- Una sezione di riepilogo rappresenta gli importi IVA totali per sezioni dei libri IVA. Tali importi sono raggruppati per sezioni del libro IVA. Queste informazioni sono rappresentate separatamente in tre parti:

    - Operazioni nel periodo effettivo con una data di competenza nel periodo effettivo
    - Operazioni nel periodo effettivo con una data di competenza nel periodo precedente
    - Operazioni nel periodo successivo con una data di competenza nel periodo effettivo

- I totali nella sezione di riepilogo rappresentano gli importi IVA totali per sezioni dei libri IVA. Tali importi sono raggruppati per sezioni del libro IVA. Queste informazioni sono rappresentate separatamente da tre righe:

    - Operazioni totali nel periodo effettivo con una data di competenza nel periodo effettivo
    - Operazioni totali nel periodo effettivo con una data di competenza nel periodo precedente
    - Operazioni totali nel periodo successivo con una data di competenza nel periodo effettivo

- L'importo **Totale calcolato considerando la data di competenza** viene fornito su una riga distinta.
