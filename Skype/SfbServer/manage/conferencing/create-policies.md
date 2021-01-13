---
title: Criar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumo: saiba como criar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 8e707e6da1a56fa1818d436714327936369b06fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828231"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="5fc72-103">Criar políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fc72-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="5fc72-104">**Resumo:** Saiba como criar políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5fc72-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="5fc72-105">Você pode criar políticas de conferência usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5fc72-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5fc72-106">Criar políticas de conferência usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fc72-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5fc72-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5fc72-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5fc72-108">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5fc72-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5fc72-109">Na barra de navegação esquerda, clique **em Conferência e** em Política de **Conferência.**</span><span class="sxs-lookup"><span data-stu-id="5fc72-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="5fc72-110">Clique em **Nova** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fc72-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="5fc72-p101">Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="5fc72-p102">Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecione um Site**, digite todo ou parte do nome do site para o qual deseja criar uma política. Na lista de sites, clique no site que deseja e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5fc72-116">O nome do site se torna o nome da política de conferência; ela não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="5fc72-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="5fc72-117">Em **Descrição**, digite uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="5fc72-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="5fc72-p103">Sob **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="5fc72-120">Para impedir que usuários convidem usuários anônimos para a reunião, desmarque a caixa de seleção **Permitir que participantes convidem usuários anônimos**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="5fc72-121">Usuários anônimos são usuários que não têm credenciais nos Serviços de Domínio Active Directory da sua organização e que, portanto, não são autenticados.</span><span class="sxs-lookup"><span data-stu-id="5fc72-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="5fc72-122">Por padrão, os usuários podem convidar usuários anônimos para as reuniões.</span><span class="sxs-lookup"><span data-stu-id="5fc72-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="5fc72-123">Em **Gravação**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fc72-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="5fc72-p105">Para evitar que os participantes gravem reuniões, clique em **Nenhum**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="5fc72-126">Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="5fc72-p106">Para permitir que os participantes externos gravem as reuniões, marque a caixa de seleção **Permitir que participantes anônimos e federados façam gravações**. O padrão é evitar que participantes externos gravem reuniões.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="5fc72-129">Em **Áudio/vídeo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fc72-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="5fc72-130">Para impedir o uso de áudio e vídeo, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="5fc72-131">Para permitir o uso de áudio, mas não de vídeo, clique em **Habilitar áudio IP**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="5fc72-p107">Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="5fc72-134">Se você escolher permitir o uso de áudio em **Áudio/vídeo**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5fc72-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="5fc72-p108">Para impedir que usuários participem da reunião de forma discada, desmarque a caixa de seleção **Habilitar conferência discada PSTN**. Por padrão, os usuários podem participar de forma discada de reuniões usando PSTN.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="5fc72-p109">Se você permitir que os usuários participem de forma discada das reuniões e deseja permitir que usuários não autenticados (anônimos) participem de uma reunião usando uma telefonia discada, marque a caixa de seleção **Permitir que participantes anônimos façam chamadas**. Com a telefonia discada, o servidor de conferência chama o usuário e o usuário atende ao telefone para participar da reunião. Por padrão, usuários anônimos não podem participar de uma reunião usando a telefonia discada.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="5fc72-140">Se você escolher permitir o uso de vídeo em **áudio/vídeo,** verifique **Permitir vários fluxos de vídeo.**</span><span class="sxs-lookup"><span data-stu-id="5fc72-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="5fc72-141">Em **Colaboração de dados**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fc72-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="5fc72-142">Para impedir a colaboração de dados, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="5fc72-p110">Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="5fc72-145">Se você escolher permitir a colaboração de dados em **Colaboração de dados**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5fc72-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="5fc72-p111">Para impedir os downloads externos, desmarque a caixa de seleção **Permitir que participantes anônimos e federados baixem conteúdo**. Por padrão, os usuários externos podem baixar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="5fc72-p112">Para impedir as transferências de arquivo, desmarque a caixa de seleção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="5fc72-150">Para impedir o uso de anotações, desmarque a caixa de seleção **Habilitar anotações**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="5fc72-151">Para o uso de anotações em apresentações compartilhadas do PowerPoint, limpe as **anotações Habilitar PowerPoint.**</span><span class="sxs-lookup"><span data-stu-id="5fc72-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="5fc72-152">Por padrão, as anotações são permitidas.</span><span class="sxs-lookup"><span data-stu-id="5fc72-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="5fc72-p114">Para impedir o uso de pools, desmarque a caixa de seleção **Habilitar pools**. Por padrão, os pools são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="5fc72-155">Em **Compartilhamento de aplicativo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fc72-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="5fc72-156">Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar o compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="5fc72-p115">Para permitir o uso do compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="5fc72-159">Se você escolher permitir o compartilhamento de aplicativos no **Compartilhamento de aplicativos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5fc72-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="5fc72-p116">Para impedir que os participantes da reunião tomem o controle do compartilhamento de aplicativos, desmarque a caixa de seleção **Permitir que os participantes tomem o controle**. Por padrão, os participantes podem tomar o controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="5fc72-p117">Se você escolher permitir que os participantes da reunião tomem o controle do compartilhamento de arquivos, marque a caixa de seleção **Permitir que participantes federados e anônimos tomem o controle** para permitir que usuários externos tomem o controle do compartilhamento de aplicativos. Por padrão, os usuários externos não podem tomar controle do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="5fc72-164">Em **Política do participante**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5fc72-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="5fc72-165">Para impedir o compartilhamento de aplicativos e o compartilhamento da área de trabalho, clique em **Desabilitar o compartilhamento de aplicativos e da área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="5fc72-166">Para permitir o compartilhamento de aplicativos, mas não o compartilhamento da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="5fc72-p118">Para permitir o compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar o compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="5fc72-p119">Para impedir as transferências de arquivo ponto a ponto, desmarque a caixa de seleção **Habilitar a transferência de arquivo ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="5fc72-p120">Para permitir a gravação ponto a ponto, marque a caixa de seleção **Habilitar a gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não é permitida.</span><span class="sxs-lookup"><span data-stu-id="5fc72-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="5fc72-173">Para permitir que os participantes participem com vários fluxos de vídeo, marque a caixa de seleção Habilitar participantes a ingressar com vários **fluxos** de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5fc72-173">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="5fc72-174">Por padrão, vários fluxos de vídeo são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5fc72-174">By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="5fc72-175">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5fc72-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5fc72-176">Criar políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fc72-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5fc72-177">Para criar políticas de conferência, use o cmdlet **New-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="5fc72-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5fc72-178">O exemplo a seguir cria uma nova política de conferência com a Identidade SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="5fc72-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="5fc72-179">Essa política usará todos os valores padrão para uma política de conferência, exceto um: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="5fc72-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="5fc72-180">Neste exemplo, o tamanho máximo de uma reunião será definido como 50, em vez do valor padrão de 250:</span><span class="sxs-lookup"><span data-stu-id="5fc72-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="5fc72-181">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5fc72-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

