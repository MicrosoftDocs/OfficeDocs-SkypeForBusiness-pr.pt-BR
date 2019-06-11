---
title: 'Lync Server 2013: modificar uma política de voz e configurar registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="6e8f5-102">Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e8f5-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6e8f5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6e8f5-104">Siga estas etapas se quiser modificar uma política de voz.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="6e8f5-105">Se você quiser criar uma nova política de voz, consulte [criar uma política de voz e configurar registros de uso PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para o procedimento.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e8f5-106">Se um usuário estiver atribuído a uma política de voz sem registros de uso PSTN (rede telefônica pública comutada) associados, o usuário não poderá fazer chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="6e8f5-107">Para obter uma lista de todos os registros de uso PSTN disponíveis na sua implantação do Enterprise Voice e exibir suas propriedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">exibir registros de uso PSTN no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="6e8f5-108">Para modificar uma política de voz</span><span class="sxs-lookup"><span data-stu-id="6e8f5-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="6e8f5-109">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6e8f5-110">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6e8f5-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6e8f5-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6e8f5-113">Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="6e8f5-114">Na página **Política de Voz**, clique duas vezes em um nome de política de voz.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e8f5-p105">O escopo e o nome foram definidos quando a política de voz foi criada. Eles não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="6e8f5-117">(Opcional) Em **Editar Política de Voz**, digite as informações descritivas adicionais para a política de voz.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="6e8f5-118">Marque ou desmarque as seguintes caixas de seleção para habilitar ou desabilitar cada um dos **Recursos de chamada**:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="6e8f5-119">**Escape de caixa postal** impede que chamadas sejam imediatamente encaminhadas ao sistema de caixa postal do telefone celular do usuário quando o toque simultâneo estiver configurado e o telefone estiver desligado, sem bateria, ou fora de área.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6e8f5-120">Esse recurso só é configurável por meio do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6e8f5-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="6e8f5-121">**Encaminhamento de chamadas** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="6e8f5-122">O Lync Server 2013 oferece uma gama significativamente mais ampla de opções de configuração para encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="6e8f5-123">Por exemplo, se uma organização não deseja permitir que chamadas de entrada sejam encaminhadas externamente à PSTN, um administrador por aplicar uma política especial de voz para implantar esta restrição.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="6e8f5-124">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-125">**Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="6e8f5-126">No Lync Server 2013, um representante pode configurar o toque simultâneo que permite que as chamadas recebidas para o gerente dele sejam encaminhadas para todos os alvos simultâneos de toque do representante.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="6e8f5-127">Isso oferece uma maior flexibilidade ao delegado em responder chamadas direcionadas ao gerente.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="6e8f5-128">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-p108">A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-p109">**Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-133">**Toque simultâneo** permite que as chamadas recebidas toquem em telefones adicionais (por exemplo, um celular) ou outros dispositivos de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="6e8f5-134">O Lync Server 2013 oferece uma gama significativamente mais ampla de opções de configuração para toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="6e8f5-135">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-136">A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="6e8f5-137">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-138">O redirecionamento **PSTN** permite chamadas feitas por usuários que recebem essa política para que outros usuários da empresa sejam redirecionados na rede telefônica pública comutada (PSTN) se a WAN estiver congestionada ou indisponível.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="6e8f5-139">Habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="6e8f5-140">A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política do controle de admissão de chamadas (CAC) por um usuário específico</span><span class="sxs-lookup"><span data-stu-id="6e8f5-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="6e8f5-141">Desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6e8f5-p114">A política será substituída apenas para chamadas em entrada do usuário e não para chamadas em saída realizadas pelo usuário. Após a sessão ser estabelecida, o consumo de largura de banda será precisamente registrado. Esta configuração deve ser usada com moderação.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="6e8f5-145">O **rastreamento de chamadas maliciosas** permite que os usuários relatem chamadas mal-intencionadas (como as ameaças de bomba) usando a interface do usuário do cliente, que, por sua vez, sinaliza as chamadas nos registros de detalhes da chamada (CDRs).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="6e8f5-146">Desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-146">Disabled by default.</span></span>

7.  <span data-ttu-id="6e8f5-147">Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="6e8f5-p116">Para escolher um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de voz e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="6e8f5-150">Para remover um registro de uso de PSTN desta política de voz, realce o registro e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="6e8f5-151">Para definir um novo registro de uso PSTN e associá-lo a essa política de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="6e8f5-152">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="6e8f5-p117">No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, convém criar um registro de uso PSTN chamado **Redmond** para funcionários em tempo integral localizados em Redmond e outro registro chamado **RedmondTemps** para funcionários temporários.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="6e8f5-p118">O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="6e8f5-157">Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="6e8f5-158">Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="6e8f5-159">Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="6e8f5-160">Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="6e8f5-161">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="6e8f5-162">Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="6e8f5-163">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="6e8f5-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="6e8f5-165">Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="6e8f5-166">Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="6e8f5-167">Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="6e8f5-168">Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="6e8f5-169">Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="6e8f5-170">Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="6e8f5-171">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="6e8f5-172">Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="6e8f5-173">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="6e8f5-174">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-174">Click **OK**.</span></span>

8.  <span data-ttu-id="6e8f5-p123">Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e8f5-177">A ordem na qual PSTN registros de uso são listados na diretiva de voz é significativa.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="6e8f5-178">O Lync Server percorre a lista de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="6e8f5-179">Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="6e8f5-180">Para associar e configurar registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo nesta política de voz, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="6e8f5-181">Para usar os mesmos registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="6e8f5-182">Para permitir o encaminhamento de chamadas e o toque simultâneo somente para usuários internos do Lync, selecione encaminhar **para usuários internos do Lync somente** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="6e8f5-183">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="6e8f5-p126">Para usar registros de uso do PSTN diferentes dos usados nesta política de voz para encaminhamento de chamadas e toque simultâneo, selecione a opção **Rotear com usos de PSTN personalizados** no menu suspenso. Esta opção exibe um controle para selecionar registros de uso do PSTN existentes ou criar novos registros de uso do PSTN, especificamente para encaminhamento de chamadas e toques simultâneos.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="6e8f5-p127">Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="6e8f5-188">Para remover um registro de uso de PSTN desta política de encaminhamento de chamadas e toque simultâneo, realce o registro e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="6e8f5-189">Para definir um novo registro de uso de PSTN e associá-lo a esta política de encaminhamento de chamadas e toque simultâneo, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="6e8f5-190">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="6e8f5-191">No campo **Nome**, digite um nome descritivo para o registro.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="6e8f5-p128">O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="6e8f5-194">Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="6e8f5-195">Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="6e8f5-196">Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="6e8f5-197">Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="6e8f5-198">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="6e8f5-199">Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="6e8f5-200">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="6e8f5-201">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="6e8f5-202">Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="6e8f5-203">Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="6e8f5-204">Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:</span><span class="sxs-lookup"><span data-stu-id="6e8f5-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="6e8f5-205">Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="6e8f5-206">Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="6e8f5-207">Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="6e8f5-208">Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="6e8f5-209">Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="6e8f5-210">Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="6e8f5-211">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-211">Click **OK**.</span></span>

10. <span data-ttu-id="6e8f5-p133">(Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e8f5-214">Você pode salvar uma política de voz que ainda não passou no teste e, em seguida, reconfigurá-lo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="6e8f5-215">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="6e8f5-216">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-216">Click **OK**.</span></span>

12. <span data-ttu-id="6e8f5-217">Na página **Política de Voz**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e8f5-218">Sempre que criar ou modificar uma política de voz, você deve executar o comando <STRONG>Confirmar todos</STRONG> para publicar a alteração da configuração.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="6e8f5-219">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="6e8f5-220">(Opcional) O escape de caixa postal detecta que uma chamada foi imediatamente atendida pelo correio de voz do celular do usuário e desconecta a chamada à caixa postal do celular.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="6e8f5-221">Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, permitindo que ele atenda à chamada.</span><span class="sxs-lookup"><span data-stu-id="6e8f5-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="6e8f5-222">Para obter detalhes sobre como configurar uma política de caixa postal, consulte Configurando o [recurso de mensagem de voz no Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="6e8f5-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e8f5-223">Confira também</span><span class="sxs-lookup"><span data-stu-id="6e8f5-223">See Also</span></span>


[<span data-ttu-id="6e8f5-224">Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="6e8f5-225">Exibir registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="6e8f5-226">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="6e8f5-227">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="6e8f5-228">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="6e8f5-229">Configurando o recurso de mensagem de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="6e8f5-230">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e8f5-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

