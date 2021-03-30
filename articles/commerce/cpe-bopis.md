---
title: Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento spiega come configurare "acquisto online, ritiro in negozio" (BOPIS) in un ambiente di valutazione Microsoft Dynamics 365 Commerce dopo il provisioning.
author: rubendel
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 71f2fb3882b51cdaed9b231cd605949195deca17
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213868"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a>Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento spiega come configurare "acquisto online, ritiro in negozio" (BOPIS) in un ambiente di valutazione Microsoft Dynamics 365 Commerce dopo il provisioning dell'ambiente.

## <a name="prerequisite"></a>Prerequisito

Completare le procedure in questo argomento solo dopo aver effettuato il provisioning e la configurazione dell'ambiente di valutazione Commerce. Per informazioni relative a come effettuare il provisioning e la configurazione dell'ambiente, consultare [Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md) e [Configurare un ambiente di valutazione Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).

Dopo aver eseguito il provisioning e la configurazione dell'ambiente Commerce end-to-end, è possibile utilizzare questo argomento per abilitare gli scenari BOPIS.

## <a name="configure-the-pos"></a>Configurare il POS

### <a name="configure-modern-pos"></a>Configurare Modern POS

Gli scenari BOPIS che prevedono il pagamento con carta di credito richiedono una stazione hardware. La stazione hardware è integrata nei client Modern POS per Windows e Android. Se si utilizza Cloud POS o Modern POS per iOS, il client del punto vendita (POS) deve essere associato a una stazione hardware condivisa. Questo argomento spiega come configurare BOPIS per client Windows e Android. Per ulteriori informazioni su come configurare una stazione hardware condivisa, vedere [Configurare e installare Retail Hardware Station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Registratori di cassa**.
2. Selezionare il registratore **SANFRAN-5**, quindi selezionare **Modifica**.
3. Modificare il valore del campo **Profilo hardware** da **HW002** in **HW001**, quindi selezionare **Salva**.
4. Per sincronizzare le modifiche, andare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
5. Selezionare la programmazione della distribuzione **1090**, quindi nel riquadro azioni selezionare **Esegui adesso**.
6. Selezionare **Sì** e poi **OK** per avviare la sincronizzazione dei dati. 

### <a name="install-modern-pos"></a>Installare Modern POS

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Dispositivi**.
2. Selezionare il dispositivo **SANFRANCIS-5**.
3. Nel riquadro azioni selezionare **Scarica**, quindi selezionare **File di configurazione**.
4. Selezionare **Scarica** e quindi **Retail Modern POS**. 
5. Quando il download del file **ModernPOSSetup.exe** è completato, selezionare **Apri file**.

    ![Apri file](./dev-itpro/media/PAYMENTS/openfile.png)

6. Selezionare **Avanti** per passare al processo di installazione. Al termine dell'installazione, selezionare **Chiudi**.

### <a name="activate-modern-pos"></a>Attivare Modern POS

1. Sul desktop di Windows, selezionare il pulsante **Start** e immettere **Retail Modern POS**.
2. Selezionare l'applicazione **Retail Modern POS** per avviare l'attivazione.
3. Selezionare **Avanti**. I campi **URL server**, **ID dispositivo** e **Numero registratore di cassa** devono essere preimpostati con le informazioni del file di configurazione scaricato nella procedura precedente.
4. Selezionare **Attiva**.
5. Viene visualizzata una finestra di dialogo di autenticazione. Selezionare l'account che utilizza l'indirizzo di posta elettronica precedentemente associato al lavoratore **000713 - Andrew Collette**.

    > [!NOTE]
    > Se non hai ancora associato un lavoratore all'identità, l'attivazione avrà esito negativo. In questo caso, seguire i passaggi nella sezione "Associare un lavoratore all'identità" nell'argomento [Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).
    
6. Quando viene richiesto di consentire all'organizzazione di gestire il dispositivo, selezionare **Solo questa app**.
7. Al termine dell'attivazione, selezionare **Inizia**.

### <a name="enable-bopis-in-modern-pos"></a>Abilitare BOPIS in Modern POS

1. Accedere a Modern POS utilizzando **000713** come ID operatore e **123** come password.
2. Durante la riproduzione del video introduttivo, selezionare le due caselle di controllo nell'angolo inferiore sinistro della finestra di dialogo, quindi chiudere la finestra di dialogo.
3. Se non viene richiesto di chiudere il turno, scorrere verso destra nella pagina di **benvenuto**, selezionare **Chiudi turno**, quindi accedere nuovamente al POS.
4. Dopo aver effettuato l'accesso, quando richiesto, selezionare **Eseguire un'operazione non relativa al cassetto**.
5. Nella pagina di **benvenuto**, scorrere verso destra e selezionare l'operazione **Seleziona stazione hardware**.
6. Selezionare **Gestione**, impostare l'opzione **Usa stazione hardware** su **Attivo**, quindi selezionare **OK**.
7. Uscire dal POS, e quindi accedere di nuovo.
8. Dopo aver effettuato l'accesso, selezionare **Apri un nuovo turno**, quindi selezionare **Cassetto**.

## <a name="complete-a-bopis-scenario"></a>Completare uno scenario BOPIS

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Creare un ordine di vetrina virtuale per il ritiro in negozio

1. Andare all'URL specificato nel passaggio [Inizializzare e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) durante la configurazione dell'ambiente.
2. Selezionare un articolo e selezionare **Aggiungi al carrello**.
3. Nella pagina del carrello, selezionare **Ritira** per la riga dell'ordine appena aggiunto.
4. Nella finestra di dialogo **Seleziona un negozio**, immettere **San Francisco**, quindi selezionare il pulsante **Ricerca**.
5. Nell'elenco dei risultati, trovare il negozio San Francisco e selezionare **Preleva qui**.
6. Nella pagina del carrello, selezionare **Checkout come ospite**. 

    > [!NOTE]
    > Per continuare con il checkout, è necessario accettare l'informativa sui cookie. Questo avviso appare come un banner nella parte superiore della pagina di checkout.

7. Per il metodo di pagamento con carta di credito, immettere i seguenti dettagli:

    - **Nome del titolare:** immettere un nome.
    - **Numero carta:** immettere **4111-1111-1111-1111**.
    - **Data di scadenza:** immettere **10/20**.
    - **Codice valore di verifica carta (CVV):** immettere **737**.

    > [!IMPORTANT]
    > Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.

8. Continuare il checkout inserendo i dettagli dell'indirizzo di fatturazione, quindi selezionare **Salva e continua**.
9. Quando l'ordine è pronto per essere effettuato, selezionare **Checkout**.

### <a name="synchronize-online-orders-to-the-back-office"></a>Sincronizzare gli ordini online con il back office

Per informazioni su come sincronizzare gli ordini online, vedere [Registrazione di vendite e pagamenti online](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).

### <a name="pick-up-an-order-in-the-store"></a>Prelevare un ordine nel punto vendita

1. Accedere al POS.
2. Nella schermata di **benvenuto**, selezionare **Evasione ordine**
3. Nell'elenco degli articoli per il ritiro, selezionare la riga dell'ordine effettuato online.
4. Mentre la riga ordine è selezionata, selezionare **Preleva**.

    L'articolo della riga viene aggiunto alla schermata della transazione e **$ 0,00** viene visualizzato come saldo dovuto.

5. Selezionare il saldo dovuto di **$ 0,00** oppure selezionare un metodo di pagamento per concludere la transazione.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>Gli ordini online recuperati nel POS hanno un saldo dovuto diverso da zero

Quando viene recuperato un ordine per il ritiro in negozio, se il saldo dovuto non è 0 (zero), assicurarsi che venga utilizzato Modern POS e che la stazione hardware sia attiva. Se si utilizza Cloud POS o Modern POS per iOS, assicurarsi che sia attiva una stazione hardware condivisa. Per recuperare i pagamenti effettuati online è necessaria una forma di stazione hardware attiva.

### <a name="general-issues-with-payment-capture"></a>Problemi generali con l'acquisizione dei pagamenti

Per tutti i problemi generali, consultare sempre i log degli eventi Modern POS o Internet Information Services (IIS) Hardware Station come primo passo. È possibile trovare questi log nei seguenti nodi del registro eventi di Windows:

- Log dei servizi e dell'applicazione \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Log dei servizi e dell'applicazione \> Microsoft \> Dynamics \> Commerce-Hardware Station

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di valutazione Dynamics 365 Commerce](cpe-overview.md)

[Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md)

[Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce](cpe-optional-features.md)

[Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Connettore pagamenti Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[Salvare gli strumenti di pagamento online con il connettore Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[Panoramica dei pagamenti omnicanale](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)


[!INCLUDE[footer-include](../includes/footer-banner.md)]