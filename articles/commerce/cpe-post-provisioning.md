---
title: Configurare un ambiente di anteprima Commerce
description: Questo argomento illustra come configurare un ambiente di anteprima di Microsoft Dynamics 365 Commerce dopo il provisioning.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f19d03f3f2f5a9f6f7ba08b682277e4e3b764d10
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906141"
---
# <a name="configure-a-commerce-preview-environment"></a>Configurare un ambiente di anteprima Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Questo argomento illustra come configurare un ambiente di anteprima di Microsoft Dynamics 365 Commerce dopo il provisioning.

## <a name="overview"></a>Panoramica

Completare le procedure in questo argomento solo dopo aver effettuato il provisioning dell'ambiente di anteprima di Commerce. Per informazioni relative a come effettuare il provisioning dell'ambiente di anteprima di Commerce, consultare [Provisioning di un ambiente di anteprima Commerce ](provisioning-guide.md).

Una volta eseguito il provisioning completo dell'ambiente di anteprima di Commerce, è necessario completare ulteriori passaggi di configurazione post-provisioning prima di poter iniziare a valutare l'ambiente. Per completare questi passaggi, è necessario utilizzare Lifecycle Services (LCS) di Microsoft Dynamics, Dynamics 365 Commerce e Dynamics 365 Retail.

## <a name="before-you-start"></a>Prima di iniziare

1. Accedere al [portale LCS](https://lcs.dynamics.com).
1. Andare al progetto.
1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Selezionare l'ambiente nell'elenco.
1. Nelle informazioni sull'ambiente a destra, selezionare **Dettagli completi**.
1. Selezionare **Accesso** per aprire un menu, quindi scegliere **Accedi all'ambiente**.
1. Assicurarsi che la persona giuridica **USRT** sia selezionata nell'angolo in alto a destra.

## <a name="configure-the-point-of-sale-in-lcs"></a>Configurare il POS in LCS

### <a name="associate-a-worker-with-your-identity"></a>Associare un lavoratore all'identità

Per associare un lavoratore all'identità in LCS, effettuare le seguenti operazioni.

1. Utilizzare il menu a sinistra e scegliere **Moduli \> Vendita al dettaglio \> Dipendenti \> Lavoratori**.
1. Nell'elenco trovare e selezionare il seguente record **000713 - Andrew Collette**.
1. Nel riquadro azioni fare clic su **Vendita al dettaglio**.
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
1. Nelle informazioni sull'ambiente a destra, selezionare **Dettagli completi**.
1. Selezionare **Accesso**per aprire un menu, quindi selezionare **Accedi a POS Cloud** per aprire il POS.
1. Selezionare **Avanti**.
1. Accedere usando l'account Microsoft Azure Active Directory ( Azure AD).
1. In **Nome punto vendita**, scegliere **San Francisco**.
1. Selezionare **Avanti**.
1. In **Registro e dispositivo**, scegliere **SANFRAN-1**.
1. Selezionare **Attiva**. Si verrà disconnessi e indirizzati alla pagina di accesso POS.
1. A questo punto è possibile accedere all'esperienza Cloud POS utilizzando l'ID operatore **000713** e la password **123**.

## <a name="set-up-your-site-in-commerce"></a>Configurare il sito in Commerce

Per iniziare a configurare il sito di anteprima in Commerce, attenersi alla seguente procedura.

1. Accedere allo strumento di gestione del sito Commerce utilizzando l'URL annotato durante l'inizializzazione di e-Commerce durante il provisioning (vedere [Inizializzare e-Commerce ](provisioning-guide.md#initialize-e-commerce)).
1. Selezionare il sito **Fabrikam** per aprire la finestra di dialogo di impostazione del sito.
1. Selezionare il dominio inserito quando è stato inizializzato e-Commerce.
1. Come canale predefinito, selezionare **Punto vendita online esteso Fabrikam**. Assicurarsi di selezionare il punto vendita online **esteso**.
1. Come lingua predefinita, selezionare **en-us**.
1. Lascia invariato valore del campo **Percorso**.
1. Selezionare **OK**. Viene visualizzato l'elenco delle pagine del sito.

## <a name="enable-jobs-in-retail"></a>Abilitare i processi in Retail

Per abilitare i processi in Retail, effettuare le operazioni seguenti.

1. Accedere all'ambiente (HQ).
1. Utilizzare il menu a sinistra per andare a**Retail \> Richieste di informazioni e report \> Processi batch**.

    Le fasi restanti di questa procedura devono essere completate per ciascuno dei seguenti processi:

    * Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio
    * Disponibilità prodotto
    * P-0001
    * Sincronizza processo di ordini

1. Utilizzare il filtro rapido per cercare il processo per nome.
1. Se lo stato del processo è **Trattenuto**, effettuare le seguenti operazioni:

    1. Selezionare il record.
    1. Nel riquadro azioni, sulla scheda **Processo batch** selezionare **Cambia stato**.
    1. Selezionare **In attesa** e quindi **OK**.

### <a name="run-full-data-synchronization-in-retail"></a>Eseguire la sincronizzazione completa dei dati in Retail

Per eseguire la sincronizzazione completa dei dati in Retail, attenersi alla seguente procedura.

1. Utilizzare il menu a sinistra per andare a **Moduli \> Retail \> Impostazione sedi centrali \> Retail Scheduler \> Database canale**.
1. Il canale**Predefinito** è selezionato nell'elenco a sinistra. Selezionare l'altro canale disponibile. Questo canale è denominato **scXXXXXXXXX**.
1. Selezionare **Sincronizzazione dati completa** nel riquadro azioni.
1. Immettere **9999** come programmazione della distribuzione.
1. Selezionare **OK**.
1. Selezionare **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Verificare le informazioni sulla carta di credito per effettuare acquisti di prova

Per eseguire transazioni di prova nel sito, è possibile utilizzare le seguenti informazioni della carta di credito di prova:

- **Numero carta:** 4111-1111-1111-1111
- **Data di scadenza:** 10/20
- **Codice valore di verifica carta (CVV):** 737

> [!IMPORTANT]
> Non utilizzare mai le informazioni di una carta di credito reale nel sito di prova.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato le fasi di provisioning e configurazione, sei pronto per valutare l'ambiente di anteprima. Utilizzare l'URL dello strumento di gestione del sito di Commerce per accedere all'esperienza di creazione. Utilizzare l'URL dello strumento di gestione del sito di Commerce per accedere all'esperienza del sito dei clienti di vendita al dettaglio.

Per configurare funzionalità facoltative per l'ambiente di anteprima Commerce, vedere [Configurare le funzioni facoltative per un ambiente di anteprima Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di anteprima di Commerce](cpe-overview.md)

[Provisioning di un ambiente di anteprima Commerce](provisioning-guide.md)

[Configurare le funzioni facoltative per un ambiente di anteprima Commerce](cpe-optional-features.md)

[Domande frequenti sull'ambiente di anteprima Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Risorse di guida per Dynamics 365 Retail](../retail/index.md)
