---
title: 'Lync Server 2013: criar uma política de voz e configurar registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7596a9efb95436452144cf2cf0cacc53cd89a9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="c353e-102">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c353e-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c353e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c353e-104">Siga essas etapas se quiser criar uma nova política de voz.</span><span class="sxs-lookup"><span data-stu-id="c353e-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="c353e-105">Se você quiser editar uma política de voz, consulte [modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) para o procedimento.</span><span class="sxs-lookup"><span data-stu-id="c353e-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c353e-106">Cada política de voz precisa ter pelo menos um registro de uso de PSTN (Rede Telefônica Pública Comutada) associada.</span><span class="sxs-lookup"><span data-stu-id="c353e-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="c353e-107">Para ver uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice e ver suas propriedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c353e-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="c353e-108">Para criar uma política de voz</span><span class="sxs-lookup"><span data-stu-id="c353e-108">To create a voice policy</span></span>

1.  <span data-ttu-id="c353e-109">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c353e-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c353e-110">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c353e-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c353e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c353e-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c353e-113">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="c353e-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="c353e-114">Na página **Política de Voz**, clique em **Novo** e selecione um escopo para a nova política:</span><span class="sxs-lookup"><span data-stu-id="c353e-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="c353e-p105">**Política do site** se aplica a todo um site, exceto algum usuário ou grupo que tenha recebido uma política de usuário. Se você selecionar Site para um escopo de política, escolha o site na caixa de diálogo **Selecionar um Site**. Se uma política de voz tiver sido criada para um site, o site não aparece na caixa de diálogo **Selecionar um Site**.</span><span class="sxs-lookup"><span data-stu-id="c353e-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="c353e-118">**Política de usuário** pode ser aplicado a usuários ou grupos especificados.</span><span class="sxs-lookup"><span data-stu-id="c353e-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="c353e-119">Se o escopo da política de voz for Usuário, digite um nome descritivo para a política no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="c353e-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c353e-120">Se o escopo da política de voz for Site, o campo <STRONG>Nome</STRONG> na <STRONG>Nova Política de Voz</STRONG> será pré-preenchido com o nome do site e não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="c353e-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="c353e-121">(Opcional) Insira informações descritivas adicionais para a política de voz.</span><span class="sxs-lookup"><span data-stu-id="c353e-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="c353e-122">Marque ou desmarque as caixas de seleção a seguir para habilitar ou desabilitar cada um dos **Recursos de chamada** para esta política de voz:</span><span class="sxs-lookup"><span data-stu-id="c353e-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="c353e-123">**Escape de caixa postal** impede que chamadas sejam imediatamente encaminhadas ao sistema de caixa postal do telefone celular do usuário quando o toque simultâneo estiver configurado e o telefone estiver desligado, sem bateria, ou fora de área.</span><span class="sxs-lookup"><span data-stu-id="c353e-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c353e-124">Este recurso só é configurável por meio do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c353e-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="c353e-125">**Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes.</span><span class="sxs-lookup"><span data-stu-id="c353e-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="c353e-126">O Lync Server 2013 oferece uma variedade significativamente maior de opções de configuração para encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c353e-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="c353e-127">Por exemplo, se uma organização não deseja permitir que as chamadas recebidas sejam encaminhadas externamente à PSTN, um administrador pode aplicar um política de voz especial para implantar essa restrição.</span><span class="sxs-lookup"><span data-stu-id="c353e-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="c353e-128">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="c353e-129">**Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome.</span><span class="sxs-lookup"><span data-stu-id="c353e-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="c353e-130">No Lync Server 2013, um representante pode configurar o toque simultâneo, permitindo que as chamadas de entrada para o seu gerente enringem todos os alvos de toque simultâneos do representante.</span><span class="sxs-lookup"><span data-stu-id="c353e-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="c353e-131">Com isso, o representante tem mais flexibilidade para atender a chamadas direcionadas ao gerente.</span><span class="sxs-lookup"><span data-stu-id="c353e-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="c353e-132">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="c353e-p108">**Transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="c353e-p109">**Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="c353e-137">**Toque simultâneo** permite as chamadas em entrada tocarem em telefones adicionais (por exemplo, um telefone celular) ou outros dispositivos de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c353e-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="c353e-138">O Lync Server 2013 oferece uma variedade significativamente maior de opções de configuração para toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="c353e-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="c353e-139">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="c353e-p111">**Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="c353e-p112">**Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN (Rede Telefônica Pública Comutada) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="c353e-p113">**Substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamada para um usuário específico. Desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c353e-p114">A política será substituída somente para chamadas de entrada para o usuário e não para chamadas de saída feitas pelo usuário. Após o estabelecimento da sessão, o consumo de largura de banda será registrado de forma precisa. Essa configuração deve ser usada com moderação e deve ser reservado em prol de decisões apropriadas de controle de chamada.</span><span class="sxs-lookup"><span data-stu-id="c353e-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="c353e-p115">**Rastreamento de chamada mal-intencionada** permite que os usuários reportem chamadas mal intencionadas (como ameaças de bomba) usando a UI do cliente, o que por sua vez marca as chamadas nos CDRs (registros de detalhe da chamada). Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c353e-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

8.  <span data-ttu-id="c353e-151">Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c353e-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="c353e-p116">Para selecionar um ou mais registros em uma lista de todos os registros de uso do PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que deseja associar a esta política de voz e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="c353e-154">Para remover um registro de uso PSTN desta política de voz, destaque o registro e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c353e-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="c353e-155">Para definir um novo registro de uso PSTN e associá-lo com esta política de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c353e-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="c353e-156">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c353e-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="c353e-p117">No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, convém criar um registro de uso PSTN chamado **Redmond** para funcionários em tempo integral localizados em Redmond e outro chamado **RedmondTemps** para funcionários temporários.</span><span class="sxs-lookup"><span data-stu-id="c353e-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="c353e-p118">O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="c353e-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="c353e-161">Use qualquer um dos métodos a seguir para associar e configurar roteamentos para este registro de uso PSTN:</span><span class="sxs-lookup"><span data-stu-id="c353e-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="c353e-162">Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="c353e-163">Para remover uma rota do registro de uso do PSTN, realce a rota e então clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c353e-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="c353e-164">Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c353e-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c353e-165">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="c353e-166">Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c353e-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c353e-167">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="c353e-168">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="c353e-169">Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c353e-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="c353e-170">Realce o registro de uso do PSTN que você deseja editar e então clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c353e-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="c353e-171">Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="c353e-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="c353e-172">Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em \*\*Selecionar \*\*, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em \*\*OK \*\*.</span><span class="sxs-lookup"><span data-stu-id="c353e-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="c353e-173">Para remover uma rota desse registro de uso do PSTN, realce a rota e então clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c353e-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="c353e-174">Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c353e-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c353e-175">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="c353e-176">Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c353e-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="c353e-177">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="c353e-178">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-178">Click **OK**.</span></span>

9.  <span data-ttu-id="c353e-p123">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="c353e-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c353e-181">A ordem na qual os registros de uso PSTN são listados na política de voz é significante.</span><span class="sxs-lookup"><span data-stu-id="c353e-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="c353e-182">O Lync Server percorre a lista de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="c353e-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="c353e-183">Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="c353e-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="c353e-184">Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c353e-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="c353e-185">Para usar os mesmos registros de uso de PSTN para enchaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="c353e-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="c353e-p125">Para permitir enchaminhamento de chamadas e toque simultâneo apenas a usuários internos do Lync, selecione a opção **Encaminhar apenas para usuários internos do Lync** no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.</span><span class="sxs-lookup"><span data-stu-id="c353e-p125">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu. Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="c353e-p126">Para especificar registros de uso de PSTN diferentes para encaminhamento de chamadas e toque simultâneos que os usados para esta política de voz, selecione a opção **Encaminhar usando usos de PSTN personalizados** no menu suspenso. Essa opção exibe um controle para selecionar registros de uso de PSTN existentes ou criar novos registros de uso de PSTN especificamente para encaminhamento de chamadas e toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="c353e-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="c353e-p127">Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="c353e-192">Para remover um registro de uso do PSTN desta política de encaminhamento de chamadas e toques simultâneos, realce o registro e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c353e-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="c353e-193">Para definir um novo registro de uso do PSTN e associá-lo a essa política de encaminhamento de chamadas e toques simultâneos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c353e-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="c353e-194">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c353e-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="c353e-195">No campo **Nome**, insira um nome descritivo exclusivo para o registro.</span><span class="sxs-lookup"><span data-stu-id="c353e-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="c353e-p128">O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="c353e-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="c353e-198">Use qualquer um dos métodos a seguir para associar e configurar roteamentos para este registro de uso PSTN:</span><span class="sxs-lookup"><span data-stu-id="c353e-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="c353e-199">Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="c353e-200">Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c353e-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="c353e-201">Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c353e-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c353e-202">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="c353e-203">Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c353e-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c353e-204">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="c353e-205">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="c353e-206">Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c353e-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="c353e-207">Realce o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c353e-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="c353e-208">Use qualquer um dos métodos a seguir para associar e configurar roteamentos para este registro de uso PSTN:</span><span class="sxs-lookup"><span data-stu-id="c353e-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="c353e-209">Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="c353e-210">Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c353e-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="c353e-211">Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c353e-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c353e-212">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="c353e-213">Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c353e-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c353e-214">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="c353e-215">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-215">Click **OK**.</span></span>

11. <span data-ttu-id="c353e-p133">(Opcional) Insira um número para testar a política de voz e clique em \*\*Ir \*\*. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.</span><span class="sxs-lookup"><span data-stu-id="c353e-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c353e-218">Você pode salvar uma política de voz que ainda não passou no teste e reconfigurá-la mais tarde.</span><span class="sxs-lookup"><span data-stu-id="c353e-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="c353e-219">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c353e-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="c353e-220">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c353e-220">Click **OK**.</span></span>

13. <span data-ttu-id="c353e-221">Na página **Política de Voz**, clique em **Confirmar** e em **Confirmar todos**.</span><span class="sxs-lookup"><span data-stu-id="c353e-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c353e-222">Sempre que você criar ou modificar uma política de voz, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="c353e-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c353e-223">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="c353e-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="c353e-224">(Opcional) O escape de caixa postal detecta que uma chamada foi imediatamente atendida pelo correio de voz do celular do usuário e desconecta a chamada à caixa postal do celular.</span><span class="sxs-lookup"><span data-stu-id="c353e-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="c353e-225">Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, permitindo que ele atenda à chamada.</span><span class="sxs-lookup"><span data-stu-id="c353e-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="c353e-226">Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="c353e-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c353e-227">Confira também</span><span class="sxs-lookup"><span data-stu-id="c353e-227">See Also</span></span>


[<span data-ttu-id="c353e-228">Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="c353e-229">Exibir registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="c353e-230">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="c353e-231">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="c353e-232">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="c353e-233">Configurando o escape de caixa postal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="c353e-234">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c353e-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

