---
title: 'Lync Server 2013: Configurando opções de arquivamento no nível global'
description: 'Lync Server 2013: Configurando opções de arquivamento no nível global.'
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
ms.openlocfilehash: 44b8939ec95d00afa2aa7632f4555bc6fef89834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571737"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="91e6d-103">Configurando opções de arquivamento no nível global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e6d-103">Configuring Archiving options at the global level in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91e6d-104">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="91e6d-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="91e6d-105">Quando você adiciona arquivamento à sua topologia e publica a topologia, o Lync Server cria uma configuração global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="91e6d-105">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="91e6d-106">Por padrão, nenhuma opção de Arquivamento está ativada na configuração global.</span><span class="sxs-lookup"><span data-stu-id="91e6d-106">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="91e6d-107">Os controles de configuração global que habilitam configurações para a implantação inteira, a não ser que você defina configurações de site ou pool que substituem a configuração global.</span><span class="sxs-lookup"><span data-stu-id="91e6d-107">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="91e6d-108">Para obter detalhes sobre como as configurações de arquivamento funcionam, incluindo a hierarquia de configurações globais, de site e de pool, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="91e6d-108">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91e6d-109">Você deve especificar todas as opções apropriadas nas configurações de Arquivamento antes de habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="91e6d-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="91e6d-110">Configurar opções de arquivamento a nível global</span><span class="sxs-lookup"><span data-stu-id="91e6d-110">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="91e6d-111">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="91e6d-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="91e6d-112">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91e6d-112">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="91e6d-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="91e6d-113">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="91e6d-114">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="91e6d-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="91e6d-115">Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="91e6d-115">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="91e6d-116">Em **Editar configuração de arquivamento - global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="91e6d-116">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="91e6d-117">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="91e6d-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="91e6d-118">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="91e6d-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="91e6d-119">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="91e6d-119">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="91e6d-120">Na página **Editar configuração de arquivamento – global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="91e6d-120">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="91e6d-121">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="91e6d-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="91e6d-122">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração com o Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="91e6d-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="91e6d-123">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="91e6d-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="91e6d-124">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="91e6d-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="91e6d-125">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="91e6d-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="91e6d-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="91e6d-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

