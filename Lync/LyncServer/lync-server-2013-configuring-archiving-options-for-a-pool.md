---
title: 'Lync Server 2013: Configurando opções de arquivamento para um pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e82c44a157b33de36495699e15cf7a48b8dd61f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="0cd41-102">Configurando opções de arquivamento para um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cd41-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cd41-103">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0cd41-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0cd41-p101">Você deve especificar as opções de Arquivamento que serão aplicadas a pools específicos criando e configurando opções em uma configuração de Arquivamento para cada um desses pools. Uma configuração de pool substitui a configuração global e de site, mas somente para o pool especificado na configuração de pool.</span><span class="sxs-lookup"><span data-stu-id="0cd41-p101">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="0cd41-106">Para obter detalhes sobre como as configurações de arquivamento funcionam, incluindo a hierarquia de configurações globais, de site e de pool, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="0cd41-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cd41-107">Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0cd41-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="0cd41-108">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="0cd41-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="0cd41-109">Configurar opções de arquivamento no nível do pool</span><span class="sxs-lookup"><span data-stu-id="0cd41-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="0cd41-110">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0cd41-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0cd41-111">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cd41-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0cd41-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0cd41-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0cd41-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="0cd41-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="0cd41-114">Na página **Configuração de arquivamento**, clique em **Nova** e em **Configuração de pool**.</span><span class="sxs-lookup"><span data-stu-id="0cd41-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="0cd41-115">Em **Selecionar um serviço**, selecione o pool que será configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0cd41-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="0cd41-116">Em **Nova configuração de arquivamento**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="0cd41-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="0cd41-117">**Desativar arquivamento**</span><span class="sxs-lookup"><span data-stu-id="0cd41-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="0cd41-118">**Arquivar sessões de IM**</span><span class="sxs-lookup"><span data-stu-id="0cd41-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="0cd41-119">**Arquivar sessões de IM e conferência da Web**</span><span class="sxs-lookup"><span data-stu-id="0cd41-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="0cd41-120">Na página **Nova configuração de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0cd41-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="0cd41-121">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="0cd41-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="0cd41-122">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração com o Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="0cd41-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="0cd41-123">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="0cd41-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="0cd41-124">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="0cd41-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="0cd41-125">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="0cd41-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="0cd41-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0cd41-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

