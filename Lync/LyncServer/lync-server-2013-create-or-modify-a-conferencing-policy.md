---
title: 'Lync Server 2013: criar ou modificar uma política de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 522f1d1240e73775ae1f0976556b882ba00fe1d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="947cd-102">Criar ou modificar uma política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="947cd-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="947cd-103">_**Última modificação do tópico:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="947cd-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="947cd-104">Siga estas etapas para criar uma política de conferência no nível do usuário ou no nível do site.</span><span class="sxs-lookup"><span data-stu-id="947cd-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="947cd-105">Para obter detalhes sobre como atribuir uma política de nível de usuário a um usuário, consulte [atribuir uma política de conferência por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="947cd-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="947cd-106">Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="947cd-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="947cd-107">Para criar uma nova política de usuário ou de site</span><span class="sxs-lookup"><span data-stu-id="947cd-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="947cd-108">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="947cd-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="947cd-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947cd-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="947cd-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="947cd-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="947cd-111">Na barra de navegação esquerda, clique em **Conferência** e em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="947cd-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="947cd-112">Clique em **Nova** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="947cd-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="947cd-p103">Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="947cd-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="947cd-p104">Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecione um Site**, digite todo ou parte do nome do site para o qual deseja criar uma política. Na lista de sites, clique no site que deseja e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="947cd-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="947cd-118">O nome do site se tornará o nome da política de conferências e não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="947cd-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="947cd-119">Em **Descrição**, digite uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="947cd-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="947cd-p105">Sob **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.</span><span class="sxs-lookup"><span data-stu-id="947cd-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="947cd-122">Para impedir que usuários convidem usuários anônimos para a reunião, desmarque a caixa de seleção **Permitir que participantes convidem usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="947cd-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="947cd-123">Usuários anônimos são usuários que não possuem credenciais nos serviços de domínio do Active Directory da sua organização e que, portanto, não são autenticados.</span><span class="sxs-lookup"><span data-stu-id="947cd-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="947cd-124">Por padrão, os usuários podem convidar usuários anônimos para as reuniões.</span><span class="sxs-lookup"><span data-stu-id="947cd-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="947cd-125">Em **Gravação**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="947cd-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="947cd-p107">Para evitar que os participantes gravem reuniões, clique em **Nenhum**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="947cd-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="947cd-128">Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.</span><span class="sxs-lookup"><span data-stu-id="947cd-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="947cd-p108">Para permitir que os participantes externos gravem as reuniões, marque a caixa de seleção **Permitir que participantes anônimos e federados façam gravações**. O padrão é evitar que participantes externos gravem reuniões.</span><span class="sxs-lookup"><span data-stu-id="947cd-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="947cd-131">Em **Áudio/vídeo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="947cd-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="947cd-132">Para impedir o uso de áudio e vídeo, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="947cd-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="947cd-133">Para permitir o uso de áudio, mas não de vídeo, clique em **Habilitar áudio IP**.</span><span class="sxs-lookup"><span data-stu-id="947cd-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="947cd-p109">Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="947cd-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="947cd-136">Se você escolher permitir o uso de áudio em **Áudio/vídeo**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="947cd-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="947cd-p110">Para impedir que usuários participem da reunião de forma discada, desmarque a caixa de seleção **Habilitar conferência discada PSTN**. Por padrão, os usuários podem participar de forma discada de reuniões usando PSTN.</span><span class="sxs-lookup"><span data-stu-id="947cd-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="947cd-p111">Se você permitir que os usuários participem de forma discada das reuniões e deseja permitir que usuários não autenticados (anônimos) participem de uma reunião usando uma telefonia discada, marque a caixa de seleção **Permitir que participantes anônimos façam chamadas**. Com a telefonia discada, o servidor de conferência chama o usuário e o usuário atende ao telefone para participar da reunião. Por padrão, usuários anônimos não podem participar de uma reunião usando a telefonia discada.</span><span class="sxs-lookup"><span data-stu-id="947cd-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="947cd-142">Se você optar por permitir o uso de vídeo em **áudio/vídeo**, marque **permitir vários fluxos de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="947cd-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="947cd-143">Em **Colaboração de dados**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="947cd-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="947cd-144">Para impedir a colaboração de dados, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="947cd-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="947cd-p112">Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="947cd-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="947cd-147">Se você escolher permitir a colaboração de dados em **Colaboração de dados**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="947cd-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="947cd-p113">Para impedir os downloads externos, desmarque a caixa de seleção **Permitir que participantes anônimos e federados baixem conteúdo**. Por padrão, os usuários externos podem baixar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="947cd-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="947cd-p114">Para impedir as transferências de arquivo, desmarque a caixa de seleção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="947cd-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="947cd-152">Para impedir o uso de anotações, desmarque a caixa de seleção **Habilitar anotações**.</span><span class="sxs-lookup"><span data-stu-id="947cd-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="947cd-153">Para o uso de anotações em fragmentar apresentações do PowerPoint, desmarque a **habilitar anotações do PowerPoint**.</span><span class="sxs-lookup"><span data-stu-id="947cd-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="947cd-154">Por padrão, as anotações são permitidas.</span><span class="sxs-lookup"><span data-stu-id="947cd-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="947cd-p116">Para impedir o uso de pools, desmarque a caixa de seleção **Habilitar pools**. Por padrão, os pools são permitidos.</span><span class="sxs-lookup"><span data-stu-id="947cd-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="947cd-157">Em **Compartilhamento de aplicativo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="947cd-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="947cd-158">Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar o compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="947cd-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="947cd-p117">Para permitir o uso do compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="947cd-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="947cd-161">Se você escolher permitir o compartilhamento de aplicativos no **Compartilhamento de aplicativos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="947cd-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="947cd-p118">Para impedir que os participantes da reunião tomem o controle do compartilhamento de aplicativos, desmarque a caixa de seleção **Permitir que os participantes tomem o controle**. Por padrão, os participantes podem tomar o controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="947cd-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="947cd-p119">Se você escolher permitir que os participantes da reunião tomem o controle do compartilhamento de arquivos, marque a caixa de seleção **Permitir que participantes federados e anônimos tomem o controle** para permitir que usuários externos tomem o controle do compartilhamento de aplicativos. Por padrão, os usuários externos não podem tomar controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="947cd-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="947cd-166">Em **Política do participante**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="947cd-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="947cd-167">Para impedir o compartilhamento de aplicativos e o compartilhamento da área de trabalho, clique em **Desabilitar o compartilhamento de aplicativos e da área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="947cd-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="947cd-168">Para permitir o compartilhamento de aplicativos, mas não o compartilhamento da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="947cd-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="947cd-p120">Para permitir o compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="947cd-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="947cd-p121">Para impedir as transferências de arquivo ponto a ponto, desmarque a caixa de seleção **Habilitar a transferência de arquivo ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.</span><span class="sxs-lookup"><span data-stu-id="947cd-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="947cd-p122">Para permitir a gravação ponto a ponto, marque a caixa de seleção **Habilitar a gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não é permitida.</span><span class="sxs-lookup"><span data-stu-id="947cd-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="947cd-175">Para permitir que os participantes ingressem com vários fluxos de vídeo, marque a caixa de seleção **permitir que os participantes ingressem com vários fluxos de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="947cd-175">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="947cd-176">Por padrão, vários fluxos de vídeo são permitidos.</span><span class="sxs-lookup"><span data-stu-id="947cd-176">By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="947cd-177">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="947cd-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="947cd-178">Para modificar uma política de usuário ou de site existente</span><span class="sxs-lookup"><span data-stu-id="947cd-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="947cd-179">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="947cd-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="947cd-180">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947cd-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="947cd-181">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="947cd-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="947cd-182">Na barra de navegação esquerda, clique em **Conferência** e em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="947cd-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="947cd-183">Na lista de políticas de conferência, clique na política que deseja alterar, clique em **Editar**e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="947cd-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="947cd-184">Em **Editar Política de Conferências**, modifique qualquer uma das configurações de política, exceto seu nome, que não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="947cd-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="947cd-185">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="947cd-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

