---
title: Configurare un ambiente sandbox Dynamics 365 Commerce
description: Questo articolo illustra come configurare un ambiente sandbox di Microsoft Dynamics 365 Commerce dopo il provisioning.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: ae6a8c63721ac32f525e1846a10c0b2caeb08f9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270374"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Configurare un ambiente sandbox Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo articolo illustra come configurare un ambiente sandbox di Microsoft Dynamics 365 Commerce dopo il provisioning.

Completa le procedure in questo articolo solo dopo aver effettuato il provisioning dell'ambiente sandbox Commerce. Per informazioni relative a come effettuare il provisioning dell'ambiente sandbox di Commerce, consulta [Provisioning di un ambiente sandbox di Commerce](provisioning-guide.md).

Una volta eseguito il provisioning completo dell'ambiente sandbox di Commerce, è necessario completare ulteriori passaggi di configurazione post-provisioning prima di poter iniziare a usare l'ambiente. Per completare questi passaggi, è necessario utilizzare Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.

## <a name="before-you-start"></a>Prima di iniziare

1. Accedere al [portale LCS](https://lcs.dynamics.com).
1. Andare al progetto.
1. Selezionare l'ambiente nell'elenco.
1. Nelle informazioni sull'ambiente a destra, selezionare **Accedi all'ambiente**. Si accederà a Commerce Headquarters.
1. Assicurarsi che la persona giuridica **USRT** sia selezionata nell'angolo in alto a destra. Questa persona giuridica è stata preconfigurata nei dati demo.
1. Andare a **Parametri Commerce \> Parametri di configurazione** e assicurarsi che ci sia una voce per **ProductSearch.UseAzureSearch** e che il valore sia impostato su **true**. Se questa voce è mancante, aggiungila e imposta il valore su **vero**.
1. Andare a **Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione Commerce \> Inizializza utilità di pianificazione Commerce**. Nel menu a comparsa **Inizializza utilità di pianificazione Commerce**, impostare l'opzione **Elimina configurazione esistente** su **Sì** e selezionare **OK**.
1. Affinché i canali del negozio e dell'e-commerce funzionino correttamente, devono essere aggiunti a Commerce Scale Unit. Vai a **Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione Commerce \> Database canale** e nel riquadro a sinistra seleziona Commerce Scale Unit. Nella Scheda dettaglio **Canale di vendita al dettaglio**, aggiungi i canali **Negozio online AW**, **Negozio online AW Business** e **Negozio online esteso Fabrikam** se prevedi di utilizzare quei canali di e-commerce. Facoltativamente, è anche possibile aggiungere punti vendita al dettaglio se si utilizzerà POS (ad esempio, **Seattle**, **San Francisco** e/o **San Jose**).
1. Per garantire che tutte le modifiche siano sincronizzate con il database del canale, seleziona **Database del canale \> Sincronizzazione completa dei dati** per Commerce Scale Unit.

Durante le attività di post-provisioning in Commerce headquarters, assicurarsi che la persona giuridica **USRT** sia sempre selezionata.

## <a name="configure-the-point-of-sale"></a>Configurare il POS

### <a name="associate-a-worker-with-your-identity"></a>Associare un lavoratore all'identità

Per associare un lavoratore all'identità, effettuare le seguenti operazioni in Commerce headquarters.

1. Utilizzare il menu a sinistra e scegliere **Moduli \> Vendita al dettaglio e commercio \> Dipendenti \> Lavoratori**.
1. Nell'elenco trovare e selezionare il seguente record **000713 - Andrew Collette**. Questo utente di esempio è associato al negozio di San Francisco che verrà utilizzato nella sezione successiva.
1. Nel riquadro azioni selezionare **Commerce**.
1. Selezionare **Associa identità esistente**.
1. Nel campo **Indirizzo di posta elettronica** a destra di **Cerca tramite posta elettronica**, digitare il proprio indirizzo di posta elettronica.
1. Selezionare **Cerca**.
1. Selezionare il record con il proprio nome.
1. Selezionare **OK**.
1. Selezionare **Salva**.

### <a name="activate-cloud-pos"></a>Attivare il Cloud POS

Per attivare Cloud POS in LCS, attenersi alla seguente procedura.

1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Selezionare l'ambiente nell'elenco.
1. Nelle informazioni sull'ambiente a destra, selezionare **Accedi a POS Cloud**.
1. Selezionare **Avanti** per aprire la finestra di dialogo **Prima di iniziare**.
1. Lasciare invariato il campo **URL server**. Selezionare **Avanti**.
1. Accedere usando l'account Microsoft Azure Active Directory ( Azure AD).
1. Sotto **Nome punto vendita**, selezionare **San Francisco**, quindi selezionare **Avanti**.
1. In **Registro e dispositivo**, scegliere **SANFRAN-1**.
1. Selezionare **Attiva**. Si verrà disconnessi e indirizzati alla pagina di accesso POS.
1. A questo punto è possibile accedere all'esperienza Cloud POS utilizzando l'ID operatore **000713** e la password **123**.

## <a name="set-up-your-e-commerce-sites"></a>Configurare i siti di e-commerce

Sono disponibili tre siti dimostrativi di e-commerce: Fabrikam, Adventure Works e Adventure Works Business. Segui i passaggi seguenti per configurare ciascun sito demo.

1. Accedi a Creazione di siti Web utilizzando l'URL di cui hai preso nota quando hai inizializzato l'e-Commerce durante il provisioning (vedere [Inizializzare l'e-Commerce](provisioning-guide.md#initialize-e-commerce)).
1. Seleziona il sito (**Fabrikam**, **Adventure Works**, o **Adventure Works Business**), per aprire la finestra di dialogo di configurazione del sito.
1. Seleziona il dominio inserito quando è stato inizializzato Commerce.
1. In headquarters, seleziona il canale preconfigurato del punto vendita online (**Negozio online esteso Fabrikam**, **Negozio online AW**, o **Negozio online AW Business**) che corrisponde al canale predefinito.
1. Come lingua predefinita, selezionare **en-us**.
1. Configura i campi del percorso. Questo può essere lasciato vuoto per un singolo sito, ma dovrà essere configurato se si utilizza lo stesso nome di dominio per più siti. Ad esempio, se il nome di dominio è `https://www.constoso.com`, puoi usare un percorso vuoto per Fabrikam (`https://contoso.com`), quindi usa "aw" per Adventure Works (`https://contoso.com/aw`) e "awbusiness" per il sito Adventure Works Business (`https://contoso.com/awbusiness`).
1. Seleziona **OK**. Viene visualizzato l'elenco delle pagine del sito.
1. Facoltativamente, ripeti i passaggi 2-7 per configurare gli altri siti demo secondo necessità.

## <a name="enable-jobs"></a>Abilitare i processi

Per abilitare i processi in Commerce, effettuare le operazioni seguenti.

1. Accedi all'ambiente headquarters.
1. Utilizzare il menu a sinistra per andare a **Vendita al dettaglio e commercio \> Richieste di informazioni e report \> Processi batch**.

    Le fasi restanti di questa procedura devono essere completate per ciascuno dei seguenti processi:

    * Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio
    * Disponibilità prodotto
    * P-0001
    * Sincronizza processo di ordini

1. Utilizzare il filtro rapido per cercare il processo per nome.
1. Se lo stato del processo è **Esecuzione**, effettuare le seguenti operazioni:

    1. Selezionare il record.
    1. Nel riquadro azioni, sulla scheda **Processo batch** selezionare **Cambia stato**.
    1. Selezionare **Annullamento** e quindi **OK**.

1. Se lo stato del processo è **Trattenuto**, effettua le seguenti operazioni:

    1. Selezionare il record.
    1. Nel riquadro azioni, sulla scheda **Processo batch** selezionare **Cambia stato**.
    1. Selezionare **In attesa** e quindi **OK**.

Facoltativamente, è anche possibile impostare l'intervallo di ricorrenza su un (1) minuto per i seguenti lavori:

* Elabora processo di notifica tramite posta elettronica di ordine di vendita al dettaglio
* Processo P-0001
* Sincronizza processo di ordini

### <a name="run-full-data-synchronization"></a>Eseguire la sincronizzazione dati completa

Per eseguire la sincronizzazione completa dei dati in Commerce, attenersi alla seguente procedura in Commerce headquarters.

1. Utilizzare il menu a sinistra per andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione commercio \> Database canale**.
1. Selezionare il canale denominato **scXXXXXXXXX**.
1. Selezionare **Sincronizzazione dati completa** nel riquadro azioni.
1. Immettere **9999** come programmazione della distribuzione.
1. Selezionare **OK**.
1. Selezionare **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Verificare le informazioni sulla carta di credito per effettuare acquisti di prova

Per eseguire transazioni di prova nel sito, è possibile utilizzare le seguenti informazioni della carta di credito di prova:

- **Numero carta:** 4111-1111-1111-1111
- **Data di scadenza:** 10/30
- **Codice valore di verifica carta (CVV):** 737

> [!IMPORTANT]
> Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato le fasi di provisioning e configurazione, è possibile iniziare a usare l'ambiente sandbox. Utilizzare l'URL di Creazione di siti Web di Commerce per accedere all'esperienza di creazione. Utilizzare l'URL del sito di Commerce per accedere all'esperienza del sito dei clienti di vendita al dettaglio.

Per configurare funzionalità facoltative per l'ambiente sandbox Commerce, vedu [Configurare le funzionalità facoltative per un ambiente sandbox Commerce](cpe-optional-features.md).

Per consentire agli utenti di e-commerce di accedere al sito di e-commerce, è necessaria una configurazione aggiuntiva per abilitare l'autenticazione del sito tramite Azure Active Directory business-to-consumer (B2C). Per istruzioni, vedi [Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>L'elenco dei canali di Creazione di siti Web è vuoto durante la configurazione del sito

Se Creazione di siti Web non mostra alcun canale di negozi online, nelle sedi centrali assicurarsi che i canali siano stati aggiunti alla Commerce Scale Unit come descritto nella precedente sezione [Prima di iniziare](#before-you-start). Inoltre, eseguire **Inizializza utilità di pianificazione Commerce** con il valore **Elimina configurazione esistente** impostato su **Sì**.  Una volta completati questi passaggi, nella pagina **Database canale** (**Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione Commerce \> Database canale**), eseguire il processo **9999** sulla Commerce Scale Unit.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>I campioni di colore non vengono visualizzati nella pagina delle categorie, ma viene eseguito il rendering nella pagina dei dettagli del prodotto (PDP)

Seguire questi passaggi per assicurarsi che i campioni di colore e dimensione siano impostati per essere ridefiniti.

1. Nelle sedi centrali, andare a **Vendita al dettaglio e commercio \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Nel riquadro a sinistra, selezionare il canale del negozio online, quindi selezionare **Imposta metadati di attributi**.
1. Impostare l'opzione **Mostra attributo sul canale** su **Sì**, impostare l'opzione **Ridefinizione possibile** su **Sì**, quindi selezionare **Salva**. 
1. Tornare alla pagina del canale del negozio online, quindi selezionare **Pubblica aggiornamenti canale**.
1. Andare a **Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Utilità di pianificazione Commerce \> Database canale** ed eseguire il processo **9999** sulla Commerce Scale Unit.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Le funzionalità aziendali non sembrano attivate per il sito aziendale AdventureWorks

Nelle sedi centrali, assicurarsi che il canale del negozio online sia configurato con il **Tipo di cliente** impostato su **B2B**. Se il **Tipo di cliente** è impostato su **B2C**, è necessario creare un nuovo canale poiché il canale esistente non può essere modificato. 

I dati dimostrativi forniti in Commerce versione 10.0.26 e precedenti presentavano un bug per cui il canale **Negozio online AW Business** era configurato in modo errato. La soluzione alternativa è creare un nuovo canale con le stesse impostazioni e configurazioni ad eccezione di **Tipo di cliente**, che deve essere impostato su **B2B**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Eseguire il provisioning dell'ambiente sandbox di Dynamics 365 Commerce](provisioning-guide.md)

[Configurare le funzionalità facoltative per un ambiente sandbox Dynamics 365 Commerce](cpe-optional-features.md)

[Configurare uno scenario BOPIS in un ambiente sandbox Dynamics 365 Commerce](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
