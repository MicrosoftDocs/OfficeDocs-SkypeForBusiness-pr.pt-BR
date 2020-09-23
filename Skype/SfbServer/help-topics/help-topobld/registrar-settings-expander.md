---
title: Expansor de Configurações do Registrador
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217152"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="459cf-105">Expansor de Configurações do Registrador</span><span class="sxs-lookup"><span data-stu-id="459cf-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="459cf-p102">A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.</span><span class="sxs-lookup"><span data-stu-id="459cf-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="459cf-109">Na seção  \*\*Resiliência \*\* da caixa de diálogo  \*\*Editar Propriedades \*\* de seu Aparelho de Filial Persistente, ou Servidor de Filial Persistente, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="459cf-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="459cf-110">**Serviço de usuário associado e pool de registradores de backup** Na lista suspensa, selecione o pool de front-ends Enterprise Edition ou o servidor front-end Standard Edition que deve atuar como registrador de backup para o aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="459cf-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="459cf-111">**Habilitar failover e failback** Selecione essa configuração para permitir a detecção automática de um registrador com falha e a determinação automática de que o registrador primário está em backup e pronto para retomar o processo registrador.</span><span class="sxs-lookup"><span data-stu-id="459cf-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="459cf-112">**Intervalo de detecção de falhas (s)** Digite o número de segundos que devem decorrer antes de determinar que o registrador principal falhou.</span><span class="sxs-lookup"><span data-stu-id="459cf-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="459cf-113">O valor padrão é 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="459cf-113">The default value is 120 seconds.</span></span> <span data-ttu-id="459cf-114">Este campo é obrigatório se você selecionou \*\*Habilitar Failover e Failback \*\*.</span><span class="sxs-lookup"><span data-stu-id="459cf-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="459cf-115">**Intervalo de detecção de fallback (s)** Digite o número de segundos que devem decorrer antes de determinar que o registrador principal é armazenado em backup.</span><span class="sxs-lookup"><span data-stu-id="459cf-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="459cf-116">O valor padrão é 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="459cf-116">The default value is 240 seconds.</span></span> <span data-ttu-id="459cf-117">Este campo é obrigatório se você selecionou  \*\*Habilitar Failover e Failback \*\*.</span><span class="sxs-lookup"><span data-stu-id="459cf-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="459cf-p105">Quando estiver definindo os intervalos de detecção de falha e de failback, tome cuidado para não informar um intervalo que cause com que o failover e o failback ocorram se um Registrador não responder em período curto de tempo. É possível que o Registrador primário não responda por curtos períodos de tempo baseado no carregamento de pool ou servidores.</span><span class="sxs-lookup"><span data-stu-id="459cf-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

