---
title: 'Lync Server 2013: configurar um tronco sem bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fce45563538b41773f76a8733b1c226454e6f76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523118"
---
# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="9731c-102">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9731c-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9731c-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9731c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9731c-104">Se quiser configurar um tronco com desvio de mídia desabilitado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9731c-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="9731c-105">Se quiser configurar um tronco com bypass de mídia habilitado, consulte [configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="9731c-p102">Uma configuração de tronco, como descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos designados com essa configuração. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.</span><span class="sxs-lookup"><span data-stu-id="9731c-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="9731c-109">Para configurar um tronco sem bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="9731c-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="9731c-110">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9731c-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9731c-111">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9731c-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9731c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9731c-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9731c-114">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.</span><span class="sxs-lookup"><span data-stu-id="9731c-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="9731c-115">Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:</span><span class="sxs-lookup"><span data-stu-id="9731c-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="9731c-116">Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.</span><span class="sxs-lookup"><span data-stu-id="9731c-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="9731c-117">Clique em **Novo** e selecione um escopo para a nova configuração do tronco:</span><span class="sxs-lookup"><span data-stu-id="9731c-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="9731c-118">**Tronco de site:** Escolha o site para essa configuração de tronco em **selecionar um site** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="9731c-119">Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**.</span><span class="sxs-lookup"><span data-stu-id="9731c-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="9731c-120">Essa configuração de tronco será aplicada a todos os troncos do site.</span><span class="sxs-lookup"><span data-stu-id="9731c-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="9731c-121">**Tronco do pool:** Escolha o nome do tronco ao qual essa configuração de tronco se aplica em **Selecione um serviço** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="9731c-122">Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="9731c-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="9731c-123">Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.</span><span class="sxs-lookup"><span data-stu-id="9731c-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9731c-124">Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="9731c-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="9731c-125">O campo <STRONG>Nome</STRONG> é preenchido previamente com o nome do site ou serviço associado à configuração do tronco e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="9731c-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="9731c-126">Selecione uma das seguintes opções de **Nível de suporte de criptografia**:</span><span class="sxs-lookup"><span data-stu-id="9731c-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="9731c-127">**Obrigatório:** A criptografia SRTP (Secure real-time Transport Protocol) deve ser usada para ajudar a proteger o tráfego entre o servidor de mediação e o gateway ou PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="9731c-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="9731c-128">**Opcional:** A criptografia SRTP será usada se o provedor de serviços ou o fabricante do equipamento oferecer suporte a ela.</span><span class="sxs-lookup"><span data-stu-id="9731c-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="9731c-129">**Sem suporte:** A criptografia SRTP não é suportada pelo provedor de serviços ou fabricante do equipamento e, portanto, não será usada.</span><span class="sxs-lookup"><span data-stu-id="9731c-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="9731c-130">Certifique-se de que a caixa de seleção **Habilitar bypass de mídia** esteja desmarcada.</span><span class="sxs-lookup"><span data-stu-id="9731c-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="9731c-p107">Marque a caixa de seleção **Processamento de mídia centralizado** se houver um ponto de encerramento de mídia conhecido [por exemplo, um gateway PSTN (Rede Telefônica Pública Comutada) no qual o encerramento de mídia tenha o mesmo IP que o encerramento de sinalização]. Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.</span><span class="sxs-lookup"><span data-stu-id="9731c-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="9731c-133">Se o par de troncos suportar o recebimento de solicitações SIP REFEREntes ao servidor de mediação, marque a caixa de seleção **habilitar o envio se refere ao gateway** .</span><span class="sxs-lookup"><span data-stu-id="9731c-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="9731c-p108">(Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas recebidas pelo tronco que não foram originadas em um ponto de extremidade do Lync. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="9731c-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="9731c-137">Para selecionar um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9731c-138">Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="9731c-139">Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="9731c-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="9731c-140">Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9731c-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="9731c-141">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9731c-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="9731c-142">No campo **Nome**, especifique um nome descritivo exclusivo para o registro.</span><span class="sxs-lookup"><span data-stu-id="9731c-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="9731c-p110">O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="9731c-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="9731c-145">Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="9731c-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="9731c-146">Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9731c-147">Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="9731c-148">Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="9731c-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="9731c-149">Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9731c-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="9731c-150">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="9731c-151">Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9731c-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="9731c-152">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="9731c-153">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="9731c-154">Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9731c-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="9731c-155">Selecione o registro de uso de PSTN que deseja editar e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9731c-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="9731c-156">Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="9731c-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="9731c-157">Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9731c-158">Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="9731c-159">Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="9731c-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="9731c-160">Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9731c-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="9731c-161">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="9731c-162">Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9731c-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="9731c-163">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="9731c-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9731c-165">É importante associar registros de uso do PSTN de acordo com o ponto do servidor de mediação associado ao tronco que está sendo configurado.</span><span class="sxs-lookup"><span data-stu-id="9731c-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="9731c-166">Se o ponto do servidor de mediação for um gateway PSTN ou um SBC (controlador de borda de sessão), é altamente recomendável que a configuração de tronco não esteja associada a um registro de uso de PSTN que roteia um destino PSTN ou qualquer outro sistema downstream conectado via Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9731c-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="9731c-p118">Organize os registros de uso de PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione esse registro de uso de PSTN e clique nas setas para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="9731c-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9731c-169">A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante.</span><span class="sxs-lookup"><span data-stu-id="9731c-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="9731c-170">O Lync Server percorre a lista de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="9731c-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="9731c-171">**Habilitar engatador RTP** deve ser selecionado para habilitar bypass de mídia para clientes sob um NAT ou firewall e um SBC que dê suporte ao engatador.</span><span class="sxs-lookup"><span data-stu-id="9731c-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="9731c-172">**Habilitar o histórico de chamadas de encaminhamento** deve ser selecionado para habilitar o envio de informações de histórico de chamadas para o par de gateway do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9731c-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="9731c-173">**Habilitar os dados de encaminhamento P-Asserted-Identity** devem ser selecionados para permitir que as informações do originador de chamadas do pai sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando presentes.</span><span class="sxs-lookup"><span data-stu-id="9731c-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="9731c-174">**Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido.</span><span class="sxs-lookup"><span data-stu-id="9731c-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="9731c-175">O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="9731c-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="9731c-176">O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9731c-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="9731c-177">Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="9731c-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="9731c-178">(Opcional) Associe e configure **regras de conversão de número de chamada** ao tronco.</span><span class="sxs-lookup"><span data-stu-id="9731c-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="9731c-179">Essas regras de conversão se aplicam ao número de chamada das chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="9731c-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="9731c-180">Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9731c-181">Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="9731c-182">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9731c-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="9731c-183">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9731c-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="9731c-184">Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9731c-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="9731c-185">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9731c-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="9731c-186">Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="9731c-187">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="9731c-188">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em \*\*Remover \*\*.</span><span class="sxs-lookup"><span data-stu-id="9731c-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="9731c-190">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="9731c-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="9731c-191">Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="9731c-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="9731c-p126">(Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="9731c-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="9731c-194">Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="9731c-195">Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="9731c-196">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9731c-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="9731c-197">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9731c-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="9731c-198">Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9731c-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="9731c-199">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9731c-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="9731c-200">Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="9731c-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="9731c-201">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="9731c-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="9731c-202">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em \*\*Remover \*\*.</span><span class="sxs-lookup"><span data-stu-id="9731c-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9731c-203">Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="9731c-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="9731c-204">Certifique-se de que as regras de conversão do tronco estejam organizadas na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="9731c-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="9731c-205">Para alterar a posição de uma regra na lista, destaque o nome da regra e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="9731c-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9731c-206">O Lync Server atravessa a lista de regras de conversão de cima para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="9731c-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="9731c-207">Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="9731c-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="9731c-208">Por exemplo, se tiver incluído uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada <EM>abaixo</EM> da regra mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="9731c-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="9731c-209">Depois de concluir a configuração do tronco, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9731c-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="9731c-210">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="9731c-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9731c-211">Sempre que você criar ou modificar uma configuração de tronco, execute o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração da configuração.</span><span class="sxs-lookup"><span data-stu-id="9731c-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="9731c-212">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="9731c-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9731c-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="9731c-213">See Also</span></span>


[<span data-ttu-id="9731c-214">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9731c-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="9731c-215">Definindo regras de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9731c-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

