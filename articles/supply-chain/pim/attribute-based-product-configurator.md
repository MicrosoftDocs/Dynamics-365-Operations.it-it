---
title: Prezzi di vendita basati su attributi per la configurazione prodotto basata su vincoli
description: In questo argomento viene descritto come creare modelli di prezzo di vendita con prezzi di vendita basati su componenti e attributi anziché sulla distinta base fisica e sul ciclo di produzione.
author: sorenva
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: ab3559ad7daf093a19cf3ced6766e8d43b38cca6ccefb2a090cab62737c56ca4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771397"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Prezzi di vendita basati su attributi per la configurazione prodotto basata su vincoli

In questo argomento viene descritto come creare modelli di prezzo di vendita con prezzi di vendita basati su componenti e attributi anziché sulla distinta base fisica e sul ciclo di produzione. Puoi creare diversi modelli di prezzo di vendita per ogni modello di configurazione prodotto.

## <a name="set-relevant-product-information-management-parameters"></a>Impostare parametri di gestione informazioni sul prodotto pertinenti

Prima di iniziare a creare modelli di prezzo, è necessario definire una valuta predefinita, che viene utilizzata quando si creano modelli di prezzo di vendita. Puoi anche scegliere se allegare un file Microsoft Excel con una scomposizione del prezzo per tutte le righe dell'ordine o dell'offerta. La scomposizione del prezzo ti consentirà di condividere i dettagli con i clienti su come sei arrivato a un prezzo di vendita specifico per un prodotto configurato.

Per impostare la valuta predefinita:

1. Vai a **Gestione informazioni sul prodotto \> Impostazione \> Parametri di gestione informazioni sul prodotto**.
1. Apri la scheda **Modello di configurazione prodotto basato su vincoli**.
1. Apri l'elenco a discesa **Valuta predefinita** e seleziona la valuta.

    ![Impostare la valuta predefinita per la configurazione prodotto basata su vincoli.](media/prod-config-currency.png "Impostare la valuta predefinita per la configurazione prodotto basata su vincoli")

1. Se desideri allegare un file Excel con una scomposizione prezzo per tutte le righe dell'ordine o dell'offerta, nella sezione **Modello di prezzo**, imposta **Allega** su *Sì*.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Creare modelli di prezzo di vendita

Per creare un modello di prezzo di vendita:

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Seleziona il modello di configurazione prodotto di destinazione.
1. Nel riquadro azioni, apri la scheda **Modello** e, nel gruppo **Imposta**, seleziona **Modelli di prezzo**.
1. Viene visualizzata la pagina **Modelli di prezzo**.
1. Seleziona un modello di prezzo o aggiungine uno nuovo alla griglia.
1. Seleziona **Modifica** per aprire la pagina di modifica per il modello selezionato, che fornisce le seguenti funzionalità:
    - L'intestazione del modulo mostra la valuta predefinita e ti consente di aggiungere nuove valute per l'impostazione del prezzo.
    - Il riquadro di sinistra mostra tutti i componenti e i requisiti utente del modello di prodotto. Ogni nodo nella struttura del modello di prodotto può avere un'espressione del prezzo di base e un numero facoltativo di regole di espressione. Una regola di espressione è costituita da una condizione e da un'espressione e ciascuna regola di espressione copre un'opzione di prodotto che consente di controllare il prezzo del prodotto.
    - Quando crei condizioni ed espressioni, hai gli stessi operatori disponibili per i calcoli in un modello di prodotto. L'editor delle espressioni supporta anche condizioni ed espressioni.
1. Seleziona un nodo nella colonna di sinistra e quindi utilizza le funzionalità descritte nel passaggio precedente per stabilire le regole per la determinazione dei prezzi (vedi anche l'esempio fornito dopo questa procedura). Ripeti questo passaggio per ogni nodo come necessario.

L'esempio seguente mostra un prezzo base di un numero statico di 899,95 EUR, che può essere modificato da una o più delle seguenti cinque regole di espressione, a seconda della configurazione selezionata dal cliente:

- Per la finitura del mobile bianco, sottrai 59,95 EUR.
- Per la protezione degli angoli, aggiungi 35,95 EUR.
- Per una griglia anteriore in metallo, aggiungi 89,95 EUR.
- Per la finitura del mobile in palissandro, aggiungi 119,95 EUR.
- Aggiungi 12,95 EUR per ogni unità di altezza dell'altoparlante.

![Esempio di modello di prezzo.](media/prod-config-rules-example.png "Esempio di modello di prezzo")

## <a name="add-support-for-multiple-currencies"></a>Aggiungere supporto per più valute

Quando un prodotto configurabile viene venduto, il sistema verifica se i prezzi sono stati impostati esplicitamente nella valuta del cliente. In tal caso, vengono utilizzati i valori espliciti. In caso contrario, il sistema utilizza i tassi di cambio della valuta stabiliti per la società di vendita per convertire il valore della valuta predefinita nella valuta del cliente.

Per aggiungere prezzi espliciti in una valuta aggiuntiva:

1. Apri la pagina di modifica per il modello di prezzo, come descritto in [Creare modelli di prezzo di vendita](#build-price-model).
1. Seleziona il pulsante **Aggiungi** nell'intestazione del modello di prezzo per aprire la finestra di dialogo **Valute**, che elenca le valute disponibili.
1. Seleziona la valuta che desideri aggiungere nella finestra di dialogo **Valute** e quindi seleziona **OK**.
1. L'elenco a discesa **Valuta corrente** ora include la valuta che hai appena aggiunto, più qualsiasi altra valuta che potrebbe essere stata aggiunta in precedenza. Seleziona la nuova valuta e nota che la griglia nella sezione **Regole espressione** ora include due campi di espressione:
    - **Espressione** - Mostra l'espressione (o il valore costante) per trovare il prezzo utilizzando la valuta attualmente selezionata in **Valuta corrente**.
    - **Espressioni predefinite** - Mostra l'espressione (o il valore costante) per trovare il prezzo utilizzando la valuta predefinita (visualizzata nel campo **Valuta predefinita**).

    > [!NOTE]
    > Il campo **Condizione** per le regole di espressione è "di proprietà" della valuta predefinita, il che significa che non è possibile modificare la condizione per altre valute. Non è inoltre possibile aggiungere nuove regole di espressione quando una valuta diversa da quella predefinita è selezionata come **Valuta corrente**.
1. Modifica i valori nella colonna **Espressione** come necessario per la valuta corrente.

Nell'esempio seguente, _EUR_ è la valuta predefinita e _USD_ è stato aggiunto come valuta aggiuntiva.

![Esempio di un modello con più valute.](media/prod-config-rules-currency-example.png "Esempio di un modello con più valute")

> [!NOTE]
> Non è possibile aggiungere regole di espressione univoche per una valuta non predefinita. Per creare regole di espressione pertinenti solo per una valuta diversa dalla valuta predefinita, imposta su zero l'espressione di prezzo per la valuta predefinita. Quindi imposta l'espressione appropriata per la valuta non predefinita.

## <a name="test-your-price-model"></a>Testare il modello di prezzo

Per verificare come funzionano i prezzi di vendita in una sessione di configurazione, apri la pagina di modifica del modello di prezzo, come descritto in [Creare modelli di prezzo di vendita](#build-price-model) e quindi seleziona **Test** nel riquadro azioni. Viene visualizzata la finestra di dialogo **Controlla modello prodotto** in cui puoi eseguire le seguenti operazioni:

- Utilizzare le impostazioni di configurazione offerte per selezionare le opzioni del prodotto e quindi vedere come influenzano il valore visualizzato in **Prezzo e data di spedizione**.
- Selezionare **Visualizza scomposizione prezzo** per scaricare un documento Excel che mostra tutti i dettagli su come è stato calcolato il prezzo.

![Testare il modello di prezzo.](media/prod-config-test.png "Testare il modello di prezzo")

Il foglio di calcolo scaricato mostra sia il valore assoluto che il contributo come percentuale per ogni elemento di prezzo attivo. Se hai impostato l'opzione **Allega** del modello di prezzo nella pagina **Parametri di gestione informazioni sul prodotto**, questo foglio Excel viene allegato alla riga dell'ordine o dell'offerta.

![Foglio di calcolo Excel che mostra la scomposizione del prezzo.](media/prod-config-excel-example.png "Foglio di calcolo Excel che mostra la scomposizione del prezzo")

## <a name="set-up-selection-criteria-for-price-models"></a>Impostare i criteri di selezione per i modelli di prezzo

Una volta creati i modelli di prezzo, devi stabilire almeno un criterio di selezione per prelevare il modello di prezzo quando configuri l'offerta o l'ordine. Eseguirai questa operazioni impostando una o più query. In una combinazione con modelli di prezzo di vendita corrispondenti, le query offrono una grande flessibilità nell'individuare prezzi di vendita di determinati clienti, aree, periodi e altri criteri.

Per impostare criteri di selezione per modelli di prezzo:

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Seleziona il modello di configurazione prodotto di destinazione.
1. Nel riquadro azioni, apri la scheda **Modello** e, nel gruppo **Imposta**, seleziona **Criteri modello di prezzo**. Viene visualizzata la pagina **Criteri modello di prezzo**.
1. Se la riga della query necessaria non esiste ancora, seleziona **Nuova** nel riquadro azioni per aggiungere una nuova riga alla griglia ed imposta le seguenti opzioni per la stessa:
    - **Nome**: immetti un nome per la riga.
    - **Descrizione**: descrivi brevemente la query e a cosa serve.
    - **Modello di prezzo**: seleziona un [modello di prezzo](#build-price-model) (nel modello di configurazione corrente) che la query applicherà quando attivata.
    - **Tipo di ordine** - Seleziona il tipo di ordine in cui verrà applicata la query.
    - **Valido dal** - Specificare il primo giorno in cui verrà applicata la query.
    - **Data scadenza** - Specifica l'ultima data in cui verrà applicata la query.

    ![Criteri modello di prezzo.](media/prod-config-price-model-criteria.png "Criteri modello di prezzo")

1. Seleziona la riga per la query che desideri definire, quindi seleziona **Modifica** nel **riquadro azioni**. Viene visualizzata la finestra di dialogo di progettazione di query. Funziona come la maggior parte delle finestre di progettazione di query in Supply Chain Management. Utilizzala per definire le condizioni in base alle quali deve essere applicato il modello di prezzo per la riga selezionata.

1. Ripeti i passaggi 4-5 per ogni query necessaria.
    > [!TIP]
    > Puoi risparmiare tempo copiando una riga esistente che è già simile a una nuova che devi aggiungere. A tale scopo, seleziona una riga di destinazione e quindi seleziona **Duplica** nel riquadro azioni.

1. Quando hai finito di impostare i criteri, disponili nell'ordine corretto nell'elenco **Criteri modello di prezzo**. Per riposizionare una riga, seleziona la riga e quindi seleziona **Su** o **Giù** nel riquadro azioni.

    > [!IMPORTANT]
    > Al momento della configurazione, il sistema avvia la ricerca dall'inizio dell'elenco e utilizza la prima query corrispondente ai dati nella riga dell'offerta o dell'ordine. Pertanto, è necessario posizionare all'inizio dell'elenco le query più specifiche. Se inserisci una query generale all'inizio dell'elenco, questa è quella che verrà utilizzata anche se potrebbe esserci una query più in basso nell'elenco relativa al prospect o al cliente esatto della configurazione.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Impostare prezzi di vendita basati su attributi per la versione del modello di prodotto

Il passaggio finale consiste nello specificare i prezzi di vendita basati su attributi per la versione del modello di prodotto. A questo proposito:

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Seleziona il modello di configurazione prodotto di destinazione.
1. Nel riquadro azioni, apri la scheda **Modello** e, nel gruppo **Dettagli modello prodotto**, seleziona **Versioni**.
1. Viene visualizzata la pagina **Versioni**. Assicurati che **Metodo di determinazione prezzo** sia impostato su **Basato su attributi**.
    ![Impostare Metodo di determinazione prezzo su Basato su attributi.](media/prod-config-versions.png "Impostare Metodo di determinazione prezzo su Basato su attributi")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]