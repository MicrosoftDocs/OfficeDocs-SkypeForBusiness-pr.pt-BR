---
title: 'Lync Server 2013: criar ou modificar um fluxo de trabalho interativo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79af52b46c25796127fcb345360ed9f424ca3bf3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514758"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="cda31-102">Criar ou modificar um fluxo de trabalho interativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda31-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cda31-103">_**Última modificação do tópico:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="cda31-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="cda31-104">Use um dos seguintes procedimentos para criar ou modificar um fluxo de trabalho interativo.</span><span class="sxs-lookup"><span data-stu-id="cda31-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cda31-105">Você pode usar o Shell de gerenciamento do Lync Server ou a ferramenta de configuração do grupo de resposta para criar e modificar fluxos de trabalho interativos.</span><span class="sxs-lookup"><span data-stu-id="cda31-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="cda31-106">Você pode acessar a ferramenta de configuração do grupo de resposta no painel de controle do Lync Server ou abrindo a página da Web diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cda31-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="cda31-107">Para usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="cda31-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="cda31-108">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="cda31-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="cda31-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cda31-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cda31-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cda31-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cda31-111">Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="cda31-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="cda31-112">Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="cda31-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="cda31-113">No campo de pesquisa **Selecionar um serviço**, digite parte ou o nome inteiro do serviço **ApplicationServer** que hospeda o fluxo de trabalho que deseja criar ou modificar.</span><span class="sxs-lookup"><span data-stu-id="cda31-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="cda31-114">Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cda31-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-115">A ferramenta de configuração do grupo de resposta é aberta.</span><span class="sxs-lookup"><span data-stu-id="cda31-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="cda31-116">Você também pode abrir a ferramenta de configuração do grupo de resposta diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cda31-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="cda31-117">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="cda31-118">Em **Criar um Novo Fluxo de Trabalho**, ao lado de **Interativo**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="cda31-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="cda31-119">Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cda31-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="cda31-120">Se ainda não estiver tudo pronto para os usuários começarem a chamar o fluxo de trabalho, desmarque a caixa de seleção **Ativar o fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="cda31-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-p105">Se estiver criando um fluxo de trabalho gerenciado, você precisa selecionar <STRONG>Ativar o fluxo de trabalho</STRONG>. Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="cda31-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="cda31-123">Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**.</span><span class="sxs-lookup"><span data-stu-id="cda31-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="cda31-124">Você também deve ter uma política de acesso externo que se aplica ao aplicativo de grupo de resposta configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="cda31-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-125">A política de acesso externo global se aplica ao aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="cda31-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="cda31-126">Você pode configurar a política global para a Federação de grupo de resposta usando o painel de controle do Lync Server ou usando o cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para definir o parâmetro EnableOutsideAccess como true.</span><span class="sxs-lookup"><span data-stu-id="cda31-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="cda31-127">Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="cda31-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="cda31-128">Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cda31-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="cda31-129">Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar a política de acesso externo no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="cda31-130">Para obter detalhes sobre a configuração de Federação, consulte <STRONG>set-CsExternalAccessPolicy</STRONG> na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cda31-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-131">Os usuários hospedados no Lync Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="cda31-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="cda31-132">Isso acontece em implantações híbridas e em casos em que uma implantação local é federada com uma implantação do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="cda31-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="cda31-133">Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.</span><span class="sxs-lookup"><span data-stu-id="cda31-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-134">Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida.</span><span class="sxs-lookup"><span data-stu-id="cda31-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="cda31-135">Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas.</span><span class="sxs-lookup"><span data-stu-id="cda31-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="cda31-136">Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cda31-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="cda31-137">Os agentes que usam o plug-in do Lync VDI podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.</span><span class="sxs-lookup"><span data-stu-id="cda31-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="cda31-138">Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cda31-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="cda31-139">Em **Nome de exibição**, digite o nome que deseja exibir no fluxo de trabalho (por exemplo, Serviço de resposta IVR de vendas).</span><span class="sxs-lookup"><span data-stu-id="cda31-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-140">Não inclua os caracteres " &lt; " ou " &gt; " no nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="cda31-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="cda31-141">Não use os nomes de exibição a seguir, pois são reservados: RGS Presence Watcher ou Announcement Service.</span><span class="sxs-lookup"><span data-stu-id="cda31-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="cda31-142">Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="cda31-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="cda31-143">Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta  (por exemplo, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="cda31-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="cda31-144">Opcion Em **Descrição**, digite uma descrição para o fluxo de trabalho que você deseja que apareça no cartão de visita no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="cda31-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="cda31-145">Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="cda31-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="cda31-146">Para atribuir os gerentes do grupo de resposta ao fluxo de trabalho, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cda31-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="cda31-147">Digite o URI SIP de um gerente deste fluxo de trabalho e clique em **Adicionar**..</span><span class="sxs-lookup"><span data-stu-id="cda31-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="cda31-148">Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**..</span><span class="sxs-lookup"><span data-stu-id="cda31-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cda31-p112">Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="cda31-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="cda31-151">Sob **Etapa 2 Selecione um Idioma**, clique no idioma a ser usado para o reconhecimento de fala e conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="cda31-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="cda31-152">Se você deseja configurar uma mensagem de boas vindas, sob **Etapa 3 Configure uma Mensagem de Boas Vindas**, selecione a opção**Reproduzir uma mensagem de boas vindas** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="cda31-153">Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="cda31-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-p113">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cda31-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="cda31-p114">Para usar uma gravação de arquivo Wave ou Windows Media Audio para a mensagem de boas vindas, clique em **Selecione uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="cda31-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-160">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="cda31-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="cda31-161">Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="cda31-162">Sob **Etapa 4 Especifique seus Horários Comerciais**, na caixa **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cda31-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-p116">O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 11:00:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="cda31-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="cda31-168">Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="cda31-169">Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="cda31-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-170">Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção.</span><span class="sxs-lookup"><span data-stu-id="cda31-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="cda31-171">É possível definir agendamentos de predefinições usando o cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="cda31-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="cda31-172">Para obter detalhes, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(opcional) definir o horário comercial do grupo de resposta no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="cda31-173">Ao selecionar uma agenda predefinida, <STRONG>Dia</STRONG>, <STRONG>Abertura</STRONG> e <STRONG>Fechamento</STRONG> são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="cda31-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="cda31-174">Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.</span><span class="sxs-lookup"><span data-stu-id="cda31-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="cda31-175">Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.</span><span class="sxs-lookup"><span data-stu-id="cda31-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="cda31-176">Se estiver criando uma agenda personalizada, digite as horas de **Abertura** e **Fechamento** em que o grupo de resposta estará disponível.</span><span class="sxs-lookup"><span data-stu-id="cda31-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-p118">As horas de <STRONG>Abertura</STRONG> e <STRONG>Fechamento</STRONG> devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como <STRONG>Abertura</STRONG> 9:00, <STRONG>Fechamento</STRONG> 12:00, <STRONG>Abertura</STRONG> 13:00 e <STRONG>Fechamento</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="cda31-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="cda31-179">Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="cda31-180">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="cda31-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-p119">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cda31-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="cda31-p120">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="cda31-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-187">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="cda31-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="cda31-188">Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="cda31-189">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="cda31-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="cda31-190">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="cda31-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="cda31-191">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="cda31-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="cda31-192">O formato para o endereço de caixa postal é \<username\> @ \<domainname\> (por exemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cda31-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="cda31-193">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="cda31-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="cda31-194">O formato do endereço do usuário é \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="cda31-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="cda31-195">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="cda31-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="cda31-196">O formato do número de telefone é \<number\> @ \<domainname\> (por exemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cda31-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="cda31-197">O nome do domínio é usado para encaminhar o chamador ao destino correto.</span><span class="sxs-lookup"><span data-stu-id="cda31-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="cda31-198">Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.</span><span class="sxs-lookup"><span data-stu-id="cda31-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-199">É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cda31-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="cda31-200">Use os cmdlets <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> para definir feriados e conjuntos de feriados.</span><span class="sxs-lookup"><span data-stu-id="cda31-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="cda31-201">Para obter detalhes, consulte <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(opcional) definir os conjuntos de feriados do grupo de resposta no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="cda31-202">Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="cda31-203">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="cda31-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-p126">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cda31-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="cda31-p127">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="cda31-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-210">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="cda31-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="cda31-211">Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="cda31-212">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="cda31-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="cda31-213">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="cda31-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="cda31-214">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="cda31-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="cda31-215">O formato para o endereço de caixa postal é \<username\> @ \<domainname\> (por exemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cda31-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="cda31-216">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="cda31-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="cda31-217">O formato do endereço do usuário é \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="cda31-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="cda31-218">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="cda31-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="cda31-219">O formato do número de telefone é \<number\> @ \<domainname\> (por exemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cda31-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="cda31-220">O nome do domínio é usado para encaminhar o chamador ao destino correto.</span><span class="sxs-lookup"><span data-stu-id="cda31-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="cda31-221">Sob **Etapa 6 Configure a Música de Espera**, escolha o que deseja que os chamadores ouçam enquanto esperam por um operador, executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="cda31-222">Para usar a gravação padrão de música em espera, clique em **Usar padrão**.</span><span class="sxs-lookup"><span data-stu-id="cda31-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="cda31-p132">Para usar uma gravação de arquivo de áudio como música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="cda31-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-227">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="cda31-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="cda31-228">Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="cda31-229">Sob **Etapa 7 Configure a Resposta Interativa de Voz**, sob o cabeçalho **O usuário ouvirá o seguinte texto ou mensagem gravada**, especifique a pergunta a ser feita aos chamadores da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cda31-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="cda31-230">Para digitar uma pergunta em formato de texto, clique em **Usar conversão de texto em fala** e digite a pergunta na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="cda31-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-p134">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="cda31-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-233">O símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número".</span><span class="sxs-lookup"><span data-stu-id="cda31-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="cda31-234">Se for necessário fazer referência à tecla #, use o nome da tecla no prompt, em vez do símbolo.</span><span class="sxs-lookup"><span data-stu-id="cda31-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="cda31-235">Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."</span><span class="sxs-lookup"><span data-stu-id="cda31-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="cda31-p136">Para usar um arquivo de áudio pré-gravado que contenha a pergunta, clique em **Selecionar uma gravação** e clique no link **uma gravação** para carregar o arquivo. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo e, opcionalmente, você pode digitar a pergunta na caixa de texto (o que habilita a pergunta e a resposta do chamador a serem encaminhadas ao operador que atenderá).</span><span class="sxs-lookup"><span data-stu-id="cda31-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cda31-239">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="cda31-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="cda31-240">Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cda31-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="cda31-241">Em **Resposta 1**, especifique a primeira resposta possível para a pergunta executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cda31-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cda31-p138">Não use aspas (") em qualquer resposta de voz. Aspas podem provocar falhas no IVR.</span><span class="sxs-lookup"><span data-stu-id="cda31-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-244">Você pode optar por permitir que os chamadores respondam usando a fala, entradas do teclado alfanumérico ou ambos.</span><span class="sxs-lookup"><span data-stu-id="cda31-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="cda31-245">Se desejar permitir que o chamador responda usando a fala, insira a resposta em **Insira uma resposta de voz**.</span><span class="sxs-lookup"><span data-stu-id="cda31-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="cda31-246">Se você desejar permitir que o chamador responda pressionando uma tecla no teclado, em **Dígito**, clique no dígito do teclado.</span><span class="sxs-lookup"><span data-stu-id="cda31-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="cda31-247">Especifique se o chamador será encaminhado para uma fila ou se será feita outra pergunta, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cda31-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="cda31-248">Para rotear o chamador para uma fila, clique em **Enviar para uma fila** e, em **Selecione uma fila**, clique na fila que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="cda31-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="cda31-p139">Para fazer outra pergunta, clique em **Fazer outra pergunta**, clique em **Use conversão de texto em fala** e digite a pergunta ou clique em **Selecione uma gravação**. Use os agrupamentos de resposta nesta seção para especificar até quatro possíveis respostas para a pergunta adicional e a fila a ser usada para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na opção **Resposta 3** ou **Resposta 4**.</span><span class="sxs-lookup"><span data-stu-id="cda31-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="cda31-p140">Especifique até três mais respostas possíveis para a pergunta original, repetindo as etapas 28 e 29 para especificar as possíveis respostas e a ação para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na caixa de seleção **Resposta 3** ou **Resposta 4**.</span><span class="sxs-lookup"><span data-stu-id="cda31-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="cda31-254">Clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="cda31-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="cda31-255">Para usar o Windows PowerShell para criar ou modificar um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="cda31-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="cda31-256">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="cda31-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="cda31-257">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cda31-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cda31-p141">Recupere o nome do serviço do serviço de Grupo de resposta e atribua-o a uma variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="cda31-p142">Um fluxo de trabalho interativo requer duas ou mais filas e dois ou mais grupos de agentes. Primeiro, crie os grupos de agentes. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="cda31-p143">Crie as filas. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="cda31-p144">Crie o primeiro prompt de grupo de resposta. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="cda31-p145">Em seguida, crie a ação que será executada depois do prompt. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="cda31-p146">Crie a primeira resposta do grupo de resposta. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="cda31-p147">Agora crie o segundo prompt, a ação da chamada e a resposta. Primeiro crie o prompt. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="cda31-p148">Crie a segunda ação de chamada. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="cda31-p149">Crie a segunda resposta do grupo de resposta. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="cda31-p150">Crie o prompt do nível superior. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="cda31-p151">Crie a pergunta do nível superior. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="cda31-p152">Agora crie o fluxo de trabalho. Execute:</span><span class="sxs-lookup"><span data-stu-id="cda31-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cda31-p153">Todos os usuários que foram designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não têm essa função, não será possível gerenciar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="cda31-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

