---
title: Creare e configurare garanzie estese
description: In questo argomento vengono descritte le garanzie estese e la procedura per crearle e configurarle in Microsoft Dynamics 365 Commerce.
author: sijoshi
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 772dc1fdda7c34448ffa946237f717e657df6d83d8fda9336049e79d19ed1af0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745382"
---
# <a name="create-and-configure-extended-warranties"></a>Creare e configurare garanzie estese

[!include [banner](includes/banner.md)]

In questo argomento vengono descritte le garanzie estese e la procedura per crearle e configurarle in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I clienti scelgono sempre più supporto e servizi estesi quando acquistano prodotti, in particolare i prodotti di consumo che vengono venduti a un prezzo superiore, come telefoni e computer. Fornendo garanzie estese per l'acquisto, i rivenditori possono fidelizzare meglio i clienti. Le garanzie estese indicano ai clienti dove possono rivolgersi per assistenza e supporto. Pertanto, possono essere certi che i loro problemi verranno gestiti in modo efficace.

Le garanzie estese possono essere vendute ai clienti in un canale al dettaglio durante l'acquisto iniziale del prodotto. Possono anche essere vendute per un tempo limitato dopo l'acquisto iniziale.

### <a name="warranty-item-setup"></a>Impostazione dell'articolo garanzia

Dynamics 365 Commerce fornisce la funzionalità per creare un articolo garanzia e impostarne gli attributi. Questi attributi includono l'associazione tra un prodotto e un articolo garanzia, il prezzo della garanzia e la durata della garanzia. Dopo che un articolo garanzia è stato configurato e rilasciato nell'unità organizzativa, un rivenditore può vendere le garanzie attraverso Modern Point of Sale (MPOS), negozi online e altri canali di vendita al dettaglio.

### <a name="warranty-item-sales"></a>Vendita dell'articolo garanzia

Le garanzie estese vengono vendute in un canale al dettaglio durante l'acquisto iniziale del prodotto. Possono anche essere vendute per un tempo limitato dopo l'acquisto iniziale.

Nel punto vendita (POS), agli addetti alle vendite viene richiesto di aggiungere una garanzia estesa quando un prodotto correlato viene aggiunto al carrello di un cliente. Pertanto, un'opportunità di up-selling o cross-selling viene presentata agli addetti alle vendite come parte del flusso delle vendite.

I clienti possono anche tornare in seguito e acquistare una garanzia estesa per un prodotto acquistato in precedenza. In questi casi, un addetto alle vendite può cercare la transazione originale e vendere al cliente l'articolo garanzia estesa correlata.

### <a name="warranty-terminology"></a>Terminologia della garanzia

La tabella seguente definisce alcuni termini relativi alla garanzia.

| Termine | Descrizione |
|------------------------------|--------------|
| Garanzia estesa/Garanzia | Una *garanzia estesa* si riferisce a un contratto di assistenza o un contratto che fornisce una garanzia prolungata ai clienti. La garanzia estesa include il servizio aggiuntivo di sostituzione o riparazione dei prodotti durante il periodo di copertura della garanzia estesa. |
| Garanzia del produttore | Una *garanzia del produttore* (spesso indicata come *garanzia limitata*) è la garanzia che i clienti ricevono quando acquistano un prodotto. Ecco alcune funzionalità della garanzia del produttore:<ul><li>Il costo della garanzia è incluso nel costo del prodotto. I clienti non devono pagare alcun importo aggiuntivo per la garanzia del produttore.</li><li>A seconda della categoria del prodotto, la garanzia del produttore dura in genere 30 giorni, sei mesi o un anno. (Per la maggior parte dei prodotti elettronici di consumo, la garanzia dura un anno).</li><li>La garanzia copre eventuali difetti causati da guasti meccanici o elettrici. La copertura è limitata e non include alcun danno accidentale al prodotto acquistato. I clienti che desiderano proteggere i prodotti che acquistano da danni quotidiani devono investire in una garanzia estesa. Le garanzie estese durano da due a dieci anni, a seconda della categoria del prodotto. Hanno anche una copertura più ampia e coprono incidenti quotidiani come gocce, liquidi e macchie.</li></ul> |
| Articolo garanzia | Un *articolo garanzia* è un articolo garanzia estesa che viene venduto per un articolo garantibile. Un esempio è un piano di protezione da danni accidentali di due anni per i laptop. |
| Articolo garantibile | Un *articolo garantibile* è un prodotto serializzato per il quale viene venduta una garanzia. Ad esempio, un laptop è un articolo garantibile per il quale vengono vendute garanzie estese di due e tre anni. |
| Gruppo di garanzie | Un *gruppo di garanzie* è una relazione tra articoli garanzia e articoli garantibili. Il POS utilizza i gruppi di garanzie per determinare per quali articoli garanzia deve essere richiesta l'aggiunta ai venditori quando un articolo garantibile viene aggiunto al carrello di un cliente. |
| Criteri di garanzia | I *criteri di garanzia* sono un'entità creata in Commerce quando vengono venduti i criteri di garanzia. I criteri di garanzia includono informazioni quali le date di inizio e fine dell'articolo garanzia acquistato, le condizioni e il numero di serie del prodotto garantito. I numeri dei criteri di garanzia possono essere condivisi con i clienti, in modo che abbiano un riferimento per l'articolo garanzia estesa che hanno acquistato. |

## <a name="create-a-warranty-item"></a>Creare un articolo garanzia

Per creare un articolo garanzia in Commerce, attenersi alla seguente procedura.

1. Andare a **Vendita al dettaglio e commercio \> Prodotti e categorie \> Prodotti**.
1. Selezionare **Nuovo** per creare un articolo garanzia.
1. Nella finestra di dialogo **Nuovo prodotto**, nel campo **Tipo di prodotto** selezionare **Servizio**.
1. Nel campo **Sottotipo di prodotto** selezionare **Prodotto**.
1. Nel campo **Tipo di servizio prodotto** selezionare **Servizio**.
1. Nel campo **Nome prodotto** immettere il nome del prodotto.
1. Nel campo **Categoria di vendita al dettaglio**, selezionare un valore nella finestra di dialogo a discesa, quindi selezionare **OK**.
1. Nel campo **Numero prodotto** immettere il numero prodotto.
1. Selezionare **OK**.
1. Nella pagina **Dettagli prodotto** nella scheda dettaglio **Garanzia** impostare i campi **Unità di tempo** e **Periodo di tempo**.

    | Nome campo | Valore | Descrizione |
    |------------|-------|-------------|
    | Unità di tempo | **Giorni**, **settimane**, **mesi** o **anni** | Questo campo specifica l'unità di tempo utilizzata per la garanzia. |
    | Periodo | Un valore intero positivo | Questo campo specifica la durata della garanzia nell'unità di tempo selezionata. |

    Ad esempio, per una garanzia di due anni, impostare il campo **Unità di tempo** su **Anni** e il campo **Periodo di tempo** su **2**. In alternativa, impostare il campo **Unità di tempo** su **Mesi** e il campo **Periodo di tempo** su **24**, come mostrato nella seguente illustrazione.

    ![Pagina dettagli prodotto per un articolo garanzia.](./media/ew-time-properties.png)

1. Selezionare **Salva** per salvare l'articolo garanzia.
1. Rilasciare il prodotto garanzia all'azienda in modo che possa essere venduto. Per ulteriori informazioni, vedere [Configurare prodotti di vendita al dettaglio](set-up-retail-products.md).
1. Nella pagina **Dettagli prodotto rilasciato** nella scheda dettaglio **Garanzia**, impostare i campi **Base scaglione prezzo**, **Limite inferiore** e **Limite superiore**.

    | Nome campo | Valore | Descrizione |
    |------------|-------|-------------|
    | Base scaglione prezzo | **Nessuno**, **Prezzo base** o **Prezzo di vendita** | <ul><li>**Nessuno** - I valori **Limite inferiore** e **Limite superiore** degli scaglioni prezzo non sono applicabili.</li><li>**Prezzo base** - Una data garanzia sarà applicabile se il prezzo base (ovvero il prezzo senza sconti) dell'articolo garantibile è compreso tra i valori **Limite inferiore** e **Limite superiore** specificati qui, in base al prezzo dell'articolo garantibile.</li><li>**Prezzo di vendita** - Questo valore è riservato per un utilizzo futuro.</li></ul> |
    | Limite inferiore, limite superiore | Un valore intero positivo | Questi campi definiscono i limiti di prezzo superiore e inferiore dell'articolo garantibile e come l'articolo garanzia corrente è applicabile all'articolo garantibile. Questi limiti possono essere basati sul prezzo base dell'articolo garantibile (noto anche come prezzo al dettaglio suggerito dal produttore \[MSRP\]). Se il campo **Base scaglione prezzo** è impostato su **Prezzo base**, solo un articolo garantibile (prodotto) che ha un prezzo base tra i valori **Limite inferiore** e **Limite superiore** attiveranno un prompt per aggiungere l'articolo garanzia nel POS. |

    Ad esempio, la seguente illustrazione mostra il campo **Base scaglione prezzo** impostato su **Prezzo base**, il campo **Limite inferiore** impostato su $500 e il campo **Limite superiore** impostato su $1000.
    
    ![Pagina dettagli prodotto rilasciato per un articolo garanzia.](./media/ew-release-product-details.png)

1. Inserire l'articolo garanzia nel canale in cui verrà venduto. Per ulteriori informazioni, vedere [Impostare assortimenti](set-up-assortments.md).

### <a name="example"></a>Esempio

Un articolo garantibile laptop (prodotto) ha un prezzo base $999 e ci sono due articoli garanzia laptop:

- Garanzia\_1 ha un limite inferiore di $500 e un limite superiore di $1.000 e il campo **Base scaglione prezzo** è impostato su **Prezzo base**.
- Garanzia\_2 ha un limite inferiore di $1.001 e un limite superiore di $2.000 e il campo **Base scaglione prezzo** è impostato su **Prezzo base**.

In questo caso, quando l'articolo garantibile laptop viene aggiunto al carrello di un cliente, la richiesta di aggiungere la Garanzia\_1 verrà mostrata sul POS, perché il prezzo del laptop è compreso tra i limiti inferiore e superiore per la Garanzia\_1.

> [!NOTE]
> Per questo esempio, se si desidera visualizzare le richieste per entrambe Garanzia\_1 e Garanzia\_2, indipendentemente dal prezzo dell'articolo garantibile, impostare il campo **Base scaglione prezzo** su **Nessuno**.

## <a name="configure-channel-specific-settings"></a>Configurare le impostazioni specifiche del canale

Le impostazioni specifiche del canale consentono di specificare se una richiesta per aggiungere un articolo garanzia deve essere visualizzato nel POS quando un articolo garantibile viene aggiunto al carrello di un cliente.

Per configurare l'impostazione specifica del canale in Commerce, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Prodotti e categorie \> Garanzia \> Impostazioni garanzia**.
1. Nella scheda **Specifico del canale** nella colonna **Richiedi garanzia** per il canale, eseguire uno di questi passaggi:

    - Selezionare la casella di controllo se nel POS deve essere visualizzata una richiesta per l'articolo garanzia quando l'articolo garantibile viene aggiunto al carrello.
    - Deselezionare la casella di controllo se nel POS non deve essere visualizzata una richiesta per l'articolo garanzia quando l'articolo garantibile viene aggiunto al carrello.

1. Eseguire il processo **1070** per sincronizzare i dati con il canale.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>Configurare una sequenza numerica per i criteri di garanzia

I criteri di garanzia sono identificati in modo univoco da un numero di criteri di garanzia generato da una sequenza numerica. Per ulteriori informazioni sulle sequenze numeriche, vedere [Panoramica delle sequenze numeriche](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Per configurare una sequenza numerica per i criteri di garanzia in Commerce, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Prodotti e categorie \> Garanzia \> Impostazioni garanzia**.
1. Nella scheda **Sequenze numeriche** nella riga per il riferimento **Criteri di garanzia**, immettere o selezionare un valore nel campo **Codice sequenza numerica**.

## <a name="set-up-a-warranty-group"></a>Impostare un gruppo di garanzie

Un gruppo di garanzie è una relazione tra articoli garanzia e articoli garantibili. Il POS utilizza i gruppi di garanzie per determinare per quali articoli garanzia deve essere richiesta l'aggiunta ai venditori quando un articolo garantibile viene aggiunto al carrello di un cliente.

Per impostare un gruppo di garanzie in Commerce, effettuare le seguenti operazioni.

1. Vai a **Retail e Commerce \> Prodotti e categorie \> Garanzia \> Gruppi di garanzie**.
1. Selezionare **Nuovo** per creare un gruppo di garanzie.
1. Nel campo **Nome** immettere un nome per il nuovo gruppo.
1. Nella scheda dettaglio **Generale**, nel campo **Descrizione** immettere una descrizione del gruppo.
1. Nella scheda dettaglio **Prodotti garanzia**, selezionare **Aggiungi riga** per aggiungere un articolo garanzia.
1. Nel campo **Ordine di visualizzazione** immettere un numero per classificare il gruppo di garanzie nel POS. Il POS mostrerà gli articoli garanzia in ordine crescente nella richiesta di garanzia.
1. Nella scheda dettaglio **Prodotti garantibili**, selezionare **Aggiungi riga** per aggiungere prodotti garantibili.
1. Se l'articolo garanzia è applicabile a un'intera categoria di articoli garantibili (prodotti) selezionare la categoria nel campo **Categoria**. Se l'articolo garanzia è applicabile a uno specifico articolo garantibile (prodotto), selezionare il prodotto nel campo **Prodotto**.
1. Nella scheda dettaglio **Canali applicabili** selezionare **Aggiungi riga** per aggiungere il canale in cui si desidera vendere l'articolo garanzia.
1. Selezionare **Salva** per salvare la configurazione.
1. Selezionare **Pubblica** per pubblicare il gruppo di garanzie.
1. Eseguire il processo **1040** per sincronizzare i dati nel canale.

## <a name="sell-warranty-items-at-the-pos"></a>Vendere gli articoli garanzia presso il POS

Due operazioni POS consentono agli addetti alle vendite di vendere gli articoli garanzia durante il flusso di lavoro per gli acquisti dei clienti:

- **Aggiungi garanzia** - Questa operazione attiva una richiesta che mostra le garanzie applicabili per un articolo garantibile selezionato nel carrello.
- **Aggiungi garanzia a transazione esistente** - Questa operazione consente agli addetti alle vendite di vendere garanzie per articoli garantibili precedentemente venduti. Gli addetti alle vendite possono trovare la transazione originale per un articolo garantibile inserendo il numero di ricevuta della transazione.

La seguente illustrazione mostra un esempio di una pagina terminale POS con la richiesta di aggiungere un articolo garanzia per l'acquisto corrente di un articolo garantibile.

![Esempio di richiesta di aggiunta di un articolo garanzia per l'acquisto corrente.](./media/ew-sell-warranty.png)

La seguente illustrazione mostra un esempio della funzione per l'aggiunta di un articolo garanzia per un articolo garantibile precedentemente venduto.

![Esempio di funzionalità per l'aggiunta di un articolo garanzia per un articolo garantibile precedentemente venduto.](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Elabora transazioni di garanzia

Quando le garanzie sono vendute in transazioni cash-and-carry, dopo che le transazioni sono state registrate in Commerce Headquarters, gli utenti di Commerce possono eseguire il processo **Elabora transazioni garanzia** per elaborare le transazioni di garanzia e creare criteri di garanzia.

Per elaborare le transazioni di garanzia in Commerce Headquarters, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Prodotti e categorie \> Garanzia \> Elabora transazioni garanzia**.
1. Nella finestra di dialogo **Scegli nodi organizzazione**, nel campo **Gerarchia organizzativa**, selezionare un valore.
1. Nell'elenco **Nodi organizzazione disponibili**, selezionare un singolo negozio o, se si desidera creare il processo batch per un gruppo di negozi, un nodo.
1. Selezionare il pulsante freccia destra per aggiungere la selezione all'elenco **Nodi organizzazione selezionati**.
1. Selezionare la scheda **Esecuzione in background**.
1. Impostare l'opzione **Elaborazione batch** su **Sì**, quindi selezionare **Ricorrenza**.
1. Nella finestra di dialogo **Definisci ricorrenza**, nel campo **Data di inizio**, selezionare o immettere una data di inizio per la ricorrenza.
1. Nel campo **Ora di inizio**, selezionare o immettere un'ora di inizio per la ricorrenza.
1. Eseguire uno dei passaggi riportati di seguito.

    - Selezionare l'opzione **Nessuna data di fine** se la ricorrenza non deve mai finire.
    - Selezionare l'opzione **Fine dopo** se la ricorrenza deve terminare dopo un numero specifico di esecuzioni. Se si seleziona questa opzione, immettere il numero di esecuzioni.
    - Selezionare l'opzione **Fine entro** se la ricorrenza deve finire entro una data specificata. Se si seleziona questa opzione, selezionare o immettere la data.

1. Selezionare **OK**.
1. Selezionare **OK**.

## <a name="warranty-policies"></a>Criteri di garanzia

Quando viene venduta una garanzia estesa, viene automaticamente creata un'entità criteri di garanzia. I numeri dei criteri di garanzia possono essere condivisi con i clienti, in modo che abbiano un riferimento per l'articolo garanzia che hanno acquistato. Le proprietà dei criteri di garanzia includono la data di inizio effettiva e la data di scadenza della garanzia, le condizioni e il numero di serie dell'articolo garantibile per il quale è stata venduta la garanzia.

> [!NOTE]
> Le proprietà dei criteri di garanzia vengono generate automaticamente quando vengono create le entità criteri di garanzia. Attualmente, non possono essere configurate o modificate manualmente.

La tabella seguente descrive le proprietà dei criteri di garanzia e i loro valori. In Commerce Headquarters, la tabella del database è denominata WARRANTYPOLICY.

| Nome proprietà | Valore | Descrizione |
|---------------|-------|-------------|
| PolicyNumber | Una stringa di caratteri (massimo 20 caratteri) | Il numero dei criteri di garanzia |
| WarrantiedItemId | Una stringa di caratteri (massimo 20 caratteri) | L'ID dell'articolo garantibile |
| WarrantiedInventoryLotId | Una stringa di caratteri (massimo 20 caratteri) | L'ID lotto di magazzino dell'articolo garantibile |
| WarrantiedSerialNumber | Una stringa di caratteri (massimo 20 caratteri) | Il numero di serie dell'articolo garantibile |
| WarrantiedFulfilledDate | Una data | La data di evasione dell'articolo garantibile |
| WarrantyItemId | Una stringa di caratteri (massimo 20 caratteri) | L'ID dell'articolo garanzia |
| WarrantyInventoryLotId | Una stringa di caratteri (massimo 20 caratteri) | L'ID lotto di magazzino dell'articolo garanzia |
| WarrantySalesDate | Una data | La data della vendita dell'articolo garanzia |
| WarrantyEffectiveDate | Una data | La data di validità dei criteri di garanzia |
| WarrantyExpirationDate | Una data | La data di scadenza dei criteri di garanzia |
| CustAccount | Una stringa di caratteri (massimo 20 caratteri) | Numero di conto cliente |
| Stato | **Creato**, **Annullato**, **Valido** o **Scaduto** | Lo stato dei criteri di garanzia |
| Note | Una stringa di caratteri (massimo 255 caratteri) | Note sui criteri di garanzia, come le condizioni |

## <a name="frequently-asked-questions-faq"></a>Domande frequenti

**Perché non viene visualizzata una richiesta di garanzia nel POS?**

Assicurarsi che l'articolo garanzia sia incluso nel canale. Assicurarsi inoltre che il gruppo di garanzie sia configurato in modo da includere il canale pertinente.

**Quando si tenta di aggiungere una garanzia a una transazione esistente e si inserisce il numero di ricevuta dell'ordine cliente, perché non vengono visualizzate le voci della transazione?**

Le ricevute sono disponibili solo se viene eseguito un processo pull (processo P) per caricare le ricevute in Commerce Headquarters. Per eseguire il processo P, andare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**, selezionare il processo **P-0001**, quindi selezionare **Esegui adesso**.

**Perché la funzione di garanzia è applicabile solo ai prodotti serializzati?**

Una garanzia è un servizio che viene fornito per un prodotto specifico e univoco. In Dynamics 365, un prodotto può essere identificato in modo univoco solo da un numero seriale.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare prodotti di vendita al dettaglio](set-up-retail-products.md)

[Impostare assortimenti](set-up-assortments.md)

[Panoramica delle sequenze numeriche](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]