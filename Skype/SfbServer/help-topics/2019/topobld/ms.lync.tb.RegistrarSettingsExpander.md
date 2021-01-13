---
title: Expansor de Configurações do Registrador
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.
ms.openlocfilehash: cb7a5204b3b282c73f9440e61267b723b112b735
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822111"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="14401-105">Expansor de Configurações do Registrador</span><span class="sxs-lookup"><span data-stu-id="14401-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="14401-p102">A resiliência oferece alta disponibilidade e recuperação de desastres para o pool de Registradores. Ao disponibilizar um Registrador de backup em caso de falha do Registrador principal, o Registrador de backup pode assumir o lugar do Registrador com falha, permitindo que os usuários façam logon e se comuniquem. É possível que os usuários tenham uma redução na funcionalidade, dependendo dos sistemas que falharam no Registrador principal.</span><span class="sxs-lookup"><span data-stu-id="14401-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="14401-109">Na seção  **Resiliência** da caixa de diálogo  **Editar Propriedades** de seu Aparelho de Filial Persistente, ou Servidor de Filial Persistente, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="14401-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="14401-110">**Serviço de usuário associado e pool de registradores de backup** Na lista drop-down, selecione o pool de Front-End Enterprise Edition ou o Servidor front-end Standard Edition que deve atuar como Registrador de backup para o Aparelho de FilialVivível ou Servidor de FilialVivível.</span><span class="sxs-lookup"><span data-stu-id="14401-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="14401-111">**Habilitar Failover e Failback** Selecione essa configuração para permitir a detecção automática de um Registrador com falha e a determinação automática de que o Registrador primário está pronto para continuar o processo de Registrador.</span><span class="sxs-lookup"><span data-stu-id="14401-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="14401-112">**Intervalo de detecção de falha (s)** Digite o número de segundos que devem se desempesar antes que seja determinado que o Registrador primário falhou.</span><span class="sxs-lookup"><span data-stu-id="14401-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="14401-113">O valor padrão é 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="14401-113">The default value is 120 seconds.</span></span> <span data-ttu-id="14401-114">Este campo é obrigatório se você selecionou **Habilitar Failover e Failback**.</span><span class="sxs-lookup"><span data-stu-id="14401-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="14401-115">**Intervalo de detecção de fallback (s)** Digite o número de segundos que devem se desemparar antes que seja determinado que o backup do Registrador primário será feito.</span><span class="sxs-lookup"><span data-stu-id="14401-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="14401-116">O valor padrão é 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="14401-116">The default value is 240 seconds.</span></span> <span data-ttu-id="14401-117">Este campo é obrigatório se você selecionou  **Habilitar Failover e Failback**.</span><span class="sxs-lookup"><span data-stu-id="14401-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="14401-p105">Quando estiver definindo os intervalos de detecção de falha e de failback, tome cuidado para não informar um intervalo que cause com que o failover e o failback ocorram se um Registrador não responder em período curto de tempo. É possível que o Registrador primário não responda por curtos períodos de tempo baseado no carregamento de pool ou servidores.</span><span class="sxs-lookup"><span data-stu-id="14401-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

