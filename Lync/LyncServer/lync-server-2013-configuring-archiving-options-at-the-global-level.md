---
title: 'Lync Server 2013: Configurando opções de arquivamento no nível global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3798d64ba8a2252058756b04b51481e90bdf95c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="7a906-102">Configurando opções de arquivamento no nível global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a906-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a906-103">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="7a906-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="7a906-104">Quando você adiciona arquivamento à sua topologia e publica a topologia, o Lync Server cria uma configuração global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7a906-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="7a906-105">Por padrão, nenhuma opção de Arquivamento está ativada na configuração global.</span><span class="sxs-lookup"><span data-stu-id="7a906-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="7a906-106">Os controles de configuração global que habilitam configurações para a implantação inteira, a não ser que você defina configurações de site ou pool que substituem a configuração global.</span><span class="sxs-lookup"><span data-stu-id="7a906-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="7a906-107">Para obter detalhes sobre como as configurações de arquivamento funcionam, incluindo a hierarquia de configurações globais, de site e de pool, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="7a906-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a906-108">Você deve especificar todas as opções apropriadas nas configurações de Arquivamento antes de habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="7a906-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="7a906-109">Configurar opções de arquivamento a nível global</span><span class="sxs-lookup"><span data-stu-id="7a906-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="7a906-110">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="7a906-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a906-111">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a906-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7a906-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7a906-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7a906-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="7a906-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="7a906-114">Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="7a906-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7a906-115">Em **Editar configuração de arquivamento - global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="7a906-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="7a906-116">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="7a906-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="7a906-117">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="7a906-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="7a906-118">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="7a906-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="7a906-119">Na página **Editar configuração de arquivamento – global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7a906-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="7a906-120">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="7a906-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="7a906-121">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração com o Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="7a906-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="7a906-122">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7a906-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="7a906-123">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="7a906-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="7a906-124">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="7a906-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="7a906-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7a906-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

