---
title: 'Lync Server 2013: configurar um tronco com bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 940470dc8b6ccb7563dede6e3deaa4f123d88858
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515718"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a3a85-102">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a85-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3a85-103">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="a3a85-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="a3a85-104">Siga estas etapas para configurar um tronco com bypass de mídia habilitado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="a3a85-105">Para configurar um tronco com bypass de mídia desabilitado, confira [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="a3a85-106">O bypass de mídia é útil quando você deseja minimizar o número de Servidores de Mediação implantados.</span><span class="sxs-lookup"><span data-stu-id="a3a85-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="a3a85-107">Geralmente, um pool de Servidores de Mediação será implantado em um site central e controlará os gateways em sites locais.</span><span class="sxs-lookup"><span data-stu-id="a3a85-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="a3a85-108">Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites.</span><span class="sxs-lookup"><span data-stu-id="a3a85-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="a3a85-109">Os roteamentos de chamadas de saída do Lync Server 2013 e as políticas do Enterprise Voice devem ser configurados corretamente para que chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="a3a85-110">É altamente recomendável que você habilite o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="a3a85-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="a3a85-111">No entanto, antes de habilitar o bypass de mídia em um tronco SIP, confirme se o seu provedor de tronco SIP qualificado suporta bypass de mídia e é capaz de acomodar os requisitos para habilitar o cenário com êxito.</span><span class="sxs-lookup"><span data-stu-id="a3a85-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="a3a85-112">Especificamente, o provedor deve ter os endereços IP de servidores na rede interna da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3a85-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="a3a85-113">Se o provedor não oferecer suporte a esse cenário, o bypass de mídia não terá êxito.</span><span class="sxs-lookup"><span data-stu-id="a3a85-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="a3a85-114">Para obter detalhes, consulte [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a3a85-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3a85-115">O bypass de mídia não interoperará com cada gateway PSTN (rede telefônica pública comutada), IP-PBX e SBC (controlador de borda de sessão).</span><span class="sxs-lookup"><span data-stu-id="a3a85-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="a3a85-116">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="a3a85-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a3a85-117">O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações unificativas – Lync Server em <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="a3a85-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="a3a85-118">Uma configuração de tronco, conforme descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos atribuídos a essa configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="a3a85-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="a3a85-119">Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool.</span><span class="sxs-lookup"><span data-stu-id="a3a85-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="a3a85-120">A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.</span><span class="sxs-lookup"><span data-stu-id="a3a85-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="a3a85-121">Para configurar um tronco com bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="a3a85-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="a3a85-122">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a3a85-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a3a85-123">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a3a85-124">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3a85-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a3a85-125">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a3a85-126">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="a3a85-127">Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:</span><span class="sxs-lookup"><span data-stu-id="a3a85-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="a3a85-128">Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="a3a85-129">Clique em **Novo** e selecione um escopo para a nova configuração do tronco:</span><span class="sxs-lookup"><span data-stu-id="a3a85-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="a3a85-130">**Tronco de site:** Escolha o site para essa configuração de tronco de **selecionar um site**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="a3a85-131">Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="a3a85-132">Essa configuração de tronco será aplicada a todos os troncos do site.</span><span class="sxs-lookup"><span data-stu-id="a3a85-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="a3a85-133">**Tronco do pool:** Escolha o nome do tronco ao qual essa configuração de tronco se aplica.</span><span class="sxs-lookup"><span data-stu-id="a3a85-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="a3a85-134">Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a3a85-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="a3a85-135">Em **selecionar um serviço**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="a3a85-136">Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3a85-137">Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="a3a85-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="a3a85-138">O campo <STRONG>Nome</STRONG> é preenchido previamente com o nome do site ou serviço associado à configuração do tronco e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="a3a85-139">Especifique um valor no **máximo de caixas de diálogo iniciais com suporte**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="a3a85-140">Este é o número máximo de respostas bifurcadas que um gateway PSTN (rede telefônica pública comutada), IP-PBX ou ITSP de borda de sessão (SBC) pode receber um convite enviado para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="a3a85-141">O valor padrão é 20.</span><span class="sxs-lookup"><span data-stu-id="a3a85-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3a85-142">Antes de alterar esse valor, consulte seu provedor de serviços ou fabricante do equipamento para obter detalhes sobre os recursos do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="a3a85-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="a3a85-143">Selecione uma das seguintes opções de **Nível de suporte de criptografia**:</span><span class="sxs-lookup"><span data-stu-id="a3a85-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="a3a85-144">**Obrigatório:** A criptografia SRTP (Secure real-time Transport Protocol) deve ser usada para ajudar a proteger o tráfego entre o servidor de mediação e o gateway ou PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="a3a85-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="a3a85-145">**Opcional:** A criptografia SRTP será usada se o provedor de serviços ou o fabricante do equipamento oferecer suporte a ela.</span><span class="sxs-lookup"><span data-stu-id="a3a85-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="a3a85-146">**Sem suporte:** A criptografia SRTP não é suportada pelo provedor de serviços ou fabricante do equipamento e, portanto, não será usada.</span><span class="sxs-lookup"><span data-stu-id="a3a85-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="a3a85-147">Marque a caixa de seleção **habilitar bypass de mídia** se quiser que a mídia ignore o servidor de mediação para processamento pelo par de troncos.</span><span class="sxs-lookup"><span data-stu-id="a3a85-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3a85-148">Para que o bypass de mídia funcione com êxito, o gateway PSTN, IP-PBX ou controlador de borda da sessão ITSP deve suportar determinados recursos.</span><span class="sxs-lookup"><span data-stu-id="a3a85-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="a3a85-149">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media bypass in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a3a85-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="a3a85-150">Marque a caixa de seleção **processamento de mídia centralizado** se houver um ponto de terminação de mídia conhecido (por exemplo, um gateway PSTN onde a terminação de mídia tem o mesmo IP que a terminação de sinalização).</span><span class="sxs-lookup"><span data-stu-id="a3a85-150">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="a3a85-151">Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.</span><span class="sxs-lookup"><span data-stu-id="a3a85-151">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="a3a85-152">Se o par de troncos suportar o recebimento de solicitações SIP REFEREntes ao servidor de mediação, marque a caixa de seleção **habilitar o envio se refere ao gateway** .</span><span class="sxs-lookup"><span data-stu-id="a3a85-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3a85-153">Se você desabilitar essa opção enquanto a opção <STRONG>habilitar bypass de mídia</STRONG> estiver selecionada, configurações adicionais serão necessárias.</span><span class="sxs-lookup"><span data-stu-id="a3a85-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="a3a85-154">Se o par de troncos não oferecer suporte ao recebimento de solicitações SIP de referência do servidor de mediação e o bypass de mídia estiver habilitado, você também deverá executar o cmdlet <STRONG>set-CsTrunkConfiguration</STRONG> para desabilitar o RTCP para chamadas ativas e mantidas a fim de oferecer suporte às condições adequadas para o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="a3a85-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="a3a85-155">Para obter detalhes, consulte a documentação do <A href="lync-server-2013-lync-server-management-shell.md">Shell de gerenciamento do Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="a3a85-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="a3a85-156">Como alternativa, você pode selecionar <STRONG>habilitar fazer referência usando o controle de chamada de terceiros</STRONG> se quiser que as chamadas transferidas sejam ignoradas, e o gateway não oferece suporte a solicitações de referência SIP.</span><span class="sxs-lookup"><span data-stu-id="a3a85-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="a3a85-p113">(Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas recebidas pelo tronco que não foram originadas em um ponto de extremidade do Lync. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="a3a85-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="a3a85-160">Para selecionar um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a3a85-161">Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="a3a85-162">Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="a3a85-163">Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3a85-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="a3a85-164">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="a3a85-165">No campo **Nome**, especifique um nome descritivo exclusivo para o registro.</span><span class="sxs-lookup"><span data-stu-id="a3a85-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="a3a85-p115">O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="a3a85-168">Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="a3a85-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="a3a85-169">Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a3a85-170">Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="a3a85-171">Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="a3a85-172">Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a3a85-173">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="a3a85-174">Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="a3a85-175">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="a3a85-176">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="a3a85-177">Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a3a85-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="a3a85-178">Selecione o registro de uso de PSTN que deseja editar e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="a3a85-179">Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:</span><span class="sxs-lookup"><span data-stu-id="a3a85-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="a3a85-180">Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a3a85-181">Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="a3a85-182">Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="a3a85-183">Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a3a85-184">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="a3a85-185">Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="a3a85-186">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="a3a85-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3a85-188">É importante associar registros de uso do PSTN de acordo com o ponto do servidor de mediação associado ao tronco que está sendo configurado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="a3a85-189">Se o ponto do servidor de mediação for um gateway PSTN ou um SBC (controlador de borda de sessão), é altamente recomendável que a configuração de tronco não esteja associada a um registro de uso de PSTN que roteia um destino PSTN ou qualquer outro sistema downstream conectado via Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3a85-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="a3a85-p123">Organize os registros de uso de PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione esse registro de uso de PSTN e clique nas setas para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="a3a85-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3a85-192">A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante.</span><span class="sxs-lookup"><span data-stu-id="a3a85-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="a3a85-193">O Lync Server percorre a lista de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="a3a85-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="a3a85-194">**Habilitar a trava de RTP** deve ser selecionada para habilitar o bypass de mídia para clientes por trás de uma NAT (conversão de endereço de rede) ou firewall e um SBC que dê suporte ao engatador.</span><span class="sxs-lookup"><span data-stu-id="a3a85-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="a3a85-195">**Habilitar o histórico de chamadas de encaminhamento** deve ser selecionado para habilitar o envio de informações de histórico de chamadas para o par de gateway do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="a3a85-196">**Habilitar os dados de encaminhamento p-Asserted-Identity** devem ser selecionados para permitir que as informações de originador de chamada p-assertd-Identity (pai) sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando presentes.</span><span class="sxs-lookup"><span data-stu-id="a3a85-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="a3a85-197">**Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido.</span><span class="sxs-lookup"><span data-stu-id="a3a85-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="a3a85-198">O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="a3a85-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="a3a85-199">O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="a3a85-200">Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="a3a85-201">(Opcional) Associe e configure **regras de conversão de número de chamada** ao tronco.</span><span class="sxs-lookup"><span data-stu-id="a3a85-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="a3a85-202">Essas regras de conversão se aplicam ao número de chamada das chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="a3a85-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="a3a85-203">Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a3a85-204">Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a3a85-205">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a3a85-206">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a3a85-207">Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="a3a85-208">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a3a85-209">Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a3a85-210">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="a3a85-211">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em \*\*Remover \*\*.</span><span class="sxs-lookup"><span data-stu-id="a3a85-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a3a85-212">Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="a3a85-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="a3a85-p131">(Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="a3a85-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="a3a85-215">Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a3a85-216">Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a3a85-217">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a3a85-218">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a3a85-219">Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="a3a85-220">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a3a85-221">Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a3a85-222">Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a3a85-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="a3a85-223">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em \*\*Remover \*\*.</span><span class="sxs-lookup"><span data-stu-id="a3a85-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a3a85-224">Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="a3a85-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="a3a85-225">Certifique-se de que as regras de conversão do tronco estejam organizadas na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="a3a85-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="a3a85-226">Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="a3a85-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a3a85-227">O Lync Server 2013 atravessa a lista de regras de conversão de cima para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="a3a85-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a3a85-228">Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="a3a85-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="a3a85-229">Por exemplo, se tiver incluído uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada <EM>abaixo</EM> da regra mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="a3a85-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="a3a85-230">Depois de concluir a configuração do tronco, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="a3a85-231">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="a3a85-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a3a85-232">Sempre que você criar ou modificar uma configuração de tronco, execute o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração da configuração.</span><span class="sxs-lookup"><span data-stu-id="a3a85-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a3a85-233">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="a3a85-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="a3a85-234">Depois de configurar o tronco, continue Configurando o bypass de mídia escolhendo entre as opções de bypass de mídia global, conforme descrito em [opções globais de bypass de mídia no Lync Server 2013](lync-server-2013-global-media-bypass-options.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a3a85-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3a85-235">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3a85-235">See Also</span></span>


[<span data-ttu-id="a3a85-236">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a85-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="a3a85-237">Configurar bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a85-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="a3a85-238">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a85-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="a3a85-239">Definindo regras de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3a85-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

