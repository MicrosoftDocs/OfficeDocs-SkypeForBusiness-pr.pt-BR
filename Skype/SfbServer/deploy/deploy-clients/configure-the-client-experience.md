---
title: Configurar a experiência do cliente com o Skype for Business
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumo: Leia este tópico para saber como configurar a experiência do cliente para Skype para usuários comerciais.'
ms.openlocfilehash: 9c1bc182c383ea7d806ce779f3d727e7925a59d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="2f459-103">Configurar a experiência do cliente com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f459-103">Configure the client experience with Skype for Business</span></span>
 
<span data-ttu-id="2f459-104">**Resumo:** Leia este tópico para saber como configurar a experiência do cliente para Skype para usuários comerciais.</span><span class="sxs-lookup"><span data-stu-id="2f459-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business users.</span></span>
  
<span data-ttu-id="2f459-105">Skype para negócios fornece uma nova experiência do usuário que baseia-se na experiência de produto do consumidor do Skype.</span><span class="sxs-lookup"><span data-stu-id="2f459-105">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="2f459-106">Além de todos os recursos do Lync, Skype para negócios fornece novos recursos com controles simplificados e ícones familiares.</span><span class="sxs-lookup"><span data-stu-id="2f459-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="2f459-107">Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync está agora Skype para empresas & #x 2014; consulte What's new](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="2f459-107">For detailed information about the new client experience, see [Lync is now Skype for Business &#x2014; see what's new](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="2f459-108">Skype para Business Server suporta a nova Skype para experiência de cliente de negócios, bem como a experiência do cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="2f459-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="2f459-109">Como administrador, você pode escolher a experiência do cliente preferida para os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2f459-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="2f459-110">Por exemplo, você talvez queira implantar a experiência do cliente Lync até que os usuários em sua organização são treinados totalmente o novo Skype para experiência de negócios.</span><span class="sxs-lookup"><span data-stu-id="2f459-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="2f459-111">Ou, se você ainda não atualizadas todos os usuários para Skype para Business Server, talvez você queira todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="2f459-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f459-112">Se sua organização tem ambas Skype para Business Server e o Lync Server implantado, a experiência do cliente padrão variarão de acordo com as versões de servidor e configurações de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f459-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="2f459-113">Quando os usuários início Skype para negócios pela primeira vez, sempre eles verão o Skype para interface de usuário de negócios – mesmo se você selecionou a experiência do cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="2f459-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="2f459-114">Após alguns minutos, os usuários serão solicitados para alternar para modo de Lync.</span><span class="sxs-lookup"><span data-stu-id="2f459-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="2f459-115">Para mais informações, consulte **Comportamento do cliente na primeira inicialização**, que será abordado neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2f459-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f459-116">A experiência do cliente Lync 2013 não é uma opção para Skype para as versões de cliente 2016 de negócios.</span><span class="sxs-lookup"><span data-stu-id="2f459-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="2f459-117">Antes de tentar configurar seu ambiente do cliente para usar o cliente do Lync 2013, verifique a versão do cliente para garantir que ele não começa com o número de 16; Por exemplo: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="2f459-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="2f459-118">Configurar experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="2f459-118">Configure the client experience</span></span>

<span data-ttu-id="2f459-119">Você pode especificar a experiência que os clientes na sua organização terão usando o cmdlet **Set-CSClientPolicy** com o parâmetro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="2f459-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="2f459-120">onde XdsIdentity refere-se à política Global ou a uma política de local nomeado.</span><span class="sxs-lookup"><span data-stu-id="2f459-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="2f459-121">O comando a seguir seleciona o Skype para a experiência do cliente de negócios para todos os usuários em sua organização afetada pela diretiva Global (Lembre-se de que diretivas específicas do usuário ou site substituem a política Global):</span><span class="sxs-lookup"><span data-stu-id="2f459-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="2f459-122">O próximo comando seleciona a experiência do cliente do Lync para todos os usuários em sua organização afetada pela diretiva Global:</span><span class="sxs-lookup"><span data-stu-id="2f459-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="2f459-123">O próximo comando seleciona o Skype para a experiência do cliente de negócios para todos os usuários dentro do site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="2f459-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="2f459-124">Se você deseja configurar a experiência do cliente para usuários específicos dentro da sua organização, você pode criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e, em seguida, atribuir a política a usuários específicos usando o **Grant-CsClientPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2f459-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2f459-125">Por exemplo, o comando a seguir cria uma nova diretiva de cliente, SalesClientUI, que seleciona o Skype para a experiência do cliente de negócios:</span><span class="sxs-lookup"><span data-stu-id="2f459-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="2f459-126">A próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de Vendas:</span><span class="sxs-lookup"><span data-stu-id="2f459-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="2f459-127">Comportamentos do cliente na primeira inicialização</span><span class="sxs-lookup"><span data-stu-id="2f459-127">First launch client behaviors</span></span>

<span data-ttu-id="2f459-128">Por padrão, quando os usuários iniciar Skype para negócios pela primeira vez, eles verão sempre o Skype para interface de usuário de negócios – mesmo se você selecionou a experiência do cliente Lync, definindo o valor do parâmetro EnableSkypeUI para $False, conforme descrito anteriormente .</span><span class="sxs-lookup"><span data-stu-id="2f459-128">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="2f459-129">Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.</span><span class="sxs-lookup"><span data-stu-id="2f459-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="2f459-130">Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:</span><span class="sxs-lookup"><span data-stu-id="2f459-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="2f459-131">Confirme se o valor da `EnableSkypeUI` estiver definida como $False na política que você está usando, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2f459-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="2f459-p106">Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes que os novos usuários iniciem o cliente Skype for Business, e deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o registro em um computador que ingressou no domínio, consulte a seção posterior no tópico.</span><span class="sxs-lookup"><span data-stu-id="2f459-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="2f459-135">Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, crie um novo valor **Binário**.</span><span class="sxs-lookup"><span data-stu-id="2f459-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="2f459-136">O **Nome do valor** deve ser **EnableSkypeUI**, e os **Dados do valor** devem ser configurados para **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="2f459-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="2f459-137">A chave deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="2f459-137">The key should look like the following:</span></span>
    
  ```
  [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
"CanSharePptInCollab"=dword:00000001
"CanShareOneNoteInCollab"=dword:00000001
"CanAppShareInCollab"=dword:00000001
"EnableSkypeUI"=hex:00,00,00,00
  ```

<span data-ttu-id="2f459-138">A interface do usuário do Lync será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="2f459-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="2f459-139">Controlar a exibição do tutorial da tela de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="2f459-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="2f459-p107">Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclui  *7 dicas rápidas mais solicitadas pelas pessoas*  . Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="2f459-p107">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*  . You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="2f459-p108">Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser definidos como **1**.</span><span class="sxs-lookup"><span data-stu-id="2f459-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="2f459-144">A chave deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="2f459-144">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="2f459-145">Desativar o tutorial do cliente</span><span class="sxs-lookup"><span data-stu-id="2f459-145">Turn off the client tutorial</span></span>

<span data-ttu-id="2f459-146">Se você não quiser que os usuários acessem o tutorial, desative o tutorial do cliente com o seguinte valor do Registro:</span><span class="sxs-lookup"><span data-stu-id="2f459-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="2f459-p109">Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser definidos como **0**.</span><span class="sxs-lookup"><span data-stu-id="2f459-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="2f459-149">Lync</span><span class="sxs-lookup"><span data-stu-id="2f459-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="2f459-150">Você pode ativar o tutorial novamente definindo os **Dados do valor** para **1**.</span><span class="sxs-lookup"><span data-stu-id="2f459-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="2f459-151">Comportamentos padrão do cliente</span><span class="sxs-lookup"><span data-stu-id="2f459-151">Default client behaviors</span></span>

<span data-ttu-id="2f459-152">Se sua organização tem ambas Skype para Business Server e o Lync Server implantado, a experiência do cliente variarão de acordo com as versões de servidor e da UI de Skype configuração.</span><span class="sxs-lookup"><span data-stu-id="2f459-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="2f459-153">A seguinte tabela mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="2f459-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="2f459-154">**Versão do servidor**</span><span class="sxs-lookup"><span data-stu-id="2f459-154">**Server version**</span></span>|<span data-ttu-id="2f459-155">**Configuração de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="2f459-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="2f459-156">**Experiência do cliente**</span><span class="sxs-lookup"><span data-stu-id="2f459-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f459-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f459-157">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="2f459-158">Padrão</span><span class="sxs-lookup"><span data-stu-id="2f459-158">Default</span></span>  <br/> |<span data-ttu-id="2f459-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f459-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2f459-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f459-160">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="2f459-161">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="2f459-161">True</span></span>  <br/> |<span data-ttu-id="2f459-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f459-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2f459-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f459-163">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="2f459-164">Falso</span><span class="sxs-lookup"><span data-stu-id="2f459-164">False</span></span>  <br/> |<span data-ttu-id="2f459-165">Usuário é solicitado a alternar para o modo do Lync (usuário pode alternar para Skype para negócios posteriormente se você alterar a configuração de interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="2f459-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="2f459-166">Lync Server 2010 ou o Lync Server 2013 (com patches corretas)</span><span class="sxs-lookup"><span data-stu-id="2f459-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2f459-167">Padrão</span><span class="sxs-lookup"><span data-stu-id="2f459-167">Default</span></span>  <br/> |<span data-ttu-id="2f459-168">Usuário é solicitado a alternar para o modo do Lync (usuário pode alternar para Skype para negócios posteriormente se você alterar a configuração de interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="2f459-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="2f459-169">Lync Server 2010 ou o Lync Server 2013 (com patches corretas)</span><span class="sxs-lookup"><span data-stu-id="2f459-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2f459-170">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="2f459-170">True</span></span>  <br/> |<span data-ttu-id="2f459-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f459-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2f459-172">Lync Server 2010 ou o Lync Server 2013 (com patches corretas)</span><span class="sxs-lookup"><span data-stu-id="2f459-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2f459-173">Falso</span><span class="sxs-lookup"><span data-stu-id="2f459-173">False</span></span>  <br/> |<span data-ttu-id="2f459-174">Usuário é solicitado a alternar para o modo do Lync (usuário pode alternar para Skype para negócios posteriormente se você alterar a configuração de interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="2f459-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="2f459-175">Lync Server 2010 ou o Lync Server 2013 (sem patches)</span><span class="sxs-lookup"><span data-stu-id="2f459-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="2f459-176">Padrão</span><span class="sxs-lookup"><span data-stu-id="2f459-176">Default</span></span>  <br/> |<span data-ttu-id="2f459-177">Usuário é solicitado a alternar para o modo do Lync (o usuário não pode alternar para Skype para negócios posterior)</span><span class="sxs-lookup"><span data-stu-id="2f459-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="2f459-178">A próxima tabela mostra a experiência do cliente quando o administrador altera a configuração inicial para a experiência do Skype UI:</span><span class="sxs-lookup"><span data-stu-id="2f459-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="2f459-179">**Versão do servidor**</span><span class="sxs-lookup"><span data-stu-id="2f459-179">**Server version**</span></span>|<span data-ttu-id="2f459-180">**Configuração de EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="2f459-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="2f459-181">**Cliente UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="2f459-181">**Client UI = Lync**</span></span>|<span data-ttu-id="2f459-182">**Cliente UI = Skype para negócios**</span><span class="sxs-lookup"><span data-stu-id="2f459-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f459-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f459-183">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="2f459-184">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="2f459-184">True</span></span>  <br/> |<span data-ttu-id="2f459-185">Usuário é solicitado a alternar para Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="2f459-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="2f459-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f459-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2f459-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f459-187">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="2f459-188">Falso</span><span class="sxs-lookup"><span data-stu-id="2f459-188">False</span></span>  <br/> |<span data-ttu-id="2f459-189">Modo do Lync</span><span class="sxs-lookup"><span data-stu-id="2f459-189">Lync mode</span></span>  <br/> |<span data-ttu-id="2f459-190">Usuário é solicitado a alternar para o modo do Lync</span><span class="sxs-lookup"><span data-stu-id="2f459-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="2f459-191">Lync Server 2010 ou o Lync Server 2013 (com patches corretas)</span><span class="sxs-lookup"><span data-stu-id="2f459-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2f459-192">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="2f459-192">True</span></span>  <br/> |<span data-ttu-id="2f459-193">Usuário é solicitado a alternar para Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="2f459-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="2f459-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f459-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2f459-195">Lync Server 2010 ou o Lync Server 2013 (com patches corretas)</span><span class="sxs-lookup"><span data-stu-id="2f459-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2f459-196">Falso</span><span class="sxs-lookup"><span data-stu-id="2f459-196">False</span></span>  <br/> |<span data-ttu-id="2f459-197">Modo do Lync</span><span class="sxs-lookup"><span data-stu-id="2f459-197">Lync mode</span></span>  <br/> |<span data-ttu-id="2f459-198">Usuário é solicitado a alternar para o modo do Lync</span><span class="sxs-lookup"><span data-stu-id="2f459-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="2f459-199">Lync Server 2010 ou o Lync Server 2013 (sem patches)</span><span class="sxs-lookup"><span data-stu-id="2f459-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="2f459-200">Padrão</span><span class="sxs-lookup"><span data-stu-id="2f459-200">Default</span></span>  <br/> |<span data-ttu-id="2f459-201">Modo do Lync (não é possível alternar para Skype para negócios)</span><span class="sxs-lookup"><span data-stu-id="2f459-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="2f459-202">Modo do Lync (não é possível alternar para Skype para negócios)</span><span class="sxs-lookup"><span data-stu-id="2f459-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="2f459-203">As versões de patch necessárias para gerenciar a configuração do Skype para o cliente de negócios são:</span><span class="sxs-lookup"><span data-stu-id="2f459-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="2f459-204">O Lync Server 2010 - atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2f459-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="2f459-205">Para obter informações, consulte [atualizações do Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="2f459-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="2f459-206">Lync Server 2013 - atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f459-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="2f459-207">Para obter informações, consulte [atualizações do Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="2f459-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="2f459-208">Criar um Objeto de Política de Grupo para modificar o Registro em um computador que ingressou no domínio</span><span class="sxs-lookup"><span data-stu-id="2f459-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="2f459-p113">A atualização do Registro para exibir a experiência de cliente do Lync na primeira vez que o usuário inicia o cliente Skype for Business deve ser realizada somente uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor. Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0.</span><span class="sxs-lookup"><span data-stu-id="2f459-p113">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="2f459-p114">O procedimento a seguir descreve como modificar o Registro para que a experiência de cliente do Lync seja exibida na primeira vez que o usuário iniciar o Skype for Business. Você também pode usar este procedimento para atualizar o Registro para desativar o tutorial da tela de boas-vindas conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2f459-p114">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="2f459-214">Para criar o GPO</span><span class="sxs-lookup"><span data-stu-id="2f459-214">To create the GPO</span></span>

1. <span data-ttu-id="2f459-215">Inicie o **Console de Gerenciamento de Política de Grupo**.</span><span class="sxs-lookup"><span data-stu-id="2f459-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="2f459-216">Para obter informações sobre como usar o Console de Gerenciamento de Política de Grupo, consulte [Console de Gerenciamento de Política de Grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="2f459-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="2f459-217">Clique com o botão direito do mouse no nó **Objetos de Política de Grupo** e selecione **Novo** no menu.</span><span class="sxs-lookup"><span data-stu-id="2f459-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="2f459-218">Na caixa de diálogo **Novo GPO**, digite o nome do GPO, por exemplo, MakeLyncDefaultUI, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f459-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="2f459-219">Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.</span><span class="sxs-lookup"><span data-stu-id="2f459-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="2f459-220">No **Editor de Gerenciamento de Política de Grupo**, expanda **Configuração do Usuário**, **Preferências**, **Configurações do Windows** e selecione o nó **Registro**.</span><span class="sxs-lookup"><span data-stu-id="2f459-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="2f459-221">Clique com o botão direito do mouse no nó **Registro** e selecione **Novo** > **Item do Registro**.</span><span class="sxs-lookup"><span data-stu-id="2f459-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="2f459-222">Na caixa de diálogo **Novas Propriedades do Registro**, atualize o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f459-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="2f459-223">**Campo**</span><span class="sxs-lookup"><span data-stu-id="2f459-223">**Field**</span></span>|<span data-ttu-id="2f459-224">**Valor a selecionar ou inserir**</span><span class="sxs-lookup"><span data-stu-id="2f459-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="2f459-225">**Ação**</span><span class="sxs-lookup"><span data-stu-id="2f459-225">**Action**</span></span> <br/> |<span data-ttu-id="2f459-226">**Criar**</span><span class="sxs-lookup"><span data-stu-id="2f459-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="2f459-227">**Hive**</span><span class="sxs-lookup"><span data-stu-id="2f459-227">**Hive**</span></span> <br/> | <span data-ttu-id="2f459-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="2f459-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="2f459-229">**Caminho chave**</span><span class="sxs-lookup"><span data-stu-id="2f459-229">**Key Path**</span></span> <br/> |<span data-ttu-id="2f459-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="2f459-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="2f459-231">**Nome do valor**</span><span class="sxs-lookup"><span data-stu-id="2f459-231">**Value name**</span></span> <br/> |<span data-ttu-id="2f459-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="2f459-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="2f459-233">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="2f459-233">**Value type**</span></span> <br/> |<span data-ttu-id="2f459-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="2f459-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="2f459-235">**Dados do valor**</span><span class="sxs-lookup"><span data-stu-id="2f459-235">**Value data**</span></span> <br/> |<span data-ttu-id="2f459-236">00000000</span><span class="sxs-lookup"><span data-stu-id="2f459-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="2f459-237">Clique em **OK** para salvar as alterações e feche o GPO.</span><span class="sxs-lookup"><span data-stu-id="2f459-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="2f459-238">Em seguida, você precisará vincular o GPO que você criou para o grupo de usuários ao qual a política será atribuída, como uma UO.</span><span class="sxs-lookup"><span data-stu-id="2f459-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="2f459-239">Para usar o GPO para atribuir a política</span><span class="sxs-lookup"><span data-stu-id="2f459-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="2f459-240">No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na UO para a qual você deseja atribuir a política e selecione **Vincular a um GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="2f459-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="2f459-241">Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f459-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="2f459-242">No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2f459-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="2f459-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="2f459-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="2f459-p115">A mensagem "Atualizando a política..." é exibida enquanto o GPO é aplicado. Ao concluir, a mensagem "A atualização da Política de Usuário foi concluída com êxito" é exibida.</span><span class="sxs-lookup"><span data-stu-id="2f459-p115">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="2f459-246">No prompt de comando, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2f459-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="2f459-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="2f459-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="2f459-248">Você verá "Objetos Atribuídos da Política de Grupo" com o nome do GPO que você criou exibido abaixo.</span><span class="sxs-lookup"><span data-stu-id="2f459-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="2f459-p116">Você também pode verificar se o GPO atualizou com sucesso o registro no computador de um usuário examinando o registro. Abra o Editor de Registro e navegue até a chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Se o GPO tiver atualizado o registro com sucesso, você verá um valor chamado EnableSkypeUI com o valor de 0.</span><span class="sxs-lookup"><span data-stu-id="2f459-p116">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

