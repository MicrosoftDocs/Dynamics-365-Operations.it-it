---
title: Risolvere i problemi di estensione di Store Commerce
description: Questo articolo spiega come risolvere i problemi di estensione nell'app Microsoft Dynamics 365 Commerce Store Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1a2d6a68b7556d8b4d05529efd90f9e66f0c5925
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269783"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>Risolvere i problemi di estensione di Store Commerce

[!include [banner](../includes/banner.md)]

Questo articolo spiega come risolvere i problemi di estensione nell'app Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="extensions-packages-arent-loaded"></a>I pacchetti di estensioni non vengono caricati

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>I pacchetti di estensioni non vengono visualizzati nella pagina POS \> Impostazioni

I trigger di Commerce Runtime (CRT) potrebbero non essere stati aggiornati per includere il pacchetto di estensioni o non essere stati distribuiti. Per ulteriori informazioni, vedi [Estendibilità e trigger di Commerce runtime (CRT)](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>I pacchetti di estensioni vengono visualizzati nella pagina POS \> Impostazioni, ma il manifesto non è caricato

Verifica che i pacchetti di estensioni esistano nella cartella **C:\\Program Files\\Microsoft Dynamics 365\\10.0\\Store Commerce\\Extensions**. Se i pacchetti esistono, dovrebbe esserci una cartella **POS** che contiene il manifesto.

Se non c'è una cartella **POS** verifica che il progetto Store Commerce faccia riferimento correttamente al progetto di estensione POS. Convalida il percorso di riferimento del progetto e assicurati che esista. 

Nell'illustrazione di esempio seguente, il progetto di installazione ha problemi con il progetto di estensione a cui si fa riferimento.

![Il riferimento al progetto di installazione di Store Commerce non è valido.](media/ReferenceNotValid.png)

Se il riferimento per il progetto di estensione viene aggiunto correttamente, non ci saranno avvisi o problemi di dipendenza nel progetto di installazione, come mostrato nell'illustrazione di esempio seguente.

![Il riferimento al progetto di installazione di Store Commerce è valido.](media/ReferenceValid.png)
