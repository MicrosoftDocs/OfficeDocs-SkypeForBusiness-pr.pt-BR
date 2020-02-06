---
title: Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. '
ms.openlocfilehash: 5be81bccdb5df94cff4e8a2a13aaabb20dfdce29
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816971"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3bcdf-103">Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bcdf-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="3bcdf-104">As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="3bcdf-105">Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="3bcdf-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="3bcdf-106">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="3bcdf-107">As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="3bcdf-108">Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="3bcdf-109">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="3bcdf-110">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="3bcdf-111">No entanto, você pode usar o painel ServerControl do Skype for Business ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) para "redefinir" as propriedades na coleção global para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="3bcdf-112">Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="3bcdf-p103">Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="3bcdf-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="3bcdf-p104">Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="3bcdf-117">Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="3bcdf-118">**Para remover os parâmetros de configuração de tronco com o painel de controle do Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="3bcdf-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="3bcdf-119">No painel de controle do Skype for Business Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="3bcdf-120">Na guia **configuração de tronco** , selecione a coleção das configurações de tronco SIP a serem excluídas, clique em **Editar**e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="3bcdf-121">Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="3bcdf-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="3bcdf-124">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="3bcdf-125">Na caixa de diálogo **painel de controle do Skype for Business Server** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="3bcdf-126">Se você mudar de ideia e decidir não excluir a coleção, clique em **confirmar**e, em seguida, clique em **cancelar todas as alterações não confirmadas**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="3bcdf-127">Quando a caixa de diálogo **painel de controle do Skype for Business Server** for exibida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3bcdf-128">Como remover as configurações de tronco usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bcdf-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="3bcdf-129">Você pode excluir as definições de configuração de tronco usando o Windows PowerShell e o cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3bcdf-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="3bcdf-130">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bcdf-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="3bcdf-131">**Para remover uma coleção especificada das definições**</span><span class="sxs-lookup"><span data-stu-id="3bcdf-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="3bcdf-132">O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="3bcdf-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="3bcdf-133">**Para remover todos os conjuntos aplicados ao escopo do site**</span><span class="sxs-lookup"><span data-stu-id="3bcdf-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="3bcdf-134">Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="3bcdf-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="3bcdf-135">**Para remover todos os conjuntos em que o bypass de mídia está habilitado**</span><span class="sxs-lookup"><span data-stu-id="3bcdf-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="3bcdf-136">O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:</span><span class="sxs-lookup"><span data-stu-id="3bcdf-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="3bcdf-137">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3bcdf-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
