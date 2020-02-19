---
title: 'Lync Server 2013: criar ou modificar um fluxo de trabalho de grupo de busca'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03563506a739ca9eb0fcf1992899ba14167627d1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="b4a46-102">Criar ou modificar um fluxo de trabalho de grupo de busca no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a46-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a46-103">_**Última modificação do tópico:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="b4a46-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="b4a46-104">Use um dos seguintes procedimentos para criar ou modificar um fluxo de trabalho de grupo de busca.</span><span class="sxs-lookup"><span data-stu-id="b4a46-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4a46-105">Você pode usar o Shell de gerenciamento do Lync Server ou a ferramenta de configuração do grupo de resposta para criar e modificar fluxos de trabalho de grupo de busca.</span><span class="sxs-lookup"><span data-stu-id="b4a46-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="b4a46-106">Você pode acessar a ferramenta de configuração do grupo de resposta no painel de controle do Lync Server ou abrindo a página da Web diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="b4a46-107">Para usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho de grupo de busca</span><span class="sxs-lookup"><span data-stu-id="b4a46-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="b4a46-108">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="b4a46-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b4a46-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4a46-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b4a46-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4a46-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b4a46-111">Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="b4a46-112">Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="b4a46-113">No campo de pesquisa **selecionar um serviço** , digite todo ou parte do nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja criar ou alterar.</span><span class="sxs-lookup"><span data-stu-id="b4a46-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="b4a46-114">Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-115">A ferramenta de configuração do grupo de resposta é aberta.</span><span class="sxs-lookup"><span data-stu-id="b4a46-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="b4a46-116">Você também pode abrir a ferramenta de configuração do grupo de resposta diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="b4a46-117">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b4a46-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="b4a46-118">Em **criar um novo fluxo de trabalho**, ao lado de **grupo de busca, clique em criar**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="b4a46-119">Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="b4a46-120">Se você estiver pronto para os usuários começarem a chamar o fluxo de trabalho, selecione **ativar o fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-p105">Se estiver criando um fluxo de trabalho gerenciado, você precisa selecionar <STRONG>Ativar o fluxo de trabalho</STRONG>. Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="b4a46-123">Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="b4a46-124">Você também deve ter uma política de acesso externo que se aplica ao aplicativo de grupo de resposta configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="b4a46-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-125">A política de acesso externo global se aplica ao aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="b4a46-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="b4a46-126">Você pode configurar a política global para a Federação de grupo de resposta usando o painel de controle do Lync Server ou usando o cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para definir o parâmetro EnableOutsideAccess como true.</span><span class="sxs-lookup"><span data-stu-id="b4a46-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="b4a46-127">Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="b4a46-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="b4a46-128">Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4a46-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="b4a46-129">Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar a política de acesso externo no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="b4a46-130">Para obter detalhes sobre a configuração de Federação, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">set-CsExternalAccessPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-131">Os usuários hospedados no Lync Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="b4a46-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="b4a46-132">Isso acontece em implantações híbridas e em casos em que uma implantação local é federada com uma implantação do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b4a46-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="b4a46-133">Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-134">Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida.</span><span class="sxs-lookup"><span data-stu-id="b4a46-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="b4a46-135">Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas.</span><span class="sxs-lookup"><span data-stu-id="b4a46-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="b4a46-136">Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b4a46-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="b4a46-137">Os agentes que usam o plug-in do Lync VDI podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.</span><span class="sxs-lookup"><span data-stu-id="b4a46-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="b4a46-138">Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4a46-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-139">O URI principal de um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado.</span><span class="sxs-lookup"><span data-stu-id="b4a46-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="b4a46-140">O URI SIP que você insere é criado como um objeto de contato nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4a46-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="b4a46-141">Para criar o URI, o objeto deve ser exclusivo no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b4a46-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="b4a46-142">Em **nome para exibição**, digite o nome que você deseja exibir para o fluxo de trabalho (por exemplo, grupo de resposta de vendas).</span><span class="sxs-lookup"><span data-stu-id="b4a46-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-143">Não inclua os caracteres "&lt;" ou "&gt;" no nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="b4a46-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="b4a46-144">Não use os nomes de exibição a seguir, pois eles são reservados: Inspetor de presença ou <STRONG>serviço de anúncio</STRONG>do <STRONG>RGS</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b4a46-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="b4a46-145">Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="b4a46-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="b4a46-146">Em **Número de exibição**, digite o número como você deseja que seja exibido para o grupo de resposta (por exemplo, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="b4a46-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="b4a46-147">Opcion Em **Descrição**, digite uma descrição para o fluxo de trabalho conforme você deseja que ele apareça no cartão de visita no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="b4a46-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="b4a46-148">Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="b4a46-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="b4a46-149">Para atribuir os gerentes do grupo de resposta ao fluxo de trabalho, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4a46-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="b4a46-150">Digite o URI SIP de um gerente para este fluxo de trabalho e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="b4a46-151">Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b4a46-p113">Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="b4a46-154">Em **Etapa 2 Selecionar um idioma**, clique no idioma que você deseja usar para o reconhecimento de fala e conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="b4a46-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="b4a46-155">Se você deseja configurar uma mensagem de boas-vindas, em **Etapa 3 Configurar uma mensagem de boas-vindas**, marque a caixa de seleção **Reproduzir uma mensagem de boas-vindas** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="b4a46-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b4a46-156">Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b4a46-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-p114">Não inclua tags HTML no texto inserido. Se incluir tags HTML, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="b4a46-p115">Para usar um arquivo wave (.wav) ou Windows Media audio (.wma) gravando a mensagem de boas-vindas, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-163">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="b4a46-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="b4a46-164">Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="b4a46-165">Em **Etapa 4 Especificar seu horário comercial**, em \*\*Seu fuso horário \*\*, clique no fuso horário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4a46-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-p117">O fuso horário é o fuso onde os chamadores e agentes do fluxo de trabalho residem. É usado para calcular as horas abertas e fechadas. Por exemplo, se o fluxo de trabalho é configurado para usar o fuso horário Hora do Leste dos Estados Unidos e o fluxo de trabalho está programado para abrir às 7:00 e fechar as 23:00 horas, as horas abertas e fechadas devem ser 7:00 Horário do Leste e 23:00 Horário do Leste, respectivamente. (Você deve inserir as horas no formato de 24 horas.)</span><span class="sxs-lookup"><span data-stu-id="b4a46-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="b4a46-171">Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b4a46-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="b4a46-172">Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b4a46-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-173">Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção.</span><span class="sxs-lookup"><span data-stu-id="b4a46-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="b4a46-174">É possível definir agendamentos de predefinições usando o cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="b4a46-175">Para obter detalhes, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(opcional) definir o horário comercial do grupo de resposta no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-176">Ao selecionar uma agenda predefinida, <STRONG>Dia</STRONG>, <STRONG>Abertura</STRONG> e <STRONG>Fechamento</STRONG> são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="b4a46-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="b4a46-177">Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="b4a46-178">Se você está criando uma programação personalizada para este fluxo de trabalho, clique nas caixas de seleção para os dias da semana nos quais o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="b4a46-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="b4a46-179">Se você está criando uma programação personalizada, digite a hora **Aberta** e **Fechado** para cada dia da semana que o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="b4a46-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-p119">As horas <STRONG>Abrir</STRONG> e <STRONG>Fechar</STRONG> deve estar no formato 24 horas. Por exemplo, se seu escritório funciona de 9 as 17 horas e fecha ao meio dia para almoço, as horas comerciais são especificadas como <STRONG>Abrir</STRONG> 9:00, <STRONG>Fechar</STRONG> 12:00, <STRONG>Abrir</STRONG> 13:00 e <STRONG>Fechar</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="b4a46-182">Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b4a46-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="b4a46-183">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b4a46-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-p120">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="b4a46-p121">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-190">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="b4a46-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="b4a46-191">Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="b4a46-192">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="b4a46-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="b4a46-193">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="b4a46-194">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="b4a46-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="b4a46-195">O formato do endereço de caixa postal é \<nome\>@\<de usuário nome_do_domínio\> (por exemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b4a46-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="b4a46-196">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="b4a46-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="b4a46-197">O formato do endereço de usuário é \<username\>@\<DomainName\>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="b4a46-198">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="b4a46-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="b4a46-199">O formato do número de telefone é \<número\>@\<DomainName\> (por exemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b4a46-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="b4a46-200">O nome do domínio é usado para encaminhar o chamador ao destino correto.</span><span class="sxs-lookup"><span data-stu-id="b4a46-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="b4a46-201">Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.</span><span class="sxs-lookup"><span data-stu-id="b4a46-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-202">É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4a46-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="b4a46-203">Use os cmdlets <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> para definir feriados e conjuntos de feriados.</span><span class="sxs-lookup"><span data-stu-id="b4a46-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="b4a46-204">Para obter detalhes, consulte <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(opcional) definir os conjuntos de feriados do grupo de resposta no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="b4a46-205">Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b4a46-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="b4a46-206">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b4a46-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-p127">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="b4a46-p128">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-213">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="b4a46-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="b4a46-214">Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="b4a46-215">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="b4a46-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="b4a46-216">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="b4a46-217">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="b4a46-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="b4a46-218">O formato do endereço de caixa postal é \<nome\>@\<de usuário nome_do_domínio\> (por exemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b4a46-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="b4a46-219">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="b4a46-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="b4a46-220">O formato do endereço de usuário é \<username\>@\<DomainName\>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="b4a46-221">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="b4a46-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="b4a46-222">O formato do número de telefone é \<número\>@\<DomainName\> (por exemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b4a46-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="b4a46-223">O nome do domínio é usado para direcionar o chamador para o destino correto.</span><span class="sxs-lookup"><span data-stu-id="b4a46-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="b4a46-224">Em **Etapa 6 Configurar uma fila**, em **Selecionar a fila que irá receber as chamadas**, selecione a fila que deseja manter os chamadores até que um agente se tornar disponível.</span><span class="sxs-lookup"><span data-stu-id="b4a46-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="b4a46-225">Em **Etapa 7 Configurar música de espera**, escolha a música que você deseja que os chamadores ouçam enquanto aguardam por um agente, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4a46-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="b4a46-226">Para usar a gravação padrão de música de espera, clique em **Usar padrão**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="b4a46-p133">Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="b4a46-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b4a46-231">Todos os arquivos de áudio fornecidos pelo usuário devem cumprir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="b4a46-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="b4a46-232">Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="b4a46-233">Clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="b4a46-234">Para usar o Windows PowerShell para criar ou modificar um fluxo de trabalho de grupo de busca</span><span class="sxs-lookup"><span data-stu-id="b4a46-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="b4a46-235">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="b4a46-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b4a46-236">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b4a46-237">Crie o prompt a ser tocado para a mensagem de boas-vindas e salve-o em uma variável.</span><span class="sxs-lookup"><span data-stu-id="b4a46-237">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="b4a46-238">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b4a46-238">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="b4a46-239">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4a46-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-240">Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="b4a46-241">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a46-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="b4a46-242">Obtenha a identidade da fila ou pergunta onde as chamadas serão direcionadas.</span><span class="sxs-lookup"><span data-stu-id="b4a46-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="b4a46-243">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b4a46-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="b4a46-244">Para obter detalhes sobre como criar a fila, consulte [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="b4a46-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="b4a46-245">Defina a ação padrão a ser tomada quando um fluxo de trabalho for aberto durante o horário comercial e salve-o em uma variável.</span><span class="sxs-lookup"><span data-stu-id="b4a46-245">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="b4a46-246">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b4a46-246">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-247">Para fluxos de trabalho de grupo de busca, a ação padrão deve direcionar a chamada para uma fila.</span><span class="sxs-lookup"><span data-stu-id="b4a46-247">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="b4a46-248">Esse parâmetro é necessário para fluxos de trabalho ativos.</span><span class="sxs-lookup"><span data-stu-id="b4a46-248">This is parameter is required for active workflows.</span></span> <span data-ttu-id="b4a46-249">Não é necessário para fluxos de trabalho inativos.</span><span class="sxs-lookup"><span data-stu-id="b4a46-249">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="b4a46-250">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4a46-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="b4a46-251">Se você deseja definir horários comerciais e feriados, precisa criá-los antes de criar ou modificar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4a46-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="b4a46-252">Para obter detalhes, consulte [(opcional) definir o horário comercial do grupo de resposta no Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) e [(opcional) definir os conjuntos de feriados do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b4a46-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="b4a46-253">Se você deseja ter solicitações para chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use o **New-CsRgsCallAction** para definir a ação a ser tomada após o prompt.</span><span class="sxs-lookup"><span data-stu-id="b4a46-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="b4a46-254">Para obter detalhes, consulte [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="b4a46-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="b4a46-255">Recupere o nome do serviço do serviço de grupo de resposta do Lync Server e atribua-o a uma variável.</span><span class="sxs-lookup"><span data-stu-id="b4a46-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="b4a46-256">No comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b4a46-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="b4a46-257">Criar ou modificar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4a46-257">Create or modify the workflow.</span></span> <span data-ttu-id="b4a46-258">Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="b4a46-259">Para modificar um fluxo de trabalho, use **set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="b4a46-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="b4a46-260">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="b4a46-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="b4a46-261">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4a46-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b4a46-262">Todos os usuários designados para os fluxos de trabalho devem ser atribuídos à função À csresponsegroupmanager.</span><span class="sxs-lookup"><span data-stu-id="b4a46-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4a46-263">Para obter detalhes sobre parâmetros opcionais adicionais, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> ou <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">set-CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="b4a46-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4a46-264">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4a46-264">See Also</span></span>


[<span data-ttu-id="b4a46-265">Opcion Definir os conjuntos de feriados do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a46-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="b4a46-266">Opcion Definir o horário comercial do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a46-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="b4a46-267">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="b4a46-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="b4a46-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="b4a46-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="b4a46-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="b4a46-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="b4a46-270">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="b4a46-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

