---
title: Fatturazione interaziendale
description: Questo articolo fornisce informazioni ed esempi sulla fatturazione interaziendale per i progetti in Microsoft Dynamics 365 for Operations.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 8af9f2c1f6720c5d0a7b98c250a2cc52a5641cef
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="intercompany-invoicing"></a>Fatturazione interaziendale

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni ed esempi sulla fatturazione interaziendale per i progetti in Microsoft Dynamics 365 for Operations.

L'organizzazione potrebbe avere più divisioni, affiliate e altre persone giuridiche che si trasferiscono prodotti e servizi a vicenda per i progetti. La persona giuridica che fornisce il servizio o prodotto è denominata *persona giuridica concessionaria* e la persona giuridica che riceve il servizio o prodotto viene denominata *persona giuridica richiedente*. 

Di seguito viene illustrata una situazione tipica in cui due persone giuridiche, SI FR (la persona giuridica richiedente) e SI USA (la persona giuridica concessionaria) condividono risorse per fornire un progetto per il cliente A. Per questo scenario, SI FR ha un contratto di fornitura del lavoro al cliente A. 

[![Esempio di fatturazione interaziendale](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

L'obiettivo è rendere più flessibili ed efficienti il controllo dei costi, il riconoscimento dei ricavi, le imposte e i prezzi di trasferimento per le transazioni di progetti interaziendali. Inoltre, sono disponibili le seguenti funzionalità:

-   Creare fatture cliente rispetto a un progetto in una persona giuridica richiedente utilizzando fogli presenze interaziendali, spese e fatture fornitore in una persona giuridica concessionaria.
-   Supportare i calcoli dell'IVA e i costi indiretti.
-   Posticipare il riconoscimento dei ricavi in una persona giuridica concessionaria e quando una persona giuridica richiedente deve riconoscere il costo.
-   Accumulare ricavi WIP nella persona giuridica concessionaria.
-   Impostare prezzi di trasferimento che possono essere basati su modelli di prezzi diversi. Di seguito sono riportati alcuni esempi.
    -   **Quantità** – L'importo immesso nel campo **Determinazione prezzo** è il costo effettivo per quantità o unità.
    -   **Importo spese** – Il prezzo/costo per transazione più l'importo delle spese immesso nel campo **Determinazione prezzo**.
    -   **Percentuale spese** - Il prezzo di trasferimento corrisponde al prezzo/costo per transazione moltiplicato per la percentuale di spese immessa nel campo **Determinazione prezzo**.
    -   **Percentuale del prezzo di vendita** – la percentuale del prezzo di vendita che viene trasferito alla persona giuridica concessionaria.
    -   **Importo inferiore al prezzo di vendita** : l'importo che la persona giuridica richiedente trattiene dai prezzi di vendita prima del trasferimento alla persona giuridica concessionaria.
    -   **Rapporto di contribuzione** - Il numero immesso nel campo **Determinazione prezzo** è il rapporto di contribuzione espresso come percentuale del prezzo di vendita.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>Esempio 1: Impostare parametri per la fatturazione interaziendale
In questo esempio, USSI è una persona giuridica concessionaria e le relative risorse registrano il tempo rispetto alla persona giuridica richiedente, FRSI, a cui appartiene il contratto con il cliente finale. Le ore e le spese che i dipendenti USSI registrano possono essere incluse nella fattura progetto FRSI genera. Inoltre, vi è una terza origine delle transazioni che possono provenire dalla persona giuridica concessionaria (in questo esempio, USSI) quando fornisce servizi di fornitori condivisi a filiali (ad esempio FRSI) e quindi passa tali costi sui progetti all'interno di queste filiali. Tutti i documenti fattura corrispondenti e i calcoli dell'IVA vengono completati da Dynamics 365 for Operations. 

Per questo esempio, FRSI deve essere un cliente nella persona giuridica USSI e USSI deve essere un fornitore nella persona giuridica FRSI. È quindi possibile impostare una relazione interaziendale tra le due persone giuridiche. La procedura riportata di seguito illustra come impostare i parametri in modo che entrambe le persone giuridiche possono partecipare alla fatturazione interaziendale.

1.  Impostare FRSI come cliente nella persona giuridica USSI e impostare USSI come fornitore nella persona giuridica FRSI. Esistono tre punti di ingresso per i passaggi necessari per questa attività.
    | Graduale | Punto di ingresso                                                                       | descrizione   |
    |------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A    | in USSI, Fare clic su **Contabilità clienti** &gt; **Clienti** &gt; **Tutti i clienti**. | Creare un nuovo record cliente per FRSI e selezionare il gruppo di clienti.                                                                                                                                                                                                                           |
    | B    | In FRSI, fare clic su **Contabilità fornitori** &gt; **Fornitori** &gt; **Tutti i fornitori**.        | Creare un nuovo record fornitore per USSI e selezionare il gruppo di fornitori.                                                                                                                                                                                                                               |
    | C    | In FRSI, aprire il record fornitore appena creato.                            | Nel riquadro azioni, scheda **Generale**, gruppo **Impostazione**, fare clic su **Interaziendale**. Nella pagina **Interaziendale**, scheda **Relazione commerciale**, impostare il dispositivo di scorrimento **Attivo** su **Sì**. Nel campo **Società cliente** selezionare il record cliente creato nel passaggio A. |

2.  Fare clic su **Gestione progetti e contabilità** &gt; **Impostazione** &gt; **Parametri Gestione progetti e contabilità**, quindi fare clic sulla scheda **Interaziendale**. Il modo in cui si impostano i parametri dipende da se si è la persona giuridica richiedente o concessionaria.
    -   Se si è la persona giuridica richiedente, selezionare la categoria di approvvigionamento che deve essere utilizzata per abbinare le fatture fornitore, che vengono generate automaticamente.
    -   Se siete la persona giuridica concessionaria, per ogni persona giuridica richiedente, selezionare una categoria di progetto predefinito per ogni tipo di transazione. Categorie di progetto vengono utilizzate per configurazione imposte quando la categoria fatturata nelle transazioni interaziendali esiste solo nella persona giuridica richiedente. È possibile scegliere di accumulare i ricavi per le transazioni interaziendali. Questo accumulo viene eseguito quando le transazioni vengono registrate e viene quindi stornato quando viene registrata la fattura interaziendale.

3.  Fare clic su **Gestione progetti e contabilità** &gt; **Impostazioni** &gt; **Prezzi** &gt; **Prezzo di trasferimento**.
4.  Selezionare una valuta, il tipo di transazione e il modello del prezzo di trasferimento. La valuta utilizzata nella fattura è la valuta che viene configurata nel record del cliente per la persona giuridica richiedente nella persona giuridica concessionaria. La valuta viene utilizzata per associare le voci nella tabella di prezzi di trasferimento.
5.  Fare clic su **Contabilità generale** &gt; **Impostazione di registrazione** &gt; **Contabilità interaziendale** e impostare una relazione per USSI e FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Esempio 2: Creare e registrare un foglio presenze interaziendale
USSI, la persona giuridica concessionaria, deve creare e registrare il foglio presenze per un progetto di FRSI, la persona giuridica richiedente. Esistono due punti di ingresso per i passaggi necessari per questa attività.

| Graduale | Punto di ingresso                                                                       | descrizione                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Gestione progetti e contabilità** &gt; **Fogli presenze** &gt; **Tutti i fogli presenze** | Creare un nuovo foglio presenze. Nella riga del foglio presenze, nel campo **Persona giuridica**, selezionare **FRSI**. Selezionare quindi il progetto in FRSI nel campo **ID progetto**. Immettere il numero di ore per ogni giorno della settimana. |
| B    | Pagina **Foglio presenze**                                                                | Dopo l'esecuzione del flusso di lavoro, registrare il foglio presenze e prendere nota del numero di giustificativo.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Esempio 3: Creare e registrare una fattura fornitore interaziendale
USSI, la persona giuridica concessionaria, deve creare e registrare la fattura fornitore interaziendale per un progetto di FRSI, la persona giuridica richiedente. Questa fattura fornitore rappresenta la manodopera in appalto e spese che sono state eseguite dai fornitori che sono pagati da USSI. Esistono due punti di ingresso per i passaggi necessari per questa attività.

| Graduale | Punto di ingresso                                                                                      | descrizione                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Contabilità fornitori** &gt; **Fatture** &gt; **Fatture fornitore aperte** &gt; **Nuova fattura fornitore** | Creare una nuova fattura fornitore e immettere i servizi che sono stati acquistati per conto di progetto di FRSI.                                                                                                                                                                                  |
| B    | Pagina **Fattura fornitore**                                                                      | Immettere le righe che rappresentano i servizi esternalizzati per conto di FRSI. Nella scheda dettaglio **Dettagli riga**, nella scheda **Progetto** per la riga di fattura, nel campo **Società progetto** immettere **FRSI**. Immettere il progetto e le informazioni corrispondenti. Quindi registrare la fattura fornitore. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Esempio 4: Creare e registrare la fattura interaziendale
USSI, la persona giuridica concessionaria , deve creare e registrare la fattura interaziendale. Esistono due punti di ingresso per i passaggi necessari per questa attività.

| Graduale | Punto di ingresso                                                                                             | descrizione                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Gestione progetti e contabilità** &gt; **Fatture progetto** &gt; **Fattura cliente interaziendale**  | Fare clic su **Nuovo** per aprire la pagina **Crea fattura interaziendale**.                                                                                  |
| B    | **Gestione progetti e contabilità** &gt; **Fatture progetto** &gt; **Fatture cliente interaziendali** | Nella pagina **Crea fattura interaziendale**, immettere la persona giuridica, specificare la transazione che deve essere inclusa e quindi fare clic su **Cerca**. |
| C    | **Gestione progetti e contabilità** &gt; **Fatture progetto** &gt; **Fatture cliente interaziendali** | Selezionare le transazioni da fatturare oppure fare clic su **Seleziona tutto** per fatturare tutte le transazioni nell'elenco e quindi fare clic su **OK**.                  |
| D    | Pagina **Fattura interaziendale**                                                                       | Viene illustrata la proposta di fattura cliente interaziendale.                                                                                             |
| E    | Pagina **Fattura interaziendale**                                                                       | Fare clic su **Registra**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Esempio 5: Registrare la fattura fornitore e fatturare al cliente
Quando la persona giuridica concessionaria, USSI, registra la fattura cliente interaziendale, una corrispindente fattura fornitore in sospeso viene creata nella persona giuridica richiedente, FRSI. Una volta registrata la fattura fornitore, FRSI fattura al cliente del progetto anche le ore immesse da USSI. Esistono tre punti di ingresso per i passaggi necessari per questa attività.

| Graduale | Punto di ingresso                                                                                        | descrizione                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | **Contabilità fornitori** &gt; **Fatture** &gt; **Fatture fornitore in sospeso**                            | Esaminare la fattura per verificare che siano inclusi i valori dei fogli presenze e quindi registrare la fattura fornitore.                  |
| B    | **Gestione progetti e contabilità** &gt; **Fatture progetto** &gt; **Proposte di fatturazione progetto** | Creare una nuova fattura di progetto per il progetto e verificare che siano visualizzate le transazioni orarie registrate.            |
| C    | Pagina **Fattura progetto**                                                                       | Selezionare la fattura progetto e quindi fare clic su **Visualizza dettagli** per esaminare l'importo di costi e vendite. Quindi registrare la fattura. |






