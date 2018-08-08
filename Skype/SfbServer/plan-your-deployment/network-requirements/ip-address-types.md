---
title: Configurar tipos de endereço IP no Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumo: Revise as considerações de tipo de endereço IP abaixo antes de implementar Skype para Business Server.'
ms.openlocfilehash: 6d1e3a53e65bb3d1b3475dc19a7a2f9e1101195d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967161"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="03b86-103">Configurar tipos de endereço IP no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="03b86-103">Configure IP address types in Skype for Business</span></span>
 
<span data-ttu-id="03b86-104">**Resumo:** Revise as considerações de tipo de endereço IP abaixo antes de implementar Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="03b86-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>
  
<span data-ttu-id="03b86-105">Você pode implantar tipos de endereço IP usando as configurações de topologia que você configurar no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="03b86-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="03b86-106">Esta seção descreve como implantar os tipos de endereço IP em servidores Front-End, servidores de mediação e servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="03b86-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="03b86-107">Implantar tipos de endereço IP em um Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="03b86-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="03b86-108">Usando o construtor de topologias, execute as etapas no procedimento a seguir para implantar tipos de endereço IP em um servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="03b86-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="03b86-109">Implantar tipos de endereço IP em um Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="03b86-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="03b86-p102">Em **Pools de Front-Ends do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).</span><span class="sxs-lookup"><span data-stu-id="03b86-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="03b86-p103">Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.</span><span class="sxs-lookup"><span data-stu-id="03b86-p103">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="03b86-114">**Editar a caixa de diálogo Propriedades do pool do servidor front-end**</span><span class="sxs-lookup"><span data-stu-id="03b86-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

  - <span data-ttu-id="03b86-p104">**Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.</span><span class="sxs-lookup"><span data-stu-id="03b86-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="03b86-117">Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).</span><span class="sxs-lookup"><span data-stu-id="03b86-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="03b86-p105">**Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.</span><span class="sxs-lookup"><span data-stu-id="03b86-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
  - <span data-ttu-id="03b86-p106">**Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="03b86-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="03b86-p107">**Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor Front-End. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="03b86-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03b86-127">Não há suporte para a instalação de placas de interface de rede adicionais (NICs) para dar suporte a configuração de endereço IP PSTN nos servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="03b86-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="03b86-128">Para obter mais informações sobre configurações de NIC com suporte para Skype para Business Server, consulte [Server hardware platforms do Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="03b86-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="03b86-129">Implantar tipos de endereço IP no Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="03b86-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="03b86-130">Usando o construtor de topologias, execute as etapas no procedimento a seguir para implantar tipos de endereço IP em um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="03b86-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="03b86-131">Para implantar os tipos de endereço IP em um Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="03b86-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="03b86-132">No construtor de topologia, em **pools de mediação**, o servidor de um pool do mouse em e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="03b86-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="03b86-133">(Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)</span><span class="sxs-lookup"><span data-stu-id="03b86-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
- <span data-ttu-id="03b86-p110">Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.</span><span class="sxs-lookup"><span data-stu-id="03b86-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="03b86-136">**Caixa de diálogo Editar Propriedades para o pool de Servidores de Mediação**</span><span class="sxs-lookup"><span data-stu-id="03b86-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="03b86-p111">**Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.</span><span class="sxs-lookup"><span data-stu-id="03b86-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="03b86-139">Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).</span><span class="sxs-lookup"><span data-stu-id="03b86-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="03b86-p112">**Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o Endereço IP principal.</span><span class="sxs-lookup"><span data-stu-id="03b86-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
  - <span data-ttu-id="03b86-p113">**Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="03b86-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="03b86-p114">**Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor Front-End. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="03b86-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03b86-149">Não há suporte para a instalação de NICs adicionais para dar suporte a configuração de endereço IP PSTN nos servidores de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="03b86-149">The installation of additional NICs to support the PSTN IP address configuration on stand-alone Mediation Servers is not supported.</span></span> <span data-ttu-id="03b86-150">Para obter mais informações sobre configurações de NIC com suporte para Skype para Business Server, consulte [Server hardware platforms do Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="03b86-150">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="03b86-151">Implantar tipos de endereço IP em um Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="03b86-151">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="03b86-152">Usando o construtor de topologias, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="03b86-152">Using Topology Builder, perform the following steps:</span></span>
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="03b86-153">Para implantar tipos de endereço IP em um servidor de borda</span><span class="sxs-lookup"><span data-stu-id="03b86-153">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="03b86-154">No construtor de topologia, em **pools de borda**, o servidor de um pool do mouse em e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="03b86-154">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="03b86-155">(Como alternativa, selecione o servidor e clique em **Editar Propriedades** no menu **Ação**.)</span><span class="sxs-lookup"><span data-stu-id="03b86-155">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="03b86-156">Na janela **Editar Propriedades**, selecione a configuração de endereço IP para a qual deseja oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="03b86-156">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>    

3. <span data-ttu-id="03b86-157">Para cada tipo de endereço selecionado, você deve fornecer os endereços internos e externos apropriados.</span><span class="sxs-lookup"><span data-stu-id="03b86-157">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
    