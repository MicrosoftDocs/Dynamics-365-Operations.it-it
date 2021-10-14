---
title: Installare, configurare e aggiornare il portale clienti
description: Questo argomento fornisce dettagli sulle licenze e istruzioni per la configurazione del portale clienti.
author: Henrikan
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b415252ef93987765d8970cde6b45f397136afd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572651"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Installare, configurare e aggiornare il portale clienti

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Requisiti di licenza

Per implementare il portale clienti, è necessario disporre delle seguenti licenze:

- **Portali Power Apps** - Questa licenza è richiesta per ospitare il portale clienti. I portali sono concessi in licenza in base all'utilizzo. Per ulteriori informazioni, consultare [Requisiti di licenza per portali Power Apps](/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Doppia scrittura** - È necessario disporre delle licenze necessarie per abilitare la doppia scrittura per le tabelle Supply Chain Management. Per ulteriori informazioni, vedere i [Requisiti di sistema per la doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Dipendenze da doppia scrittura e portali Power Apps

Il portale clienti dipende dai portali Power Apps e dalla doppia scrittura, come mostrato nella figura seguente.

![Dipendenze del portale clienti.](media/customer-portal-elements.png "Dipendenze del portale clienti")

A differenza di altre funzionalità di Supply Chain Management, il modello di portale clienti risiede nei portali Power Apps. Pertanto, il portale clienti è limitato dalle funzionalità fornite dai portali  Power Apps e dalle tabelle in doppia scrittura.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Configurazione richiesta per abilitare il portale clienti

Dopo aver verificato di disporre delle licenze necessarie, è possibile configurare la doppia scrittura come descritto in [Istruzioni di sincronizzazione iniziale con doppia scrittura](/dynamics365/supply-chain/sales-marketing/enable-entity-map).

Assicurarsi di abilitare i seguenti mapping di tabelle in doppia scrittura:

- Intestazione ordine cliente
- Dettagli ordini cliente
- Conti
- Contatti
- Prodotti

Al termine della configurazione, è possibile eseguire il provisioning del modello di portale clienti.

## <a name="provision-the-customer-portal"></a>Provisioning del portale clienti

Prima di iniziare, assicurarsi di aver già completato la [configurazione richiesta](#required-setup). Quindi seguire questi passaggi per eseguire il provisioning del portale clienti.

1. Andare a [make.powerapps.com](https://make.powerapps.com/).
2. Assicurarsi di utilizzare l'ambiente in cui la doppia scrittura è stata abilitata.
3. Nella scheda **Crea**, scorrere verso il basso fino alla sezione **Inizia da modello** e selezionare il modello denominato **Portale clienti**.
4. Seguire le istruzioni visualizzate.

Una volta completato il provisioning, è possibile accedere al portale clienti nella sezione **App personali** della **Home page**.

> [!NOTE]
> Se la soluzione di doppia scrittura non è installata nell'ambiente in cui si sta lavorando, verrà visualizzato un messaggio di errore e il provisioning del portale clienti non verrà eseguito.

## <a name="update-the-customer-portal"></a>Aggiornare il portale clienti

Ulteriori funzionalità potrebbero essere aggiunte al portale clienti in seguito. Qualsiasi modifica apportata da Microsoft ai componenti della soluzione sottostante apparirà automaticamente nell'ambiente corrente. Tuttavia, il sito Web di cui viene eseguito il provisioning nell'ambiente non rifletterà automaticamente le modifiche apportate ai dati di configurazione. Sarà necessario applicare manualmente tali modifiche ottenendo il codice dal nuovo modello ed eseguendone il merging con il sito Web di cui è stato eseguito il provisioning.

## <a name="additional-resources"></a>Risorse aggiuntive

Per informazioni su come configurare e personalizzare il portale clienti, è necessario consultare la seguente documentazione per le tecnologie sottostanti:

- [Documentazione sui portali Power Apps](/powerapps/maker/portals/overview)
- [Documentazione sulla doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Per gestire efficacemente i portali, è necessario acquisire familiarità con i portali Power Apps e il ciclo di vita di Microsoft Dataverse. Per ulteriori informazioni, vedi le seguenti risorse:

- [Informazioni sul ciclo di vita dei portali](/powerapps/maker/portals/admin/portal-lifecycle)
- [Aggiornare un portale](/powerapps/maker/portals/admin/upgrade-portal)
- [Migrare la configurazione del portale](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Gestione del ciclo di vita delle soluzioni: app Dynamics 365 for Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]