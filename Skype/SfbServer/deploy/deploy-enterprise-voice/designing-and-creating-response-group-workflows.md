---
title: Projetando e criando fluxos de trabalho do grupo de resposta no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Projete e crie fluxos de trabalho do Grupo de Resposta, no Skype for Business Server Enterprise Voice. Fluxos de trabalho de grupo de busca e fluxos de trabalho interativos são abordados.
ms.openlocfilehash: 3ebd5f2705547aa96a9ebfcc6857781ef25854b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831031"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a><span data-ttu-id="accd0-104">Projetando e criando fluxos de trabalho do grupo de resposta no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="accd0-104">Designing and creating response group workflows in Skype for Business</span></span>

<span data-ttu-id="accd0-105">Projete e crie fluxos de trabalho do Grupo de Resposta, no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="accd0-105">Design and create Response Group workflows, in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="accd0-106">Fluxos de trabalho de grupo de busca e fluxos de trabalho interativos são abordados.</span><span class="sxs-lookup"><span data-stu-id="accd0-106">Both hunt group workflows and interactive workflows are covered.</span></span>

<span data-ttu-id="accd0-107">Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada.</span><span class="sxs-lookup"><span data-stu-id="accd0-107">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="accd0-108">O fluxo de trabalho especifica a fila a ser usada para manter a chamada e especifica o método de roteamento a ser usado para fluxos de trabalho de grupo de busca ou as perguntas e respostas a ser usada para fluxos de trabalho interativos do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-108">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt group workflows or the questions and answers to use for interactive response group workflows.</span></span>

<span data-ttu-id="accd0-109">Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.</span><span class="sxs-lookup"><span data-stu-id="accd0-109">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="accd0-110">É necessário criar grupos de agentes e filas antes de criar um fluxo de trabalho que os use.</span><span class="sxs-lookup"><span data-stu-id="accd0-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="creating-or-modifying-a-hunt-group-workflow"></a><span data-ttu-id="accd0-111">Criando ou modificando um fluxo de trabalho de grupo de busca</span><span class="sxs-lookup"><span data-stu-id="accd0-111">Creating or modifying a hunt group workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="accd0-112">Para usar a Ferramenta de Configuração do Grupo de Resposta para criar ou modificar um fluxo de trabalho do grupo de busca</span><span class="sxs-lookup"><span data-stu-id="accd0-112">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="accd0-113">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="accd0-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="accd0-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="accd0-115">Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="accd0-115">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="accd0-116">Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="accd0-116">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="accd0-117">No campo **Selecionar um Serviço** de pesquisa, digite todo ou parte do nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja criar ou alterar.</span><span class="sxs-lookup"><span data-stu-id="accd0-117">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="accd0-118">Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="accd0-118">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-119">A Ferramenta de Configuração do Grupo de Resposta é aberta.</span><span class="sxs-lookup"><span data-stu-id="accd0-119">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="accd0-120">Você também pode abrir a Ferramenta de Configuração do Grupo de Resposta diretamente de um navegador da Web digitando a seguinte URL: https:// \<webPoolFqdn\> /RgsConfig.</span><span class="sxs-lookup"><span data-stu-id="accd0-120">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="accd0-121">Faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="accd0-121">Do one of the following:</span></span>

   - <span data-ttu-id="accd0-122">Em **Criar um Novo Fluxo de Trabalho**, ao lado de Grupo de **Busca**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-122">Under **Create a New Workflow**, next to **Hunt Group**, click **Create**.</span></span>

   - <span data-ttu-id="accd0-123">Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-123">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="accd0-124">Se você estiver pronto para que os usuários comecem a chamar o fluxo de trabalho, selecione **Ativar o fluxo de trabalho.**</span><span class="sxs-lookup"><span data-stu-id="accd0-124">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="accd0-125">Se você estiver criando um fluxo de trabalho gerenciado, precisará selecionar **Ativar o fluxo de trabalho.**</span><span class="sxs-lookup"><span data-stu-id="accd0-125">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="accd0-126">Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="accd0-126">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="accd0-127">Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**.</span><span class="sxs-lookup"><span data-stu-id="accd0-127">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="accd0-128">Você também deve ter uma política de acesso externo que se aplique ao aplicativo Grupo de Resposta configurado para federação.</span><span class="sxs-lookup"><span data-stu-id="accd0-128">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-129">A política de acesso externo global se aplica ao aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-129">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="accd0-130">Você pode configurar a política global para federação do grupo de resposta usando o Painel de Controle do Skype for Business Server ou o cmdlet **Set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como True.</span><span class="sxs-lookup"><span data-stu-id="accd0-130">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="accd0-131">Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="accd0-131">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="accd0-132">Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="accd0-132">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="accd0-133">Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-133">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="accd0-134">Para obter detalhes sobre a configuração de federação, [consulte Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="accd0-134">For details about the federation setting, see [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-135">Os usuários hospedados no Skype for Business Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="accd0-135">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="accd0-136">Isso é verdadeiro em implantações híbridas e em casos em que uma implantação local é federada com uma implantação do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="accd0-136">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="accd0-137">Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.</span><span class="sxs-lookup"><span data-stu-id="accd0-137">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-138">Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida.</span><span class="sxs-lookup"><span data-stu-id="accd0-138">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="accd0-139">Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas.</span><span class="sxs-lookup"><span data-stu-id="accd0-139">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="accd0-140">Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="accd0-140">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="accd0-141">Agentes que usam o Plug-in VDI do Lync podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.</span><span class="sxs-lookup"><span data-stu-id="accd0-141">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="accd0-142">Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-142">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-143">O URI principal de um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado.</span><span class="sxs-lookup"><span data-stu-id="accd0-143">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="accd0-144">O URI do SIP que você inserir é criado como um objeto de contato nos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="accd0-144">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="accd0-145">Para criar o URI, o objeto deve ser exclusivo no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="accd0-145">To create the URI, the object must be unique in Active Directory.</span></span>

11. <span data-ttu-id="accd0-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span><span class="sxs-lookup"><span data-stu-id="accd0-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-147">Não inclua os caracteres "<" ou ">" no nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="accd0-147">Do not include the "<" or ">" characters in the display name.</span></span> <span data-ttu-id="accd0-148">Não use os seguintes nomes de exibição porque eles são reservados: **RGS Presence Watcher** ou **Announcement Service**.</span><span class="sxs-lookup"><span data-stu-id="accd0-148">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="accd0-149">Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="accd0-149">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="accd0-150">Em **Número de exibição**, digite o número como você deseja que seja exibido para o grupo de resposta (por exemplo, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="accd0-150">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="accd0-151">(Opcional) Em **Descrição,** digite uma descrição para o fluxo de trabalho como você deseja que ele apareça no cartão de visita no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="accd0-151">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="accd0-152">Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-152">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="accd0-153">Faça o seguinte para atribuir Gerentes do Grupo de Resposta ao fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="accd0-153">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="accd0-154">a.</span><span class="sxs-lookup"><span data-stu-id="accd0-154">a.</span></span> <span data-ttu-id="accd0-155">Digite o URI sip de um gerente para este fluxo de trabalho e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-155">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="accd0-156">b.</span><span class="sxs-lookup"><span data-stu-id="accd0-156">b.</span></span> <span data-ttu-id="accd0-157">Digite o URI sip de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-157">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="accd0-p116">Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-p116">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="accd0-160">Em **Etapa 2 Selecionar um idioma**, clique no idioma que você deseja usar para o reconhecimento de fala e conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="accd0-160">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="accd0-161">Se você deseja configurar uma mensagem de boas-vindas, em **Etapa 3 Configurar uma mensagem de boas-vindas**, marque a caixa de seleção **Reproduzir uma mensagem de boas-vindas** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="accd0-161">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="accd0-162">Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-162">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p117">Não inclua tags HTML no texto inserido. Se incluir tags HTML, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p117">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="accd0-p118">Para usar um arquivo wave (.wav) ou Windows Media audio (.wma) gravando a mensagem de boas-vindas, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p118">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-169">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-169">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-170">Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-170">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="accd0-171">Em **Etapa 4 Especificar seu horário comercial**, em **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-171">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p120">O fuso horário é o fuso onde os chamadores e agentes do fluxo de trabalho residem. É usado para calcular as horas abertas e fechadas. Por exemplo, se o fluxo de trabalho é configurado para usar o fuso horário Hora do Leste dos Estados Unidos e o fluxo de trabalho está programado para abrir às 7:00 e fechar as 23:00 horas, as horas abertas e fechadas devem ser 7:00 Horário do Leste e 23:00 Horário do Leste, respectivamente. (Você deve inserir as horas no formato de 24 horas.)</span><span class="sxs-lookup"><span data-stu-id="accd0-p120">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="accd0-177">Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-177">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-178">Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="accd0-178">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-179">Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção.</span><span class="sxs-lookup"><span data-stu-id="accd0-179">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="accd0-180">É possível definir agendamentos de predefinições usando o cmdlet **New-CSRgsHoursOfBusiness**.</span><span class="sxs-lookup"><span data-stu-id="accd0-180">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="accd0-181">Para obter detalhes, consulte [(Opcional) Definir horário](optional-define-response-group-business-hours.md)comercial do Grupo de Resposta no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="accd0-181">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-182">Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-182">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="accd0-183">Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.</span><span class="sxs-lookup"><span data-stu-id="accd0-183">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="accd0-184">Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-184">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="accd0-185">Se você estiver criando uma  agenda  personalizada, digite as horas de Abertura e Fechamento para cada dia da semana em que o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-185">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group is available.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p122">As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.</span><span class="sxs-lookup"><span data-stu-id="accd0-p122">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="accd0-188">Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-188">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-189">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-189">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-p123">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p123">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="accd0-p124">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p124">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-196">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-196">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-197">Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-197">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="accd0-198">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="accd0-198">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="accd0-199">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="accd0-199">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="accd0-200">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="accd0-200">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="accd0-201">O formato do endereço da caixa postal *\<username\>* @ *\<domainName\>* é (por exemplo, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-201">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="accd0-202">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="accd0-202">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="accd0-203">O formato para o endereço do usuário é _\<username\>_ @ _\<domainName\>_ .</span><span class="sxs-lookup"><span data-stu-id="accd0-203">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="accd0-204">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="accd0-204">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="accd0-205">O formato do número de telefone *\<number\>* @ *\<domainName\>* é (por exemplo, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-205">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="accd0-206">O nome do domínio é usado para encaminhar o chamador ao destino correto.</span><span class="sxs-lookup"><span data-stu-id="accd0-206">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="accd0-207">Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.</span><span class="sxs-lookup"><span data-stu-id="accd0-207">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-208">É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-208">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="accd0-209">Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados.</span><span class="sxs-lookup"><span data-stu-id="accd0-209">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="accd0-210">Para obter detalhes, consulte [(Opcional) Definir conjuntos de feriados do Grupo de Resposta no Skype for Business.](optional-define-response-group-holiday-sets.md)</span><span class="sxs-lookup"><span data-stu-id="accd0-210">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="accd0-211">Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-211">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-212">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-212">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p130">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p130">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="accd0-p131">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p131">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-219">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-219">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-220">Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-220">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="accd0-221">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="accd0-221">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="accd0-222">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="accd0-222">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="accd0-223">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="accd0-223">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="accd0-224">O formato do endereço da caixa postal *\<username\>* @ *\<domainName\>* é (por exemplo, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-224">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="accd0-225">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="accd0-225">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="accd0-226">O formato para o endereço do usuário é _\<username\>_ @ _\<domainName\>_ .</span><span class="sxs-lookup"><span data-stu-id="accd0-226">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="accd0-227">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="accd0-227">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="accd0-228">O formato do número de telefone *\<number\>* @ *\<domainName\>* é (por exemplo, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-228">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="accd0-229">O nome do domínio é usado para direcionar o chamador para o destino correto.</span><span class="sxs-lookup"><span data-stu-id="accd0-229">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="accd0-230">Em **Etapa 6 Configurar uma fila**, em **Selecionar a fila que irá receber as chamadas**, selecione a fila que deseja manter os chamadores até que um agente se tornar disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-230">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="accd0-231">Em **Etapa 7 Configurar música de espera**, escolha a música que você deseja que os chamadores ouçam enquanto aguardam por um agente, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="accd0-231">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-232">Para usar a gravação padrão de música de espera, clique em **Usar padrão**.</span><span class="sxs-lookup"><span data-stu-id="accd0-232">To use the default music-on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="accd0-p136">Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p136">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-237">Todos os arquivos de áudio fornecidos pelo usuário devem cumprir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-237">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-238">Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-238">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="accd0-239">Clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-239">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="accd0-240">Para usar o Shell de Gerenciamento do Skype for Business Server para criar ou modificar um fluxo de trabalho de grupo de busca</span><span class="sxs-lookup"><span data-stu-id="accd0-240">To use Skype for Business Server Management Shell to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="accd0-241">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-241">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="accd0-242">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="accd0-242">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="accd0-243">Crie o prompt a ser tocado para a mensagem de boas-vindas e salve-o em uma variável.</span><span class="sxs-lookup"><span data-stu-id="accd0-243">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="accd0-244">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-244">At the command line, run:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    <span data-ttu-id="accd0-245">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="accd0-245">For example:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > <span data-ttu-id="accd0-246">Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="accd0-246">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="accd0-247">Para obter detalhes, [consulte Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="accd0-247">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span>

4. <span data-ttu-id="accd0-248">Obter a identidade da fila ou pergunta para onde as chamadas serão direcionadas.</span><span class="sxs-lookup"><span data-stu-id="accd0-248">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="accd0-249">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-249">At the command line, run:</span></span>

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    <span data-ttu-id="accd0-250">Para obter detalhes sobre como criar a fila, [consulte New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="accd0-250">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span></span>

5. <span data-ttu-id="accd0-251">Defina a ação padrão a ser tomada quando um fluxo de trabalho for aberto durante o horário comercial e salve-o em uma variável.</span><span class="sxs-lookup"><span data-stu-id="accd0-251">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="accd0-252">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-252">At the command line, run:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > <span data-ttu-id="accd0-253">Para fluxos de trabalho de grupo de busca, a ação padrão deve direcionar a chamada para uma fila.</span><span class="sxs-lookup"><span data-stu-id="accd0-253">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="accd0-254">Esse parâmetro é necessário para fluxos de trabalho ativos.</span><span class="sxs-lookup"><span data-stu-id="accd0-254">This parameter is required for active workflows.</span></span> <span data-ttu-id="accd0-255">Não é necessário para fluxos de trabalho inativos.</span><span class="sxs-lookup"><span data-stu-id="accd0-255">It is not required for inactive workflows.</span></span>

    <span data-ttu-id="accd0-256">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="accd0-256">For example:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. <span data-ttu-id="accd0-257">Se você quiser definir o horário comercial e feriados, será necessário criar antes de criar ou modificar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-257">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="accd0-258">Para obter detalhes, consulte [(Opcional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="accd0-258">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

7. <span data-ttu-id="accd0-259">Se você quiser ter prompts para chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use **o New-CsRgsCallAction** para definir a ação a ser tomada após o prompt.</span><span class="sxs-lookup"><span data-stu-id="accd0-259">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="accd0-260">Para obter detalhes, [consulte New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="accd0-260">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span>

8. <span data-ttu-id="accd0-261">Recupere o nome do serviço para o serviço grupo de resposta do Lync Server e atribua-o a uma variável.</span><span class="sxs-lookup"><span data-stu-id="accd0-261">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="accd0-262">No comando, execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-262">At the command, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. <span data-ttu-id="accd0-263">Criar ou modificar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-263">Create or modify the workflow.</span></span> <span data-ttu-id="accd0-264">Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="accd0-264">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="accd0-265">Para modificar um fluxo de trabalho, use **Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="accd0-265">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="accd0-266">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="accd0-266">At the command line, type:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    <span data-ttu-id="accd0-267">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="accd0-267">For example:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > <span data-ttu-id="accd0-268">Todos os usuários designados para fluxos de trabalho devem ter a função CsResponseGroupManager atribuída.</span><span class="sxs-lookup"><span data-stu-id="accd0-268">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

     > [!NOTE]
     > <span data-ttu-id="accd0-269">Para obter detalhes sobre parâmetros opcionais adicionais, consulte [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) ou [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="accd0-269">For details about additional optional parameters, see [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) or [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span></span>

## <a name="designing-an-interactive-workflow"></a><span data-ttu-id="accd0-270">Projetando um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="accd0-270">Designing an interactive workflow</span></span>

<span data-ttu-id="accd0-271">Você pode usar a IVR (resposta interativa de voz) para obter informações dos chamadores e direcionar a chamada para a fila apropriada.</span><span class="sxs-lookup"><span data-stu-id="accd0-271">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="accd0-272">Pares de perguntas e respostas determinam qual fila usar.</span><span class="sxs-lookup"><span data-stu-id="accd0-272">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="accd0-273">Dependendo da resposta do chamador, o chamador ouve uma pergunta de acompanhamento ou é roteado para a fila apropriada.</span><span class="sxs-lookup"><span data-stu-id="accd0-273">Depending on the caller's response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="accd0-274">As perguntas IVR e as respostas do chamador são fornecidas ao agente de resposta que aceita a chamada, fornecendo informações valiosas ao agente.</span><span class="sxs-lookup"><span data-stu-id="accd0-274">The IVR questions and the caller's responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

### <a name="overview-of-ivr-features"></a><span data-ttu-id="accd0-275">Visão geral dos recursos do IVR</span><span class="sxs-lookup"><span data-stu-id="accd0-275">Overview of IVR Features</span></span>

<span data-ttu-id="accd0-276">O aplicativo Grupo de Resposta oferece recursos de reconhecimento de fala e de texto em fala em 26 idiomas.</span><span class="sxs-lookup"><span data-stu-id="accd0-276">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="accd0-277">É possível inserir perguntas IVR usando a conversão texto em fala ou um arquivo wave (.wav) ou Windows Media audio (.wma).</span><span class="sxs-lookup"><span data-stu-id="accd0-277">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="accd0-278">Os chamadores podem responder usando a voz ou multifrequência de dois tons (DTMF).</span><span class="sxs-lookup"><span data-stu-id="accd0-278">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="accd0-279">Os fluxos de trabalho interativos suportam até dois níveis de perguntas, com cada pergunta tendo até quatro respostas possíveis.</span><span class="sxs-lookup"><span data-stu-id="accd0-279">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="accd0-280">A IVR faz uma pergunta ao chamador e, dependendo da resposta do chamador, encaminha o chamador para uma fila ou faz uma segunda pergunta.</span><span class="sxs-lookup"><span data-stu-id="accd0-280">The IVR asks the caller a question, and depending on the caller's response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="accd0-281">A segunda pergunta também pode ter quatro respostas possíveis.</span><span class="sxs-lookup"><span data-stu-id="accd0-281">The second question can also have four possible answers.</span></span> <span data-ttu-id="accd0-282">Dependendo da resposta à pergunta de segundo nível, o chamador é roteado para a fila adequada.</span><span class="sxs-lookup"><span data-stu-id="accd0-282">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

> [!NOTE]
> <span data-ttu-id="accd0-283">Ao projetar fluxos de chamadas usando o Shell de Gerenciamento do Skype for Business Server, você pode definir qualquer número de níveis de perguntas IVR e qualquer número de respostas.</span><span class="sxs-lookup"><span data-stu-id="accd0-283">When you design call flows by using Skype for Business Server Management Shell, you can define any number of levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="accd0-284">No entanto, para melhor usabilidade do chamador, recomendamos que você não use mais de três níveis de perguntas, com não mais do que cinco respostas cada.</span><span class="sxs-lookup"><span data-stu-id="accd0-284">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="accd0-285">Além disso, se você projetar um fluxo de chamadas com mais de dois níveis de perguntas com mais de quatro respostas cada, não será possível editar o fluxo de chamadas usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="accd0-285">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="accd0-286">As perguntas IVR e as respostas do chamador são fornecidas ao agente de resposta que aceita a chamada.</span><span class="sxs-lookup"><span data-stu-id="accd0-286">The IVR questions and the caller's responses are provided to the responding agent who accepts the call.</span></span>

### <a name="working-with-speech-technologies"></a><span data-ttu-id="accd0-287">Trabalhando com tecnologias de fala</span><span class="sxs-lookup"><span data-stu-id="accd0-287">Working with Speech Technologies</span></span>

<span data-ttu-id="accd0-p151">Tecnologias de fala, como o reconhecimento de fala e conversão de texto em fala, podem aprimorar a experiência do cliente e permitir que as pessoas acessem informações de forma mais natural e eficaz. No entanto, pode haver casos em que o texto especificado ou a resposta de voz do usuário não é reconhecido corretamente pelo mecanismo de fala. Por exemplo, o símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número". Este problema pode ser reduzido pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="accd0-p151">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively. However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine. For example, the "#" symbol is translated by the text-to-speech engine as the word "number." This issue can be mitigated by the following:</span></span>

- <span data-ttu-id="accd0-p152">O mecanismo de fala fornece ao chamador cinco tentativas de responder a pergunta. Se o chamador responder incorretamente (isto é, a resposta não é uma das respostas especificadas) ou não oferecer uma resposta, ele ou ela tem outra chance de responder. O chamador tem cinco tentativas de responder a pergunta antes de ser desconectado. É possível configurar a IVR para reproduzir uma mensagem personalizada após cada erro do chamador. A pergunta é repetida todas as vezes.</span><span class="sxs-lookup"><span data-stu-id="accd0-p152">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

- <span data-ttu-id="accd0-p153">Para minimizar que o potencial ruído ambiente seja interpretado pelo mecanismo de fala como uma resposta, use respostas mais longas. Por exemplo, as respostas devem ter mais de uma sílaba e devem soar diferente uma da outra.</span><span class="sxs-lookup"><span data-stu-id="accd0-p153">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

- <span data-ttu-id="accd0-p154">Se suas perguntas possuem respostas de fala e DTMF, configure as respostas de fala com palavras que representam um conceito ao invés da resposta DTMF. Por exemplo, ao invés de usar "Pressione ou fale 1", use "Pressione 1 ou fale faturamento."</span><span class="sxs-lookup"><span data-stu-id="accd0-p154">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

- <span data-ttu-id="accd0-p155">Após projetar sua IVR, ligue par ao fluxo de trabalho, ouça às solicitações, responda cada uma delas usando a voz e verifique se a IVR soa e se comporta conforme esperado. É possível modificar a IVR para corrigir qualquer problema de interpretação. No exemplo a seguir, se você precisa consultar a tecla #, é possível regravar sua solicitação IVR para usar o nome da tecla ao invés do símbolo #. Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."</span><span class="sxs-lookup"><span data-stu-id="accd0-p155">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected. You can then modify the IVR to fix any interpretation issues. Following the previous example, if you need to refer to the # key, you can rewrite your IVR prompt to use the key name, rather than the # symbol. For example, "To talk to sales, press the pound key."</span></span>

### <a name="ivr-design-examples"></a><span data-ttu-id="accd0-305">Exemplos de design de IVR</span><span class="sxs-lookup"><span data-stu-id="accd0-305">IVR Design Examples</span></span>

<span data-ttu-id="accd0-306">As seções a seguir contêm exemplos de diferentes cenários de IVR e pares de perguntas e respostas.</span><span class="sxs-lookup"><span data-stu-id="accd0-306">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

#### <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="accd0-307">IVR com um nível de perguntas</span><span class="sxs-lookup"><span data-stu-id="accd0-307">IVR with One Level of Questions</span></span>

<span data-ttu-id="accd0-308">O exemplo a seguir mostra uma IVR que usa um nível de perguntas.</span><span class="sxs-lookup"><span data-stu-id="accd0-308">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="accd0-309">Ele usa o reconhecimento de fala para detectar a resposta do chamador.</span><span class="sxs-lookup"><span data-stu-id="accd0-309">It uses speech recognition to detect the caller's response.</span></span>

 <span data-ttu-id="accd0-p157">**Pergunta:** "Obrigado por ligar para os Recursos Humanos. Se você deseja falar com a folha de pagamentos, diga folha de pagamentos. Caso contrário, diga RH."</span><span class="sxs-lookup"><span data-stu-id="accd0-p157">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

- <span data-ttu-id="accd0-313">**A opção 1 é selecionada:** O chamador é roteado para a equipe de folha de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="accd0-313">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

- <span data-ttu-id="accd0-314">**A opção 2 é selecionada:** O chamador é roteado para a equipe de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="accd0-314">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="accd0-315">A figura a seguir mostra o fluxo da chamada.</span><span class="sxs-lookup"><span data-stu-id="accd0-315">The following figure shows the call flow.</span></span>

 <span data-ttu-id="accd0-316">**Fluxo de chamada interativa de um nível**</span><span class="sxs-lookup"><span data-stu-id="accd0-316">**One-level interactive call flow**</span></span>

![Projetar fluxos de chamada usando o respo de voz interativo](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="accd0-318">IVR com dois níveis de perguntas</span><span class="sxs-lookup"><span data-stu-id="accd0-318">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="accd0-p158">O exemplo a seguir mostra uma IVR que usa dois níveis de perguntas. Permite aos chamadores responder usando fala ou entrada do teclado DTMF.</span><span class="sxs-lookup"><span data-stu-id="accd0-p158">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

 <span data-ttu-id="accd0-p159">**Pergunta:** "Obrigado por ligar para o Help Desk de TI. Se você está com um problema de acesso à rede, pressione 1 ou diga rede. Se você está com um problema de software, pressione 2 ou diga software. Se você está com um problema de hardware, pressione 3 ou diga hardware."</span><span class="sxs-lookup"><span data-stu-id="accd0-p159">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

- <span data-ttu-id="accd0-325">**A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte de rede.</span><span class="sxs-lookup"><span data-stu-id="accd0-325">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

- <span data-ttu-id="accd0-326">**A opção 2 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:</span><span class="sxs-lookup"><span data-stu-id="accd0-326">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="accd0-p160">**Pergunta:** "Se é um problema do sistema operacional, pressione 1 ou diga sistema operacional. Se é um problema com um aplicativo interno, pressione 2 ou diga aplicativo interno. Caso contrário, pressione 3 ou diga outro."</span><span class="sxs-lookup"><span data-stu-id="accd0-p160">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>

  - <span data-ttu-id="accd0-330">**A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte ao sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="accd0-330">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>

  - <span data-ttu-id="accd0-331">**A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte a aplicativos internos.</span><span class="sxs-lookup"><span data-stu-id="accd0-331">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>

  - <span data-ttu-id="accd0-332">**A opção 3 é selecionada:** O chamador é roteado para a equipe de suporte de software.</span><span class="sxs-lookup"><span data-stu-id="accd0-332">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

- <span data-ttu-id="accd0-333">**A opção 3 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:</span><span class="sxs-lookup"><span data-stu-id="accd0-333">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="accd0-p161">**Pergunta:** "Se é um problema de impressora, pressione 1. Caso contrário, pressione 2."</span><span class="sxs-lookup"><span data-stu-id="accd0-p161">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>

  - <span data-ttu-id="accd0-336">**A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte a impressoras.</span><span class="sxs-lookup"><span data-stu-id="accd0-336">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>

  - <span data-ttu-id="accd0-337">**A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte ao hardware.</span><span class="sxs-lookup"><span data-stu-id="accd0-337">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="accd0-338">A figura a seguir mostra o fluxo de chamadas.</span><span class="sxs-lookup"><span data-stu-id="accd0-338">The following figure shows the call flow.</span></span>

 <span data-ttu-id="accd0-339">**Fluxo de chamada interativa de dois níveis**</span><span class="sxs-lookup"><span data-stu-id="accd0-339">**Two-level interactive call flow**</span></span>

![Projetar fluxos de chamada usando o respo de voz interativo](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a><span data-ttu-id="accd0-341">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="accd0-341">Best Practices</span></span>

<span data-ttu-id="accd0-342">A lista a seguir descreve algumas práticas recomendadas para projetar sua IVR:</span><span class="sxs-lookup"><span data-stu-id="accd0-342">The following list describes some best practices for designing your IVR:</span></span>

- <span data-ttu-id="accd0-p162">Permita que o chamador chegue à tarefa rapidamente. Evite oferecer muita informação ou mensagens de marketing longas em sua IVR.</span><span class="sxs-lookup"><span data-stu-id="accd0-p162">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

- <span data-ttu-id="accd0-p163">Se você deseja incluir uma mensagem longa, considere anexá-la à primeira pergunta ao invés da mensagem de boas-vindas. Os chamadores podem ignorar a mensagem se fizer parte da primeira pergunta respondendo à pergunta, mas não podem ignorar a mensagem de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="accd0-p163">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

- <span data-ttu-id="accd0-347">Fale no idioma do chamador.</span><span class="sxs-lookup"><span data-stu-id="accd0-347">Speak in the caller's language.</span></span> <span data-ttu-id="accd0-348">Evite usar uma linguagem refinada.</span><span class="sxs-lookup"><span data-stu-id="accd0-348">Avoid stilted language.</span></span> <span data-ttu-id="accd0-349">Fale naturalmente.</span><span class="sxs-lookup"><span data-stu-id="accd0-349">Speak naturally.</span></span>

- <span data-ttu-id="accd0-350">Grave prompts eficazes e eficientes.</span><span class="sxs-lookup"><span data-stu-id="accd0-350">Write efficient and effective prompts.</span></span> <span data-ttu-id="accd0-351">Remova qualquer opção desnecessária.</span><span class="sxs-lookup"><span data-stu-id="accd0-351">Remove any unnecessary options.</span></span> <span data-ttu-id="accd0-352">Es estrutura as informações para que a resposta esperada do chamador seja no final da frase.</span><span class="sxs-lookup"><span data-stu-id="accd0-352">Structure the information so that the caller's expected response is at the end of the sentence.</span></span> <span data-ttu-id="accd0-353">Por exemplo, "Para falar com a equipe de vendas, pressione 1".</span><span class="sxs-lookup"><span data-stu-id="accd0-353">For example, "To speak to the sales team, press 1."</span></span>

- <span data-ttu-id="accd0-p166">Torne as respostas de voz fáceis. Por exemplo, se você especificar as respostas DTMF e voz, use algo como: "Para falar com a equipe de vendas, pressione 1 ou diga vendas."</span><span class="sxs-lookup"><span data-stu-id="accd0-p166">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

- <span data-ttu-id="accd0-356">Teste a IVR em um grupo de usuários antes de implantar na sua organização.</span><span class="sxs-lookup"><span data-stu-id="accd0-356">Test the IVR on a group of users before you deploy it across your organization.</span></span>

## <a name="creating-or-modifying-an-interactive-workflow"></a><span data-ttu-id="accd0-357">Criando ou modificando um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="accd0-357">Creating or modifying an interactive workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="accd0-358">Para usar a Ferramenta de Configuração do Grupo de Resposta para criar ou modificar um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="accd0-358">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1. <span data-ttu-id="accd0-359">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-359">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="accd0-360">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="accd0-360">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="accd0-361">Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="accd0-361">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="accd0-362">Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="accd0-362">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="accd0-363">No campo de pesquisa **Selecionar um serviço**, digite parte ou o nome inteiro do serviço **ApplicationServer** que hospeda o fluxo de trabalho que deseja criar ou modificar.</span><span class="sxs-lookup"><span data-stu-id="accd0-363">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="accd0-364">Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="accd0-364">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-365">A Ferramenta de Configuração do Grupo de Resposta é aberta.</span><span class="sxs-lookup"><span data-stu-id="accd0-365">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="accd0-366">Você também pode abrir a Ferramenta de Configuração do Grupo de Resposta diretamente de um navegador da Web digitando a seguinte URL: https:// \<webPoolFqdn\> /RgsConfig.</span><span class="sxs-lookup"><span data-stu-id="accd0-366">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="accd0-367">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-367">Do one of the following:</span></span>

   - <span data-ttu-id="accd0-368">Em **Criar um Novo Fluxo de Trabalho**, ao lado de **Interativo**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-368">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>

   - <span data-ttu-id="accd0-369">Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-369">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="accd0-370">Se ainda não estiver tudo pronto para os usuários começarem a chamar o fluxo de trabalho, desmarque a caixa de seleção **Ativar o fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="accd0-370">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="accd0-371">Se você estiver criando um fluxo de trabalho gerenciado, precisará selecionar **Ativar o fluxo de trabalho.**</span><span class="sxs-lookup"><span data-stu-id="accd0-371">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="accd0-372">Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="accd0-372">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="accd0-373">Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**.</span><span class="sxs-lookup"><span data-stu-id="accd0-373">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="accd0-374">Você também deve ter uma política de acesso externo que se aplique ao aplicativo Grupo de Resposta configurado para federação.</span><span class="sxs-lookup"><span data-stu-id="accd0-374">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-375">A política de acesso externo global se aplica ao aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-375">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="accd0-376">Você pode configurar a política global para federação do grupo de resposta usando o Painel de Controle do Skype for Business Server ou o cmdlet **Set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como True.</span><span class="sxs-lookup"><span data-stu-id="accd0-376">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="accd0-377">Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="accd0-377">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="accd0-378">Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="accd0-378">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="accd0-379">Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-379">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="accd0-380">Para obter detalhes sobre a configuração de federação, **consulte Set-CsExternalAccessPolicy** na documentação.</span><span class="sxs-lookup"><span data-stu-id="accd0-380">For details about the federation setting, see **Set-CsExternalAccessPolicy** in documentation..</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-381">Os usuários hospedados no Skype for Business Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="accd0-381">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="accd0-382">Isso é verdadeiro em implantações híbridas e em casos em que uma implantação local é federada com uma implantação do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="accd0-382">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="accd0-383">Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.</span><span class="sxs-lookup"><span data-stu-id="accd0-383">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-384">Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida.</span><span class="sxs-lookup"><span data-stu-id="accd0-384">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="accd0-385">Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas.</span><span class="sxs-lookup"><span data-stu-id="accd0-385">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="accd0-386">Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="accd0-386">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="accd0-387">Agentes que usam o Plug-in VDI do Lync podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.</span><span class="sxs-lookup"><span data-stu-id="accd0-387">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="accd0-388">Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-388">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="accd0-389">Em **Nome de exibição**, digite o nome que deseja exibir no fluxo de trabalho (por exemplo, Serviço de resposta IVR de vendas).</span><span class="sxs-lookup"><span data-stu-id="accd0-389">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-390">Não inclua os caracteres \<" or "\> " " no nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="accd0-390">Do not include the "\<" or "\>" characters in the display name.</span></span> <span data-ttu-id="accd0-391">Não use os seguintes nomes de exibição porque eles são reservados: **RGS Presence Watcher** ou **Announcement Service**.</span><span class="sxs-lookup"><span data-stu-id="accd0-391">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="accd0-392">Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="accd0-392">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="accd0-393">Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta  (por exemplo, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="accd0-393">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="accd0-394">(Opcional) Em **Descrição,** digite uma descrição para o fluxo de trabalho que você deseja que apareça no cartão de visita no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="accd0-394">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="accd0-395">Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-395">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="accd0-396">Faça o seguinte para atribuir Gerentes do Grupo de Resposta ao fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="accd0-396">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="accd0-397">a.</span><span class="sxs-lookup"><span data-stu-id="accd0-397">a.</span></span> <span data-ttu-id="accd0-398">Digite o URI sip de um gerente para este fluxo de trabalho e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-398">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="accd0-399">b.</span><span class="sxs-lookup"><span data-stu-id="accd0-399">b.</span></span> <span data-ttu-id="accd0-400">Digite o URI sip de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-400">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="accd0-p178">Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-p178">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="accd0-403">Sob **Etapa 2 Selecione um Idioma**, clique no idioma a ser usado para o reconhecimento de fala e conversão de texto em fala.</span><span class="sxs-lookup"><span data-stu-id="accd0-403">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="accd0-404">Se você deseja configurar uma mensagem de boas vindas, sob **Etapa 3 Configure uma Mensagem de Boas Vindas**, selecione a opção **Reproduzir uma mensagem de boas vindas** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-404">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="accd0-405">Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-405">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p179">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p179">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="accd0-p180">Para usar uma gravação de arquivo Wave ou Windows Media Audio para a mensagem de boas vindas, clique em **Selecione uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p180">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-412">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-412">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-413">Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-413">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="accd0-414">Sob **Etapa 4 Especifique seus Horários Comerciais**, na caixa **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-414">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p182">O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 11:00:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="accd0-p182">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="accd0-420">Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-420">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-421">Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="accd0-421">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-422">Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção.</span><span class="sxs-lookup"><span data-stu-id="accd0-422">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="accd0-423">Defina agendas predefinidas usando o cmdlet **New-CsRgsHoursOfBusiness.**</span><span class="sxs-lookup"><span data-stu-id="accd0-423">You define preset schedules by using the **New-CsRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="accd0-424">Para obter detalhes, consulte [(Opcional) Definir horário](optional-define-response-group-business-hours.md)comercial do Grupo de Resposta no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="accd0-424">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span> <span data-ttu-id="accd0-425">Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-425">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="accd0-426">Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.</span><span class="sxs-lookup"><span data-stu-id="accd0-426">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="accd0-427">Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-427">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="accd0-428">Se você estiver criando uma agenda personalizada, digite as horas **de** Abertura e **Fechamento** quando o grupo de resposta estará disponível.</span><span class="sxs-lookup"><span data-stu-id="accd0-428">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group will be available.</span></span>

     > [!NOTE]
     > <span data-ttu-id="accd0-p184">As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.</span><span class="sxs-lookup"><span data-stu-id="accd0-p184">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="accd0-431">Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-431">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-432">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-432">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-p185">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p185">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="accd0-p186">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p186">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-439">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-439">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-440">Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-440">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="accd0-441">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="accd0-441">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="accd0-442">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="accd0-442">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="accd0-443">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="accd0-443">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="accd0-444">O formato do endereço da caixa postal *\<username\>* @ *\<domainname\>* é (por exemplo, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-444">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="accd0-445">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="accd0-445">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="accd0-446">O formato para o endereço do usuário é _\<username\>_ @ _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="accd0-446">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="accd0-447">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="accd0-447">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="accd0-448">O formato do número de telefone *\<number\>* @ *\<domainname\>* é (por exemplo, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-448">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="accd0-449">O nome do domínio é usado para encaminhar o chamador ao destino correto.</span><span class="sxs-lookup"><span data-stu-id="accd0-449">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="accd0-450">Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.</span><span class="sxs-lookup"><span data-stu-id="accd0-450">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-451">É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="accd0-451">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="accd0-452">Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados.</span><span class="sxs-lookup"><span data-stu-id="accd0-452">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="accd0-453">Para obter detalhes, consulte [(Opcional) Definir conjuntos de feriados do Grupo de Resposta no Skype for Business.](optional-define-response-group-holiday-sets.md)</span><span class="sxs-lookup"><span data-stu-id="accd0-453">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="accd0-454">Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-454">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-455">Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-455">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-p192">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p192">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="accd0-p193">Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p193">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-462">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-462">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-463">Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-463">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="accd0-464">Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):</span><span class="sxs-lookup"><span data-stu-id="accd0-464">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="accd0-465">Para desconectar a chamada, clique em **Desconectar Chamada**.</span><span class="sxs-lookup"><span data-stu-id="accd0-465">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="accd0-466">Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="accd0-466">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="accd0-467">O formato do endereço da caixa postal *\<username\>* @ *\<domainname\>* é (por exemplo, bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-467">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="accd0-468">Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário.</span><span class="sxs-lookup"><span data-stu-id="accd0-468">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="accd0-469">O formato para o endereço do usuário é _\<username\>_ @ _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="accd0-469">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="accd0-470">Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="accd0-470">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="accd0-471">O formato do número de telefone *\<number\>* @ *\<domainname\>* é (por exemplo, +14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="accd0-471">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="accd0-472">O nome do domínio é usado para encaminhar o chamador ao destino correto.</span><span class="sxs-lookup"><span data-stu-id="accd0-472">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="accd0-473">Sob **Etapa 6 Configure a Música de Espera**, escolha o que deseja que os chamadores ouçam enquanto esperam por um operador, executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-473">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="accd0-474">Para usar a gravação padrão de música em espera, clique em **Usar padrão**.</span><span class="sxs-lookup"><span data-stu-id="accd0-474">To use the default music on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="accd0-p198">Para usar uma gravação de arquivo de áudio como música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="accd0-p198">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-479">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-479">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-480">Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-480">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

28. <span data-ttu-id="accd0-481">Sob **Etapa 7 Configure a Resposta Interativa de Voz**, sob o cabeçalho **O usuário ouvirá o seguinte texto ou mensagem gravada**, especifique a pergunta a ser feita aos chamadores da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="accd0-481">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>

    - <span data-ttu-id="accd0-482">Para digitar uma pergunta em formato de texto, clique em **Usar conversão de texto em fala** e digite a pergunta na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="accd0-482">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-p200">Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="accd0-p200">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-485">O símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número".</span><span class="sxs-lookup"><span data-stu-id="accd0-485">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="accd0-486">Se for necessário fazer referência à tecla #, use o nome da tecla no prompt, em vez do símbolo.</span><span class="sxs-lookup"><span data-stu-id="accd0-486">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="accd0-487">Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."</span><span class="sxs-lookup"><span data-stu-id="accd0-487">For example, "To talk to sales, press the pound key."</span></span>

    - <span data-ttu-id="accd0-488">Para usar um arquivo de áudio pré-gravado que contenha a pergunta, clique em **Selecionar uma gravação** e clique no link **uma gravação** para carregar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="accd0-488">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="accd0-489">Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="accd0-489">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="accd0-490">Clique **em** Carregar para carregar o arquivo e, opcionalmente, você pode digitar a pergunta na caixa de texto (isso permite que a pergunta e a resposta do chamador sejam encaminhadas para o agente de resposta).</span><span class="sxs-lookup"><span data-stu-id="accd0-490">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller's response, to be forwarded to the responding agent).</span></span>

      > [!NOTE]
      > <span data-ttu-id="accd0-491">Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="accd0-491">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="accd0-492">Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span><span class="sxs-lookup"><span data-stu-id="accd0-492">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="accd0-493">Em **Resposta 1**, especifique a primeira resposta possível para a pergunta executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="accd0-493">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="accd0-p204">Não use aspas (") em qualquer resposta de voz. Aspas podem provocar falhas no IVR.</span><span class="sxs-lookup"><span data-stu-id="accd0-p204">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="accd0-496">Você pode optar por permitir que os chamadores respondam usando a fala, entradas do teclado alfanumérico ou ambos.</span><span class="sxs-lookup"><span data-stu-id="accd0-496">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    - <span data-ttu-id="accd0-497">Se desejar permitir que o chamador responda usando a fala, insira a resposta em **Insira uma resposta de voz**.</span><span class="sxs-lookup"><span data-stu-id="accd0-497">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>

    - <span data-ttu-id="accd0-498">Se você desejar permitir que o chamador responda pressionando uma tecla no teclado, em **Dígito**, clique no dígito do teclado.</span><span class="sxs-lookup"><span data-stu-id="accd0-498">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="accd0-499">Especifique se o chamador será encaminhado para uma fila ou se será feita outra pergunta, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="accd0-499">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>

    - <span data-ttu-id="accd0-500">Para rotear o chamador para uma fila, clique em **Enviar para uma fila** e, em **Selecione uma fila**, clique na fila que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="accd0-500">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>

    - <span data-ttu-id="accd0-p205">Para fazer outra pergunta, clique em **Fazer outra pergunta**, clique em **Use conversão de texto em fala** e digite a pergunta ou clique em **Selecione uma gravação**. Use os agrupamentos de resposta nesta seção para especificar até quatro possíveis respostas para a pergunta adicional e a fila a ser usada para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na opção **Resposta 3** ou **Resposta 4**.</span><span class="sxs-lookup"><span data-stu-id="accd0-p205">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="accd0-p206">Especifique até três mais respostas possíveis para a pergunta original, repetindo as etapas 28 e 29 para especificar as possíveis respostas e a ação para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na caixa de seleção **Resposta 3** ou **Resposta 4**.</span><span class="sxs-lookup"><span data-stu-id="accd0-p206">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="accd0-506">Clique em **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="accd0-506">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="accd0-507">Para usar o Shell de Gerenciamento do Skype for Business Server para criar ou modificar um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="accd0-507">To use Skype for Business Server Management Shell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="accd0-508">Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-508">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="accd0-509">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="accd0-509">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="accd0-p207">Recupere o nome do serviço do serviço de Grupo de resposta e atribua-o a uma variável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p207">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. <span data-ttu-id="accd0-p208">Um fluxo de trabalho interativo requer duas ou mais filas e dois ou mais grupos de agentes. Primeiro, crie os grupos de agentes. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p208">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. <span data-ttu-id="accd0-p209">Crie as filas. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p209">Create the queues. Run:</span></span>

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. <span data-ttu-id="accd0-p210">Crie o primeiro prompt de grupo de resposta. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p210">Create the first response group prompt. Run:</span></span>

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. <span data-ttu-id="accd0-p211">Em seguida, crie a ação que será executada depois do prompt. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p211">Then create the action to be performed after the prompt. Run:</span></span>

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. <span data-ttu-id="accd0-p212">Crie a primeira resposta do grupo de resposta. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p212">Create the first response group answer. Run:</span></span>

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. <span data-ttu-id="accd0-p213">Agora crie o segundo prompt, a ação da chamada e a resposta. Primeiro crie o prompt. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p213">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. <span data-ttu-id="accd0-p214">Crie a segunda ação de chamada. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p214">Create the second call action. Run:</span></span>

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. <span data-ttu-id="accd0-p215">Crie a segunda resposta do grupo de resposta. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p215">Create the second response group answer. Run:</span></span>

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. <span data-ttu-id="accd0-p216">Crie o prompt do nível superior. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p216">Create the top-level prompt. Run:</span></span>

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. <span data-ttu-id="accd0-p217">Crie a pergunta do nível superior. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p217">Create the top-level question. Run:</span></span>

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. <span data-ttu-id="accd0-p218">Agora crie o fluxo de trabalho. Execute:</span><span class="sxs-lookup"><span data-stu-id="accd0-p218">Now create the workflow. Run:</span></span>

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > <span data-ttu-id="accd0-536">Todos os usuários designados como gerentes de um grupo de resposta devem ter a função CsResponseGroupManager atribuída.</span><span class="sxs-lookup"><span data-stu-id="accd0-536">All users who have been designated as manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="accd0-537">Se os usuário não têm essa função, não será possível gerenciar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="accd0-537">If users are not assigned this role, they cannot manage response groups.</span></span>

## <a name="see-also"></a><span data-ttu-id="accd0-538">Confira também</span><span class="sxs-lookup"><span data-stu-id="accd0-538">See also</span></span>

[<span data-ttu-id="accd0-539">(Opcional) Definir conjuntos de feriados do Grupo de Resposta no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="accd0-539">(Optional) Define Response Group holiday sets in Skype for Business</span></span>](optional-define-response-group-holiday-sets.md)

[<span data-ttu-id="accd0-540">(Opcional) Definir o horário comercial do Grupo de Resposta no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="accd0-540">(Optional) Define Response Group business hours in Skype for Business</span></span>](optional-define-response-group-business-hours.md)

[<span data-ttu-id="accd0-541">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="accd0-541">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="accd0-542">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="accd0-542">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="accd0-543">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="accd0-543">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[<span data-ttu-id="accd0-544">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="accd0-544">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

