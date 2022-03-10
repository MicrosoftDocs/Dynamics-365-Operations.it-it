---
title: Configurare buffer e livelli di scorte
description: Questo argomento spiega come configurare i buffer e i livelli di scorte che determinano la messaggistica sulla disponibilità delle scorte nei siti Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 842389811169f785235de7ac7d9a49ab903f99ddf7d43f139aba0873a2577d72
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727535"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Configurare buffer scorte e livelli scorte

[!include [banner](includes/banner.md)]

Questo argomento spiega come configurare i buffer e i livelli di scorte che determinano la messaggistica sulla disponibilità delle scorte nei siti Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce Headquarters include dati sulle scorte e vari canali come applicazioni POS, vetrine di e-commerce e altre applicazioni integrate personalizzate che eseguono il pull e push delle scorte in modo asincrono. Pertanto, i valori sulle scorte disponibili ottenuti tramite la pagina delle scorte disponibili in Commerce Headquarters, l'interfaccia utente POS e le API di disponibilità delle scorte di e-Commerce non sono sempre accurate al 100% in tempo reale.

Anziché mostrare i valori sulle scorte effettivi nelle vetrine di e-commerce, molti rivenditori preferiscono solo mostrare la messaggistica sullo stato di disponibilità delle scorte (ad esempio, "Disponibile" o "Esaurito") per informare i clienti se un articolo è disponibile per l'acquisto o potenzialmente esaurito. Per questo approccio, i buffer e i livelli di scorte che determinano la messaggistica di disponibilità delle scorte devono essere resi disponibili e configurati.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Prerequisito: attivare la funzionalità dei buffer e dei livelli di scorte

La funzionalità per i buffer e i livelli di scorte viene controllata mediante la pagina Gestione funzionalità di Commerce Headquarters. Per attivare la funzionalità, effettuare le seguenti operazioni.

1. Andare a **Amministrazione sistema** \> **Aree di lavoro** \> **Gestione funzionalità**.
1. Cercare la funzionalità **Abilita buffer e livelli di scorte**, selezionare la relativa riga, quindi selezionare **Abilita ora**.

Dopo aver attivato la funzionalità, è possibile trovare i livelli di scorte in **Retail e Commerce \> Gestione articoli**.

## <a name="create-and-configure-an-inventory-level-profile"></a>Creare e configura un profilo di livello di scorte

Un *profilo di livello di scorte* determina se una determinata quantità di prodotto è considerata disponibile, esaurita o in qualche altro stato personalizzato. È possibile creare e configurare più profili di livello di scorte per persona giuridica. Ogni profilo è costituito da un insieme di livelli di scorte e ogni livello è definito da un *intervallo*, un *codice* e un'*etichetta*.

- **Intervallo** - Ogni intervallo è definito da una *quantità iniziale* e una *quantità finale*. Un valore di quantità rientra in un intervallo se è superiore alla quantità iniziale di tale intervallo e non superiore alla quantità finale.
- **Codice** - Un codice è un'abbreviazione interna che rappresenta il livello. I clienti che si integrano direttamente con le API di scorte possono utilizzare codici per creare una logica aggiuntiva per un determinato livello di scorte. Ad esempio, possono disattivare la capacità di acquisto di un prodotto quando il relativo codice di livello di scorte è **ESA** (Esaurito).
- **Etichetta** - Un'etichetta è un messaggio significativo per il cliente che trasmette un livello di scorte ai clienti in un sito di e-commerce.

### <a name="create-an-inventory-level-profile"></a>Creare un profilo di livello di scorte

Per creare un profilo di livello di scorte, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce** \> **Gestione articoli** \> **Livelli scorte**.
1. Nel riquadro azioni selezionare **Nuovo**, quindi immettere valori nei campi **ID profilo** e **Descrizione**.
1. Nella Scheda dettaglio **Intervalli**, selezionare **Aggiungi** per aggiungere un nuovo livello, quindi inserire i valori nelle colonne **Quantità iniziale**, **Quantità finale**, **Codice** e **Etichetta** per quel livello. Ripetere questo passaggio per aggiungere ulteriori livelli. Se necessario, è possibile modificare i valori nella griglia dei dati oppure selezionare **Elimina** per rimuovere un livello.
1. Nel riquadro azioni selezionare **Salva**.

Quando viene creato un nuovo profilo, vengono automaticamente inizializzati due livelli di scorte:

- **ESA** - Il livello "esaurito" dove il limite inferiore dell'intervallo è infinito negativo. La quantità iniziale e il codice non possono essere modificati per questo livello.
- **DISP** - Il livello "disponibile", in cui il limite superiore dell'intervallo è infinito. La quantità finale e il codice non possono essere modificati per questo livello.

> [!NOTE]
> Non ci possono essere spazi vuoti o sovrapposizioni tra gli intervalli nella definizione del profilo.

È possibile utilizzare il pulsante **Traduzioni** nel riquadro azioni per configurare le stringhe localizzate per il messaggio dell'etichetta. È quindi necessario eseguire il processo di programmazione della distribuzione **1110** (**Configurazione globale**) per sincronizzare le stringhe localizzate con i canali.

### <a name="configure-an-inventory-level-profile"></a>Configurare un profilo di livello di scorte

È possibile configurare un profilo di livello di scorte a livello di categoria di prodotto o a livello di singolo prodotto. Quando viene configurato un profilo di livello di scorte per un prodotto, il livello di scorte viene determinato in base agli intervalli definiti nel profilo collegato. In caso contrario, il livello di scorte "disponibile" o "esaurito" viene determinato in base al fatto che il prodotto abbia o meno una quantità disponibile positiva.

Per configurare un profilo di livello di scorte per una categoria, attenersi alla seguente procedura.

1. Selezionare **Retail e Commerce** \> **Prodotti e categorie** \> **Gerarchia di prodotti di Commerce**.
1. Selezionare la categoria per la quale configurare un profilo di livello di scorte.
1. Nella Scheda dettaglio **Proprietà di vendita prodotto**, selezionare una persona giuridica.
1. Nella sezione **Scorte e-commerce**, nel campo **Profilo di livello di scorte**, selezionare uno dei profili di livello di scorte predefiniti.

È possibile usare il pulsante **Aggiorna prodotti** nel riquadro azioni per propagare il valore del profilo a livello di categoria ai prodotti sottostanti della categoria. Per ulteriori informazioni, vedere [Gestire le categorie di prodotti e i prodotti](category-management-product-creation.md).

Per configurare un profilo di livello di scorte per un prodotto rilasciato, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce** \> **Prodotti e categorie** \> **Prodotti relasciati per categorie**.
1. Selezionare un prodotto, quindi aprire la pagina dei dettagli del prodotto.
1. Nella Scheda dettagli **Vendita** nella sezione **Scorte e-commerce**, nel campo **Profilo di livello di scorte**, selezionare uno dei profili di livello di scorte predefiniti.

Quando viene creato un nuovo prodotto, il campo **Profilo di livello di corte**, come molti altri attributi a livello di prodotto, verrà impostato sul valore configurato per la categoria a cui è associato il prodotto.

> [!NOTE]
> Il profilo di livello di scorte è un attributo specifico della persona giuridica. Per la stessa categoria o prodotto, il valore del profilo di livello di scorte può variare tra le persone giuridiche.

Per sincronizzare le configurazioni dei profili di livello di scorte con i canali, attenersi alla seguente procedura.

1. Selezionare **Retail e Commerce** \> **Vendita al dettaglio e commercio IT** \> **Programmazione della distribuzione**.
1. Eseguire la programmazione della distribuzione **1040** (**Prodotto**).

## <a name="configure-an-inventory-buffer"></a>Configurare un buffer di scorte

Il *buffer di scorte* è un valore definito dall'utente che sottrae la quantità aggiuntiva di un articolo dalla quantità originale per calcolare la quantità stimata. Questa quantità stimata offre ai rivenditori un buffer di sicurezza di modo che non vendano un prodotto oltre la disponibilità effettiva dello stesso. È possibile configurare il buffer di scorte a livello di categoria di prodotto o a livello di singolo prodotto. Se non viene specificato un buffer di scorte, viene utilizzato il valore predefinito **0** (zero).

Per configurare il buffer di scorte per una categoria, attenersi alla seguente procedura.

1. Selezionare **Retail e Commerce** \> **Prodotti e categorie** \> **Gerarchia di prodotti di Commerce**.
1. Selezionare la categoria per la quale configurare il buffer di scorte.
1. Nella Scheda dettaglio **Proprietà di vendita prodotto**, selezionare una persona giuridica.
1. Nella sezione **Scorte e-commerce**, nel campo **Buffer di scorte**, immettere un valore positivo.

È possibile usare il pulsante **Aggiorna prodotti** nel riquadro azioni per propagare il valore del buffer a livello di categoria ai prodotti sottostanti della categoria. Per ulteriori informazioni, vedere [Gestire le categorie di prodotti e i prodotti](category-management-product-creation.md).

Per configurare il buffer di scorte per un prodotto rilasciato, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce** \> **Prodotti e categorie** \> **Prodotti relasciati per categorie**.
1. Selezionare un prodotto, quindi aprire la pagina dei dettagli del prodotto.
1. Nella Scheda dettagli **Vendita**, nella sezione **Scorte e-commerce**, nel campo **Buffer di scorte**, immettere un valore positivo.

Quando viene creato un nuovo prodotto, il campo **Buffer di corte** verrà impostato sul valore configurato per la categoria a cui è associato il prodotto.

> [!NOTE]
> Se il profilo di buffer di scorte e quello di livello di scorte sono configurati per un prodotto, la quantità stimata del prodotto (ovvero la quantità originale meno il valore del buffer) verrà utilizzata per il calcolo dell'intervallo per determinare il livello di scorte.

Per sincronizzare le configurazioni dei buffer di scorte con i canali, attenersi alla seguente procedura.

1. Selezionare **Retail e Commerce** \> **Vendita al dettaglio e commercio IT** \> **Programmazione della distribuzione**.
1. Eseguire la programmazione della distribuzione **1040** (**Prodotto**).

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>Utilizzare i buffer e i livelli di scorte nello scenario di e-commerce

Creazione di siti Web di Commerce utilizza le funzionalità di buffer di scorte e livelli di scorte in Commerce Headquarters per determinare la messaggistica di disponibilità delle scorte sui siti di e-Commerce. Per ulteriori informazioni, vedere [Applicare impostazioni relative alle scorte](inventory-settings.md).

In alternativa, in caso di integrazione con una soluzione di e-commerce di terze parti, è possibile utilizzare le API **GetEstimatedAvailability** e **GetEstimatedProductWarehouseAvailability** per mostrare la disponibilità delle scorte per un prodotto nello scenario di e-commerce. Per ulteriori informazioni su queste API, vedere [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md).

L'introduzione dei buffer e dei livelli di scorte consente a queste API di restituire i codici di livello di scorte e messaggi di etichetta determinati in base ai valori fisici disponibili e totali disponibili. Le API possono essere configurate ulteriormente per determinare se la quantità di scorte viene restituita insieme al messaggio e se la quantità disponibile viene ridotta del valore del buffer di scorte.

Per configurare la risposta delle API di disponibilità dei prodotti, attenersi alla seguente procedura.

1. Accedere a **Retail e Commerce** \> **Impostazione sedi centrali** \> **Parametri** \> **Parametri di commercio**.
1. Nel campo **API di disponibilità prodotto per e-commerce** della scheda **Scorte** nella sezione **Store inventory**, selezionare un valore.
1. Per applicare le impostazioni ai canali, eseguire il processo di programmazione della distribuzione **1110** (**Configurazione globale**).

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire le categorie di prodotti e i prodotti](category-management-product-creation.md)

[Applicare impostazioni relative alle scorte](inventory-settings.md)

[Calcolare la disponibilità scorte per i canali di vendita al dettaglio](calculated-inventory-retail-channels.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
