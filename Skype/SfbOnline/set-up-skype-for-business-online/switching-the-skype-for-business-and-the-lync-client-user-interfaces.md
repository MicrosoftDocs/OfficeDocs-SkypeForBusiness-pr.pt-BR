---
title: Alternando entre as interfaces do usuário do cliente Skype for Business e do cliente Lync
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 5458fb4838ce2e7847a49caa31f92d2151e2a382
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="c66cc-103">Alternando entre as interfaces do usuário do cliente Skype for Business e do cliente Lync</span><span class="sxs-lookup"><span data-stu-id="c66cc-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="c66cc-104">Para as organizações que têm o Skype for Business Online, você pode usar o PowerShell Remoto no Office 365 para permitir que os usuários do Skype for Business utilizem a interface do usuário do cliente Skype for Business ou do cliente Skype for Business (Lync).</span><span class="sxs-lookup"><span data-stu-id="c66cc-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="c66cc-105">Na configuração padrão, os usuários devem utilizar a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="c66cc-106">Se você preferir usar a experiência do cliente Lync, é possível gerenciar o comportamento do cliente primeiro lançamento para exibir a interface de usuário do Lync seguindo as etapas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c66cc-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c66cc-p102">[!OBSERVAçãO] A experiência do cliente Lync 2013 não é uma opção para as versões do cliente Skype for Business 2016. Antes de tentar configurar seu ambiente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ela não começa com o número 16. Por exemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c66cc-109">[!DICA] Se desejar alternar facilmente a interface do usuário sem seguir as etapas manuais, consulte o [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?LinkId=532431) para obter um script PowerShell e tornar essa tarefa mais fácil.</span><span class="sxs-lookup"><span data-stu-id="c66cc-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="c66cc-110">Alternando a interface do Skype for Business para os usuários</span><span class="sxs-lookup"><span data-stu-id="c66cc-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="c66cc-p103">O módulo Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Para obter outras informações, consulte [Configurando o computador para gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="c66cc-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c66cc-p104">[!IMPORTANTE] A configuração da política  _Global_ para alternar a interface do usuário não será aplicada aos usuários que já têm uma política personalizada aplicada. Para alterar a interface, você precisará executar o seguinte para cada usuário que tiver uma política personalizada aplicada:</span><span class="sxs-lookup"><span data-stu-id="c66cc-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="c66cc-116">[!CUIDADO] A política  _ClientPolicyEnableSkypeUI_ substituirá a configuração de política existente do usuário.</span><span class="sxs-lookup"><span data-stu-id="c66cc-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="c66cc-117">Para permitir que todos os usuários de sua organização utilizem o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="c66cc-118">Se definir a política corretamente, você verá:</span><span class="sxs-lookup"><span data-stu-id="c66cc-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="c66cc-120">Para permitir que todos os usuários de sua organização utilizem o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="c66cc-121">Se definir a política corretamente, você verá:</span><span class="sxs-lookup"><span data-stu-id="c66cc-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="c66cc-123">Para permitir que um único usuário de sua organização utilize o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="c66cc-124">Se definir a política corretamente, você verá:</span><span class="sxs-lookup"><span data-stu-id="c66cc-124">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - Habilitar interface do usuário](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="c66cc-126">Para permitir que um único usuário de sua organização utilize o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="c66cc-127">Se definir a política corretamente, você verá:</span><span class="sxs-lookup"><span data-stu-id="c66cc-127">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - Interface do Usuário Desabilitada](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="c66cc-129">Para permitir que vários usuários de sua organização utilizem o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="c66cc-130">Para permitir que vários usuários de sua organização utilizem o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="c66cc-131">Para permitir que um grupo de usuários de sua organização utilize o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="c66cc-132">Para permitir que um grupo de usuários de sua organização utilize o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="c66cc-p105">[!OBSERVAçãO]  O nome do usuário é o nome da conta do usuário à qual a política deve ser atribuída. O nome da conta do usuário pode ser inserido em um dos seguintes formatos:>  Endereço SIP do usuário>  Nome UPN do usuário>  Domínio\\nome de usuário do usuário>  Nome para exibição do Active Directory do usuário</span><span class="sxs-lookup"><span data-stu-id="c66cc-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="c66cc-135">Usando o Windows PowerShell para gerenciar o Lync Online</span><span class="sxs-lookup"><span data-stu-id="c66cc-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="c66cc-136">Configurações de política do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c66cc-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="c66cc-137">Esta tabela mostra a experiência do usuário quando a política é aplicada pela primeira aos usuários:</span><span class="sxs-lookup"><span data-stu-id="c66cc-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="c66cc-138">**Configuração da política de Administração**</span><span class="sxs-lookup"><span data-stu-id="c66cc-138">**Admin policy setting**</span></span>|<span data-ttu-id="c66cc-139">**Interface do usuário exibida**</span><span class="sxs-lookup"><span data-stu-id="c66cc-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c66cc-140">A política não está definida.</span><span class="sxs-lookup"><span data-stu-id="c66cc-140">The policy isn't set.</span></span> |<span data-ttu-id="c66cc-141">O usuário continuará a utilizar a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-141">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|<span data-ttu-id="c66cc-142">O usuário continuará a utilizar a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-142">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|<span data-ttu-id="c66cc-p106">O usuário será solicitado a alternar para a interface do cliente Skype for Business (Lync). Ele poderá alternar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p106">The user will be asked to switch to the Skype for Business (Lync) client user interface. They can switch later.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|<span data-ttu-id="c66cc-145">O usuário utilizará a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-145">The user will be using the Skype for Business client user interface.</span></span> |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|<span data-ttu-id="c66cc-146">O usuário será solicitado para alternar para o Skype para interface de usuário do cliente de negócios (Lync).</span><span class="sxs-lookup"><span data-stu-id="c66cc-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="c66cc-147">No futuro, o administrador poderá alterar a configuração de modo que o usuário alterne para a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="c66cc-148">Esta tabela mostra a experiência do usuário quando a política é alterada:</span><span class="sxs-lookup"><span data-stu-id="c66cc-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="c66cc-149">**Configuração da política de Administração**</span><span class="sxs-lookup"><span data-stu-id="c66cc-149">**Admin policy setting**</span></span>|<span data-ttu-id="c66cc-150">**Interface do usuário do Skype for Business (Lync)**</span><span class="sxs-lookup"><span data-stu-id="c66cc-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="c66cc-151">**Interface do usuário do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="c66cc-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|<span data-ttu-id="c66cc-152">O usuário será solicitado a alternar para a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="c66cc-153">O usuário continuará a utilizar a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|<span data-ttu-id="c66cc-154">O usuário continuará a usar o Skype para interface de negócios (Lync).</span><span class="sxs-lookup"><span data-stu-id="c66cc-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="c66cc-155">O usuário será solicitado para alternar para o Skype para interface de usuário do cliente de negócios (Lync).</span><span class="sxs-lookup"><span data-stu-id="c66cc-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="c66cc-156">A política não está definida.</span><span class="sxs-lookup"><span data-stu-id="c66cc-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="c66cc-157">Os usuários verão o Skype para interface de usuário do cliente de negócios (Lync) nunca se a diretiva não estiver definida.</span><span class="sxs-lookup"><span data-stu-id="c66cc-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="c66cc-158">Eles sempre utilizarão a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="c66cc-159">O usuário continuará a utilizar a interface do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="c66cc-p109">Esta tabela mostra todas as políticas personalizadas online disponíveis. Novas políticas foram criadas para dar flexibilidade aos administradores na retenção da antiga política personalizada durante a troca entre os sinalizadores EnableSkypeUI. Use os cmdlets acima para conceder uma das políticas abaixo para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="c66cc-163">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="c66cc-163">**Policy name**</span></span>|<span data-ttu-id="c66cc-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="c66cc-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |<span data-ttu-id="c66cc-165">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-165">False</span></span>|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |<span data-ttu-id="c66cc-166">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-166">False</span></span>|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |<span data-ttu-id="c66cc-167">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-167">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |<span data-ttu-id="c66cc-168">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-168">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |<span data-ttu-id="c66cc-169">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-169">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|<span data-ttu-id="c66cc-170">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-170">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |<span data-ttu-id="c66cc-171">Falsa</span><span class="sxs-lookup"><span data-stu-id="c66cc-171">False</span></span>|

   
<span data-ttu-id="c66cc-172">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c66cc-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="c66cc-173">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="c66cc-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="c66cc-174">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c66cc-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="c66cc-175">Comportamentos do cliente na primeira inicialização</span><span class="sxs-lookup"><span data-stu-id="c66cc-175">First launch client behaviors</span></span>

<span data-ttu-id="c66cc-176">Por padrão, quando os usuários iniciar Skype para negócios pela primeira vez, eles verão sempre o Skype para interface de usuário de negócios – mesmo se você selecionou a experiência do cliente Lync, definindo a política de cliente para a experiência do cliente Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c66cc-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="c66cc-177">Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.</span><span class="sxs-lookup"><span data-stu-id="c66cc-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="c66cc-178">Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:</span><span class="sxs-lookup"><span data-stu-id="c66cc-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="c66cc-179">Siga as etapas descritas anteriormente neste tópico e confirme se a política do cliente está configurada para desabilitar a interface do usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c66cc-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="c66cc-p111">Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes que os novos usuários iniciem o cliente Skype for Business, e deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o registro em um computador que ingressou no domínio, consulte a seção posterior no tópico.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="c66cc-183">Na chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, crie um novo valor **Binário**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="c66cc-184">O **Nome do valor** deve ser **EnableSkypeUI**, e os **Dados do valor** devem ser configurados para **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="c66cc-185">A chave deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="c66cc-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="c66cc-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="c66cc-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="c66cc-187">"CanSharePptInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="c66cc-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="c66cc-188">"CanShareOneNoteInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="c66cc-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="c66cc-189">"CanAppShareInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="c66cc-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="c66cc-190">"EnableSkypeUI" = hex: 00, 00, 00,00</span><span class="sxs-lookup"><span data-stu-id="c66cc-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="c66cc-191">A interface do usuário do Lync será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="c66cc-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="c66cc-192">Controlar a exibição do tutorial da tela de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="c66cc-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="c66cc-193">Quando os usuários abrem o Skype para o cliente de negócios, o comportamento padrão é exibir uma tela de boas-vindas que inclui *7 dicas rápidas para a maioria das pessoas pedir*.</span><span class="sxs-lookup"><span data-stu-id="c66cc-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="c66cc-194">Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="c66cc-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="c66cc-p113">Na chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, crie um novo valor **DWORD (32 bits)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser configurados para **1**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="c66cc-197">A chave deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="c66cc-197">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="c66cc-198">Desativar o tutorial do cliente</span><span class="sxs-lookup"><span data-stu-id="c66cc-198">Turn off the client tutorial</span></span>

<span data-ttu-id="c66cc-199">Se você não quiser que os usuários acessem o tutorial, desative o tutorial do cliente com o seguinte valor do Registro:</span><span class="sxs-lookup"><span data-stu-id="c66cc-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="c66cc-p114">Na chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, crie um novo valor **DWORD (32 bits)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser configurados para **0**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="c66cc-202">Você pode reativar o tutorial configurando os **Dados de valor** para **1**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="c66cc-203">Criar um Objeto de Política de Grupo para modificar o Registro em um computador que ingressou no domínio</span><span class="sxs-lookup"><span data-stu-id="c66cc-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="c66cc-p115">A atualização do Registro para exibir a experiência de cliente do Lync na primeira vez que o usuário inicia o cliente Skype for Business deve ser realizada somente uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor. Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="c66cc-p116">O procedimento a seguir descreve como modificar o Registro para que a experiência de cliente do Lync seja exibida na primeira vez que o usuário iniciar o Skype for Business. Você também pode usar este procedimento para atualizar o Registro para desativar o tutorial da tela de boas-vindas conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="c66cc-209">**Para criar o GPO**</span><span class="sxs-lookup"><span data-stu-id="c66cc-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="c66cc-210">Inicie o **Console de Gerenciamento de Política de Grupo**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="c66cc-211">Para obter informações sobre como usar o Console de Gerenciamento de Política de Grupo, consulte [Console de Gerenciamento de Política de Grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="c66cc-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="c66cc-212">Clique com o botão direito do mouse no nó **Objetos de Política de Grupo** e selecione **Novo** no menu.</span><span class="sxs-lookup"><span data-stu-id="c66cc-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="c66cc-213">Na caixa de diálogo **Novo GPO**, digite o nome do GPO, por exemplo, MakeLyncDefaultUI, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="c66cc-214">Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.</span><span class="sxs-lookup"><span data-stu-id="c66cc-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="c66cc-215">No **Editor de Gerenciamento de Política de Grupo**, expanda **Configuração do Usuário**, **Preferências**, **Configurações do Windows** e selecione o nó **Registro**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="c66cc-216">Clique com o botão direito do mouse no nó **Registro** e selecione **Novo** > **Item do Registro**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="c66cc-217">Na caixa de diálogo **Novas Propriedades do Registro**, atualize o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c66cc-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="c66cc-218">**Campo**</span><span class="sxs-lookup"><span data-stu-id="c66cc-218">**Field**</span></span>|<span data-ttu-id="c66cc-219">**Valor a selecionar ou inserir**</span><span class="sxs-lookup"><span data-stu-id="c66cc-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c66cc-220">**Ação**</span><span class="sxs-lookup"><span data-stu-id="c66cc-220">**Action**</span></span> <br/> |<span data-ttu-id="c66cc-221">**Criar**</span><span class="sxs-lookup"><span data-stu-id="c66cc-221">**Create**</span></span> <br/> |
|<span data-ttu-id="c66cc-222">**Hive**</span><span class="sxs-lookup"><span data-stu-id="c66cc-222">**Hive**</span></span> <br/> | <span data-ttu-id="c66cc-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="c66cc-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="c66cc-224">**Caminho da Chave**</span><span class="sxs-lookup"><span data-stu-id="c66cc-224">**Key Path**</span></span> <br/> |<span data-ttu-id="c66cc-225">Software\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="c66cc-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="c66cc-226">**Nome do valor**</span><span class="sxs-lookup"><span data-stu-id="c66cc-226">**Value name**</span></span> <br/> |<span data-ttu-id="c66cc-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="c66cc-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="c66cc-228">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="c66cc-228">**Value type**</span></span> <br/> |<span data-ttu-id="c66cc-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="c66cc-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="c66cc-230">**Dados do valor**</span><span class="sxs-lookup"><span data-stu-id="c66cc-230">**Value data**</span></span> <br/> |<span data-ttu-id="c66cc-231">00000000</span><span class="sxs-lookup"><span data-stu-id="c66cc-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="c66cc-232">Clique em **OK** para salvar as alterações e feche o GPO.</span><span class="sxs-lookup"><span data-stu-id="c66cc-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="c66cc-233">Em seguida, você precisará vincular o GPO que você criou para o grupo de usuários ao qual a política será atribuída, como uma UO.</span><span class="sxs-lookup"><span data-stu-id="c66cc-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="c66cc-234">**Usar o GPO para atribuir a política**</span><span class="sxs-lookup"><span data-stu-id="c66cc-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="c66cc-235">No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na UO para a qual você deseja atribuir a política e selecione **Vincular a um GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="c66cc-236">Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c66cc-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="c66cc-237">No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c66cc-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="c66cc-238">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="c66cc-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="c66cc-p117">A mensagem "Atualizando a política..." é exibida enquanto o GPO é aplicado. Ao concluir, a mensagem "A atualização da Política de Usuário foi concluída com êxito" é exibida.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="c66cc-241">No prompt de comando, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c66cc-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="c66cc-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="c66cc-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="c66cc-243">Você deve ver "Objetos de Política de Grupo Atribuídos" com o nome do GPO criado exibido abaixo.</span><span class="sxs-lookup"><span data-stu-id="c66cc-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="c66cc-p118">Você também pode verificar se o GPO atualizou com êxito o Registro no computador de um usuário examinando o Registro. Abra o Editor do Registro e navegue até a chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Se o GPO atualizou o Registro com êxito, você verá um valor chamado EnableSkypeUI com o valor 0.</span><span class="sxs-lookup"><span data-stu-id="c66cc-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c66cc-247">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c66cc-247">Related topics</span></span>
[<span data-ttu-id="c66cc-248">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c66cc-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="c66cc-249">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="c66cc-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 