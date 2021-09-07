---
title: Tipo di destinazione posta elettronica ER
description: Questo argomento spiega come configurare una destinazione e-mail per ogni componente FOLDER o FILE di un formato di creazione di report elettronici (ER).
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4ee1ae4d8a106e467640a8cbcf5986e770395431
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343862"
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

## <a name="enable-an-email-destination"></a>Abilitare una destinazione posta elettronica

Per inviare uno o più file di output tramite e-mail, segui questi passaggi.

1. Nella pagina **Destinazione report elettronici**, nella Scheda dettaglio **Destinazione file**, seleziona un componente o un gruppo di componenti nella griglia.
2. Seleziona **Impostazioni** e quindi nella finestra di dialogo **Impostazioni destinazione**, nella scheda **E-mail**, imposta l'opzione **Abilitato** su **Sì**.

[![Impostare l'opzione Abilitato su Sì per una destinazione di posta elettronica.](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>Configurare una destinazione e-mail

### <a name="email-content"></a>Contenuto del messaggio e-mail

Puoi modificare l'oggetto e il corpo del messaggio e-mail.

Nel campo **Oggetto** , inserite il testo dell'oggetto dell'e-mail che dovrebbe apparire nel campo dell'oggetto di un messaggio elettronico generato in fase di esecuzione. Nel campo **Corpo** , inserisci il testo del corpo dell'e-mail che dovrebbe apparire nel campo corpo di un messaggio elettronico. Puoi impostare un testo costante per l'oggetto e il corpo dell'email, oppure puoi usare le [formule](er-formula-language.md) ER per creare dinamicamente il testo dell'email in tempo reale. La formula configurata deve restituire un valore di tipo [String](er-formula-supported-data-types-primitive.md#string) .

Il corpo dell'e-mail è composto in formato TEXT o HTML, a seconda del client di posta elettronica. Puoi utilizzare qualsiasi layout, stile e marchio HTML e fogli CSS (Cascading Style Sheets) consentiti.

> [!NOTE]
> I client e-mail impongono limiti di layout e stile che potrebbero richiedere modifiche al codice HTML e CSS che usi per il corpo del messaggio. Si consiglia di familiarizzare con le migliori pratiche per la creazione di HTML che i client di posta elettronica più popolari supportano.
>
> Utilizzare la codifica corretta per implementare un ritorno a capo, a seconda della formattazione del corpo. Per maggiori informazioni, vedere la definizione del tipo di dati [String](er-formula-supported-data-types-primitive.md#string) .

### <a name="email-addresses"></a>Indirizzi di posta elettronica

È possibile specificare il mittente e i destinatari dell'e-mail. Per impostazione predefinita, l'e-mail viene inviata a nome dell'utente corrente. Per specificare un mittente differente, devi configurare il campo **Da**.

> [!NOTE]
> Quando viene configurata una destinazione di posta elettronica, il campo **Da** è visibile solo agli utenti che hanno il privilegio di sicurezza `ERFormatDestinationSenderEmailConfigure`, **Configura l'indirizzo e-mail del mittente per le destinazioni in formato ER**.
>
> Quando una destinazione di posta elettronica viene proposta per la modifica al [runtime](electronic-reporting-destinations.md#security-considerations), il campo **Da** è visibile solo agli utenti che hanno il privilegio di sicurezza `ERFormatDestinationSenderEmailMaintain`, **Mantieni l'indirizzo e-mail del mittente per la destinazione in formato ER**.
>
> Quando il campo **Da** è configurato per utilizzare un indirizzo e-mail diverso da quello dell'utente corrente, l'autorizzazione **Invia come** o **Invia per conto di** deve essere [impostata](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group?view=o365-worldwide) correttamente in anticipo. In caso contrario, viene generata la seguente eccezione al runtime: "Impossibile inviare e-mail come \<from email account\> dall'account \<current user account\>. Controlla le autorizzazioni "Invia come" in \<from email account\>."

Puoi configurare il campo **Da** per restituire più di un indirizzo email. In questo caso, il primo indirizzo nell'elenco viene utilizzato come indirizzo del mittente.

Per specificare i destinatari del messaggio e-mail, devi configurare i campi (facoltativi) **A** e **Cc**.

È possibile configurare gli indirizzi di posta elettronica per ER in due modi. La configurazione può essere completata come avviene con la funzionalità Gestione stampa oppure è possibile risolvere un indirizzo di posta elettronica utilizzando un riferimento diretto alla configurazione ER mediante una formula.

## <a name="email-address-types"></a>Tipi di indirizzo di posta elettronica

Se si seleziona **Modifica** accanto al campo **Da**, **A** o **Cc** nella finestra di dialogo **Impostazioni destinazione**, viene visualizzata la finestra di dialogo **Mittente messaggio di posta elettronica**, **Destinatario messaggio di posta elettronica** o **Cc messaggio di posta elettronica**. In quella finestra di dialogo puoi configurare il mittente dell'e-mail e i destinatari dell'e-mail. Selezionare **Aggiungi** e quindi selezionare il tipo di indirizzo di posta elettronica da utilizzare. Due tipi sono attualmente supportati: **Gestione stampa posta elettronica** e **Posta elettronica configurazione**.

[![Selezione del tipo di indirizzo e-mail.](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>Gestione stampa posta elettronica

Se selezioni **Gestione stampa posta elettronica** come tipo di indirizzo di posta elettronica, puoi immettere indirizzi di posta elettronica fissi nella finestra di dialogo **Mittente messaggio di posta elettronica**, **Destinatario messaggio di posta elettronica** o **Cc messaggio di posta elettronica** impostando i seguenti campi:

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
- Persona giuridica

Ad esempio, per configurare una destinazione di posta elettronica per un formato ER utilizzato per elaborare i pagamenti del fornitore, selezionare il ruolo **Fornitore**.

Dopo aver selezionato il ruolo desiderato, selezionare il pulsante **Associa** (simbolo della catena) accanto al campo **Conto di origine posta elettronica** per aprire la pagina [Designer formula](general-electronic-reporting-formula-designer.md). È quindi possibile utilizzare questa pagina per configurare una formula che restituisca, in fase di esecuzione, il numero di conto della parte assegnata al ruolo configurato dal documento elaborato alla destinazione del messaggio di posta elettronica.

> [!NOTE]
> Le formule sono specifiche alla configurazione ER.

Nella pagina **Designer formula**, nel campo **Formula** immettere un riferimento specifico del documento a un ruolo supportato. Invece di digitare il riferimento, nel riquadro **Origine dati**, trova e seleziona il nodo di origine dati che rappresenta un conto del ruolo configurato, quindi selezionare **Aggiungi origine dati** per aggiornare la formula. Ad esempio, se si configura la destinazione di posta elettronica per la configurazione **bonifico ISO 20022** utilizzata per elaborare i pagamenti fornitore, il nodo che rappresenta un conto fornitore è `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Configurazione di un account di origine di posta elettronica.](./media/er_destinations-emaildefineaddresssource.gif)

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

Selezionare **Posta elettronica configurazione** come tipo di indirizzo di posta elettronica se la configurazione utilizzata ha un nodo nelle origini dati che restituisce un singolo indirizzo di posta elettronica o più indirizzi di posta elettronica separati da punto e virgola (;). È possibile usare [origini dati](general-electronic-reporting.md#FormatComponentOutbound) e [funzioni](er-formula-language.md#Functions) nella designer formula per ottenere un indirizzo di posta elettronica formattato correttamente o indirizzi di posta elettronica formattati correttamente separati da punto e virgola. Ad esempio, se si utilizza la configurazione **bonifico ISO 20022**, il nodo che rappresenta l'indirizzo di posta elettronica principale di un fornitore dai dettagli di contatto del fornitore a cui deve essere inviata la lettera di presentazione è `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurazione dell'origine dell'indirizzo e-mail.](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Raggruppare i componenti formato

Per raggruppare i componenti formato, nella pagina **Destinazione report elettronici**, nella scheda dettaglio **Destinazione del file**, selezionare i componenti nella griglia, quindi selezionare **Gruppo**.

**Posta elettronica** è l'unica destinazione precedentemente configurata che è ancora disponibile per i componenti selezionati. Non sono disponibili altre destinazioni configurate in precedenza, poiché sono considerate non supportate per un gruppo di componenti. Riceverai una notifica su queste modifiche come appropriato.

Il record che hai aggiunto in precedenza è considerato l'intestazione del gruppo creato. Questo record di intestazione contiene le impostazioni di destinazione dell'email per il gruppo. Gli altri record sono membri del gruppo che utilizzeranno le impostazioni di destinazione della posta elettronica del record di intestazione del gruppo.

Per separare i componenti formato, nella scheda dettaglio **Destinazione del file**, selezionare un record che appartiene al gruppo, quindi selezionare **Separa**.

- Se selezioni un record di intestazione, l'intero gruppo verrà separato.
- Se selezioni un record di membro ed è l'ultimo record di membro in un gruppo, l'intero gruppo verrà separato.
- Se selezioni un record membro che non è l'ultimo record membro in un gruppo, quel record verrà escluso dal gruppo corrente.

La seguente illustrazione mostra la struttura di un formato ER configurato per produrre un file compresso in uscita che contiene una nota della lettera di sollecito e le fatture cliente appropriate in formato PDF.

[![Struttura di un formto ER che genera documenti in uscita.](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

La seguente illustrazione mostra il processo, come descritto in questo argomento, di raggruppamento di singoli componenti e abilitazione di **Destinazione posta elettronica** per il nuovo gruppo, in modo che una nota di lettera di sollecito venga inviata insieme alle fatture del cliente appropriate come allegati di posta elettronica.

[![Raggruppamento di singoli componenti e attivazione della destinazione posta elettronica.](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
