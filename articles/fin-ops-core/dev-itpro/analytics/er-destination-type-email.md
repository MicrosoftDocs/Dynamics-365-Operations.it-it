---
title: Tipo di destinazione posta elettronica ER
description: Questo argomento spiega come configurare una destinazione e-mail per ogni componente FOLDER o FILE di un formato di creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e2e0da1c724269e0956be2f402b34ff376ed1990
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094106"
---
# <a name="email-er-destination-type"></a>Tipo di destinazione posta elettronica ER

[!include [banner](../includes/banner.md)]

Quando viene eseguito un formato di reporting elettronico (ER), è possibile generare uno o più documenti in uscita. I componenti del formato **Cartella** o **File** vengono utilizzati nei formati ER per specificare la struttura dei documenti in uscita. È possibile configurare una destinazione di posta elettronica per questi tipi di componenti per inviare documenti in uscita come allegati di posta elettronica.

È possibile configurare una destinazione di posta elettronica per ciascun componente **Cartella** o **File** di un formato ER. In questo caso, **ogni documento in uscita viene inviato individualmente tramite posta elettronica**. In base a questa impostazione di destinazione, un documento generato viene fornito come allegato di un messaggio di posta elettronica. 

> [!NOTE]
> espressione filtroSe non viene generato alcun documento, perché l'espressione **Abilitato** per il componente **File** pertinente è stata configurata per restituire un valore booleano **Falso**, nessun messaggio di posta elettronica viene inviato, anche se una destinazione di posta elettronica è configurata e abilitata per il componente.

È possibile anche [raggruppare](#grouping) vari compennti **Cartella** o **File** insieme, quindi configurare una destinazione di posta elettronica per tutti i componenti del gruppo. In questo caso, tutti i documenti in uscita generati dai componenti che appartengono al gruppo **vengono inviati come allegati multipli di una singola email**. In base a questa impostazione di destinazione, ogni documento generato viene fornito come allegato di un singolo messaggio di posta elettronica.

> [!NOTE]
> Se almeno un documento è generato da un componente **File** in un gruppo di componenti, viene inviata un'e-mail. Se non viene generato alcun documento dai componenti raggruppati, perché l'espressione **Abilitato** per ogni componente **File** pertinente è stata configurata per restituire un valore booleano **Falso**, nessun messaggio di posta elettronica viene inviato, anche se una destinazione di posta elettronica è configurata e abilitata per quel gruppo di componenti.
>
> L'**E-mail** è l'unica destinazione che può essere configurata per un gruppo di componenti. Per recapitare un documento inviato tramite posta elettronica in base all'impostazione della destinazione di posta elettronica per un gruppo, aggiungere un altro record di destinazione, selezionare il componente desiderato e quindi configurare un'altra destinazione per questo record.

È possibile configurare più gruppi di componenti per una singola configurazione del formato ER. In questo modo, puoi configurare una destinazione e-mail per ogni gruppo di componenti e una destinazione e-mail per ogni componente.

## <a name="configure-an-email-destination"></a>Configurare una destinazione e-mail

Per inviare un file di output o diversi file di output tramite e-mail, nella pagina **Destinazione di segnalazione elettronica**, nella scheda dettaglio **Destinazione del file**, selezionare un componente o un gruppo di componenti nella griglia, quindi selezionare **Impostazioni**. Nella finestra di dialogo **Impostazioni di destinazione** che appare, nella scheda **E-mail**, impostare l'opzione **Abilitato** per **Sì**. È possibile specificare i destinatari del messaggio di posta elettronica e modificare l'oggetto e il corpo del messaggio. È possibile impostare testo costante per l'oggetto e il corpo del messaggio di posta elettronica oppure utilizzare le [formule](er-formula-language.md) ER per creare in modo dinamico i testi del messaggio di posta elettronica.

È possibile configurare gli indirizzi di posta elettronica per ER in due modi. La configurazione può essere completata come avviene con la funzionalità Gestione stampa oppure è possibile risolvere un indirizzo di posta elettronica utilizzando un riferimento diretto alla configurazione ER mediante una formula.

[![Impostare l'opzione Abilitato su Sì per una destinazione di posta elettronica](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Tipi di indirizzo di posta elettronica

Se si seleziona **Modifica** accanto al campo **A** o **Cc** nella finestra di dialogo **Impostazioni destinazione**, viene visualizzata la finestra di dialogo **Destinatario messaggio di posta elettronica**. Selezionare **Aggiungi** e quindi selezionare il tipo di indirizzo di posta elettronica da utilizzare. Due tipi sono attualmente supportati: **Gestione stampa posta elettronica** e **Posta elettronica configurazione**.

[![Selezionare il tipo di indirizzo di posta elettronica](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>Gestione stampa posta elettronica

Se si seleziona **Gestione stampa posta elettronica** come tipo di indirizzo di posta elettronica, è possibile immettere indirizzi di posta elettronica fissi nella finestra di dialogo **Destinatario messaggio di posta elettronica** impostando i seguenti campi:

- Nel campo **Origine posta elettronica**, selezionare **Nessuna**.
- Nel campo **Indirizzi di posta elettronica aggiuntivi, separati da ";"**, immettere gli indirizzi di posta elettronica fissi.

In alternativa, è possibile ottenere indirizzi di posta elettronica dai dettagli di contatto della parte per la quale si genera un documento in uscita. Per utilizzare indirizzi di posta elettronica non fissi, nel campo **Origine posta elettronica** selezionare il [ruolo](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles) della parte per una destinazione file. Sono supportati i ruoli che seguono:

- Cliente
- Fornitore
- Prospect
- Contatto
- Concorrente
- Lavoro
- Richiedente
- Fornitore potenziale
- Fornitore non autorizzato

Ad esempio, per configurare una destinazione di posta elettronica per un formato ER utilizzato per elaborare i pagamenti del fornitore, selezionare il ruolo **Fornitore**.

Dopo aver selezionato il ruolo desiderato, selezionare il pulsante **Associa** (simbolo della catena) accanto al campo **Conto di origine posta elettronica** per aprire la pagina [Designer formula](general-electronic-reporting-formula-designer.md). È quindi possibile utilizzare questa pagina per configurare una formula che restituisca, in fase di esecuzione, il numero di conto della parte assegnata al ruolo configurato dal documento elaborato alla destinazione del messaggio di posta elettronica.

> [!NOTE]
> Le formule sono specifiche alla configurazione ER.

Nella pagina **Designer formula**, nel campo **Formula** immettere un riferimento specifico del documento a un ruolo supportato. Invece di digitare il riferimento, nel riquadro **Origine dati**, trova e seleziona il nodo di origine dati che rappresenta un conto del ruolo configurato, quindi selezionare **Aggiungi origine dati** per aggiornare la formula. Ad esempio, se si configura la destinazione di posta elettronica per la configurazione **bonifico ISO 20022** utilizzata per elaborare i pagamenti fornitore, il nodo che rappresenta un conto fornitore è `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Configurare un conto di origine di posta elettronica](./media/er_destinations-emaildefineaddresssource.gif)

Se i numeri conto del ruolo configurato sono univoci per l'intera istanza di Microsoft Dynamics 365 Finance, il campo **Società dell'origine posta elettronica** nella finestra di dialogo **Destinatario messaggio di posta elettronica** può rimanere vuota.

In alternativa, potrebbe verificarsi una situazione in cui diverse parti nella [Rubrica globale](../../fin-ops/organization-administration/overview-global-address-book.md) sono state registrate in diverse società ([persone giuridiche](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) in modo che utilizzino tutti lo stesso numero di conto per ricoprire il ruolo configurato. In questo caso, i numeri di conto per il ruolo configurato non sono univoci per l'intera istanza di Finance. Pertanto, per selezionare esplicitamente una parte, non è possibile specificare solo un numero di conto. È inoltre necessario specificare l'azienda per la quale la parte è stata registrata nell'ambito di per ricoprire il ruolo configurato. Selezionare il pulsante **Associa** (simbolo della catena) accanto al campo **Conto di origine posta elettronica** nella finestra di dialogo **Destinatario messaggio di posta elettronica** per aprire la pagina [Designer formula](general-electronic-reporting-formula-designer.md). È quindi possibile utilizzare questa pagina per configurare una formula che restituisca, in fase di esecuzione, il codice dell'azienda di cui deve essere trovata la fonte desiderata nell'ambito di applicazione.

> [!TIP]
> Se è necessario utilizzare il codice dell'azienda per eseguire un formato ER, ma il formato ER non fornisce alcuna origine dati da cui è possibile ottenere il codice aziendale, configurare la formula `GetCurrentCompany()` utilizzando la funzione ER incorporata [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md).

> [!NOTE]
> Le formule sono specifiche alla configurazione ER.

Per specificare il tipo di indirizzi di posta elettronica da utilizzare in fase di esecuzione, nella finestra di dialogo **Destinatario messaggio di posta elettronica**, selezionare **Modifica** accanto al campo **A** per aprire la finestra di dialogo a discesa **Assegna indirizzi di posta elettronica**. Quindi impostare i seguenti campi:

- Nel campo **Scopo**, selezionare gli scopi desiderati. Verranno utilizzati solo gli indirizzi e-mail degli scopi selezionati dai contatti della parte scoperta.
- Impostare l'opzione **Contatto primario** su **Sì** per utilizzare un indirizzo di posta elettronica configurato per la parte scoperta come indirizzo di posta elettronica principale.

> [!NOTE]
> Se gli scopi sono selezionati nel campo **Scopo** e l'opzione **Contatto primario** è impostata su **Sì** allo stesso tempo, tutti i messaggi di posta elettronica che soddisfano almeno un criterio configurato verranno utilizzati in fase di esecuzione.

### <a name="configuration-email"></a>Posta elettronica configurazione

Selezionare **Posta elettronica configurazione** come tipo di indirizzo di posta elettronica se la configurazione utilizzata ha un nodo nelle origini dati che restituisce un singolo indirizzo di posta elettronica o più indirizzi di posta elettronica separati da punto e virgola (;). È possibile usare [origini dati](general-electronic-reporting.md#FormatComponentOutbound) e [funzioni](er-formula-language.md#functions) nella designer formula per ottenere un indirizzo di posta elettronica formattato correttamente o indirizzi di posta elettronica formattati correttamente separati da punto e virgola. Ad esempio, se si utilizza la configurazione **bonifico ISO 20022**, il nodo che rappresenta l'indirizzo di posta elettronica principale di un fornitore dai dettagli di contatto del fornitore a cui deve essere inviata la lettera di presentazione è `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurare un'origine di un indirizzo di posta elettronica](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Raggruppare i componenti formato

Per raggruppare i componenti formato, nella pagina **Destinazione report elettronici**, nella scheda dettaglio **Destinazione del file**, selezionare i componenti nella griglia, quindi selezionare **Gruppo**.

**Posta elettronica** è l'unica destinazione precedentemente configurata che è ancora disponibile per i componenti selezionati. Non sono disponibili altre destinazioni configurate in precedenza, poiché sono considerate non supportate per un gruppo di componenti. Riceverai una notifica su queste modifiche come appropriato.

Il record che hai aggiunto in precedenza è considerato l'intestazione del gruppo creato. Questo record di intestazione contiene le impostazioni di destinazione dell'email per il gruppo. Gli altri record sono membri del gruppo che utilizzeranno le impostazioni di destinazione della posta elettronica del record di intestazione del gruppo.

Per separare i componenti formato, nella scheda dettaglio **Destinazione del file**, selezionare un record che appartiene al gruppo, quindi selezionare **Separa**.

- Se selezioni un record di intestazione, l'intero gruppo verrà separato.
- Se selezioni un record di membro ed è l'ultimo record di membro in un gruppo, l'intero gruppo verrà separato.
- Se selezioni un record membro che non è l'ultimo record membro in un gruppo, quel record verrà escluso dal gruppo corrente.

La seguente illustrazione mostra la struttura di un formato ER configurato per produrre un file compresso in uscita che contiene una nota della lettera di sollecito e le fatture cliente appropriate in formato PDF.

[![Struttura di un formato ER che genera documenti in uscita](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

La seguente illustrazione mostra il processo, come descritto in questo argomento, di raggruppamento di singoli componenti e abilitazione di **Destinazione posta elettronica** per il nuovo gruppo, in modo che una nota di lettera di sollecito venga inviata insieme alle fatture del cliente appropriate come allegati di posta elettronica.

[![Raggruppare singoli componenti e attivare la destinazione posta elettronica](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]