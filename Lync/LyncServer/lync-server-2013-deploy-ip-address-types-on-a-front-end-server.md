---
title: 'Lync Server 2013: implantar tipos de endereço IP em um servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fae6ceef3bbc9d49bbc3afcb4236c4f8ba8bfb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="3764b-102">Implantar tipos de endereço IP em um servidor front-end para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3764b-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3764b-103">_**Última modificação do tópico:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="3764b-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="3764b-104">Usando o construtor de topologias, execute as etapas no procedimento a seguir para implantar tipos de endereço IP em um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="3764b-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="3764b-105">Implantar tipos de endereço IP em um Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="3764b-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="3764b-p101">Em **Pools de front-end do Enterprise Edition**, clique com o botão direito em um servidor de um pool e selecione **Editar propriedades**. (Como alternativa, selecione o servidor e clique em **Editar propriedades** no menu **Ação**).</span><span class="sxs-lookup"><span data-stu-id="3764b-p101">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="3764b-p102">Na caixa de diálogo **Editar propriedades**, selecione o tipo de endereço IP que você deseja configurar. Para uma configuração de pilha dual, selecione **Habilitar IPv4** e **Habilitar IPv6**, como mostrado na seguinte imagem.</span><span class="sxs-lookup"><span data-stu-id="3764b-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3764b-110">**Editar a caixa de diálogo Propriedades do pool do servidor front-end**</span><span class="sxs-lookup"><span data-stu-id="3764b-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="3764b-111">![Caixa de diálogo Editar propriedades do servidor front-end](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Caixa de diálogo Editar propriedades do servidor front-end")</span><span class="sxs-lookup"><span data-stu-id="3764b-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="3764b-p103">**Usar todos os endereços IP configurados**. Selecione esta opção se você deseja permitir qualquer endereço IP definido no computador que será usado.</span><span class="sxs-lookup"><span data-stu-id="3764b-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3764b-114">Esta é a opção recomendada para as configurações da versão 6 do IP (IPv6).</span><span class="sxs-lookup"><span data-stu-id="3764b-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="3764b-p104">**Limitar uso de serviços para selecionar endereços IP**. Selecione esta opção para especificar um endereço específico para usar um novo servidor. Se você selecionar esta opção, é necessário inserir um valor para o **Endereço IP principal**.</span><span class="sxs-lookup"><span data-stu-id="3764b-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="3764b-p105">**Endereço IP principal**. Insira um endereço IP que o servidor usará para todas as comunicações exceto a PSTN (Rede telefônica pública comutada). O endereço IP inserido deve corresponder ao formato do tipo de endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="3764b-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="3764b-121">**Endereço IP da PSTN**.</span><span class="sxs-lookup"><span data-stu-id="3764b-121">**PSTN IP address**.</span></span> <span data-ttu-id="3764b-122">A instalação de placas de interface de rede adicionais (NIC) s para suportar a configuração de endereço IP PSTN para Lync Server 2013 não é suportada em funções de servidor de mediação posicionadas.</span><span class="sxs-lookup"><span data-stu-id="3764b-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="3764b-123">Para obter mais informações sobre configurações de NIC compatíveis com o Lync Server 2013, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="3764b-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

