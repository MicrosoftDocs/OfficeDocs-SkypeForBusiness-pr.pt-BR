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
ms.openlocfilehash: 16c12a5d8cff03f8d5755b5a2b54a6ff4dcf8399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="08034-102">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08034-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08034-103">_**Tópico da última modificação:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="08034-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="08034-104">Siga estas etapas se desejar configurar um tronco com o bypass de mídia habilitado.</span><span class="sxs-lookup"><span data-stu-id="08034-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="08034-105">Para configurar um tronco com bypass de mídia desabilitado, consulte [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="08034-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="08034-106">O bypass de mídia é útil quando você deseja minimizar o número de servidores de mediação implantados.</span><span class="sxs-lookup"><span data-stu-id="08034-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="08034-107">Geralmente, um pool de servidores de mediação será implantado em um site central, e ele controlará os gateways em sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="08034-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="08034-108">Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites.</span><span class="sxs-lookup"><span data-stu-id="08034-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="08034-109">Os roteamentos de chamadas de saída do Lync Server 2013 e as políticas de voz corporativa devem ser configurados corretamente para que chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.</span><span class="sxs-lookup"><span data-stu-id="08034-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="08034-110">É altamente recomendável habilitar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="08034-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="08034-111">No entanto, antes de habilitá-lo em um tronco SIP, confirme se seu provedor do tronco SIP oferece suporte ao bypass de mídia e pode acomodar os requisitos para habilitar o cenário com êxito.</span><span class="sxs-lookup"><span data-stu-id="08034-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="08034-112">Especificamente, o provedor deve ter os endereços IP dos servidores na rede interna da sua organização.</span><span class="sxs-lookup"><span data-stu-id="08034-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="08034-113">Se o provedor não puder dar suporte a esse cenário, o bypass de mídia não terá êxito.</span><span class="sxs-lookup"><span data-stu-id="08034-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="08034-114">Para obter detalhes, consulte [planejando o bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="08034-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08034-115">O bypass de mídia não interoperará com cada gateway PSTN (rede telefônica pública comutada), IP-PBX e controlador de borda de sessão (SBC).</span><span class="sxs-lookup"><span data-stu-id="08034-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="08034-116">A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="08034-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="08034-117">O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberta da comunicação unificada – Lync Server em <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="08034-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="08034-p104">Uma configuração de tronco, como descrita abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos atribuídos a essa configuração de tronco. O escopo de uma configuração de tronco específica pode ser global (para todos os troncos que não têm configuração de site ou pool mais específica), ou para um site ou pool. A configuração de tronco no nível do pool é usada para fazer o escopo de uma configuração de tronco específico para um único tronco.</span><span class="sxs-lookup"><span data-stu-id="08034-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="08034-121">Para configurar um tronco com bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="08034-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="08034-122">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="08034-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="08034-123">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="08034-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="08034-124">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08034-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08034-125">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="08034-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08034-126">Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.</span><span class="sxs-lookup"><span data-stu-id="08034-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="08034-127">Na página **Configuração do Tronco**, use um dos métodos a seguir para configurar um tronco:</span><span class="sxs-lookup"><span data-stu-id="08034-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="08034-128">Dê um duplo clique em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.</span><span class="sxs-lookup"><span data-stu-id="08034-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="08034-129">Clique em **Novo** e depois, selecione um escopo para a nova configuração de tronco:</span><span class="sxs-lookup"><span data-stu-id="08034-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="08034-130">**Tronco de site:** Escolha o site para esta configuração de tronco **Selecione um site**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="08034-131">Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**.</span><span class="sxs-lookup"><span data-stu-id="08034-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="08034-132">Essa configuração de tronco será aplicada a todos os troncos no site.</span><span class="sxs-lookup"><span data-stu-id="08034-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="08034-133">**Tronco de pool:** Escolha o nome do tronco ao qual essa configuração de tronco se aplica.</span><span class="sxs-lookup"><span data-stu-id="08034-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="08034-134">Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="08034-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="08034-135">Em **Selecionar um Serviço**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="08034-136">Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, o tronco não aparecerá em **Selecionar um Serviço**.</span><span class="sxs-lookup"><span data-stu-id="08034-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08034-137">Depois de selecionar o escopo da configuração de tronco, ele não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="08034-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="08034-138">O campo <STRONG>Nome</STRONG> é pré-preenchido com o nome do site ou serviço associado à configuração de tronco e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="08034-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="08034-p109">Especifique um valor em **Máximo de caixas de diálogo iniciais com suporte**. Este é o número máximo de respostas bifurcadas que um gateway de rede de telefonia comutada pública (PSTN), IP-PBX, ou Controlador de Borda de Sessão (SBC) ITSP pode receber para um INVITE enviado para o Servidor de Mediação. O valor padrão é 20.</span><span class="sxs-lookup"><span data-stu-id="08034-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08034-142">Antes de alterar este valor, consulte seu provedor de serviços ou fabricante do equipamento para detalhes sobre as capacidades do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="08034-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="08034-143">Selecione uma das seguintes opções de **Nível de suporte de criptografia**:</span><span class="sxs-lookup"><span data-stu-id="08034-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="08034-144">**Obrigatório:** A criptografia do SRTP (protocolo de transporte em tempo real seguro) deve ser usada para ajudar a proteger o tráfego entre o servidor de mediação e o gateway ou PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="08034-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="08034-145">**Opcional:** A criptografia SRTP será usada se o provedor de serviços ou o fabricante de equipamento oferecer suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="08034-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="08034-146">**Sem suporte:** A criptografia do SRTP não é compatível com o provedor de serviços ou com o fabricante do equipamento e, portanto, não será usada.</span><span class="sxs-lookup"><span data-stu-id="08034-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="08034-147">Selecione a opção **Habilitar bypass de mídia** se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="08034-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08034-148">Para que o bypass de mídia funcione com êxito, o gateway PSTN gateway, IP-PBX ou Controlador de Borda de Sessão ITSP deve oferecer suporte a determinados recursos.</span><span class="sxs-lookup"><span data-stu-id="08034-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="08034-149">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planejando o bypass de mídia no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="08034-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="08034-p111">Selecione a opção **Processamento de mídia centralizado** se houver um ponto de terminação de mídia conhecido (por exemplo, um gateway PSTN em que a terminação de mídia tem o mesmo IP da terminação de sinalização). Desmarque esta opção se o tronco não possuir um ponto de terminação de mídia conhecido.</span><span class="sxs-lookup"><span data-stu-id="08034-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="08034-152">Se o par de troncos der suporte para receber solicitações de referência SIP do servidor de mediação, marque a caixa de seleção **habilitar o envio para o gateway** .</span><span class="sxs-lookup"><span data-stu-id="08034-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08034-153">Se esta opção for desabilitada enquanto a opção <STRONG>Habilitar bypass de mídia</STRONG> estiver selecionada, configurações adicionais são necessárias.</span><span class="sxs-lookup"><span data-stu-id="08034-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="08034-154">Se o ponto do tronco não oferecer suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação e o bypass de mídia estiver habilitado, você também deve executar o cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> para desabilitar o RTCP para chamadas ativas e em espera para suportar as condições adequadas para bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="08034-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="08034-155">Para obter detalhes, consulte a documentação do <A href="lync-server-2013-lync-server-management-shell.md">Shell de gerenciamento do Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="08034-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="08034-156">Como alternativa, é possível selecionar <STRONG>Ativar referenciamento usando controle de chamada de terceiros</STRONG> se quiser que as chamadas transferidas contornem a mídia e o gateway não suporte solicitações SIP REFER.</span><span class="sxs-lookup"><span data-stu-id="08034-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="08034-157">(Opcional) Para permitir roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="08034-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="08034-158">Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas de entrada por meio do tronco que não se originam de um ponto de extremidade do Lync.</span><span class="sxs-lookup"><span data-stu-id="08034-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="08034-159">Para gerenciar os registros de uso de PSTN associados à configuração de tronco, use um dos métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="08034-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="08034-160">Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="08034-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08034-161">Realce os registros que você deseja associar a essa configuração de tronco e depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="08034-162">Para remover um registro de uso de PSTN desta configuração de tronco, selecione o registro e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="08034-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="08034-163">Para definir um novo registro de uso PSTN e associá-lo a essa configuração de tronco, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08034-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="08034-164">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="08034-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="08034-165">No campo **Nome**, especifique um nome descritivo que seja exclusivo para o registro.</span><span class="sxs-lookup"><span data-stu-id="08034-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="08034-p115">O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="08034-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="08034-168">Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="08034-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="08034-169">Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="08034-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08034-170">Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="08034-171">Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="08034-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="08034-172">Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="08034-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="08034-173">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="08034-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="08034-174">Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="08034-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="08034-175">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="08034-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="08034-176">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="08034-177">Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08034-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="08034-178">Selecione o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="08034-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="08034-179">Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="08034-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="08034-180">Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="08034-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08034-181">Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="08034-182">Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="08034-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="08034-183">Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="08034-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="08034-184">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="08034-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="08034-185">Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="08034-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="08034-186">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="08034-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="08034-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08034-188">É importante associar registros de uso PSTN de acordo com o peer do servidor de mediação associado ao tronco que está sendo configurado.</span><span class="sxs-lookup"><span data-stu-id="08034-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="08034-189">Se o peer do servidor de mediação for um gateway PSTN ou um controle de borda de sessão (SBC), é altamente recomendável que a configuração de troncos não esteja associada a um registro de uso PSTN que roteia para um destino PSTN ou qualquer outro sistema downstream conectado via Lync Servidor.</span><span class="sxs-lookup"><span data-stu-id="08034-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="08034-p123">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione o registro de uso e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="08034-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08034-192">A ordem na qual PSTN registros de uso são listados na configuração de tronco é significativa.</span><span class="sxs-lookup"><span data-stu-id="08034-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="08034-193">O Lync Server percorre a lista de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="08034-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="08034-194">**Enable RTP Latching** deve ser selecionado para permitir desvio de mídia para clientes atrás de uma NAT (conversão de endereço de rede) ou firewall, e um SBC que suporte travamento.</span><span class="sxs-lookup"><span data-stu-id="08034-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="08034-195">**Habilitar o histórico de chamadas de encaminhamento** deve ser selecionado para permitir o envio de informações de histórico de chamadas para o par de gateways do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="08034-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="08034-196">**Habilitar encaminhar os dados de identidades p-declarados** devem ser selecionados para permitir que as informações do originador da chamada p-Asserted-Identity (pai) sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="08034-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="08034-197">**Enable outbound routing failover timer** deve ser selecionado para permitir failover rápido.</span><span class="sxs-lookup"><span data-stu-id="08034-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="08034-198">O gateway associado a esse tronco pode fornecer notificações em 10 segundos de que está processando uma chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="08034-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="08034-199">O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="08034-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="08034-200">Em redes onde a latência pode atrasar o tempo de resposta ou o gateway levar mais de 10 segundos para responder, o failover rápido deverá ser desativado.</span><span class="sxs-lookup"><span data-stu-id="08034-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="08034-201">(Opcional) Associe e configure as **regras de conversão do número de chamada** do tronco.</span><span class="sxs-lookup"><span data-stu-id="08034-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="08034-202">Essas regras de conversão se aplicam ao número chamado para chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="08034-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="08034-203">Para escolher uma ou mais regras de uma lista de todas as regras de tradução que estão disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="08034-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08034-204">Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="08034-205">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="08034-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="08034-206">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08034-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08034-207">Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="08034-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="08034-208">Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08034-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08034-209">Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="08034-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="08034-210">Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="08034-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="08034-211">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="08034-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="08034-212">Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="08034-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="08034-p131">(Opcional) Associe e configure as **regras de conversão de números chamados** do tronco. As regras de conversão se aplicam ao número chamado em uma chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="08034-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="08034-215">Para escolher uma ou mais regras de uma lista de todas as regras de tradução que estão disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="08034-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08034-216">Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="08034-217">Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="08034-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="08034-218">Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08034-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08034-219">Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="08034-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="08034-220">Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08034-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08034-221">Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="08034-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="08034-222">Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="08034-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="08034-223">Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="08034-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="08034-224">Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.</span><span class="sxs-lookup"><span data-stu-id="08034-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="08034-p136">Verifique se as regras de conversão do tronco estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="08034-p136">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08034-227">O Lync Server 2013 percorre a lista de regras de tradução da parte superior para baixo e usa a primeira regra que corresponde ao número discado.</span><span class="sxs-lookup"><span data-stu-id="08034-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="08034-228">Se você configurar um tronco de forma que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas.</span><span class="sxs-lookup"><span data-stu-id="08034-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="08034-229">Por exemplo, se você incluiu uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponda a qualquer número de 11 dígitos esteja classificada <EM>abaixo</EM> da regra mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="08034-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="08034-230">Ao terminar de configurar o tronco, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="08034-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="08034-231">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="08034-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08034-232">Sempre que criar ou modificar uma configuração de tronco, você deve executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="08034-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="08034-233">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="08034-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="08034-234">Depois de configurar o tronco, continue a configuração do bypass de mídia escolhendo entre as opções de bypass de mídia global, conforme descrito em [Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08034-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08034-235">Confira também</span><span class="sxs-lookup"><span data-stu-id="08034-235">See Also</span></span>


[<span data-ttu-id="08034-236">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08034-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="08034-237">Configurar bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08034-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="08034-238">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08034-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="08034-239">Definindo regras de tradução no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08034-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

