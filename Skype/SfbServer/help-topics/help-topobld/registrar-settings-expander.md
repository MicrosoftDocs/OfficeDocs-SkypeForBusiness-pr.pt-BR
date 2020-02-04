---
title: Expansor de configurações do Registrador Avançado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Resiliência fornece alta disponibilidade e recuperação de desastres para o pool do registrador. Ao fornecer um registrador de backup em caso de falha do registrador principal, o registrador de backup pode assumir o registro com falha, permitindo que os usuários façam logon e se comuniquem. Os usuários podem experimentar recursos reduzidos, dependendo de quais sistemas falharam com o registrador principal.
ms.openlocfilehash: bac382486b45acbb2e25d3be26d23ea67f1aa15b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696726"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="8d9c2-105">Expansor de configurações do Registrador Avançado</span><span class="sxs-lookup"><span data-stu-id="8d9c2-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="8d9c2-106">Resiliência fornece alta disponibilidade e recuperação de desastres para o pool do registrador.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="8d9c2-107">Ao fornecer um registrador de backup em caso de falha do registrador principal, o registrador de backup pode assumir o registro com falha, permitindo que os usuários façam logon e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="8d9c2-108">Os usuários podem experimentar recursos reduzidos, dependendo de quais sistemas falharam com o registrador principal.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="8d9c2-109">Na seção **resiliência** da caixa de diálogo **Editar propriedades** de seu aparelho de ramificação e servidor de ramificação sobreviventes, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8d9c2-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="8d9c2-110">**Serviço de usuário associado e pool de registradores de backup** Na lista suspensa, selecione o pool de front-end do Enterprise Edition ou o servidor front-end Standard Edition que é para atuar como registrador de backup para o aparelho de ramificação sobreviventes ou para o servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="8d9c2-111">**Habilitar failover e failback** Selecione essa configuração para permitir a detecção automática de um registrador de falha e a determinação automática de que o registrador principal está em andamento e pronto para continuar o processo registrador.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="8d9c2-112">**Intervalo de detecção de falha (s)** Digite o número de segundos que devem decorrer antes que seja determinado que o registrador primário falhou.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="8d9c2-113">O valor padrão é 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-113">The default value is 120 seconds.</span></span> <span data-ttu-id="8d9c2-114">Este campo é obrigatório se você selecionar **habilitar failover e failback**.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="8d9c2-115">**Intervalo de detecção de fallback (s)** Digite o número de segundos que devem decorrer antes de determinar que o registrador primário está em backup.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="8d9c2-116">O valor padrão é 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-116">The default value is 240 seconds.</span></span> <span data-ttu-id="8d9c2-117">Este campo é obrigatório se você selecionar **habilitar failover e fallback**.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="8d9c2-118">Quando você define o intervalo de detecção de falha e o intervalo de detecção de fallback, tome cuidado para não inserir um intervalo que causará o failover e o fallback para ocorrer se o registrador não responder por um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="8d9c2-119">É possível que o registrador principal possa não responder por períodos curtos de tempo com base no carregamento do pool ou dos servidores.</span><span class="sxs-lookup"><span data-stu-id="8d9c2-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

