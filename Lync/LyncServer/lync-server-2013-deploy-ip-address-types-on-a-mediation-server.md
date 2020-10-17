---
title: 'Lync Server 2013: implantar tipos de endereço IP em um servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76dcde03d2a85eb45f7b2c28d6b7c7d99b41b20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531478"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="db971-102">Implantar tipos de endereço IP em um servidor de mediação para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db971-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db971-103">_**Última modificação do tópico:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="db971-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="db971-104">Usando o construtor de topologias, execute as etapas no procedimento a seguir para implantar tipos de endereço IP em um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="db971-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="db971-105">Para implantar os tipos de endereço IP em um Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="db971-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="db971-106">No construtor de topologias, em **pools de mediação**, clique com o botão direito do mouse no servidor dentro de um pool e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="db971-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="db971-107">(Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).</span><span class="sxs-lookup"><span data-stu-id="db971-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="db971-p102">Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.</span><span class="sxs-lookup"><span data-stu-id="db971-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="db971-110">**Caixa de diálogo Editar Propriedades para o pool de Servidores de Mediação**</span><span class="sxs-lookup"><span data-stu-id="db971-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="db971-111">![Página de propriedades gerais do Lync Server com FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Página de propriedades gerais do Lync Server com FQDN")</span><span class="sxs-lookup"><span data-stu-id="db971-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="db971-p103">**Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.</span><span class="sxs-lookup"><span data-stu-id="db971-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="db971-114">Essa é a opção recomendada para configurações IPv6.</span><span class="sxs-lookup"><span data-stu-id="db971-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="db971-p104">**Limitar o uso do serviço para os endereços IP selecionados**. Selecione esta opção para informar um endereço específico a ser usado no novo servidor. Se você selecionar esta opção, terá que inserir um valor para Endereço IP principal.</span><span class="sxs-lookup"><span data-stu-id="db971-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="db971-p105">**Endereço IP principal**. Insira o endereço IP que o servidor usará para todas as comunicações, com exceção de PSTN (rede telefônica pública comutada). O endereço IP inserido deve ter o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="db971-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="db971-121">**Endereço IP da PSTN**.</span><span class="sxs-lookup"><span data-stu-id="db971-121">**PSTN IP address**.</span></span> <span data-ttu-id="db971-122">Defina um endereço IP PSTN quando um servidor de mediação for autônomo.</span><span class="sxs-lookup"><span data-stu-id="db971-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="db971-123">Este endereço deve ser compatível com o formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="db971-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="db971-124">A instalação de placas de interface de rede adicionais (NIC) s para suportar a configuração de endereço IP PSTN para Lync Server 2013 não é suportada em funções de servidor de mediação posicionadas.</span><span class="sxs-lookup"><span data-stu-id="db971-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="db971-125">Para obter mais informações sobre configurações de NIC compatíveis com o Lync Server 2013, consulte <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="db971-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

