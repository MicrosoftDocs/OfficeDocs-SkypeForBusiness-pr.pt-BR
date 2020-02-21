---
title: 'Lync Server 2013: habilitando ou desabilitando a integração com o armazenamento do Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc219e06e0d9bb6f7d76d4d08aef991c525b3aaf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="2ee34-102">Habilitar ou desabilitar a integração do Lync Server 2013 com o armazenamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="2ee34-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ee34-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2ee34-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2ee34-104">No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar a integração com o armazenamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2ee34-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="2ee34-105">Isso inclui as seguintes configurações de Arquivamento:</span><span class="sxs-lookup"><span data-stu-id="2ee34-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="2ee34-106">Uma configuração global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ee34-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2ee34-107">Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.</span><span class="sxs-lookup"><span data-stu-id="2ee34-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="2ee34-108">Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="2ee34-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="2ee34-109">Para habilitar ou desabilitar a integração com o armazenamento do Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="2ee34-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="2ee34-110">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2ee34-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ee34-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ee34-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ee34-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ee34-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ee34-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="2ee34-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="2ee34-114">Clique no nome da configuração do pool, local ou global adequada na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2ee34-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="2ee34-115">Para habilitar a integração com o armazenamento 2013 do Exchange, marque a caixa de seleção integração com o **Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="2ee34-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="2ee34-116">Para desabilitar a integração com o armazenamento do Exchange 2013, desmarque a caixa de seleção integração com o **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="2ee34-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="2ee34-117">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2ee34-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ee34-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ee34-118">See Also</span></span>


[<span data-ttu-id="2ee34-119">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ee34-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="2ee34-120">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</span><span class="sxs-lookup"><span data-stu-id="2ee34-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

