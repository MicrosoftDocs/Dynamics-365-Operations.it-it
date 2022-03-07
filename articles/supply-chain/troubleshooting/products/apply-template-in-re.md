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
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026636"
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
