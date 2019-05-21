---
title: Criar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumo: saiba como criar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 323a50ab779e772ca6149dc4c151f9d42d55df66
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304009"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="986ed-103">Criar políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="986ed-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="986ed-104">**Resumo:** Saiba como criar políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="986ed-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="986ed-105">Você pode criar políticas de conferência usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="986ed-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="986ed-106">Criar políticas de conferência usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="986ed-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="986ed-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="986ed-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="986ed-108">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="986ed-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="986ed-109">Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="986ed-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="986ed-110">Clique em **Novo** e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="986ed-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="986ed-p101">Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="986ed-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="986ed-p102">Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="986ed-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="986ed-116">O nome do site se tornará o nome da política de conferências e não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="986ed-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="986ed-117">Em **Descrição**, digite uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="986ed-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="986ed-p103">Em **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.</span><span class="sxs-lookup"><span data-stu-id="986ed-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="986ed-120">Para impedir que usuários convidem usuários anônimos para reuniões, desmarque a opção **Permitir que participantes convidem usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="986ed-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="986ed-121">Usuários anônimos são usuários que não têm credenciais nos serviços de domínio do Active Directory da sua organização e quem, portanto, não são autenticados.</span><span class="sxs-lookup"><span data-stu-id="986ed-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="986ed-122">Por padrão, usuários podem convidar usuários anônimos para reuniões.</span><span class="sxs-lookup"><span data-stu-id="986ed-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="986ed-123">Em **Gravação**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="986ed-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="986ed-p105">Para impedir que os participantes gravem reuniões, clique em **Nenhuma**. Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="986ed-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="986ed-126">Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.</span><span class="sxs-lookup"><span data-stu-id="986ed-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="986ed-p106">Para permitir que participantes externos gravem reuniões, selecione a opção **Permitir que participantes federados e anônimos gravem**. O padrão é impedir que participantes externos gravem reuniões.</span><span class="sxs-lookup"><span data-stu-id="986ed-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="986ed-129">Em **Áudio/vídeo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="986ed-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="986ed-130">Para impedir o uso de áudio e vídeo, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="986ed-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="986ed-131">Para permitir o uso de áudio mas não de vídeo, clique em **Habilitar áudio IP**.</span><span class="sxs-lookup"><span data-stu-id="986ed-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="986ed-p107">Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="986ed-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="986ed-134">Se você optar por permitir o uso de áudio em **Áudio/vídeo**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="986ed-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="986ed-p108">Para impedir os usuários de entrar em uma reunião discando, desmarque a opção **Habilitar conferências discadas PSTN**. Por padrão, os usuários podem discar para reuniões usando a rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="986ed-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="986ed-p109">Se for permitido que usuários disquem para reuniões e você desejar permitir que usuários não autenticados (anônimos) entrem em reuniões usando dial out phoning, selecione a opção **Permitir que participantes anônimos façam chamadas**. Com o dial-out phoning, o servidor de conferências faz uma chamada para o usuário e o usuário atende o telefone para e entrar na reunião. Por padrão, usuários anônimos não podem entrar em uma reunião usando dial-out phoning.</span><span class="sxs-lookup"><span data-stu-id="986ed-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="986ed-140">Se você escolher permitir o uso de vídeo em **Áudio/vídeo**, marque **Permitir vários fluxos de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="986ed-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="986ed-141">Em **Colaboração de Dados**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="986ed-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="986ed-142">Para impedir a colaboração de dados, clique em **Nenhuma**.</span><span class="sxs-lookup"><span data-stu-id="986ed-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="986ed-p110">Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Essa é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="986ed-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="986ed-145">Se você optar por permitir a colaboração de dados em **Colaboração de Dados**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="986ed-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="986ed-p111">Para impedir downloads externos, desmarque a opção **Permitir que participantes federados e anônimos façam download de conteúdo**. Por padrão, usuários externos não podem fazer download de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="986ed-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="986ed-p112">Para impedir transferências de arquivos, desmarque a opção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="986ed-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="986ed-p113">Para impedir o uso de anotações, desmarque a opção **Habilitar anotações**. Para usar as anotações em apresentações do PowerPoint compartilhadas, marque **Habilitar anotações do PowerPoint**. Por padrão, as anotações são permitidas.</span><span class="sxs-lookup"><span data-stu-id="986ed-p113">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="986ed-p114">Para impedir o uso de votações, desmarque a opção **Habilitar votações**. Por padrão, votações são permitidas.</span><span class="sxs-lookup"><span data-stu-id="986ed-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="986ed-155">Em **Compartilhamento de aplicativos**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="986ed-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="986ed-156">Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="986ed-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="986ed-p115">Para permitir o uso de compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="986ed-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="986ed-159">Se você optar por permitir o compartilhamento de aplicativos em **Compartilhamento de aplicativos**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="986ed-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="986ed-p116">Para impedir que participantes de reuniões assumam o controle do compartilhamento de aplicativos, desmarque a opção **Permitir que participantes assumam o controle**. Por padrão, os participantes podem assumir o controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="986ed-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="986ed-p117">Se você optar por permitir que os participantes de uma reunião assumam o controle do compartilhamento de aplicativos, selecione a opção **Permitir que participantes federados e anônimos assumam o controle** para permitir que usuários externos assumam o controle do compartilhamento de aplicativos. Por padrão, usuários externos não podem assumir o controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="986ed-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="986ed-164">Sob **Política do participante**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="986ed-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="986ed-165">Para impedir ambos, compartilhamento de aplicativos e de área de trabalho, clique em **Desabilitar compartilhamento de aplicativos e da área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="986ed-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="986ed-166">Para permitir o compartilhamento de aplicativos mas não da área de trabalho, clique em **Habilitar compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="986ed-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="986ed-p118">Para permitir ambos, compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="986ed-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="986ed-p119">Para impedir transferências de arquivo ponto a ponto, desmarque a opção **Habilitar transferências de arquivos ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.</span><span class="sxs-lookup"><span data-stu-id="986ed-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="986ed-p120">Para permitir a gravação ponto a ponto, selecione a opção **Habilitar gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="986ed-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="986ed-p121">Para permitir que os participantes façam parte de vários fluxos de vídeo, marque a caixa de seleção **Habilitar os participantes a se unir a vários fluxos de vídeo**. Por padrão, vários fluxos de vídeo são permitidos.</span><span class="sxs-lookup"><span data-stu-id="986ed-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="986ed-175">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="986ed-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="986ed-176">Criar políticas de conferência usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="986ed-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="986ed-177">Para criar políticas de conferência, use o cmdlet **New-Cs ConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="986ed-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="986ed-178">O exemplo a seguir cria uma nova política de conferência com o SalesConferencingPolicy de identidade.</span><span class="sxs-lookup"><span data-stu-id="986ed-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="986ed-179">Essa política utilizará todos os valores padrão em uma política de conferência, exceto um: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="986ed-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="986ed-180">Nesse exemplo, o tamanho máximo de uma reunião será definido como 50, em vez do valor padrão de 250.:</span><span class="sxs-lookup"><span data-stu-id="986ed-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="986ed-181">Para obter mais informações, incluindo uma descrição completa da sintaxe e lista de parâmetros, veja [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="986ed-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

