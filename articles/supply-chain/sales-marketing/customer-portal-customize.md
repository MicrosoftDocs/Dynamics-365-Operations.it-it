---
title: Personalizzare e utilizzare il portale clienti
description: In questo argomento viene descritto come personalizzare il portale clienti dopo che è stato aggiunto al sistema.
author: dasani-madipalli
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 16d5c13c0fbff8c5033b0d1e9dd0d07851521126
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840775"
---
# <a name="customize-and-use-the-customer-portal"></a>Personalizzare e utilizzare il portale clienti

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo argomento vengono descritte diverse pagine predefinite del portale clienti. Viene inoltre spiegata la funzione delle pagine e come è possibile personalizzarle.

Il portale clienti include alcune pagine Web e azioni predefinite. La seguente mappa del sito fornisce una panoramica di tali pagine Web e azioni e dei ruoli che possono svolgere le azioni.

![Mappa del sito del portale clienti](media/customer-portal-site-map.png "Mappa del sito del portale clienti")

## <a name="typical-customizations"></a>Personalizzazioni tipiche

Mediante i seguenti argomenti è possibile apprendere le nozioni di basi sui portali Power Apps e come personalizzare i portali:

- [Utilizzare i modelli](https://docs.microsoft.com/powerapps/maker/portals/work-with-templates) - Questo argomento fornisce una panoramica generale del funzionamento dei portali Power Apps e spiega come eseguire semplici personalizzazioni dei portali.
- [Gestire il contenuto del portale](https://docs.microsoft.com/dynamics365/portals/manage-portal-content) - Questo argomento spiega come è possibile gestire e personalizzare il contenuto visibile nel portale.
- [Modificare CSS](https://docs.microsoft.com/powerapps/maker/portals/edit-css) - Questo argomento consente di eseguire personalizzazioni più complesse nell'interfaccia utente del portale.
- [Creare un tema per il portale](https://docs.microsoft.com/dynamics365/portals/create-theme) - Questo argomento consente di creare un tema dell'interfaccia utente per il portale.
- [Creare ed esporre facilmente il contenuto del portale](https://docs.microsoft.com/dynamics365/portals/create-expose-portal-content) - Questo argomento consente di gestire i dati e le tabelle sottostanti utilizzate per il portale.
- [Configurare un contatto per l'uso in un portale](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-contacts) - Questo argomento spiega come creare e personalizzare i ruoli utente nonché la sicurezza e l'autenticazione nei portali Power Apps.
- [Configurare note per i moduli tabella e i moduli Web nei portali ](https://docs.microsoft.com/powerapps/maker/portals/configure-notes) - Questo argomento spiega come aggiungere documenti e spazio di archiviazione aggiuntivo al portale.
- [Gestione degli errori per il sito Web del portale](https://docs.microsoft.com/powerapps/maker/portals/admin/view-portal-error-log) - Questo argomento descrive come visualizzare i log degli errori del portale e memorizzarli nell'account dell'archiviazione BLOB di Microsoft Azure .

## <a name="customize-the-order-creation-process"></a>Personalizzare il processo di creazione di ordini

Quando un utente invia un ordine utilizzando il portale clienti, l'ordine viene automaticamente sincronizzato con l'ambiente Dynamics 365 Supply Chain Management corrispondente. Poiché l'utente è un cliente esterno, alcune informazioni richieste sono intenzionalmente nascoste dallo stesso. Queste informazioni verranno automaticamente compilate all'invio del modulo.

Questa sezione mostra come configurare i contatti per evitare errori. Spiega i campi configurati automaticamente e come è possibile modificare, se necessario, il valore degli stessi.

### <a name="the-out-of-box-order-creation-process"></a>Processo di creazione di ordini predefinito

Di seguito sono riportati i passaggi standard per l'invio di un ordine dal portale clienti.

1. Nella home page, selezionare il riquadro **Crea ordine** per aprire la procedura guidata **Crea ordine**.
1. Nella pagina **Informazioni sugli ordini**, impostare i seguenti campi:

    - **Data di ricevimento richiesta** - Specificare la data di consegna.
    - **Indirizzo di consegna** - Immettere l'indirizzo presso il quale consegnare l'ordine.
    - **Società** - Selezionare il nome della società cliente. Questo campo viene automaticamente impostato per gli utenti non amministratori.
    - **Numero della richiesta** - Immettere il numero di richiesta dell'ordine. Questo campo non è obbligatorio.
    - **Spedisci a paese** - Immettere il paese in cui gli articoli verranno consegnati. Questo campo viene automaticamente impostato per gli utenti non amministratori.

    ![Pagina Informazioni ordine](media/customer-portal-order-information.png "Pagina Informazioni ordine")

1. Selezionare **Avanti**.
1. Nella pagina **Articoli** selezionare **Aggiungi articolo**.

    ![Pagina Articoli](media/customer-portal-items.png "Pagina Articoli")

1. Nella finestra di dialogo **Informazioni articolo**, impostare i seguenti campi:

    - **Nome prodotto** - Trovare e selezionare un prodotto da aggiungere all'ordine.
    - **Quantità** - Immettere la quantità del prodotto selezionato.
    - **Unità** - Specificare l'unità di misura (ad esempio, **unità**, **kg** o **scatola**).
    - **Importo netto stimato** - Il valore viene calcolato come il prezzo stimato dell'articolo × la quantità nell'unità selezionata.

    ![Finestra di dialogo Informazioni articolo](media/customer-portal-item-information.png "Finestra di dialogo Informazioni articolo")

1. Selezionare **Invia** per aggiungere l'articolo all'ordine.
1. Ripetere i passaggi da 4 a 6 fino a quando non sono stati aggiunti tutti gli articoli che si desidera ordinare.
1. Dopo aver aggiunto gli articoli, selezionare **Avanti** nella pagina **Articoli**.
1. La pagina **Informazioni ordine** fornisce un riepilogo dell'ordine. Esaminare il contenuto dell'ordine e i dettagli sulla consegna. Se tutto sembra corretto, selezionare **Invia** per inviare l'ordine.

    ![Pagina Informazioni ordine](media/customer-portal-order-submit.png "Pagina Informazioni ordine")

### <a name="standard-data-setup"></a>Configurazione dei dati standard

Per garantire un'esperienza utente senza problemi, il portale clienti inserisce automaticamente i valori per diversi campi obbligatori. Questi valori si basano sulle informazioni nel record di contatto del cliente che sta inviando l'ordine.

Per ogni [riga di contatto](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-contacts) che appartiene a un cliente che utilizzerà il portale clienti per inviare ordini, i valori devono essere specificati per i seguenti campi obbligatori. Altrimenti, si verificheranno degli errori.

- **Società** - L'entità legale a cui appartiene l'ordine
- **Cliente potenziale** - L'account cliente associato all'ordine
- **Listino prezzi** - Il listino prezzi personalizzato per il cliente
- **Valuta** - La valuta del prezzo
- **Spedisci a paese** - Immettere il paese in cui gli articoli verranno consegnati

I seguenti campi vengono impostati automaticamente per la tabella ordine cliente:

- **Lingua** - La lingua dell'ordine (per impostazione predefinita, il valore viene ricavato dal record di contatto)
- **Spedisci a paese** - Il paese in cui verranno consegnati gli articoli (per impostazione predefinita, il valore viene ricavato dal record di contatto)
- **Contatto** - L'utente che può essere contattato per informazioni sull'ordine (per impostazione predefinita, il valore viene ricavato dal record di contatto)
- **Società** - La persona giuridica a cui appartiene l'ordine (per impostazione predefinita, il valore viene ricavato dal record di contatto)
- **Cliente potenziale** - L'account cliente associato all'ordine (per impostazione predefinita, il valore viene ricavato dal record di contatto)
- **Cliente fattura** - L'account di fatturazione dell'ordine (il valore predefinito è il cliente potenziale nel record di contatto)
- **Nome ordine cliente** - Il nome dell'ordine cliente (il valore predefinito è **ordine cliente**)
- **Valuta** - La valuta del prezzo (per impostazione predefinita, il valore viene ricavato dal record di contatto)
- **Listino prezzi** - Il listino prezzi personalizzato per il cliente (per impostazione predefinita, il valore è ricavato dal record del contatto.)
- **Descrizione indirizzo di consegna** - L'indirizzo di consegna dell'ordine cliente (il valore predefinito è **Descrizione indirizzo di consegna**)

### <a name="modify-the-order-creation-process"></a>Modificare il processo di creazione di ordini

È possibile modificare liberamente l'aspetto e l'interfaccia utente del portale clienti se non si modifica il processo di creazione di ordini di base. Se si desidera modificare il processo di creazione di ordini, è necessario tenere presente alcuni aspetti.

Non rimuovere le seguenti colonne dalla tabella ordine cliente in Microsoft Dataverse, poiché sono necessari per creare un ordine cliente in doppia scrittura:

- **Società** - L'entità legale a cui appartiene l'ordine
- **Nome** - Il nome dell'ordine cliente
- **Valuta** - La valuta del prezzo
- **Listino prezzi** - Il listino prezzi personalizzato per il cliente
- **Spedisci a paese** - Immettere il paese in cui gli articoli verranno consegnati
- **Cliente potenziale** - L'account cliente associato all'ordine
- **Lingua** - La lingua dell'ordine (in genere, questa lingua è la lingua del cliente potenziale)
- **Descrizione indirizzo di consegna** - L'indirizzo di consegna dell'ordine cliente

Per gli articoli, le colonne seguenti sono obbligatorie:

- **Prodotto** - Il prodotto da ordinare
- **Quantità** - La quantità del prodotto selezionato
- **Unità** - L'unità di misura (ad esempio, **unità**, **kg** o **scatola**)
- **Spedisci a paese** - Il paese di consegna
- **Descrizione indirizzo di consegna** - L'indirizzo di consegna dell'ordine

È necessario assicurarsi che il portale clienti invii i valori per tutte queste colonne.

Se si desidera aggiungere colonne alla pagina o rimuovere colonne, vedere [Creare o modificare moduli di creazione rapida per un'esperienza di immissione dati ottimizzata](https://docs.microsoft.com/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Se si desidera modificare la modalità di preimpostazione delle colonne e di impostazione dei valori al momento del salvataggio della pagina, consultare le seguenti informazioni nella documentazione sui portali Power Apps:

- [Prepopolare i campi](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Impostare i valori al salvataggio](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>Personalizzare la home page

Tutti i controlli nel portale clienti sono integrati nei controlli dei portali Power Apps. È possibile personalizzarli seguendo i passaggi in [Comporre una pagina](https://docs.microsoft.com/powerapps/maker/portals/compose-page) nella documentazione sui portali Power Apps.

L'unico controllo personalizzato incluso nel modello di portale clienti è utilizzato per creare i riquadri nella home page.

![Riquadri nella home page](media/customer-portal-home-page-tiles.png "Riquadri nella home page")

Per utilizzare i riquadri, seguire questi passaggi.

1. Aprire l'[app Gestione portali](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-portal).
1. Selezionare **Modelli pagina** nel pannello di navigazione a sinistra.

    ![Pannello di navigazione di Gestione portali](media/customer-portal-nav.png "Pannello di navigazione di Gestione portali")

1. Selezionare il modello di pagina denominato **Home**.
1. Nel campo **Modello Web**, selezionare il collegamento **Home** per aprire il codice sorgente di quella pagina.

    ![Campo Modello Web](media/customer-portal-web-template.png "Campo Modello Web")

1. Ora dovrebbe essere visualizzato tutto il codice sorgente della home page, che può essere modificato come necessario.

## <a name="resources"></a>Risorse

Per ulteriori informazioni su come configurare e personalizzare il portale clienti, consultare le seguenti risorse:

- [Documentazione sui portali Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Documentazione sulla doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [Informazioni sul ciclo di vita dei portali](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Aggiornare un portale](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migrare la configurazione del portale](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Gestione del ciclo di vita delle soluzioni: app Dynamics 365 for Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]