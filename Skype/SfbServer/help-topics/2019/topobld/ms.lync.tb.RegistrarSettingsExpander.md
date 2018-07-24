---
title: Expansor de configurações de registrador
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: Resiliência oferece alta disponibilidade e recuperação de desastres para o pool de registrador. Fornecendo um registrador de backup em caso de falha do registrador principal, o backup registrador possa assumir o controle para o registro com falha, permitindo que os usuários se conectem e se comunicar. Os usuários podem potencialmente experimentar funcionalidade reduzida, dependendo de qual sistemas falharam com o registrador principal.
ms.openlocfilehash: ff8193ced1f731812cdd4d4095013d1a7cf72cee
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21067535"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="e9077-105">Expansor de configurações de registrador</span><span class="sxs-lookup"><span data-stu-id="e9077-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="e9077-106">Resiliência oferece alta disponibilidade e recuperação de desastres para o pool de registrador.</span><span class="sxs-lookup"><span data-stu-id="e9077-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="e9077-107">Fornecendo um registrador de backup em caso de falha do registrador principal, o backup registrador possa assumir o controle para o registro com falha, permitindo que os usuários se conectem e se comunicar.</span><span class="sxs-lookup"><span data-stu-id="e9077-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="e9077-108">Os usuários podem potencialmente experimentar funcionalidade reduzida, dependendo de qual sistemas falharam com o registrador principal.</span><span class="sxs-lookup"><span data-stu-id="e9077-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="e9077-109">Na seção **resiliência** da caixa de diálogo **Editar propriedades** para o aparelho de filial persistente ou servidor de filial persistente, você pode alterar as configurações a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9077-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="e9077-110">**Serviço de usuário associados e o pool de registradores de backup** Na lista suspensa, selecione o pool de Front End do Enterprise Edition ou Standard Edition servidor Front-End que deve agir como o registrador de backup para o aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="e9077-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="e9077-111">**Habilitar o Failover e Failback** Selecione esta configuração para permitir a detecção automática de uma falha registrador e a determinação automática que o registro primário estiver fazer backup e pronto para continuar o processo de registrador.</span><span class="sxs-lookup"><span data-stu-id="e9077-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="e9077-112">**Intervalo de detecção de falha (s)** Digite o número de segundos que deverão decorrer antes de ser determinado que a principal registrador falhou.</span><span class="sxs-lookup"><span data-stu-id="e9077-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="e9077-113">O valor padrão é de 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="e9077-113">The default value is 120 seconds.</span></span> <span data-ttu-id="e9077-114">Este campo é obrigatório se você selecionar **Habilitar o Failover e Failback**.</span><span class="sxs-lookup"><span data-stu-id="e9077-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="e9077-115">**Intervalo de detecção de fallback (s)** Digite o número de segundos que deverão decorrer antes que o registrador principal é feito o backup for determinado.</span><span class="sxs-lookup"><span data-stu-id="e9077-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="e9077-116">O valor padrão é 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="e9077-116">The default value is 240 seconds.</span></span> <span data-ttu-id="e9077-117">Este campo é obrigatório se você selecionar **Habilitar o Failover e failback**.</span><span class="sxs-lookup"><span data-stu-id="e9077-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e9077-118">Quando você definir o intervalo de detecção de falha e o intervalo de detecção de fallback, ser cuidado para não inserir um intervalo que fará com que o failover e failback para ocorrer se o registrador não responder por um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="e9077-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="e9077-119">É possível que o registrador principal pode não responder por curtos períodos de tempo baseado no carregamento do pool ou servidores.</span><span class="sxs-lookup"><span data-stu-id="e9077-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

