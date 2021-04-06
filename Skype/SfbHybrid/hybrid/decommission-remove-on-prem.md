---
title: Desativação do Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções para desativação do Skype for Business Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593870"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="f0b87-103">Remover sua implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b87-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="f0b87-104">Este artigo descreve como remover sua implantação local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f0b87-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="f0b87-105">Esta é a etapa 3 das etapas a seguir para desmantelar seu ambiente local:</span><span class="sxs-lookup"><span data-stu-id="f0b87-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="f0b87-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f0b87-106">Step 1.</span></span> <span data-ttu-id="f0b87-107">Mova todos os usuários e pontos de extremidade de aplicativo [necessários do local para o online](decommission-move-on-prem-users.md).</span><span class="sxs-lookup"><span data-stu-id="f0b87-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="f0b87-108">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f0b87-108">Step 2.</span></span> <span data-ttu-id="f0b87-109">[Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="f0b87-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="f0b87-110">**Etapa 3. Remova sua implantação local do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="f0b87-110">**Step 3. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="f0b87-111">(Este artigo)</span><span class="sxs-lookup"><span data-stu-id="f0b87-111">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="f0b87-112">As etapas deste artigo só se aplicam se você estiver usando o Método 2 para gerenciar atributos de usuário, conforme descrito [aqui](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span><span class="sxs-lookup"><span data-stu-id="f0b87-112">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="f0b87-113">Se você estiver usando o Método 1, não use as etapas descritas neste artigo para remover seus servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f0b87-113">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="f0b87-114">Em vez disso, você pode reimimá-los.</span><span class="sxs-lookup"><span data-stu-id="f0b87-114">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="f0b87-115">Para concluir as etapas deste artigo, você precisa de privilégios para o grupo Administradores de Esquema e para o grupo Administrador empresarial.</span><span class="sxs-lookup"><span data-stu-id="f0b87-115">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="f0b87-116">Você precisará desses privilégios para desfazer o esquema do Skype for Business Server e as alterações no nível da floresta nos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0b87-116">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="f0b87-117">Você também precisará ser membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f0b87-117">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="f0b87-118">Preparar para remover a implantação do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b87-118">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="f0b87-119">Depois de mover todas as contas de usuário necessárias para a nuvem, ainda pode haver alguns objetos locais restantes, como contatos e aplicativos que você precisará limpar.</span><span class="sxs-lookup"><span data-stu-id="f0b87-119">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="f0b87-120">Use as etapas abaixo para limpar esses objetos e certifique-se de que você seja membro do grupo Administrador Local e do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f0b87-120">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="f0b87-121">Observe que o ExUmContacts e PersistantChatEndPoints não estão disponíveis no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f0b87-121">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f0b87-122">Se você tiver o Skype for Business Server 2019, os cmdlets correspondentes nas etapas abaixo devem ser omitidos.</span><span class="sxs-lookup"><span data-stu-id="f0b87-122">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="f0b87-123">Para verificar se há contatos ou aplicativos associados à implantação local do Skype for Business Server, execute os seguintes cmdlets do PowerShell do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0b87-123">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="f0b87-124">Revise as listas de saída dos cmdlets na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f0b87-124">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="f0b87-125">Em seguida, se os objetos puderem ser removidos, execute os seguintes cmdlets do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f0b87-125">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="f0b87-126">Remover sua implantação local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b87-126">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="f0b87-127">Após concluir todas as etapas preliminares, você pode remover a implantação do Skype for Business seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f0b87-127">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="f0b87-128">Remova logicamente a implantação do Skype for Business Server, exceto por um único front-end, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f0b87-128">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="f0b87-129">a.</span><span class="sxs-lookup"><span data-stu-id="f0b87-129">a.</span></span> <span data-ttu-id="f0b87-130">Atualize sua topologia do Skype for Business Server para ter um único pool front-end:</span><span class="sxs-lookup"><span data-stu-id="f0b87-130">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="f0b87-131">No Construtor de Topologias, baixe uma nova cópia e navegue até o pool frontend.</span><span class="sxs-lookup"><span data-stu-id="f0b87-131">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="f0b87-132">Clique com o botão direito no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f0b87-132">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="f0b87-133">Em **Associações, desmarque** **Associar Pool** de Borda (para componentes de mídia) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0b87-133">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="f0b87-134">Se houver mais de um Pool frontend, remova Associações para todos os pools restantes.</span><span class="sxs-lookup"><span data-stu-id="f0b87-134">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="f0b87-135">Selecione **Ação > Remover Implantação**.</span><span class="sxs-lookup"><span data-stu-id="f0b87-135">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="f0b87-136">Selecione **Ação > Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="f0b87-136">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="f0b87-137">b.</span><span class="sxs-lookup"><span data-stu-id="f0b87-137">b.</span></span> <span data-ttu-id="f0b87-138">Depois de publicar a topologia, conclua as etapas adicionais descritas no assistente.</span><span class="sxs-lookup"><span data-stu-id="f0b87-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="f0b87-139">Remova os diretórios de conferência do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f0b87-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="f0b87-140">Finalize a desinstalação da implantação do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f0b87-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="f0b87-141">Se essa etapa retornar um erro, abra um tíquete de suporte da Microsoft para obter ajuda para remover os objetos que restam.</span><span class="sxs-lookup"><span data-stu-id="f0b87-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="f0b87-142">Remova o Ponto de Controle do Serviço do Armazenamento de Gerenciamento Central executando o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f0b87-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="f0b87-143">Desfazer alterações no nível da floresta do Domínio do Active Directory do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f0b87-143">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="f0b87-144">Desfazer alterações de esquema de Domínio do Active Directory do Skype for Business Server executando o seguinte cmdlet do PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f0b87-144">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="f0b87-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0b87-145">See also</span></span>

- [<span data-ttu-id="f0b87-146">Desmantelar seu ambiente local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f0b87-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="f0b87-147">Mover usuários e pontos de extremidade para a nuvem</span><span class="sxs-lookup"><span data-stu-id="f0b87-147">Move user and endpoints to the cloud</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="f0b87-148">Desabilitar sua configuração híbrida</span><span class="sxs-lookup"><span data-stu-id="f0b87-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)














