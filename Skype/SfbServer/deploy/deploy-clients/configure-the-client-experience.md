---
title: Configurar a experiência do cliente com o Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumo: Leia este tópico para saber como configurar a experiência do cliente para usuários do Skype for Business.'
ms.openlocfilehash: 0122e86648a30cf0c4a17957b5d000b742d4c16a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003531"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="f3c04-103">Configurar a experiência do cliente com o Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="f3c04-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="f3c04-104">**Resumo:** Leia este tópico para saber como configurar a experiência do cliente para os usuários do Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="f3c04-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="f3c04-105">O Skype for Business 2015 oferece uma nova experiência de usuário baseada na experiência do produto Skype para consumidores.</span><span class="sxs-lookup"><span data-stu-id="f3c04-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="f3c04-106">Além de todos os recursos do Lync, o Skype for Business oferece novos recursos com controles simplificados e ícones conhecidos.</span><span class="sxs-lookup"><span data-stu-id="f3c04-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="f3c04-107">Para obter informações detalhadas sobre a nova experiência do cliente, consulte [explorar o Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="f3c04-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="f3c04-108">O Skype for Business Server é compatível com a nova experiência de cliente do Skype for Business, bem como com a experiência do cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="f3c04-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="f3c04-109">Como administrador, você pode escolher a experiência do cliente preferida para os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f3c04-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="f3c04-110">Por exemplo, talvez você queira implantar a experiência do cliente do Lync até que os usuários em sua organização sejam totalmente treinados na nova experiência do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f3c04-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="f3c04-111">Ou, se você ainda não tiver atualizado todos os usuários para o Skype for Business Server, talvez queira que todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="f3c04-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f3c04-112">Se a sua organização tiver o Skype for Business Server e o Lync Server implantados, a experiência do cliente padrão será diferente, dependendo das versões do servidor e das configurações da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="f3c04-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="f3c04-113">Quando os usuários iniciarem o Skype for Business pela primeira vez, eles verão sempre a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="f3c04-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="f3c04-114">Após alguns minutos, os usuários são solicitados a alternar para o modo Lync.</span><span class="sxs-lookup"><span data-stu-id="f3c04-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="f3c04-115">Para mais informações, consulte **Comportamento do cliente na primeira inicialização**, que será abordado neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f3c04-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3c04-116">A experiência do cliente do Lync 2013 não é uma opção para versões do cliente do Skype for Business 2016 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f3c04-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="f3c04-117">Antes de tentar configurar o ambiente do cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não comece com o número 16; por exemplo: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="f3c04-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="f3c04-118">Configurar experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="f3c04-118">Configure the client experience</span></span>

<span data-ttu-id="f3c04-119">Você pode especificar a experiência que os clientes na sua organização terão usando o cmdlet **Set-CSClientPolicy** com o parâmetro EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="f3c04-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="f3c04-120">onde XdsIdentity refere-se à política Global ou a uma política de local nomeado.</span><span class="sxs-lookup"><span data-stu-id="f3c04-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="f3c04-121">O comando a seguir seleciona a experiência do cliente Skype for Business para todos os usuários da sua organização afetados pela política global (Lembre-se de que as políticas específicas do site ou do usuário substituem a política global):</span><span class="sxs-lookup"><span data-stu-id="f3c04-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="f3c04-122">O próximo comando seleciona a experiência do cliente do Lync para todos os usuários da sua organização afetados pela política global:</span><span class="sxs-lookup"><span data-stu-id="f3c04-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="f3c04-123">O próximo comando seleciona a experiência do cliente Skype for Business para todos os usuários no site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="f3c04-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="f3c04-124">Se você quiser configurar a experiência do cliente para usuários específicos em sua organização, poderá criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e, em seguida, atribuir a política a usuários específicos usando o cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f3c04-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f3c04-125">Por exemplo, o comando a seguir cria uma nova política de cliente, SalesClientUI, que seleciona a experiência do cliente do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="f3c04-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="f3c04-126">A próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de Vendas:</span><span class="sxs-lookup"><span data-stu-id="f3c04-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="f3c04-127">Comportamentos do cliente na primeira inicialização</span><span class="sxs-lookup"><span data-stu-id="f3c04-127">First launch client behaviors</span></span>

<span data-ttu-id="f3c04-128">Por padrão, quando os usuários iniciam o Skype for Business 2015 pela primeira vez, eles sempre verão a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync definindo o valor do $False parâmetro EnableSkypeUI como descrito tenha.</span><span class="sxs-lookup"><span data-stu-id="f3c04-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="f3c04-129">Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.</span><span class="sxs-lookup"><span data-stu-id="f3c04-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="f3c04-130">Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:</span><span class="sxs-lookup"><span data-stu-id="f3c04-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="f3c04-131">Confirme se o valor de `EnableSkypeUI` está definido como $false na política que você está usando, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f3c04-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="f3c04-p106">Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes que os novos usuários iniciem o cliente Skype for Business, e deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o registro em um computador que ingressou no domínio, consulte a seção posterior no tópico.</span><span class="sxs-lookup"><span data-stu-id="f3c04-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="f3c04-135">Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, crie um novo valor **Binário**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="f3c04-136">O **Nome do valor** deve ser **EnableSkypeUI**, e os **Dados do valor** devem ser configurados para **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="f3c04-137">A chave deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="f3c04-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="f3c04-138">A interface do usuário do Lync será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="f3c04-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="f3c04-139">Tutorial de controle da exibição da tela de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="f3c04-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="f3c04-140">Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclua *7 dicas rápidas que a maioria das pessoas pede*.</span><span class="sxs-lookup"><span data-stu-id="f3c04-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="f3c04-141">Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="f3c04-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="f3c04-p108">Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser definidos como **1**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="f3c04-144">A chave resultante deve se parecer com a seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3c04-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="f3c04-145">Desativar o tutorial do cliente</span><span class="sxs-lookup"><span data-stu-id="f3c04-145">Turn off the client tutorial</span></span>

<span data-ttu-id="f3c04-146">Se não quiser que seus usuários tenham acesso ao tutorial, você pode desligar o tutorial do cliente com o seguinte valor de Registro:</span><span class="sxs-lookup"><span data-stu-id="f3c04-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="f3c04-p109">Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser definidos como **0**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="f3c04-149">Lync</span><span class="sxs-lookup"><span data-stu-id="f3c04-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="f3c04-150">Você pode ativar o tutorial novamente definindo os **Dados do valor** para **1**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="f3c04-151">Comportamentos padrão do cliente</span><span class="sxs-lookup"><span data-stu-id="f3c04-151">Default client behaviors</span></span>

<span data-ttu-id="f3c04-152">Se a sua organização tiver o Skype for Business Server e o Lync Server implantados, a experiência do cliente será diferente, dependendo das versões do servidor e da configuração da interface do usuário do Skype.</span><span class="sxs-lookup"><span data-stu-id="f3c04-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="f3c04-153">A seguinte tabela mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="f3c04-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="f3c04-154">**Versão do servidor**</span><span class="sxs-lookup"><span data-stu-id="f3c04-154">**Server version**</span></span>|<span data-ttu-id="f3c04-155">**Configuração EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="f3c04-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="f3c04-156">**Experiência do cliente**</span><span class="sxs-lookup"><span data-stu-id="f3c04-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3c04-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3c04-157">Skype for Business Server</span></span> |<span data-ttu-id="f3c04-158">Padrão</span><span class="sxs-lookup"><span data-stu-id="f3c04-158">Default</span></span>  <br/> |<span data-ttu-id="f3c04-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="f3c04-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3c04-160">Skype for Business Server</span></span>  |<span data-ttu-id="f3c04-161">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f3c04-161">True</span></span>  <br/> |<span data-ttu-id="f3c04-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="f3c04-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3c04-163">Skype for Business Server</span></span>  |<span data-ttu-id="f3c04-164">Falso</span><span class="sxs-lookup"><span data-stu-id="f3c04-164">False</span></span>  <br/> |<span data-ttu-id="f3c04-165">O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="f3c04-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="f3c04-166">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="f3c04-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="f3c04-167">Padrão</span><span class="sxs-lookup"><span data-stu-id="f3c04-167">Default</span></span>  <br/> |<span data-ttu-id="f3c04-168">O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="f3c04-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="f3c04-169">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="f3c04-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="f3c04-170">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f3c04-170">True</span></span>  <br/> |<span data-ttu-id="f3c04-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="f3c04-172">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="f3c04-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="f3c04-173">Falso</span><span class="sxs-lookup"><span data-stu-id="f3c04-173">False</span></span>  <br/> |<span data-ttu-id="f3c04-174">O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="f3c04-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="f3c04-175">Lync Server 2010 ou Lync Server 2013 (sem patches)</span><span class="sxs-lookup"><span data-stu-id="f3c04-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="f3c04-176">Padrão</span><span class="sxs-lookup"><span data-stu-id="f3c04-176">Default</span></span>  <br/> |<span data-ttu-id="f3c04-177">O usuário pediu alternar para o modo Lync (o usuário não pode mudar para o Skype for Business mais tarde)</span><span class="sxs-lookup"><span data-stu-id="f3c04-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="f3c04-178">A tabela a seguir mostra a experiência do cliente quando o administrador muda a configuração inicial para a experiência da interface do usuário do Skype:</span><span class="sxs-lookup"><span data-stu-id="f3c04-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="f3c04-179">**Versão do servidor**</span><span class="sxs-lookup"><span data-stu-id="f3c04-179">**Server version**</span></span>|<span data-ttu-id="f3c04-180">**Configuração EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="f3c04-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="f3c04-181">**Interface do usuário do cliente = Lync**</span><span class="sxs-lookup"><span data-stu-id="f3c04-181">**Client UI = Lync**</span></span>|<span data-ttu-id="f3c04-182">**Interface do usuário do cliente = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="f3c04-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3c04-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3c04-183">Skype for Business Server</span></span> |<span data-ttu-id="f3c04-184">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f3c04-184">True</span></span>  <br/> |<span data-ttu-id="f3c04-185">O usuário pediu que mudar para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="f3c04-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="f3c04-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3c04-187">Skype for Business Server</span></span> |<span data-ttu-id="f3c04-188">Falso</span><span class="sxs-lookup"><span data-stu-id="f3c04-188">False</span></span>  <br/> |<span data-ttu-id="f3c04-189">Modo Lync</span><span class="sxs-lookup"><span data-stu-id="f3c04-189">Lync mode</span></span>  <br/> |<span data-ttu-id="f3c04-190">O usuário pediu alternar para o modo Lync</span><span class="sxs-lookup"><span data-stu-id="f3c04-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="f3c04-191">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="f3c04-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="f3c04-192">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f3c04-192">True</span></span>  <br/> |<span data-ttu-id="f3c04-193">O usuário pediu que mudar para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="f3c04-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f3c04-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="f3c04-195">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="f3c04-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="f3c04-196">Falso</span><span class="sxs-lookup"><span data-stu-id="f3c04-196">False</span></span>  <br/> |<span data-ttu-id="f3c04-197">Modo Lync</span><span class="sxs-lookup"><span data-stu-id="f3c04-197">Lync mode</span></span>  <br/> |<span data-ttu-id="f3c04-198">O usuário pediu alternar para o modo Lync</span><span class="sxs-lookup"><span data-stu-id="f3c04-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="f3c04-199">Lync Server 2010 ou Lync Server 2013 (sem patches)</span><span class="sxs-lookup"><span data-stu-id="f3c04-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="f3c04-200">Padrão</span><span class="sxs-lookup"><span data-stu-id="f3c04-200">Default</span></span>  <br/> |<span data-ttu-id="f3c04-201">Modo Lync (não é possível mudar para o Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="f3c04-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="f3c04-202">Modo Lync (não é possível mudar para o Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="f3c04-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="f3c04-203">As versões de patch necessárias para gerenciar a configuração do cliente Skype for Business são:</span><span class="sxs-lookup"><span data-stu-id="f3c04-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="f3c04-204">Lync Server 2010-atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f3c04-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="f3c04-205">Para obter informações, consulte [atualizações para o Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="f3c04-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="f3c04-206">Lync Server 2013-atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3c04-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="f3c04-207">Para obter informações, consulte [atualizações para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="f3c04-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="f3c04-208">Crie um Objeto de Política de Grupo para modificar o registro em um computador com ingresso no domínio</span><span class="sxs-lookup"><span data-stu-id="f3c04-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="f3c04-209">A atualização do registro para exibir a experiência do cliente do Lync na primeira vez que um usuário iniciar o cliente Skype for Business 2015 deve ser feito apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="f3c04-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="f3c04-210">Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor.</span><span class="sxs-lookup"><span data-stu-id="f3c04-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="f3c04-211">Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0.</span><span class="sxs-lookup"><span data-stu-id="f3c04-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="f3c04-212">O procedimento a seguir descreve como modificar o registro para que a experiência do cliente do Lync seja exibida na primeira vez que um usuário iniciar o cliente Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="f3c04-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="f3c04-213">Você também pode usar esse procedimento para atualizar o registro para desabilitar o tutorial da tela de boas-vindas, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f3c04-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="f3c04-214">Para criar o GPO</span><span class="sxs-lookup"><span data-stu-id="f3c04-214">To create the GPO</span></span>

1. <span data-ttu-id="f3c04-215">Inicie o **Console de Gerenciamento de Política de Grupo**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="f3c04-216">Para obter informações sobre como usar o Console de Gerenciamento de Política de Grupo, consulte [Console de Gerenciamento de Política de Grupo](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="f3c04-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="f3c04-217">Clique com o botão direito do mouse no nó **Objetos de Política de Grupo** e selecione **Novo** no menu.</span><span class="sxs-lookup"><span data-stu-id="f3c04-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="f3c04-218">Na caixa de diálogo **Novo GPO**, digite o nome do GPO, por exemplo, MakeLyncDefaultUI, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="f3c04-219">Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.</span><span class="sxs-lookup"><span data-stu-id="f3c04-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="f3c04-220">No **Editor de Gerenciamento de Política de Grupo**, expanda **Configuração do Usuário**, **Preferências**, **Configurações do Windows** e selecione o nó **Registro**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="f3c04-221">Clique com o botão direito do mouse no nó **Registro** e selecione **Novo** > **Item do Registro**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="f3c04-222">Na caixa de diálogo **Novas Propriedades do Registro**, atualize o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3c04-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="f3c04-223">**Campo**</span><span class="sxs-lookup"><span data-stu-id="f3c04-223">**Field**</span></span>|<span data-ttu-id="f3c04-224">**Valor a selecionar ou inserir**</span><span class="sxs-lookup"><span data-stu-id="f3c04-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="f3c04-225">**Ação**</span><span class="sxs-lookup"><span data-stu-id="f3c04-225">**Action**</span></span> <br/> |<span data-ttu-id="f3c04-226">**Criar**</span><span class="sxs-lookup"><span data-stu-id="f3c04-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="f3c04-227">**Hive**</span><span class="sxs-lookup"><span data-stu-id="f3c04-227">**Hive**</span></span> <br/> | <span data-ttu-id="f3c04-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="f3c04-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="f3c04-229">**Caminho chave**</span><span class="sxs-lookup"><span data-stu-id="f3c04-229">**Key Path**</span></span> <br/> |<span data-ttu-id="f3c04-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="f3c04-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="f3c04-231">**Nome do valor**</span><span class="sxs-lookup"><span data-stu-id="f3c04-231">**Value name**</span></span> <br/> |<span data-ttu-id="f3c04-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="f3c04-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="f3c04-233">**Tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="f3c04-233">**Value type**</span></span> <br/> |<span data-ttu-id="f3c04-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="f3c04-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="f3c04-235">**Dados do valor**</span><span class="sxs-lookup"><span data-stu-id="f3c04-235">**Value data**</span></span> <br/> |<span data-ttu-id="f3c04-236">00000000</span><span class="sxs-lookup"><span data-stu-id="f3c04-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="f3c04-237">Clique em **OK** para salvar as alterações e feche o GPO.</span><span class="sxs-lookup"><span data-stu-id="f3c04-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="f3c04-238">Em seguida, você terá de vincular o GPO criado ao grupo de usuários ao qual você deseja atribuir a política, tal como uma unidade organizacional (OU).</span><span class="sxs-lookup"><span data-stu-id="f3c04-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="f3c04-239">Para usar o GPO para atribuir a política</span><span class="sxs-lookup"><span data-stu-id="f3c04-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="f3c04-240">No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na OU à qual você deseja atribuir a política e, em seguida, selecione **Vincular a um GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="f3c04-241">Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3c04-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="f3c04-242">No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f3c04-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="f3c04-243">No prompt de comando, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f3c04-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="f3c04-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="f3c04-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="f3c04-245">Você verá "Objetos Atribuídos da Política de Grupo" com o nome do GPO que você criou exibido abaixo.</span><span class="sxs-lookup"><span data-stu-id="f3c04-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="f3c04-p115">Você também pode verificar se o GPO atualizou com sucesso o registro no computador de um usuário examinando o registro. Abra o Editor de Registro e navegue até a chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Se o GPO tiver atualizado o registro com sucesso, você verá um valor chamado EnableSkypeUI com o valor de 0.</span><span class="sxs-lookup"><span data-stu-id="f3c04-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

