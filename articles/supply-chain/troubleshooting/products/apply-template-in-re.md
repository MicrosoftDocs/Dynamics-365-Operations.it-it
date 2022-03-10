---
title: Impossibile applicare un modello a un prodotto rilasciato
description: Impossibile applicare un modello a un prodotto rilasciato.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 566686b6a86e67c87f75f9f2e397592174d3d749034f18997ca8ce651c2594a2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760396"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>Impossibile applicare un modello per creare un prodotto rilasciato

Numero KB: 4612097

## <a name="symptoms"></a>Sintomi

Quando crei un nuovo prodotto rilasciato utilizzando la finestra di dialogo **Nuovo prodotto rilasciato**, puoi selezionare un modello. Il modello dovrebbe fornire le impostazioni predefinite di molti campi del nuovo prodotto rilasciato. Tuttavia, alcuni o tutti i campi non vengono impostati dopo aver selezionato il modello.

## <a name="cause"></a>Causa

Molte pagine in Microsoft Dynamics 365 Supply Chain Management ti consentono di creare un modello che stabilisce le impostazioni iniziali dei record visualizzati in quelle pagine. Puoi creare uno di questi modelli selezionando **Informazioni sui record** nella scheda **Opzioni** del riquadro Azioni. Tuttavia, i prodotti rilasciati sono molto più complessi della maggior parte degli altri tipi di record. Sebbene sia possibile selezionare **Informazioni sui record** nella pagina **Prodotti rilasciati** per creare un modello e, sebbene sia possibile selezionare quel modello quando si crea un prodotto rilasciato, il modello non fornirà i valori di campo previsti per il nuovo prodotto rilasciato. Pertanto, non puoi utilizzare i modelli "Informazioni sui record" per i prodotti rilasciati. Devi invece creare modelli prodotto dedicati.

## <a name="resolution"></a>Risoluzione

Per creare un modello prodotto, utilizza il menu **Modello** nella scheda **Prodotto** del riquadro Azioni, non il pulsante **Informazioni sui record** nella scheda **Opzioni**.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nel riquadro Azioni, nella scheda **Prodotto**, nel gruppo **Nuovo**, seleziona **Modello**, quindi seleziona **Crea un modello personale** o **Crea modello condiviso**, come appropriato.
