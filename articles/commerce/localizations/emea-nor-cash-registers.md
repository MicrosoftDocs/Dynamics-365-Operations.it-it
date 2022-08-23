---
title: Funzionalità registratore di cassa per la Norvegia
description: Questo articolo fornisce una panoramica della funzionalità del registratore di cassa disponibile per la Norvegia in Microsoft Dynamics 365 Commerce e fornisce le linee guida per l'impostazione della funzionalità.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 42eda805646dbb30b40528254a3137102e3075e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292738"
---
# <a name="cash-register-functionality-for-norway"></a>Funzionalità registratore di cassa per la Norvegia

[!include[banner](../includes/banner.md)]

Questo articolo fornisce una panoramica della funzionalità del registratore di cassa disponibile per la Norvegia in Dynamics 365 Commerce. Fornisce inoltre le linee guida per l'impostazione della funzionalità. La funzionalità è composta dalle seguenti parti:

- Funzionalità POS (point-of-sale) comuni disponibili per i clienti in tutti i paesi o aree geografiche. Gli esempi includono un'opzione che consente di impedire che una copia di una ricevuta venga stampata più di una volta.
- Funzionalità specifiche per la Norvegia, come le firme digitali per le transazioni di vendita.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Panoramica della funzionalità del registratore di cassa per la Norvegia

### <a name="common-pos-features"></a>Funzionalità POS comuni

Per conoscere le funzionalità POS disponibili per i clienti in tutti i paesi o aree geografiche, vedi [Risorse della guida per Dynamics 365 Retail](../index.md).

Le seguenti funzionalità di localizzazione POS che erano state precedentemente implementate e rese disponibili ai clienti in tutti i paesi o aree geografiche ora possono essere utilizzate specificamente per la Norvegia:

- **Stampa i campi di testo su una ricevuta con caratteri di grandi dimensioni.** Puoi usare il parametro **Dimensione carattere** nella progettazione formato ricevuta per specificare che la dimensione del carattere grande deve essere utilizzata per un campo nel formato ricevuta. La dimensione del carattere grande è circa il doppio della dimensione del carattere normale. Ad esempio, è possibile utilizzare questo parametro per stampare l'indicatore "Copia" su una copia di una ricevuta a caratteri grandi.
- **Registra la stampa delle copie delle ricevute nel registro eventi di controllo POS.** Puoi usare il parametro **Controllo** nel profilo di funzionalità POS per consentire la stampa di copie delle ricevute e la registrazione di altri eventi di controllo POS. Gli eventi di controllo sono registrati nel database del canale e in Headquarters. È possibile visualizzare gli eventi di controllo nella pagina **Eventi di controllo**.
- **Impedisci che una copia di una ricevuta venga stampata più di una volta.** Quando il parametro **Controllo** nel profilo della funzionalità POS è abilitato, l'autorizzazione POS **Consenti la stampa delle copie delle ricevute** controlla se le copie delle ricevute possono essere stampate. C'è anche un'opzione che consente di impedire che una copia di una ricevuta venga stampata più di una volta.

Inoltre, la seguente funzionalità POS è stata implementata per la Norvegia, ma è stata resa disponibile ai clienti in tutti i paesi o aree geografiche:

- **Registra eventi aggiuntivi nel registro eventi di controllo POS.** Se il parametro **Controllo** nel profilo della funzionalità POS è abilitato, i seguenti eventi vengono registrati nel registro eventi di controllo POS:

    - Controlli di prezzi
    - Forzature imposte
    - Correzioni alle quantità di riga
    - Cancellazione delle transazioni dal database del canale

### <a name="norway-specific-pos-features"></a>Funzionalità POS specifiche della Norvegia

Le seguenti funzionalità POS specifiche per la Norvegia sono abilitate quando il parametro **Codice ISO** nel profilo della funzionalità POS è impostato su **No**.

#### <a name="digital-signing-of-sales-transactions"></a>Firma digitale delle transazioni di vendita

Ogni transazione di vendita è firmata digitalmente. La firma viene creata e registrata nel giornale delle transazioni POS contemporaneamente alla finalizzazione della transazione. La firma è disponibile anche nel giornale esportato a scopo di controllo.

Vengono firmate solo le transazioni per le vendite in contanti. Ecco alcuni esempi di transazioni escluse dal processo di firma:

- Pagamenti anticipati (deposito conto cliente)
- Pagamenti anticipati per ordini cliente (deposito ordine cliente)
- Emissione di una gift card
- Transazioni non di vendita (immissione in borsa, rimozione di offerte e così via)

I dati firmati sono una stringa di testo composta dai seguenti campi di dati. I campi dati sono separati da punto e virgola.

1. Firma precedente per lo stesso POS (zero \[**0**\] viene utilizzato per la prima transazione.)
2. Data transazione
3. Ora della transazione
4. Numero di transazione firmata sequenziale
5. Importo della transazione tasse incluse
6. Importo della transazione tasse escluse

Il processo di firma digitale utilizza una chiave RSA a 1024 bit con una funzione hash SHA-1 (RSA-SHA1-1024). Per la firma viene utilizzato un certificato installato su Commerce Scale Unit. L'identificativo univoco del certificato (footprint) viene registrato insieme alla firma.

La firma viene archiviata nel database del negozio e nel database headquarters (HQ) insieme ai dati della transazione. Puoi visualizzare la firma della transazione, insieme ai dati della transazione utilizzati per generarla nella scheda Dettaglio **Transazioni fiscali** della pagina **Transazioni punto vendita**.

#### <a name="receipts"></a>Ricezioni

Le ricevute per la Norvegia possono includere informazioni aggiuntive che sono state implementate utilizzando campi personalizzati:

- **Titolo ricevuta** – È possibile aggiungere un campo a un layout formato ricevuta per identificare il tipo di ricevuta. Ad esempio, una ricevuta di vendita includerà il testo "Scontrino di vendita".
- **Numero progressivo della transazione firmata** – Sulla ricevuta può comparire il numero progressivo di una transazione firmata per associare una ricevuta stampata a una firma digitale nel database.
- **Totali ricevute** – I campi personalizzati per i totali delle ricevute escludono gli importi non di vendita dagli importi totali delle transazioni. Gli importi non di vendita includono gli importi per le seguenti operazioni:

    - Pagamenti anticipati (deposito conto cliente)
    - Pagamenti anticipati per ordini cliente (deposito ordine cliente)
    - Emissione di una gift card
    - Aggiunta di fondi a una gift card

#### <a name="x-and-z-reports"></a>Report X e Z

Le informazioni incluse nei report X e Z si basano sui requisiti norvegesi. Per esempio, gli importi **Vendite totali in contanti** includono solo gli importi per le transazioni di vendita in contanti ed escludono le operazioni di emissione di gift card e pagamenti anticipati. Vengono inoltre elencate le vendite totali in contanti per gruppo di articoli e metodo di pagamento. Inoltre, gli importi cumulativi **Totale complessivo vendite** e **Totale complessivo resi** vengono mantenuti e stampati.

#### <a name="saf-t-cash-register-audit-file"></a>File di controllo registratore di cassa SAF-T

È possibile esportare il giornale di registrazione delle transazioni POS nel formato predefinito File di controllo standard - Registratore di cassa fiscale (SAF-T). Il file di controllo include informazioni sull'organizzazione, dati master rilevanti (come gruppi di articoli, articoli e codici imposta), dati sulle transazioni di vendita in contanti insieme alle firme per tali transazioni, dati sugli eventi non di vendita e dati del report di fine data.

Il file di controllo può essere esportato per i seguenti scenari:

- Per negozio
- Tutti i punti vendita
- Per terminale
- Tutti i terminali

Puoi anche inviare un report da una persona giuridica per conto di un'altra persona giuridica. In questo caso, è necessario eseguire l'esportazione dalla persona giuridica operativa e specificare la persona giuridica che crea il report come mittente del report.

Il formato del registratore di cassa SAF-T è implementato presso Headquarters utilizzando la [Creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>Impostazione di Commerce per la Norvegia

Questa sezione descrive le impostazioni specifiche e consigliate per la Norvegia. Per ulteriori informazioni, vedi [Risorse della guida per Dynamics 365 Retail](../index.md).

È necessario completare la seguente attività per utilizzare la funzionalità specifica della Norvegia:

- Imposta il campo **Paese/area geografica** su **NOR** (Norvegia) nell'indirizzo principale della persona giuridica.
- Imposta il campo **Codice ISO** su **NO** (Norvegia) nel profilo della funzionalità POS di ogni negozio che si trova in Norvegia.

È inoltre necessario specificare le seguenti impostazioni per la Norvegia.

### <a name="set-up-the-legal-entity"></a>Impostare la persona giuridica

Assicurati che sia specificato il nome della persona giuridica. Questo nome verrà stampato sui report X e Z.

Inoltre, nella scheda dettaglio **Informazioni sul conto bancario** nel campo **Numero di registrazioner** specifica il numero dell'organizzazione.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Impostare l'IVA per i requisiti norvegesi


È necessario creare codici IVA, fasce IVA e fasce IVA articoli. È inoltre necessario impostare le informazioni sull'IVA per prodotti e servizi. Per ulteriori informazioni su come impostare e usare l'IVA vedi [Panoramica dell'IVA](../../finance/general-ledger/indirect-taxes-overview.md).

È inoltre necessario specificare le fasce IVA e abilitare l'opzione **Prezzi IVA inclusa** per i negozi che si trovano in Norvegia.

### <a name="set-up-functionality-profiles"></a>Impostare i profili della funzionalità

È necessario abilitare il controllo e impostare la numerazione delle ricevute.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>Aggiornare i gruppi di autorizzazioni POS e le impostazioni di autorizzazione individuali per i lavoratori del negozio

Imposta l'autorizzazione **Consenti la stampa della copia della ricevuta** su un valore appropriato:

- **Consenti sempre** – L'operatore può stampare più volte la copia di una ricevuta.
- **Consenti una volta** – L'operatore può stampare solo una volta la copia di una ricevuta.
- **Consenti solo una volta e solo se HQ DB è disponibile** – L'operatore può stampare una copia di una ricevuta solo una volta e solo se il database HQ è disponibile tramite Commerce Data Exchange: Real-time Service, in modo che il sistema possa verificare che nessuna copia della ricevuta sia stata precedentemente stampata in nessun punto vendita.
- **Mai** – L'operatore non può stampare la copia di una ricevuta.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurare i campi personalizzati in modo che possano essere utilizzati nei formati per ricevute di vendita

Nella pagina **Testo lingua** aggiungi i record seguenti per le etichette dei campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID lingua**, **ID testo** e **Testo** visualizzati nella seguente tabella sono solo esempi. Puoi modificarli in base alle esigenze.

| ID lingua | Testo                   | ID testo |
|-------------|------------------------|---------|
| en-US       | Titolo ricevuta          | 900011  |
| en-US       | Gift card           | 900012  |
| en-US       | Totale (vendite)          | 900013  |
| en-US       | Totale imposte (vendite)      | 900014  |
| en-US       | Totale imposte incluse (vendite) | 900015  |
| en-US       | Importo imposta (vendite)     | 900016  |
| en-US       | ID transazione in contanti    | 900017  |

Nella pagina **Campi personalizzati**, aggiungi i record seguenti per i campi personalizzati per i layout di ricevuta. Tieni presente che i valori **ID testo didascalia** devono corrispondere ai valori **ID testo** specificati nella pagina **Testo lingua**.

| Name                            | Tipo    | ID testo didascalia |
|---------------------------------|---------|-----------------|
| ReceiptTitle                    | Ricevimento | 900011          |
| IsGiftCard                      | Ricevimento | 900012          |
| SalesTotalExt                   | Ricevimento | 900013          |
| TaxTotalExt                     | Ricevimento | 900014          |
| TotalWithTaxExt                 | Ricevimento | 900015          |
| AmountPerTaxExt                 | Ricevimento | 900016          |
| CashTransactionSequentialNumber | Ricevimento | 900017          |

> [!NOTE]
> È importante specificare i nomi dei campi personalizzati corretti, come elencato nella tabella sopra. Un nome di campo personalizzato errato causerà la mancanza di dati nelle ricevute.

### <a name="configure-receipt-formats"></a>Configurare i formati di ricevuta

Per tutti i formati di ricevuta richiesti, modifica il valore del campo **Comportamento stampa** su **Stampa sempre** per il formato di ricevuta.

Nella progettazione formato ricevuta, aggiungi i seguenti campi personalizzati alle sezioni ricevuta appropriate. Tieni presente che i nomi dei campi corrispondono ai testi in lingua definiti nella sezione precedente.

1. Intestazione:

    - **Titolo ricevuta** – Questo campo identifica il tipo di ricevuta.
    - **ID transazione di cassa** – Questo campo stampa il numero progressivo della transazione di cassa firmata.

2. Righe:

    - **Gift card** – Questo campo contrassegna la riga della ricevuta come correlata all'operazione Emetti gift card o Aggiungi a gift card.

3. Piè di pagina:

    - **Totale (vendite)** – Questo campo stampa l'importo totale della vendita in contanti della ricevuta. L'importo non include le imposte. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
    - **Totale imposte (vendite)** – Questo campo stampa l'importo totale delle imposte per la vendita in contanti della ricevuta. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
    - **Totale imposte incluse (vendite)** – Questo campo stampa l'importo totale della vendita in contanti della ricevuta. L'importo include le imposte. Sono esclusi i pagamenti anticipati e le operazioni con gift card.
    - **Importo imposte (vendite)** – Questo campo stampa l'importo delle imposte per la vendita in contanti della ricevuta per codice imposta. Sono esclusi i pagamenti anticipati e le operazioni con gift card.

Per ulteriori informazioni sulle modalità di utilizzo dei formati di ricevute, vedi [Impostare e progettare formati di ricevute](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Configurare il formato di esportazione del registratore di cassa SAF-T

La configurazione del registratore di cassa SAF-T è disponibile per il download da Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedi [Importare le configurazioni di creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). È necessario scaricare le seguenti configurazioni:

- **Retail channel data.version.1** – La configurazione del modello dati.
- **DMM Retail channel data.version.1.14** – La configurazione del mapping del modello dati.
- **NO SAF T Cash Register.version.1.20** – La configurazione del formato.

Dopo aver importato le configurazioni, nella pagina **Parametri di Commerce** nella scheda **Documenti elettronici** nel campo **Formato di esportazione del registratore di cassa SAF-T** seleziona il nome della configurazione del formato importata.

È inoltre necessario mappare i dati master richiesti ai codici standard SAF-T predefiniti. Per ulteriori informazioni, vedi la documentazione del registratore di cassa SAF-T fornita dall'amministrazione fiscale norvegese. Per creare il mapping, è necessario impostare il nuovo campo **Codice registratore di cassa SAF-T** nelle seguenti pagine:

- Gruppi di articoli
- Metodi di pagamento
- Codici IVA

### <a name="configure-channel-components"></a>Configurare i componenti del canale

Per abilitare la funzionalità specifica per la Norvegia, devi configurare i componenti del canale. Per ulteriori informazioni, vedi le [linee guida per la distribuzione](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
