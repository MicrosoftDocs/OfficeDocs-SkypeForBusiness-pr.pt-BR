---
title: 'Lync Server 2013: criar ou modificar uma política de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898ffb4473fadd4470ef7e1559fa3cc0c54185c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="94b82-102">Criar ou modificar uma política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94b82-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94b82-103">_**Tópico da última modificação:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="94b82-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="94b82-104">Siga estas etapas para criar uma política de conferência em nível de usuário ou em nível de site.</span><span class="sxs-lookup"><span data-stu-id="94b82-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="94b82-105">Para obter detalhes sobre como atribuir uma política de nível de usuário a um usuário, consulte [atribuir uma política de conferência por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="94b82-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="94b82-106">Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="94b82-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="94b82-107">Para criar uma nova política de usuário ou de site</span><span class="sxs-lookup"><span data-stu-id="94b82-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="94b82-108">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="94b82-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="94b82-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94b82-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94b82-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94b82-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="94b82-111">Na barra de navegação à esquerda, clique em **conferência** e, em seguida, clique em **política de conferência**.</span><span class="sxs-lookup"><span data-stu-id="94b82-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="94b82-112">Clique em **Novo** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="94b82-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="94b82-p103">Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="94b82-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="94b82-p104">Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94b82-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="94b82-118">O nome do site se torna o nome da política de conferência e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="94b82-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="94b82-119">Em **Descrição**, digite uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="94b82-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="94b82-p105">Em **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.</span><span class="sxs-lookup"><span data-stu-id="94b82-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="94b82-122">Para impedir que usuários convidem usuários anônimos para reuniões, desmarque a opção **Permitir que participantes convidem usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="94b82-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="94b82-123">Usuários anônimos são usuários que não têm credenciais nos serviços de domínio do Active Directory da sua organização e quem, portanto, não são autenticados.</span><span class="sxs-lookup"><span data-stu-id="94b82-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="94b82-124">Por padrão, usuários podem convidar usuários anônimos para reuniões.</span><span class="sxs-lookup"><span data-stu-id="94b82-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="94b82-125">Em **Gravação**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="94b82-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="94b82-p107">Para impedir que os participantes gravem reuniões, clique em **Nenhuma**. Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="94b82-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="94b82-128">Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.</span><span class="sxs-lookup"><span data-stu-id="94b82-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="94b82-p108">Para permitir que participantes externos gravem reuniões, selecione a opção **Permitir que participantes federados e anônimos gravem**. O padrão é impedir que participantes externos gravem reuniões.</span><span class="sxs-lookup"><span data-stu-id="94b82-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="94b82-131">Em **Áudio/vídeo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="94b82-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="94b82-132">Para impedir o uso de áudio e vídeo, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="94b82-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="94b82-133">Para permitir o uso de áudio mas não de vídeo, clique em **Habilitar áudio IP**.</span><span class="sxs-lookup"><span data-stu-id="94b82-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="94b82-p109">Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="94b82-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="94b82-136">Se você optar por permitir o uso de áudio em **Áudio/vídeo**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="94b82-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="94b82-p110">Para impedir os usuários de entrar em uma reunião discando, desmarque a opção **Habilitar conferências discadas PSTN**. Por padrão, os usuários podem discar para reuniões usando a rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="94b82-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="94b82-p111">Se for permitido que usuários disquem para reuniões e você desejar permitir que usuários não autenticados (anônimos) entrem em reuniões usando dial out phoning, selecione a opção **Permitir que participantes anônimos façam chamadas**. Com o dial-out phoning, o servidor de conferências faz uma chamada para o usuário e o usuário atende o telefone para e entrar na reunião. Por padrão, usuários anônimos não podem entrar em uma reunião usando dial-out phoning.</span><span class="sxs-lookup"><span data-stu-id="94b82-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="94b82-142">Se você optou por permitir o uso de vídeo em **áudio/vídeo**, marque **permitir vários fluxos de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="94b82-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="94b82-143">Em **Colaboração de Dados**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="94b82-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="94b82-144">Para impedir a colaboração de dados, clique em **Nenhuma**.</span><span class="sxs-lookup"><span data-stu-id="94b82-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="94b82-p112">Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="94b82-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="94b82-147">Se você optar por permitir a colaboração de dados em **Colaboração de Dados**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="94b82-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="94b82-p113">Para impedir downloads externos, desmarque a opção **Permitir que participantes federados e anônimos façam download de conteúdo**. Por padrão, usuários externos não podem fazer download de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="94b82-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="94b82-p114">Para impedir transferências de arquivos, desmarque a opção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="94b82-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="94b82-152">Para impedir o uso de anotações, desmarque a opção **Habilitar anotações**.</span><span class="sxs-lookup"><span data-stu-id="94b82-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="94b82-153">Para o uso de anotações nas apresentações do PowerPoint de fragmentos, desmarque a guia **habilitar anotações do PowerPoint**.</span><span class="sxs-lookup"><span data-stu-id="94b82-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="94b82-154">Por padrão, as anotações são permitidas.</span><span class="sxs-lookup"><span data-stu-id="94b82-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="94b82-p116">Para impedir o uso de votações, desmarque a opção **Habilitar votações**. Por padrão, votações são permitidas.</span><span class="sxs-lookup"><span data-stu-id="94b82-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="94b82-157">Em **Compartilhamento de aplicativos**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="94b82-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="94b82-158">Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="94b82-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="94b82-p117">Para permitir o uso de compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="94b82-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="94b82-161">Se você optar por permitir o compartilhamento de aplicativos em **Compartilhamento de aplicativos**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="94b82-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="94b82-p118">Para impedir que participantes de reuniões assumam o controle do compartilhamento de aplicativos, desmarque a opção **Permitir que participantes assumam o controle**. Por padrão, os participantes podem assumir o controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="94b82-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="94b82-p119">Se você optar por permitir que os participantes de uma reunião assumam o controle do compartilhamento de aplicativos, selecione a opção **Permitir que participantes federados e anônimos assumam o controle** para permitir que usuários externos assumam o controle do compartilhamento de aplicativos. Por padrão, usuários externos não podem assumir o controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="94b82-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="94b82-166">Sob **Política do participante**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="94b82-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="94b82-167">Para impedir ambos, compartilhamento de aplicativos e de área de trabalho, clique em **Desabilitar compartilhamento de aplicativos e da área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="94b82-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="94b82-168">Para permitir o compartilhamento de aplicativos mas não da área de trabalho, clique em **Habilitar compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="94b82-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="94b82-p120">Para permitir ambos, compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="94b82-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="94b82-p121">Para impedir transferências de arquivo ponto a ponto, desmarque a opção **Habilitar transferências de arquivos ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.</span><span class="sxs-lookup"><span data-stu-id="94b82-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="94b82-p122">Para permitir a gravação ponto a ponto, selecione a opção **Habilitar gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="94b82-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="94b82-p123">Para permitir que os participantes façam parte de vários fluxos de vídeo, marque a caixa de seleção **Habilitar os participantes a se unir a vários fluxos de vídeo**. Por padrão, vários fluxos de vídeo são permitidos.</span><span class="sxs-lookup"><span data-stu-id="94b82-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="94b82-177">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="94b82-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="94b82-178">Para modificar uma política de usuário ou de site existente</span><span class="sxs-lookup"><span data-stu-id="94b82-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="94b82-179">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="94b82-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="94b82-180">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94b82-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="94b82-181">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94b82-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="94b82-182">Na barra de navegação à esquerda, clique em **conferência** e, em seguida, clique em **política de conferência**.</span><span class="sxs-lookup"><span data-stu-id="94b82-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="94b82-183">Na lista de políticas de conferência, clique na política que deseja alterar, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="94b82-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="94b82-184">Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="94b82-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="94b82-185">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="94b82-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

