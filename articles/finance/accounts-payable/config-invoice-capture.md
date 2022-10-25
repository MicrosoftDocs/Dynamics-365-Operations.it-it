---
title: Configurare la soluzione Invoice Capture
description: Questo articolo spiega come configurare la soluzione Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691179"
---
# <a name="configure-the-invoice-capture-solution"></a>Configurare la soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Dopo aver installato la soluzione Invoice Capture, è necessario configurare l'ambiente. Il processo comporta i seguenti passaggi di base.

1. **Obbligatorio:** sincronizza le persone giuridiche da Microsoft Dynamics 365 Finance. Questo passaggio viene utilizzato per configurare la struttura organizzativa in Microsoft Power Platform.
2. **Obbligatorio:** configura i canali per l'importazione delle immagini delle fatture. La soluzione supporta i canali seguenti:

    - Office 365 Outlook (predefinito)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Facoltativo:** definisci gruppi di configurazione aggiuntivi per il servizio di riconoscimento ottico dei caratteri (OCR).
4. **Facoltativo:** definisci le regole di mapping per la persona giuridica, il conto fornitore, l'articolo e il tipo di approvvigionamento.

Questo articolo è incentrato sui due passaggi obbligatori del processo. Per ulteriori informazioni sui gruppi di configurazione, vedi [Gruppi di configurazione della soluzione Invoice Capture](invoice-capture-config-group.md). Per ulteriori informazioni sulle regole di mapping, vedi [Regole di mapping della soluzione Invoice Capture](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Gestisci persone giuridiche

Finance definisce le persone giuridiche come organizzazioni identificata mediante registrazione presso le autorità giuridiche. Le attività commerciali sono svolte e registrate in persone giuridiche separate. In Microsoft Power Platform, le Business Unit, i ruoli di sicurezza e gli utenti sono collegati tra loro in modo conforme al modello di sicurezza basato sui ruoli.

Le Business Unit vengono utilizzate insieme ai ruoli di sicurezza per controllare l'accesso ai dati. Gli utenti vedono solo le informazioni di cui hanno bisogno per eseguire i loro processi. La soluzione Invoice Capture fornisce uno spazio di configurazione in cui è possibile caricare informazioni di base da persone giuridiche esistenti in Finance e gestire quelle create manualmente. Le persone giuridiche vengono utilizzate nelle fatture fornitore e nel controllo di sicurezza.

Quando una persona giuridica viene creata e visualizzata nella visualizzazione elenco, viene creata automaticamente una Business Unit predefinita con lo stesso nome. Al team viene concesso il ruolo di sicurezza **Addetto contabilità fornitori**. Quando vengono importate le persone giuridiche, vengono importati i dati master di base da Finance. Gli articoli inesistenti verranno identificati dalla persona giuridica e verranno aggiunti alla soluzione Invoice Capture. Il gruppo di configurazione predefinito viene assegnato a nuove persone giuridiche.

### <a name="sync-legal-entities"></a>Sincronizzare le persone giuridiche

Non è possibile creare direttamente le persone giuridiche. Tuttavia, puoi sincronizzare le persone giuridiche da Finance. Per sincronizzare le persone giuridiche, segui questi passaggi.

1. Vai a **Impostazione \> Impostazioni sistema \> Gestisci persone giuridiche**.
2. Seleziona **Sincronizza persone giuridiche**, quindi seleziona **OK** nella finestra di dialogo di conferma.

Al termine della sincronizzazione, viene visualizzato il numero di nuove persone giuridiche. Le nuove persone giuridiche vengono visualizzate nella visualizzazione elenco. Il gruppo di configurazione predefinito viene assegnato a nuove persone giuridiche.

## <a name="configure-invoice-import-channels"></a>Configurare i canali di importazione delle fatture

I fornitori inviano fatture da diversi canali (e-mail, area di lavoro file o portale fatture) in formati diversi (cartacei o immagine). La soluzione Invoice Capture fatture può gestire diversi canali e formati. Sono supportati i seguenti tipi:

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

Quando viene creato un canale per un account specifico, viene creato un flusso automatizzato con un modello predefinito per monitorare i messaggi e-mail o i file in arrivo nella Posta in arrivo o nello spazio. Qualsiasi file che ha una fattura valida può essere riconosciuto e inviato all'area fattura in attesa dell'elaborazione da parte dell'addetto alla contabilità fornitori (AP). L'allegato deve essere in formato PDF o immagine. Le fatture possono essere caricate nella soluzione Invoice Capture in base alla configurazione del canale.

### <a name="create-a-channel"></a>Creare un canale

Se hai importato il pacchetto della soluzione aggiuntivo (Dynamics 365 Invoice Capture – Strumenti di installazione), la connessione predefinita per Office 365 Outlook è pronta per l'uso. Se desideri creare più connessioni per diversi account e-mail o altri tipi di canali, consulta [Creare connessioni aggiuntive per i canali](invoice-capture-advanced-settings.md#create-additional-connections-for-channels).

Per creare un canale, effettuare le seguenti operazioni.

1. Vai a **Impostazione \> Impostazioni di sistema \> Configura canali**.
2. Selezionare **Nuovo**.
3. Impostare i seguenti campi:

    - Nome canale
    - Description
    - Tipo
    - Connessione

Nella soluzione possono essere importati solo messaggi di posta elettronica o file che soddisfano i seguenti criteri.

| Tipo               | Configurazione  | Ulteriori informazioni |
|--------------------|----------------|------------------|
| Office 365 Outlook | Cartella         | La cartella e-mail deve trovarsi nella directory radice. Per impostazione predefinita, viene utilizzata la cartella Posta in arrivo. La cartella secondaria non è supportata. |
|                    | Filtro oggetto | (Facoltativo) Una substring che deve essere inclusa nell'oggetto. |
|                    | Dalle           | (Facoltativo) L'indirizzo e-mail del mittente o dei mittenti. Se specifichi più indirizzi, utilizza i punti e virgola (;) come separatori. |
| SharePoint         | Indirizzo sito   | URL dell'indirizzo del sito. |
|                    | Cartella         | La cartella nell'indirizzo del sito. |

### <a name="activate-the-channel"></a>Attivare il canale

Quando un flusso viene salvato, i campi mostrano lo stato del canale e l'ora in cui è stato creato. Inizialmente, il campo **Stato** è impostato su **Inattivo**. Il campo **Motivo stato** indica che il canale è stato inizializzato ed è pronto per essere attivato.

Per attivare il canale, seleziona **Attiva**. I campi **Stato** e **Motivo stato** vengono aggiornati.

Se un canale non è obbligatorio, puoi disattivarlo. Per disattivare il canale, seleziona **Disattiva**. I campi **Stato** e **Motivo stato** vengono aggiornati.

### <a name="manage-flows-in-flow-management"></a>Gestire i flussi nella gestione dei flussi

È possibile visualizzare un canale nella pagina **Configura canali** o nella gestione del flusso.

Per visualizzare maggiori dettagli, vai a **Amministrazione sistema \> Soluzione predefinita \> Flussi cloud** e seleziona il flusso di destinazione. I dettagli visualizzati includono connessioni collegate, proprietari e cronologie di esecuzione.

Per sincronizzare lo stato, seleziona **Controlla** per confermare che lo stato del canale corrisponda allo stato del flusso.

Alcuni casi di gestione delle eccezioni sono mostrati nel campo **Motivo stato**:

- **Connessione Dataverse mancante** – L'utente corrente non ha creato almeno un riferimento a una connessione **Microsoft Dataverse**.
- **Non trovato** – Il flusso collegato al canale è stato eliminato nella gestione del flusso. Il canale deve essere salvato di nuovo per creare un nuovo canale.
- **Disattivato nella gestione del flusso** – Il flusso è stato disattivato nella gestione del flusso e lo stato del canale è diverso dallo stato del flusso.
- **Attivato nella gestione del flusso** – Il flusso è stato attivato nella gestione del flusso e lo stato del canale è diverso dallo stato del flusso.
- **Si è verificato un errore imprevisto** – L'utente deve confermare che il sito è un "Sito di comunicazione" e che la cartella è "Raccolta documenti".
