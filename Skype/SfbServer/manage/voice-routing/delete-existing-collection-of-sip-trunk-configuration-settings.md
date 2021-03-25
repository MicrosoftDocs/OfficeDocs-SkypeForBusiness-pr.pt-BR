---
title: Excluir uma coleção existente de configurações de tronco SIP no Skype for Business Server
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
description: 'As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. '
ms.openlocfilehash: c24633e598efe8f5bd9f62e7e46651045d24b71b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120893"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f0bc4-103">Excluir uma coleção existente de configurações de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f0bc4-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="f0bc4-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="f0bc4-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="f0bc4-106">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="f0bc4-107">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="f0bc4-108">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f0bc4-109">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f0bc4-110">Essa coleção global de configurações não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="f0bc4-111">No entanto, você pode usar o Painel Skype for Business ServerControl ou o cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) para "redefinir" as propriedades na coleção global para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="f0bc4-112">Por exemplo, se você definiu a propriedade Enable3pccRefer como True, quando você redefinir a coleção global, a propriedade Enable3pccRefer será revertida para seu valor padrão de False.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="f0bc4-113">Os administradores também podem criar configurações personalizadas de tronco no escopo do site ou no escopo do serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="f0bc4-114">Ao remover essas configurações personalizadas, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="f0bc4-114">When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="f0bc4-115">Se você remover as configurações de escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, se elas existirem.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="f0bc4-116">Se as configurações do site não existirem, esses troncos serão gerenciados pela coleção global de configurações de tronco.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="f0bc4-117">Se você remover as configurações com escopo de site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pela coleção global de configurações de tronco.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="f0bc4-118">**Para remover as configurações de tronco com o Painel de Controle do Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="f0bc4-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="f0bc4-119">No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e clique em **Configuração de Tronco.**</span><span class="sxs-lookup"><span data-stu-id="f0bc4-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="f0bc4-120">Na guia **Configuração do** Tronco, selecione a coleção de configurações de tronco SIP a serem excluídas, clique em **Editar** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="f0bc4-121">Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída, segure a tecla Ctrl e clique em quaisquer coleções adicionais que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="f0bc4-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="f0bc4-124">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="f0bc4-125">Na caixa de diálogo Painel de Controle do **Skype for Business Server,** clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="f0bc4-126">Se você mudar de ideia e decidir não excluir a coleção, clique em Confirmação **e,** em seguida, clique em Cancelar Todas as Alterações **Não Confirmados**.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="f0bc4-127">Quando a caixa de diálogo Painel de Controle do **Skype for Business Server** aparecer, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f0bc4-128">Removendo configurações de tronco usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="f0bc4-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="f0bc4-129">Você pode excluir as configurações de tronco usando Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="f0bc4-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="f0bc4-130">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0bc4-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="f0bc4-131">**Para remover uma coleção especificada de configurações**</span><span class="sxs-lookup"><span data-stu-id="f0bc4-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="f0bc4-132">O comando a seguir remove as configurações de tronco aplicadas ao site redmond:</span><span class="sxs-lookup"><span data-stu-id="f0bc4-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="f0bc4-133">**Para remover todas as coleções aplicadas ao escopo do site**</span><span class="sxs-lookup"><span data-stu-id="f0bc4-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="f0bc4-134">Este comando remove todas as configurações de tronco aplicadas ao escopo de serviço:</span><span class="sxs-lookup"><span data-stu-id="f0bc4-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="f0bc4-135">**Para remover todas as coleções em que o bypass de mídia está habilitado**</span><span class="sxs-lookup"><span data-stu-id="f0bc4-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="f0bc4-136">O comando a seguir remove todas as configurações de tronco onde o bypass de mídia foi habilitado:</span><span class="sxs-lookup"><span data-stu-id="f0bc4-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="f0bc4-137">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/Remove-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="f0bc4-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>