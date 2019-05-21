---
title: Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumo: saiba como excluir uma coleção de definições de configuração de tronco usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: 830f5c42e26c4ef7a5ffca0a57fc7e70c2509f83
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280457"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="577d5-103">Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="577d5-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="577d5-104">**Resumo:** Saiba como excluir uma coleção de definições de configuração de tronco usando o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="577d5-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="577d5-p101">As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="577d5-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="577d5-107">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="577d5-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="577d5-108">As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="577d5-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="577d5-109">Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="577d5-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="577d5-110">Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="577d5-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="577d5-111">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="577d5-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="577d5-112">No entanto, você pode usar o painel de controle do Skype for Business Server ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) para "redefinir" as propriedades na coleção global para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="577d5-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="577d5-113">Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.</span><span class="sxs-lookup"><span data-stu-id="577d5-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="577d5-p103">Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="577d5-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="577d5-p104">Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="577d5-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="577d5-118">Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="577d5-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="577d5-119">Para remover as definições de configuração de tronco com o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="577d5-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="577d5-120">No painel de controle do Skype for Business Server, clique em **Roteamento de voz** e, em seguida, clique em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="577d5-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="577d5-p105">Na guia **Configuração do Tronco**, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e, então, clique em **Excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="577d5-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="577d5-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="577d5-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="577d5-125">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="577d5-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="577d5-126">Na caixa de diálogo **painel de controle do Skype for Business Server** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="577d5-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="577d5-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="577d5-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="577d5-128">Quando a caixa de diálogo **painel de controle do Skype for Business Server** for exibida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="577d5-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="577d5-129">Como remover as configurações de tronco usando cmdlets do Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="577d5-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="577d5-130">Você pode excluir as definições de configuração de tronco usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="577d5-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="577d5-131">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="577d5-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="577d5-132">Para remover uma coleção especificada das definições</span><span class="sxs-lookup"><span data-stu-id="577d5-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="577d5-133">O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="577d5-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="577d5-134">Para remover todos os conjuntos aplicados ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="577d5-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="577d5-135">Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="577d5-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="577d5-136">Para remover todos os conjuntos em que o bypass de mídia está habilitado</span><span class="sxs-lookup"><span data-stu-id="577d5-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="577d5-137">O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:</span><span class="sxs-lookup"><span data-stu-id="577d5-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="577d5-138">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="577d5-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

