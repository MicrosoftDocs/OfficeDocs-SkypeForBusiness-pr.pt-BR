---
title: Excluir um conjunto existente de definições de configuração de tronco SIP no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumo: Saiba como excluir uma coleção de definições de configuração do tronco usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 27e022588798e848cf690bb643d921e46d827b39
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890534"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="84be9-103">Excluir um conjunto existente de definições de configuração de tronco SIP no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="84be9-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="84be9-104">**Resumo:** Saiba como excluir um conjunto de definições de configuração do tronco usando o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="84be9-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="84be9-p101">As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="84be9-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="84be9-107">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="84be9-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="84be9-108">As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="84be9-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="84be9-109">Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="84be9-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="84be9-110">Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="84be9-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="84be9-111">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="84be9-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="84be9-112">No entanto, você pode usar o Skype para painel de controle do Business Server ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) "Redefinir" as propriedades na coleção global para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="84be9-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="84be9-113">Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.</span><span class="sxs-lookup"><span data-stu-id="84be9-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="84be9-p103">Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="84be9-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="84be9-p104">Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="84be9-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="84be9-118">Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="84be9-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="84be9-119">Para remover as definições de configuração do tronco com Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="84be9-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="84be9-120">No painel de controle do servidor de negócios do Skype, clique em **Roteamento de voz** e clique em **Configuração do tronco**.</span><span class="sxs-lookup"><span data-stu-id="84be9-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="84be9-p105">Na guia **Configuração do Tronco**, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e, então, clique em **Excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="84be9-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="84be9-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="84be9-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="84be9-125">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="84be9-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="84be9-126">Na caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="84be9-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="84be9-127">Se mudar de ideia e decidir não excluir o conjunto, clique em **Confirmar** e, depois, em **Cancelar todas as alterações não confirmadas**.</span><span class="sxs-lookup"><span data-stu-id="84be9-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="84be9-128">Quando for exibida a caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="84be9-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="84be9-129">Removendo definições de configuração de tronco usando Skype para Cmdlets do Shell de gerenciamento de servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="84be9-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="84be9-130">Você pode excluir as definições de configuração de tronco usando Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="84be9-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="84be9-131">Você pode executar esse cmdlet seja do Skype para Business Server Management Shell ou de uma sessão remota do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="84be9-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="84be9-132">Para remover uma coleção especificada das definições</span><span class="sxs-lookup"><span data-stu-id="84be9-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="84be9-133">O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="84be9-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="84be9-134">Para remover todos os conjuntos aplicados ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="84be9-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="84be9-135">Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:</span><span class="sxs-lookup"><span data-stu-id="84be9-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="84be9-136">Para remover todos os conjuntos em que o bypass de mídia está habilitado</span><span class="sxs-lookup"><span data-stu-id="84be9-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="84be9-137">O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:</span><span class="sxs-lookup"><span data-stu-id="84be9-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="84be9-138">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="84be9-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

