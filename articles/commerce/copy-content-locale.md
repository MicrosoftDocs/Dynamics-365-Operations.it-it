---
title: Copiare il contenuto in un'altra impostazione locale
description: Questo articolo descrive come copiare il contenuto esistente in un'altra impostazione locale all'interno di un sito nel generatore di siti di Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: bcfa3c7cb2ea8018422803d85df6b6761b8d1145
ms.sourcegitcommit: d719d0a549aecac231fad0abb42250eab9dd0ded
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2022
ms.locfileid: "9126451"
---
# <a name="copy-content-to-another-locale"></a>Copiare il contenuto in un'altra impostazione locale

[!include[banner](../includes/banner.md)]

Questo articolo descrive come copiare il contenuto esistente in un'altra impostazione locale all'interno di un sito nel generatore di siti di Microsoft Dynamics 365 Commerce.

Quando crei dei contenuti nel generatore di siti di Commerce, questo è sempre associato a un identificatore delle impostazioni locali, ad esempio "en-us". Puoi copiare le singole pagine e i singoli cespiti in una diversa impostazione locale all'interno dello stesso sito di e-commerce commutando l'impostazione locale quando modifichi un elemento di contenuto, per poi creare una nuova variante dell'elemento. In alcuni casi, ad esempio quando stai avviando una nuova impostazione locale nella tua vetrina, potrebbe essere utile duplicare tutti gli elementi di contenuto nell'impostazione locale esistente nella nuova impostazione locale. Se la nuova impostazione locale ha la stessa lingua di base di una delle impostazioni locali esistenti, puoi usare l'impostazione locale esistente come impostazione di origine per l'operazione di copia dell'impostazione locale. (Ad esempio, le impostazioni locali "en-us" e "en-au" usano entrambi la lingua inglese.) Ciò permette di ridurre le attività richieste per localizzare il contenuto nella nuova impostazione locale.

Le procedure di seguito illustrano come aggiungere una nuova impostazione locale a un canale esistente, copiare tutti gli elementi di contenuto da una impostazione locale esistente a una nuova impostazione locale e monitorare lo stato di un'operazione di copia di un'impostazione locale.

## <a name="add-a-new-locale"></a>Aggiungere una nuova impostazione locale

Per aggiungere una nuova impostazione locale nel generatore di siti Web di Commerce, segui questi passaggi.

1. Nel generatore di siti, accedi al sito.
1. Nel riquadro di spostamento a sinistra, seleziona **Impostazioni sito**, quindi seleziona **Canali**.
1. In **Canale**, seleziona il canale cui aggiungere la nuova impostazione locale.
1. Nella finestra di dialogo Canale visualizzata a destra, seleziona **Aggiungi impostazione locale**.
1. Nella finestra di dialogo **Aggiungi impostazione locale**, nel campo **Impostazione locale da supportare**, seleziona un'impostazione locale.
1. Verifica che il valore **Dominio** sia corretto.
1. In **Percorso**, immetti un percorso URL univoco (ad esempio, **en-us** o **english-us**).
1. Seleziona **OK**.
1. Chiudi la finestra di dialogo del canale.
1. In **Canale**, verifica che la nuova impostazione locale sia elencata accanto al canale corretto.
1. Seleziona **Salva e pubblica**.

> [!NOTE]
> Prima che la nuova impostazione locale possa essere configurata nel generatore di siti, deve essere aggiunta al canale punto vendita online associato in Commerce headquarters.

## <a name="copy-all-content-items-to-a-new-locale"></a>Copiare tutti gli elementi di contenuto in una nuova impostazione locale

Per copiare tutti gli elementi di contenuto in una nuova impostazione locale nel generatore di siti Web di Commerce, segui questi passaggi.

1. Nel generatore di siti, accedi al sito.
1. Nel riquadro di spostamento a sinistra, seleziona **Impostazioni sito**, quindi seleziona **Canali**.
1. Nella barra dei comandi, seleziona **Crea copia impostazione locale da**.
1. Nella finestra di dialogo **Crea copia impostazione locale** visualizzata a destra, in **Origine sito**, verifica che sia selezionato il sito corretto.
1. Nel campo **Canale di origine** seleziona il canale di origine.
1. Nel campo **Canale di destinazione** seleziona lo stesso canale di origine.
1. Nel campo **Impostazione locale di origine** seleziona l'impostazione locale di origine.
1. Nel campo **Impostazione locale di destinazione** seleziona la nuova impostazione locale.
1. Seleziona **Copia impostazione locale**. Una notifica conferma l'inizio dell'operazione di copia dell'impostazione locale.

> [!NOTE]
> Puoi anche copiare il contenuto tra canali diversi.

## <a name="monitor-the-status-of-the-locale-copy"></a>Monitorare lo stato della copia locale

Per monitorare lo stato di un'operazione di copia dell'impostazione locale, segui questi passaggi.

1. Nel generatore di siti, accedi al sito.
1. Nel riquadro di spostamento a sinistra, seleziona **Impostazioni sito**, quindi seleziona **Processi**.
1. In **processi correnti**, seleziona il processo da monitorare. I dettagli del processo vengono visualizzati nella finestra di dialogo visualizzata a destra.
