---
title: Configurare la gestione delle spese
description: "Questo articolo descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di configurare la gestione delle spese in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 198e37258f45966b92d963cc0c233d4790ca049e
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="configure-expense-management"></a>Configurare la gestione delle spese

[!include[banner](../includes/banner.md)]


Questo argomento descrive ciò che si deve considerare e le decisioni che è necessario prendere durante il processo di pianificazione prima di configurare la gestione delle spese in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. In Gestione spese, è possibile archiviare informazioni su metodi di pagamento, richieste di viaggio, note spese, criteri e altro ancora.

Poiché molte decisioni che prese quando si pianifica la configurazione per la gestione delle spese si basano sulla struttura finanziaria e gerarchica dell'organizzazione, è necessario fare riferimento ai documenti di pianificazione per le aree.

## <a name="intercompany-expenses"></a>Spese interaziendali

Quando si abilitano le spese interaziendali, si consente alle persone giuridiche e ai dipendenti di effettuare spese per conto di un'altra persona giuridica, e riscuotere il pagamento dalla persona giuridica di impiego all'interno dell'organizzazione. Ad esempio, un dipendente nella persona giuridica A completa un progetto per la persona giuridica B e il progetto comporta spese di viaggio. Se le spese interaziendali sono abilitate, il dipendente può quindi creare una nota spese che registrerà le spese per la persona giuridica B e le spese devono quindi essere pagate dalla persona giuridica A. Se l'organizzazione non ha molteplici persone giuridiche, non sarà necessario abilitare le spese interaziendali.

**Decisione:** Si desidera abilitare le spese interaziendali?

## <a name="financial-management"></a>Gestione finanziaria

La gestione delle spese è strettamente integrata alla gestione finanziaria dell'organizzazione. Gran parte della configurazione per la gestione delle spese verrà basata sulle decisioni prese riguardo le finanze dell'organizzazione. Nelle sezioni seguenti vengono descritte le varie aree che richiedono pianificazione e decisioni, in base alle decisioni finanziarie dell'organizzazione e alle indicazioni del team di responsabili.

### <a name="per-diems"></a>Trasferte giornaliere

È necessario definire le trasferte giornaliere del dipendente che l'organizzazione garantisce. Poiché le trasferte giornaliere sono in genere utilizzate per coprire le spese quali vitto, alloggio e altre spese extra, è possibile creare regole per le indennità di trasferta giornaliera che l'organizzazione offre. Le tariffe giornaliere infatti possono essere impostate in base al periodo dell'anno, alla destinazione di viaggio o a entrambi gli elementi. Quando si definisce una regola per le trasferte giornaliere, è possibile specificare che verrà trattenuta una percentuale della tariffa prevista se il lavoratore usufruisce gratuitamente di pasti o servizi. È anche possibile definire livelli di tariffe giornaliere per impostare un numero minimo e massimo di ore a cui la tariffa giornaliera può essere applicata per una trasferta di un lavoratore.

**Decisioni:**

- Regole relative alla trasferta giornaliera predefinite per il primo e l'ultimo giorno:

    - Qual è il numero minimo di ore che un dipendente può richiedere per un giorno e ricevere comunque una trasferta giornaliera?
    - Esiste una riduzione dell'importo che viene offerto per il vitto per il primo e l'ultimo giorno? Se sì, qual è la percentuale di riduzione?
    - Esiste una riduzione dell'importo che viene offerto per l'alloggio per il primo e l'ultimo giorno? Se sì, qual è la percentuale di riduzione?
    - Esiste una riduzione dell'importo che viene offerto per le altre spese sostenute il primo e l'ultimo giorno? Se sì, qual è la percentuale di riduzione?

- Regole relative alla trasferta giornaliera predefinite:

    - Esiste una riduzione percentuale di indennità di trasferta giornaliera per ogni pasto se, ad esempio, il pasto è extra? Se sì, qual è la relativa percentuale per ogni pasto?
    - La riduzione per vitto viene calcolata al giorno, per viaggio, o per numero di pasti al giorno?
    - Gli importi di trasferta giornaliera devono essere arrotondati normalmente o per eccesso?
    - Gli importi di trasferta giornaliera vengono calcolati su un periodo di 24 ore o su un giorno di calendario?

- Regole relative alla trasferta giornaliera in base all'ubicazione:

    - Le tariffe giornaliere variano a seconda dell'ubicazione? Quali ubicazioni sono incluse?
    - Se le tariffe giornalierie variano in base all'ubicazione, per ciascuna ubicazione, quale importo percentuale viene fornito per i seguenti tipi di spese:

        - Vitto
        - Hotel
        - Altre spese

### <a name="expense-management-journals-and-accounts"></a>Conti e giornali di registrazione di gestione spese

La gestione delle spese richiede che vengano utilizzati più giornali di registrazione e conti. È possibile, ad esempio, decidere se lo stesso conto viene utilizzato per gli anticipi contanti e le controversie su carta di credito.

**Decisioni:**

- In quale giornale contabile vengono registrate le note spese approvate?
- Quale conto viene utilizzato per gli anticipi contanti?
- Gli anticipi contanti devono essere registrati immediatamente?

### <a name="payment-methods"></a>Metodi di pagamento

Quando si consente ai dipendenti di sostenere spese per conto dell'azienda, è necessario definire i metodi di pagamento che ai dipendenti è concesso di utilizzare. Ad esempio, è possibile consentire ai dipendenti di utilizzare contanti o una carta di credito aziendale. È inoltre possibile consentire ai dipendenti di utilizzare carte di credito personali e poi rimborsare i dipendenti. È necessario prendere le decisioni seguenti per ciascun metodo di pagamento che si consente.

**Decisioni:**

- Quali metodi di pagamento sono consentiti?
- Chi possiede le spese per il metodo di pagamento?
- Esiste un tipo di conto di contropartita? Se sì, qual è?
- Se è presente un conto di contropartita, qual è il conto?
- Se il metodo di pagamento è una carta di credito, il metodo di pagamento deve essere utilizzato solo con le transazioni importate?

### <a name="expense-categories-and-shared-categories"></a>Categorie di spesa e condivise

Quando i dipendenti creano una nota spese, ogni spesa registrata deve essere associata a una categoria di spesa. Le categorie di spesa derivano dalle categorie condivise che possono essere condivise per tutte le persone giuridiche dell'organizzazione. Tali categorie possono inoltre essere condivise in Gestione progetti e contabilità, in base al modo in cui l'organizzazione è definita. In base alla definizione dell'organizzazione e alle istruzioni del team di implementazione, determinare se le categorie utilizzate in Gestione spese saranno utilizzate solo in Gestione spese o se devono essere condivise tra Gestione progetti e contabilità e Gestione spese. Si noti che le categorie possono essere condivise tra progetto e spesa o progetto e produzione, ma non tra spesa e produzione. È necessario prendere le seguenti decisioni per ciascuna categoria di spesa.

**Decisioni:**

- Qual è la categoria di spesa? Le categorie di esempio includono voli, hotel o chilometraggio.
- La categoria di spesa può essere utilizzata anche in Gestione progetti e contabilità?
- Qual è il tipo di spesa?
- Qual è il metodo di pagamento predefinito per la categoria di spesa?
- Le spese nella categoria di spesa devono essere dettagliate?
- Qual è il conto predefinito principale per la categoria di spesa?
- Qual è la fascia IVA articoli predefinita per la categoria di spesa?
- Sono consentiti metodi di pagamento aggiuntivi per la categoria di spesa? Se sono consentiti ulteriori metodi di pagamento, quali sono?
- Sono presenti sottocategorie nella categoria di spesa? Se lo sono, è necessario prendere anche le decisioni seguenti:

    - Le sottocategorie sono escluse dal recupero imposte?
    - Qual è la fascia IVA articoli relativa alle sottocategorie?

Se la categoria di spesa viene utilizzata anche in Gestione progetti e contabilità, rispondere alle domande rimanenti. In caso contrario, passare alla sezione successiva.

- Quali conti costi verranno utilizzati per le spese seguenti?

    - Costo
    - Allocazione retribuzioni
    - WIP - Valore di costo
    - Costo - articolo
    - WIP - Valore di costo - Articolo
    - Ratei e risconti passivi
    - WIP - Ratei e risconti passivi

- Quali conti relativi ai ricavi verranno utilizzati per quanto segue?

    - Ricavi fatturati
    - Ricavi sospesi - Valore netto di vendita
    - WIP - Valore netto di vendita
    - Ricavi sospesi - produzione
    - WIP - produzione
    - Ricavi sospesi - profitto
    - WIP - profitto
    - Ricavi sospesi - Sottoscrizione
    - WIP - Sottoscrizione

### <a name="taxes"></a>Imposte

Per le imposte di spesa, è necessario determinare cosa è incluso o abilitato nelle note spese.

**Decisioni:**

- L'IVA è inclusa negli importi relativi alle spese?
- Il recupero imposte deve essere abilitato sulle spese?

    > [!NOTE]
    > Se durante la pianificazione della contabilità generale, si è deciso di applicare l'IVA U.S.A. e utilizzare le regole di tassazione, non è possibile abilitare il recupero imposte sulle spese. Per applicare l'IVA U.S.A. e utilizzare le regole di tassazione, impostare l'opzione **Applica regole di tassazione IVA** su **Sì**.

## <a name="policies"></a>Criteri

Creando criteri delle note spese, è possibile risparmiare tempo e denaro quando i dipendenti sostengono spese per conto dell'organizzazione. Grazie ai criteri i dipendenti non sforano il budget, forniscono tutte le informazioni necessarie e spendono denaro solo se necessario. È necessario prendere le seguenti decisioni per tutti i criteri delle note spese e tutti i criteri di approvazione della note spese creati.

**Decisioni:**

- Qual è il nome dei criteri?
- A cosa servono i criteri di spesa?
- Se in precedenza è stato deciso di abilitare le spese interaziendali, a quali società dell'organizzazione si applicheranno i criteri?
- Quando i criteri diventano effettivi?
- Quando i criteri scadono?
- Qual è la regola dei criteri?
- Qual è il risultato della regola dei criteri?

