---
title: Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
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
ms.openlocfilehash: f8e7e3576640e4c560cd620349f5c3afdaf541cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816321"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8b83d-103">Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b83d-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="8b83d-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="8b83d-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="8b83d-106">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="8b83d-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="8b83d-107">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="8b83d-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="8b83d-108">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="8b83d-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="8b83d-109">Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você.</span><span class="sxs-lookup"><span data-stu-id="8b83d-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8b83d-110">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="8b83d-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="8b83d-111">No entanto, você pode usar o Painel Do Skype for Business ServerControl ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) para "redefinir" as propriedades na coleção global com seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="8b83d-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="8b83d-112">Por exemplo, se você tiver definido a propriedade Enable3pccRefer como True, quando você redefinir a coleção global, a propriedade Enable3pccRefer será revertida para seu valor padrão de False.</span><span class="sxs-lookup"><span data-stu-id="8b83d-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="8b83d-113">Os administradores também podem criar definições de configuração de tronco personalizadas no escopo do site ou no escopo de serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="8b83d-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="8b83d-114">Ao remover essas configurações personalizadas, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b83d-114">When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="8b83d-115">Se você remover as configurações de escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam.</span><span class="sxs-lookup"><span data-stu-id="8b83d-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="8b83d-116">Se as configurações de site não existirem, esses troncos serão gerenciados pelo conjunto global de definições de configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="8b83d-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="8b83d-117">Se você remover as definições de escopo do site, todos os troncos SIP gerenciados por essas configurações agora serão gerenciados pelo conjunto global de definições de configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="8b83d-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="8b83d-118">**Para remover as definições de configuração de tronco com o Painel de Controle do Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="8b83d-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="8b83d-119">No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e em **Configuração de Tronco.**</span><span class="sxs-lookup"><span data-stu-id="8b83d-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="8b83d-120">Na guia **Configuração do** Tronco, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="8b83d-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="8b83d-121">Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída, mantenha a tecla Ctrl e clique nas coleções adicionais que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="8b83d-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="8b83d-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="8b83d-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="8b83d-124">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b83d-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="8b83d-125">Na caixa de diálogo Painel de **Controle do Skype for Business Server,** clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="8b83d-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="8b83d-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="8b83d-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="8b83d-127">Quando a caixa de diálogo Painel de Controle do **Skype for Business Server** for exibida, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="8b83d-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8b83d-128">Removendo definições de configuração de tronco usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b83d-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="8b83d-129">Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="8b83d-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="8b83d-130">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b83d-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="8b83d-131">**Para remover um conjunto especificado de configurações**</span><span class="sxs-lookup"><span data-stu-id="8b83d-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="8b83d-132">O comando a seguir remove as definições de configuração de tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="8b83d-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="8b83d-133">**Para remover todos os coleções aplicados ao escopo do site**</span><span class="sxs-lookup"><span data-stu-id="8b83d-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="8b83d-134">Este comando remove todas as definições de configuração de tronco aplicadas ao escopo de serviço:</span><span class="sxs-lookup"><span data-stu-id="8b83d-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="8b83d-135">**Para remover todas as coleções onde o bypass de mídia está habilitado**</span><span class="sxs-lookup"><span data-stu-id="8b83d-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="8b83d-136">O comando a seguir remove todas as definições de configuração de tronco onde o bypass de mídia foi habilitado:</span><span class="sxs-lookup"><span data-stu-id="8b83d-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="8b83d-137">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="8b83d-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
