---
title: Abilitare e configurare addebiti automatici per canale
description: Questo argomento spiega come abilitare e configurare le spese automatiche per canale in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 23d02cf96faf3753303435acc148bf71e487d791
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799916"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Abilitare e configurare addebiti automatici per canale

Questo argomento spiega come abilitare e configurare le spese automatiche per canale in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

È possibile avere scenari in cui le spese per il riciclaggio o altre spese devono essere applicate a un gruppo di prodotti venduti in tutti o in alcuni punti vendita in uno stato specifico (ad esempio, California). La funzione **Abilita filtro spese automatiche per canale** in Commerce consente di specificare le spese automatiche per canale (ad esempio, un canale tradizionale specifico). Questa funzionalità è disponibile in Dynamics 365 Commerce versione 10.0.10 e successiva.

Per abilitare e configurare le spese automatiche per canale, è necessario completare le seguenti attività:

- Attivare la funzionalità **Abilita filtro spese automatiche per canale**.
- Configurare lo scopo della gerarchia organizzativa.
- Definire le spese automatiche per canale.

> [!NOTE]
> La funzionalità **Abilita filtro spese automatiche per canale** funziona solo se è attiva anche la funzione di spese automatiche avanzate. Per informazioni su come attivare la funzione di spese automatiche avanzate, vedere [Spese automatiche avanzate omnicanale](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Attivare la funzionalità Abilita filtro spese automatiche per canale

Per abilitare le spese automatiche per canale in Commerce, attenersi alla seguente procedura.

1. Passare in **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Nella scheda **Non abilitato**, nell'elenco **Nome della funzione**, trovare e selezionare **Abilita filtro spese automatiche per canale**.
1. Nell'angolo in basso a destra, selezionare **Abilita ora**. Dopo che la funzione è stata attivata, verrà visualizzata nell'elenco nella scheda **Tutte**.
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Nel riquadro a sinistra, trovare e selezionare il processo **1110** (**Configurazione globale**).
1. Nel riquadro azioni selezionare **Esegui ora** per propagare le modifiche alla configurazione.

> [!WARNING]
> Se si disattiva la funzionalità **Abilita filtro spese automatiche per canale** dopo averla già utilizzata, il campo **Relazione canale di vendita al dettaglio** sotto **Spese automatiche** non verrà più visualizzato e si perderanno tutte le configurazioni esistenti. Se la rimozione delle configurazioni **Relazione canale di vendita al dettaglio** causa la duplicazione delle regole delle spese automatiche, il tentativo di disattivare la funzione non riesce. Prima di disattivare la funzione, assicurarsi di rivedere tutte le regole delle spese automatiche e apportare le modifiche necessarie.

## <a name="configure-the-organization-hierarchy-purpose"></a>Configurare lo scopo della gerarchia organizzativa

Un nuovo scopo della gerarchia organizzativa denominato **Spese automatiche vendita al dettaglio** è stato creato per gestire la gerarchia delle spese automatiche per canale.

Per assegnare una gerarchia predefinita a uno scopo della gerarchia dell'organizzazione in Commerce, attenersi alla seguente procedura.
        
1. Andare in **Amministrazione organizzazione \> Organizzazioni \> Scopi gerarchia organizzativa**.
1. Nel riquadro a sinistra selezionare **Spese automatiche vendita al dettaglio**.
1. In **Gerarchie assegnate**, selezionare **Aggiungi**.
1. Nella finestra di dialogo **Gerarchie organizzative** selezionare una gerarchia organizzativa (ad esempio, **Punti vendita al dettaglio per area geografica**), quindi selezionare **OK**.
1. In **Gerarchie assegnate**, selezionare **Imposta come predefinito**.
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Nel riquadro a sinistra, trovare e selezionare il processo **1040** (**Prodotti**).
1. Nel riquadro azioni selezionare **Esegui adesso**.
1. Ripetere i due passaggi precedenti per eseguire i processi **1070** (**Configurazione del canale**) e **1110** (**Configurazione globale**).

![Configurazione dello scopo della gerarchia organizzativa per le spese automatiche vendita al dettaglio](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Definire le spese automatiche per canale

Dopo aver attivato la funzionalità **Abilita filtro spese automatiche per canale** e configurato lo scopo della gerarchia organizzativa **Spese automatiche vendita al dettaglio**, le spese automatiche per canale possono essere definite a livello di intestazione dell'ordine o a livello di riga dell'ordine.

Per definire le spese automatiche per canale in Commerce, attenersi alla seguente procedura.

1. Accedere a **Contabilità clienti \> Impostazione spese \> Spese automatiche**.
1. Nel riquadro a sinistra, nel campo **Livello**, selezionare **Intestazione** o **Riga**, a seconda delle esigenze aziendali.
1. Nel campo **Codice canale di vendita al dettaglio**, selezionare il codice canale appropriato (ad esempio, **Tabella** o **Gruppo**). Se l'impostazione predefinita **Tutti** è utilizzata, le regole di addebito vengono applicate a tutti i canali.

    - Se si seleziona **Gruppo**, assicurarsi che venga creato un gruppo di spese per i canali di vendita al dettaglio in **Retail e Commerce \> Impostazione canale \> Spese \> Gruppi di spese canale di vendita al dettaglio**.
    - Se si seleziona **Tabella**, è possibile selezionare un canale specifico (ad esempio, **San Francisco**) nel campo **Relazione canale di vendita al dettaglio**.

1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Nel riquadro a sinistra, trovare e selezionare il processo **1040** (**Prodotti**).
1. Nel riquadro azioni selezionare **Esegui adesso**.
1. Ripetere i due passaggi precedenti per eseguire i processi **1070** (**Configurazione del canale**) e **1110** (**Configurazione globale**).
    
![Spese automatiche definite per canale](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Scenario di esempio

L'esempio seguente descrive i passaggi necessari per configurare un prodotto in modo che le spese per il riciclaggio vengano addebitati quando il prodotto viene venduto attraverso un canale fisico San Francisco. L'esempio mostra anche come vengono visualizzate le spese automatiche nell'applicazione Commerce POS (POS).

L'organizzazione definisce un codice di spesa denominato **RECYCLE**, come mostrato nella seguente illustrazione.

![Codice di addebito RECYCLE](media/Auto-charges-charge-code.png)

Una spesa automatica è creata a livello di riga. Ha la seguente configurazione:

- Il campo **Codice conto** è impostato su **Tutto**.
- Il campo **Codice articolo** è impostato su **Tabella**.
- Il campo **Relazione articolo** è impostato sull'ID prodotto **91001**.
- Il campo **Codice modalità di consegna** è impostato su **Tutto**.
- Il campo **Codice canale di vendita al dettaglio** è impostato su **Tabella**.
- La campo **Relazione canale di vendita al dettaglio** è impostato sul punto vendita **San Francisco**.

Viene creata una riga di spese automatiche. Ha la seguente configurazione:

- Il campo **Valuta** è impostato su **USD**.
- Il campo **Codice spese** è impostato su **RECYCLE**.
- Il campo **Categoria** è impostato su **Fisso**.
- Il campo **Spese** è impostato su **$ 6,25**.

![Configurazione delle spese automatiche a livello di riga e della riga di spese automatiche](media/Auto-charges-recyclingfee-line-fee.png)

Nell'applicazione POS, un ordine cliente viene creato nel canale del punto vendita **San Francisco**. La riga **Spese** mostra le spese per il riciclaggio di **$ 6,25**.

Selezionando **Opzioni di transazione \> Spese \> Gestisci spese** nell'applicazione POS, è possibile visualizzare il codice di addebito e la descrizione per le spese per il riciclaggio.

![Spese per il riciclaggio nell'applicazione POS](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Addebiti automatici avanzati omnicanale](omni-auto-charges.md)

[Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]