---
title: Impostare e generare file di pagamento sicuri utilizzando la creazione di report elettronici
description: In questo articoloviene descritto come impostare un pagamento sicuro usando la creazione di report elettronici.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 491048c7274ba6bb52e0a4b7a6ea5cd0f5ff4741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878220"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Impostare file di pagamento sicuri utilizzando la creazione di report elettronici

In questo articolo viene descritto come impostare un pagamento sicuro e generare file pagamenti sicuri usando la creazione di report elettronici.

> [!NOTE] 
> Prima di utilizzare la funzione **Genera file di pagamento sicuro della banca** dovrai prima aggiornare l'elenco di entità.
> Vai in **Gestione dati > Importa / Esporta > Parametri framework** 
> scheda dettaglio **Impostazioni entità** e seleziona **Aggiorna elenco entità**.


Impostare il pagamento sicuro per generare l'elenco elettronico degli assegni che viene fornito alla banca. Quando si presenta un assegno alla banca, la banca lo confronta con l'elenco degli assegni. Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida. Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.

## <a name="security-for-positive-pay-files"></a>Sicurezza dei file pagamenti sicuri
I file pagamenti sicuri possono contenere dati riservati sui beneficiari e sugli importi dell'assegno. Di conseguenza, assicurarsi di utilizzare le misure di sicurezza appropriate dalla generazione dei file fino alla loro ricezione da parte della banca. I file pagamenti sicuri vengono scaricati nel percorso specificato dal Web browser. Poiché i file pagamenti sicuri possono contenere informazioni riservate, è importante che solo gli utenti autorizzati abbiano accesso per generare e visualizzare queste informazioni in Microsoft Microsoft Dynamics 365 Finance. Utilizzare la seguente tabella per determinare i privilegi necessari.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attività</th>
<th>Privilegio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generare i file pagamenti sicuri dalla pagina elenco <strong>Conti bancari</strong> o dalla pagina <strong>Conti bancari</strong>.</td>
<td><ul>
<li><strong>Gestisci informazioni su pagamenti sicuri bancari</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generare file pagamenti sicuri per più persone giuridiche e conti bancari dalla pagina <strong>Genera un file pagamenti sicuri</strong>.</td>
<td><ul>
<li><strong>Gestisci informazioni su pagamenti sicuri bancari</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visualizzare i file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</td>
<td><strong>Visualizza le informazioni sui pagamenti sicuri per più persone giuridiche</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Confermare un file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</td>
<td><strong>Conferma file pagamenti sicuri</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Richiamare un file pagamenti sicuri nella pagina <strong>Riepilogo file pagamenti sicuri</strong>.</td>
<td><strong>Richiama file pagamenti sicuri</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-the-electronic-reporting-configuration"></a>Impostare la creazione di report elettronici

1. Vai in **Aree di lavoro \> Creazione di report elettronici**.
2. Nel riquadro per il provider di configurazione **Microsoft**, seleziona **Archivi**.
3. Seleziona **Globale** e quindi seleziona **Apri**.
4. Se è necessario stabilire una connessione al repository, seleziona il collegamento blu nella finestra di dialogo.
5. Nell'elenco di configurazione, trova e seleziona **Modello di pagamento sicuro \> Formato di pagamento sicuro**.
6. Nella Scheda dettaglio **Versioni** seleziona la versione più recente, quindi selezionare **Importa**.

## <a name="set-up-a-positive-pay-format"></a>Impostare un formato pagamenti sicuri

1. Passa a **Gestione cassa e banche \> Impostazioni \> Formato di pagamento sicuro**.
2. Selezionare **Nuovo**.
3. Imposta i campi **Formato di pagamento** e **Descrizione**.
4. Seleziona la casella di controllo **Formato esportazione elettronica generica**.
5. Imposta il campo **Configurazione formato esportazione** su **Formato di pagamento sicuro**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Assegnare un formato pagamenti sicuri a un conto bancario
Per ogni conto bancario per il quale generare le informazioni pagamenti sicuri, è necessario assegnare il formato pagamenti sicuri specificato nella sezione precedente. Nella pagina Conti bancari selezionare il formato pagamenti sicuri che corrisponde al conto bancario. Nel campo **Data di inizio pagamenti sicuri** immettere la prima data per generare i file pagamenti sicuri. 

>[!Important]
> Immetti una data nel campo **Data di inizio pagamento sicuro**. Se il campo viene lasciato vuoto, il file pagamenti sicuri generato includerà tutti gli assegni creati per questo conto bancario.

1. Passa a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Apri il conto bancario.
3. Nella Scheda dettaglio **Generale**, imposta il campo **Formato di pagamento sicuro** nel formato creato in precedenza.
4. Imposta il campo **Data di inizio pagamento sicuro** sulla data corrente.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Assegnare una sequenza numerica per i file pagamenti sicuri
Ogni file pagamenti sicuri deve essere dotato di un numero univoco. Nella pagina **Parametri di gestione cassa e banche** crea una sequenza numerica per i file pagamenti sicuri nella scheda **Sequenze numeriche**.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generare un file pagamenti sicuri per un singolo conto bancario
È possibile generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario. Per informazioni su come generare contemporaneamente file pagamenti sicuri per più persone giuridiche e conti bancari, vedere la sezione successiva. Per generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario, aprire la finestra di dialogo **Genera un file pagamenti sicuri** dalla pagina **Conti bancari**. Nel campo **Data limite** immettere l'ultima data dell'assegno da includere nel file pagamenti sicuri. Tutti gli assegni che non sono stati inclusi in un file pagamenti sicuri entro questa data vengono inclusi nel file.

1. Passa a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Apri un conto bancario per il quale è impostato un pagamento sicuro.
3. Seleziona **Gestisci pagamenti \> Pagamento sicuro \> File di pagamento sicuro**.
4. Imposta il campo **Data limite**. Verranno inclusi gli assegni generati prima di questa data.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generare un file pagamenti sicuri per più conti bancari
Per generare un file pagamenti sicuri per più conti bancari, utilizza l'attività periodica **File pagamenti sicuri**. Selezionare il formato pagamenti sicuri per il file e specificare se generare il file per tutte le persone giuridiche o per una persona giuridica selezionata. È anche possibile generare il file pagamenti sicuri per tutti i conti bancari che utilizzano il formato specificato o per un conto bancario selezionato. Nel campo **Data limite** immettere l'ultima data dell'assegno da includere nel file pagamenti sicuri. Tutti gli assegni che non sono stati inclusi in un file pagamenti sicuri entro questa data vengono inclusi nel file.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Visualizzare i risultati della generazione del file pagamenti sicuri
Dopo che il file pagamenti sicuri è stato generato, è possibile visualizzare i risultati nella pagina **Riepilogo file pagamenti sicuri**. Per visualizzare i dettagli dei singoli assegni, utilizza la pagina dei dettagli **File pagamenti sicuri**.

## <a name="confirm-a-positive-pay-file"></a>Conferma un file pagamenti sicuri
Dopo aver pagato gli assegni elencati in un file pagamenti sicuri, viene visualizzato un numero di conferma dalla banca. È quindi possibile confermare il file pagamenti sicuri. Nella pagina **Riepilogo file pagamenti sicuri**, selezionare un file pagamenti sicuri con stato **Creato**, quindi selezionare l'azione **Immetti conferma**. Quando si conferma un file pagamenti sicuri, viene registrato il numero di conferma ricevuto dalla banca.

## <a name="recall-a-positive-pay-file"></a>Richiamare un file pagamenti sicuri
Per modificare un file pagamenti sicuri, è possibile richiamarlo. Nella pagina **Riepilogo file pagamenti sicuri**, selezionare un file pagamenti sicuri con stato **Creato**, quindi selezionare l'azione **Immetti conferma**. Per ogni assegno nel file pagamenti sicuri, viene reimpostato il campo che indica se l'assegno è stato incluso in un file pagamenti sicuri. È quindi possibile creare un nuovo file pagamenti sicuri che includa l'assegno richiamato.


Il file XML risultante verrà scaricato.
