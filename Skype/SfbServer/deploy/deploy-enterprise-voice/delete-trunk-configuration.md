---
title: Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumo: Saiba como excluir um conjunto de definições de configuração de tronco usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836971"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3bbac-103">Excluir uma coleção existente de definições de configuração de tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bbac-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3bbac-104">**Resumo:** Saiba como excluir um conjunto de definições de configuração de tronco usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bbac-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="3bbac-105">As definições de configuração do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) da IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="3bbac-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="3bbac-106">Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="3bbac-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="3bbac-107">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="3bbac-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="3bbac-108">As condições sob as quais pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados.</span><span class="sxs-lookup"><span data-stu-id="3bbac-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="3bbac-109">Se a criptografia SRTP (Secure Realtime Transport Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="3bbac-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="3bbac-110">Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você.</span><span class="sxs-lookup"><span data-stu-id="3bbac-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="3bbac-111">Este conjunto global de configurações não pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="3bbac-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="3bbac-112">No entanto, você pode usar o Painel de Controle do Skype for Business Server ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) para "redefinir" as propriedades na coleção global com seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="3bbac-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="3bbac-113">Por exemplo, se você tiver definido a propriedade Enable3pccRefer como True, quando você redefinir a coleção global, a propriedade Enable3pccRefer será revertida para seu valor padrão de False.</span><span class="sxs-lookup"><span data-stu-id="3bbac-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="3bbac-114">Os administradores também podem criar definições de configuração de tronco personalizadas no escopo do site ou no escopo de serviço (para um gateway PSTN individual); essas configurações personalizadas podem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="3bbac-114">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="3bbac-115">Ao remover essas configurações personalizadas, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="3bbac-115">When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="3bbac-116">Se você remover as configurações de escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam.</span><span class="sxs-lookup"><span data-stu-id="3bbac-116">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="3bbac-117">Se as configurações de site não existirem, esses troncos serão gerenciados pelo conjunto global de definições de configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="3bbac-117">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="3bbac-118">Se você remover as definições de escopo do site, todos os troncos SIP gerenciados por essas definições agora serão gerenciados pelo conjunto global de definições de configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="3bbac-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="3bbac-119">Para remover as definições de configuração de tronco com o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bbac-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3bbac-120">No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e em **Configuração de Tronco.**</span><span class="sxs-lookup"><span data-stu-id="3bbac-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="3bbac-121">Na guia **Configuração do** Tronco, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="3bbac-121">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="3bbac-122">Para excluir várias coleções na mesma operação, clique na primeira coleção a ser excluída, mantenha a tecla Ctrl e clique nas coleções adicionais que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="3bbac-122">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="3bbac-p106">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="3bbac-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="3bbac-125">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bbac-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="3bbac-126">Na caixa **de diálogo Painel de Controle do Skype for Business Server,** clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="3bbac-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="3bbac-127">Se você mudar de ideia e decidir  não excluir a coleção, clique em Confirmação e em Cancelar Todas as Alterações **Não Confirmados.**</span><span class="sxs-lookup"><span data-stu-id="3bbac-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="3bbac-128">Quando a caixa de diálogo Painel de Controle do **Skype for Business Server** for exibida, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="3bbac-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="3bbac-129">Removendo definições de configuração de tronco usando cmdlets do Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bbac-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="3bbac-130">Você pode excluir definições de configuração de tronco usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="3bbac-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="3bbac-131">Você pode executar esse cmdlet a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bbac-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="3bbac-132">Para remover um conjunto especificado de configurações</span><span class="sxs-lookup"><span data-stu-id="3bbac-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="3bbac-133">O comando a seguir remove as definições de configuração de tronco aplicadas ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="3bbac-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="3bbac-134">Para remover todos os coleções aplicados ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="3bbac-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="3bbac-135">Este comando remove todas as definições de configuração de tronco aplicadas ao escopo de serviço:</span><span class="sxs-lookup"><span data-stu-id="3bbac-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="3bbac-136">Para remover todas as coleções onde o bypass de mídia está habilitado</span><span class="sxs-lookup"><span data-stu-id="3bbac-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="3bbac-137">O comando a seguir remove todas as definições de configuração de tronco onde o bypass de mídia foi habilitado:</span><span class="sxs-lookup"><span data-stu-id="3bbac-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="3bbac-138">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3bbac-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

