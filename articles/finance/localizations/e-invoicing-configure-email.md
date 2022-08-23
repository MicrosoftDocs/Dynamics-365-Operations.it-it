---
title: Configurare un canale e-mail
description: Questo articolo spiega come configurare un canale e-mail per ricevere fatture elettroniche.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 19339cbcc59e93289609690363b0dd9195a66f6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279872"
---
# <a name="configure-an-email-channel"></a>Configurare un canale e-mail

[!include [banner](../includes/banner.md)]

Se la funzionalità di Fatturazione elettronica creata importa fatture fornitore elettroniche da file allegati ricevuti tramite posta elettronica, è consigliabile configurare un canale di account e-mail.

1. In Regulatory Configuration Service (RCS), seleziona la funzionalità di fatturazione elettronica che hai creato. Assicurati di selezionare la versione con lo stato **Bozza**.
2. Nella scheda **Configurazioni**, seleziona **Aggiungi**.
3. Nella finestra di dialogo a discesa **Crea configurazione funzionalità**, nel gruppo di campi **Nuovo**, selezionare l'opzione **Configurazione personalizzata**.
4. Nel gruppo di campi **Tipo di configurazione**, seleziona l'opzione **Canale dati**.
5. Nel campo **Seleziona canale dati**, immetti **Posta elettronica in arrivo**.
6. Selezionare **Crea**.
7. Seleziona la riga che hai creato e seleziona **Modifica**.
8. Nella scheda **Canale dati**, nella sezione **Parametri**, imposta i seguenti campi obbligatori.

    | Campo                | Description |
    |----------------------|-------------|
    | Canale dati         | Immetti un nome univoco per identificare il canale dati. Il nome può contenere un massimo di 10 caratteri. Verrà fatto riferimento nelle regole di applicabilità e nelle applicazioni connesse durante il processo di comunicazione. |
    | Indirizzo server       | Immetti l'indirizzo del server del provider dell'account di posta elettronica. Ad esempio, l'indirizzo del server per il provider `https://outlook.live.com` è imap-mail.outlook.com. |
    | Porta server          | Immetti il numero della porta utilizzata dal provider dell'account e-mail. Ad esempio, la porta del server per il provider `https://outlook.live.com` è 993. |
    | Segreto nome utente     | Immetti il nome del segreto del Microsoft Azure Key Vault che contiene l'ID dell'account utente di posta elettronica. Questo segreto deve essere creato in Key Vault e configurato nell'ambiente del servizio. |
    | Segreto password utente | Immetti il nome del segreto del Key Vault che contiene la password dell'account utente di posta elettronica. |
    | Timeout              | Il limite di tempo massimo, in millisecondi (ms), che il sistema deve attendere per una risposta. Il valore predefinito è pari a 10.000 ms (10 secondi). |
    | Cartella principale          | Specifica l'origine dell'importazione dell'e-mail o la cartella da cui il servizio deve elaborare i messaggi e-mail. |
    | Cartella di archiviazione       | Specifica la cartella in cui devono essere archiviati i messaggi e-mail elaborati. Se non specifichi questa cartella, il sistema la creerà automaticamente. |
    | Cartella di errore         | Specifica la cartella in cui il sistema deve spostare i messaggi e-mail se l'elaborazione non riesce. Se non specifichi questa cartella, il sistema la creerà automaticamente. |
    | Dimensione massima messaggio     | Immetti la dimensione massima, in byte, di un singolo messaggio che viene elaborato. Il valore predefinito è 20.000,000 byte. |
    | Numero massimo messaggi   | Immetti il numero massimo di messaggi da elaborare per una singola azione. Se non vuoi limitare il numero di messaggi, imposta il valore su **0** (zero). |
    | Filtro Da          | Immetti una stringa da filtrare per indirizzo del mittente. Verranno elaborati solo i messaggi e-mail in cui l'indirizzo del mittente corrisponde al filtro. Questo campo è facoltativo. Per specificare più indirizzi di mittente, utilizza i punti e virgola (;) come separatori. |
    | Filtro oggetto       | Immetti una stringa da filtrare per oggetto. Verranno elaborati solo i messaggi e-mail in cui l'oggetto corrisponde al filtro. Questo campo è facoltativo. Una semplice maschera come **\*smth\*.est** è supportata, dove ogni asterisco (\*) rappresenta zero o più occorrenze di qualsiasi carattere. |
    | Filtro data          | Specifica una data per definire la durata massima, in giorni, dei messaggi elaborati. Questo campo è facoltativo. Il valore predefinito è 30 giorni. |
    | Modalità di elaborazione      | <p>Seleziona una delle seguenti opzioni per specificare se tutti gli allegati di un messaggio e-mail possono essere elaborati insieme o se ogni allegato deve essere elaborato separatamente:</p><ul><li><b>Per allegato</b> – Verrà creato un nuovo documento elettronico per ogni allegato nel messaggio e-mail. Ad esempio, se un messaggio e-mail include più file che contengono dati di una fattura elettronica, ogni file sarà considerato una nuova fattura elettronica nel sistema.</li><li><b>Per e-mail</b> – Un allegato sarà considerato un allegato di base e una fattura elettronica verrà creata nel sistema. Altri allegati possono essere utilizzati come file di supporto.</li></ul> |

9. Nella sezione **Filtro allegati**, aggiungi le informazioni sul filtro dei file. Vengono elaborati solo gli allegati che soddisfano il filtro definito. Per esempio, **\*.xml** filtrerà gli allegati con estensione del nome file .xml. Il nome dell'allegato viene utilizzato in Dynamics 365 Finance o Dynamics 365 Supply Chain Management durante la configurazione.

    - Se imposti il campo **Modalità di elaborazione** su **Per e-mail** nel passaggio precedente, puoi aggiungere più filtri qui. Il nome identificherà il documento specifico.
    - Se imposti il campo **Modalità di elaborazione** su **Per allegato**, puoi aggiungere un solo filtro.

10. Nella scheda **Regole di applicabilità**, esaminare e aggiornare i criteri in base alle necessità. Il valore del campo **Canale** deve essere uguale al valore che hai inserito nel campo **Canale dati** nel passaggio 8.
11. Selezionare **Salva**, quindi chiudere la pagina.
