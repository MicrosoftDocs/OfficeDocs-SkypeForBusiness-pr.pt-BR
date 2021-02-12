---
title: Configurar tipos de endereço IP no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumo: revise as considerações de tipo de endereço IP abaixo antes de implementar o Skype for Business Server.'
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825251"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="8ffa9-103">Configurar tipos de endereço IP no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8ffa9-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="8ffa9-104">**Resumo:** Revise as considerações de tipo de endereço IP abaixo antes de implementar o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="8ffa9-105">Você implanta tipos de endereço IP usando configurações de topologia que você configura no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="8ffa9-106">Esta seção descreve como implantar tipos de endereço IP em Servidores Front-End, Servidores de Mediação e Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="8ffa9-107">Implantar tipos de endereço IP em um Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="8ffa9-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="8ffa9-108">Usando o Construtor de Topologias, execute as etapas do procedimento a seguir para implantar tipos de endereço IP em um Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="8ffa9-109">Implantar tipos de endereço IP em um Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="8ffa9-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="8ffa9-p102">Em **Pools de front-end do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="8ffa9-112">Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="8ffa9-113">Para uma configuração de pilha dupla, selecione **Habilitar IPv4** e **Habilitar IPv6**.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="8ffa9-114">**Editar a caixa de diálogo Propriedades do pool do servidor front-end**</span><span class="sxs-lookup"><span data-stu-id="8ffa9-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="8ffa9-p104">**Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8ffa9-117">Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).</span><span class="sxs-lookup"><span data-stu-id="8ffa9-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="8ffa9-p105">**Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="8ffa9-p106">**Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="8ffa9-p107">**Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor front-end. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="8ffa9-127">A instalação de NICs (placas de interface de rede) adicionais para dar suporte à configuração de endereço IP PSTN (ou por qualquer outro motivo) em Servidores Front-End não é suportada.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="8ffa9-128">Para obter mais informações sobre as configurações NIC suportadas para o Skype for Business Server, consulte Server [hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="8ffa9-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="8ffa9-129">Implantar tipos de endereço IP em um Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="8ffa9-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="8ffa9-130">Usando o Construtor de Topologias, execute as etapas do procedimento a seguir para implantar tipos de endereço IP em um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="8ffa9-131">Para implantar os tipos de endereço IP em um Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="8ffa9-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="8ffa9-132">No Construtor de Topologias, em **Pools de** Mediação, clique com o botão direito do mouse no servidor em um pool e selecione **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="8ffa9-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="8ffa9-133">(Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).</span><span class="sxs-lookup"><span data-stu-id="8ffa9-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="8ffa9-p110">Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="8ffa9-136">**Caixa de diálogo Editar Propriedades para o pool de Servidores de Mediação**</span><span class="sxs-lookup"><span data-stu-id="8ffa9-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="8ffa9-p111">**Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8ffa9-139">Essa é a opção recomendada para configurações IPv6.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="8ffa9-p112">**Limitar o uso do serviço para os endereços IP selecionados**. Selecione esta opção para informar um endereço específico a ser usado no novo servidor. Se você selecionar esta opção, terá que inserir um valor para Endereço IP principal.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="8ffa9-p113">**Endereço IP principal**. Insira o endereço IP que o servidor usará para todas as comunicações, com exceção de PSTN (rede telefônica pública comutada). O endereço IP inserido deve ter o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="8ffa9-p114">**Endereço IP da PSTN**. Defina um endereço IP da PSTN quando um Servidor de mediação for colocado no Servidor front-end. Este endereço deve ser compatível com o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8ffa9-149">Só damos suporte a duas placas de rede em *Servidores de* Mediação dedicados.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="8ffa9-150">Se a função Servidor de Mediação for locada no Front End, não há suporte para placas de rede duplas.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="8ffa9-151">Para obter mais informações sobre as configurações NIC suportadas para o Skype for Business Server 2015, consulte [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="8ffa9-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="8ffa9-152">Para obter mais informações sobre as configurações NIC suportadas para o Skype for Business Server 2019, consulte [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="8ffa9-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="8ffa9-153">Implantar tipos de endereço IP em um Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="8ffa9-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="8ffa9-154">Usando o Construtor de Topologias, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8ffa9-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="8ffa9-155">Para implantar tipos de endereço IP em um servidor de borda</span><span class="sxs-lookup"><span data-stu-id="8ffa9-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="8ffa9-156">No Construtor de Topologias, em **pools de Borda,** clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="8ffa9-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="8ffa9-157">(Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).</span><span class="sxs-lookup"><span data-stu-id="8ffa9-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="8ffa9-158">Na janela **Editar Propriedades**, selecione a configuração de endereço IP para a qual deseja oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="8ffa9-159">Para cada tipo de endereço selecionado, você deve fornecer os endereços internos e externos apropriados.</span><span class="sxs-lookup"><span data-stu-id="8ffa9-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
