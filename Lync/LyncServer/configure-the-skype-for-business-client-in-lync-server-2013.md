---
title: Configurar o cliente Skype for Business no Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a78e229b54ec165897d920d8f04db49451eac9b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="8cdfe-102">Configurar a experiência do cliente com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cdfe-103">_**Última modificação do tópico:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="8cdfe-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="8cdfe-104">**Resumo:** Este tópico descreve como configurar a experiência do cliente para usuários clientes do Skype for Business em um ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="8cdfe-105">Você pode configurar a experiência do cliente somente se você estiver executando o Lync Server 2013 com a atualização cumulativa de dezembro de 2014 (5.0.8308.857) ou posterior instalada.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="8cdfe-106">Para obter informações sobre como atualizar o Lync Server 2013, consulte [atualizações para o Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="8cdfe-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="8cdfe-107">O Skype for Business oferece uma nova experiência de usuário que se baseia na experiência do produto consumidor do Skype.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="8cdfe-108">Além de todos os recursos do Lync, o Skype for Business oferece novos recursos com controles simplificados e ícones conhecidos.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="8cdfe-109">Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Lync agora é Skype for Business – Veja o que há de novo](https://go.microsoft.com/fwlink/?linkid=529022).</span><span class="sxs-lookup"><span data-stu-id="8cdfe-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="8cdfe-110">O Lync Server 2013 oferece suporte à nova experiência de cliente do Skype for Business, bem como à experiência de cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="8cdfe-111">Como administrador, você pode escolher a experiência de cliente preferencial para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="8cdfe-112">Por exemplo, você pode querer implantar a experiência de cliente do Lync até que os usuários em sua organização sejam totalmente treinados na nova experiência do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="8cdfe-113">Ou, se você ainda não tiver atualizado todos os usuários para o Skype for Business Server 2015, talvez queira que todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8cdfe-114">Se sua organização tiver o Skype for Business Server 2015 e o Lync Server 2013 implantados, a experiência do cliente padrão será diferente, dependendo das versões do servidor e das configurações da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="8cdfe-115">Quando os usuários iniciam o Skype for Business pela primeira vez, eles sempre verão a interface de usuário do Skype for Business, mesmo que você tenha selecionado a interface de usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="8cdfe-116">Após alguns minutos, os usuários são solicitados a alternar para o modo Lync.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="8cdfe-117">Para obter mais informações, consulte <STRONG>primeiro início do comportamento de cliente</STRONG> mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8cdfe-118">A experiência de cliente do Lync 2013 não é uma opção para as versões do cliente do Skype for Business 2016.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="8cdfe-119">Antes de tentar configurar seu ambiente de cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não inicie com o número 16; por exemplo: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="8cdfe-120">Configurar a experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="8cdfe-120">Configure the client experience</span></span>

<span data-ttu-id="8cdfe-121">Você pode especificar a experiência do cliente que os usuários da sua organização verão usando o cmdlet **set-CSClientPolicy** com o parâmetro EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="8cdfe-122">O comando a seguir seleciona a experiência de cliente do Skype for Business para todos os usuários da sua organização afetados pela política global (Lembre-se, políticas específicas de site ou usuário substituem a política global):</span><span class="sxs-lookup"><span data-stu-id="8cdfe-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="8cdfe-123">O próximo comando seleciona a experiência de cliente do Lync para todos os usuários da sua organização afetados pela política global:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="8cdfe-124">O próximo comando seleciona a experiência de cliente do Skype for Business para todos os usuários no site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="8cdfe-125">Se você quiser configurar a experiência do cliente para usuários específicos dentro da sua organização, você pode criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e, em seguida, atribuir a política a usuários específicos usando o cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="8cdfe-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="8cdfe-126">Por exemplo, o seguinte comando cria uma nova política de cliente, SalesClientUI, que seleciona a experiência de cliente do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="8cdfe-127">O próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de vendas:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="8cdfe-128">Primeiro iniciar comportamentos do cliente</span><span class="sxs-lookup"><span data-stu-id="8cdfe-128">First launch client behaviors</span></span>

<span data-ttu-id="8cdfe-129">Por padrão, quando os usuários iniciam o Skype for Business pela primeira vez, eles sempre verão a interface de usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync Configurando o valor do $False parâmetro EnableSkypeUI como descrito anteriormente .</span><span class="sxs-lookup"><span data-stu-id="8cdfe-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="8cdfe-130">Após alguns minutos, os usuários serão solicitados a alternar para o modo Lync.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="8cdfe-131">Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes que o cliente seja iniciado pela primeira vez após a atualização:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="8cdfe-132">Confirme se o valor de `EnableSkypeUI` está definido como $false na política que você está usando, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="8cdfe-133">Atualize o registro do sistema no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="8cdfe-134">Você deve fazer isso antes da primeira vez que os usuários iniciam o cliente Skype for Business e você deve fazer isso apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="8cdfe-135">Para obter informações sobre como criar um objeto de diretiva de grupo para atualizar o registro em um computador ingressado no domínio, consulte a seção mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="8cdfe-136">Na chave \*\* \[hKey\_Current\_user\\software\\\\\\Office Lync\] \*\* , crie um novo valor **binário** .</span><span class="sxs-lookup"><span data-stu-id="8cdfe-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="8cdfe-137">O **nome do valor** deve ser **EnableSkypeUI**, e os **dados do valor** devem ser definidos como **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="8cdfe-138">A chave deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="8cdfe-139">A interface de usuário do Lync agora será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="8cdfe-140">Controlar a exibição do tutorial de tela de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="8cdfe-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="8cdfe-141">Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclui *7 dicas rápidas que a maioria das pessoas pede*.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="8cdfe-142">Você pode desativar a exibição da tela de boas-vindas, mas ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do registro no computador cliente:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="8cdfe-143">Na chave \*\* \[de\_software\_\\do\\usuário atual\\do\\Microsoft\\Office\] 15,0 Lync\*\* , crie um novo **valor de DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="8cdfe-144">O **nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **dados do valor** devem ser definidos como **1**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="8cdfe-145">A chave deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="8cdfe-146">Desativar o tutorial do cliente</span><span class="sxs-lookup"><span data-stu-id="8cdfe-146">Turn off the client tutorial</span></span>

<span data-ttu-id="8cdfe-147">Se você não quiser que os usuários possam acessar o tutorial, desative o tutorial do cliente com o seguinte valor de registro:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="8cdfe-148">Na chave \*\* \[de\_software\_\\do\\usuário atual\\do\\Microsoft\\Office\] 15,0 Lync\*\* , crie um novo **valor de DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="8cdfe-149">O **nome do valor** deve ser **TutorialFeatureEnabled**, e os **dados do valor** devem ser definidos como **0**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="8cdfe-150">Você pode ativar o tutorial novamente definindo os dados do **valor** como **1**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="8cdfe-151">Experiências de cliente padrão</span><span class="sxs-lookup"><span data-stu-id="8cdfe-151">Default client experiences</span></span>

<span data-ttu-id="8cdfe-152">Se sua organização tiver o Skype for Business Server 2015 e o Lync Server implantados, a experiência do cliente será diferente, dependendo das versões do servidor e da configuração da interface do usuário do Skype.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="8cdfe-153">A tabela a seguir mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8cdfe-154">Versão do servidor</span><span class="sxs-lookup"><span data-stu-id="8cdfe-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="8cdfe-155">Configuração EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="8cdfe-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="8cdfe-156">Experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="8cdfe-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8cdfe-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-158">Padrão</span><span class="sxs-lookup"><span data-stu-id="8cdfe-158">Default</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cdfe-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8cdfe-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-161">True</span><span class="sxs-lookup"><span data-stu-id="8cdfe-161">True</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8cdfe-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-164">Falso</span><span class="sxs-lookup"><span data-stu-id="8cdfe-164">False</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-165">O usuário é solicitado a alternar para o modo Lync (o usuário pode mudar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cdfe-166">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-167">Padrão</span><span class="sxs-lookup"><span data-stu-id="8cdfe-167">Default</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-168">O usuário é solicitado a alternar para o modo Lync (o usuário pode mudar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-169">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-170">True</span><span class="sxs-lookup"><span data-stu-id="8cdfe-170">True</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cdfe-172">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-173">Falso</span><span class="sxs-lookup"><span data-stu-id="8cdfe-173">False</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-174">O usuário é solicitado a alternar para o modo Lync (o usuário pode mudar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-175">Lync Server 2010 ou Lync Server 2013 (sem patches)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-176">Padrão</span><span class="sxs-lookup"><span data-stu-id="8cdfe-176">Default</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-177">O usuário é solicitado a alternar para a experiência de cliente do Lync (o usuário não pode mudar para o Skype for Business mais tarde)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8cdfe-178">A próxima tabela mostra a experiência do cliente quando o administrador altera a configuração inicial da experiência da interface do usuário do Skype:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8cdfe-179">Versão do servidor</span><span class="sxs-lookup"><span data-stu-id="8cdfe-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="8cdfe-180">Configuração da interface do usuário do Skype</span><span class="sxs-lookup"><span data-stu-id="8cdfe-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="8cdfe-181">UI de cliente = Lync</span><span class="sxs-lookup"><span data-stu-id="8cdfe-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="8cdfe-182">UI de cliente = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8cdfe-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-184">True</span><span class="sxs-lookup"><span data-stu-id="8cdfe-184">True</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-185">O usuário é solicitado a alternar para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cdfe-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8cdfe-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-188">Falso</span><span class="sxs-lookup"><span data-stu-id="8cdfe-188">False</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-189">IU do Lync</span><span class="sxs-lookup"><span data-stu-id="8cdfe-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-190">O usuário é solicitado a alternar para a interface do usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="8cdfe-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-191">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-192">True</span><span class="sxs-lookup"><span data-stu-id="8cdfe-192">True</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-193">O usuário é solicitado a alternar para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8cdfe-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cdfe-195">Lync Server 2010 ou Lync Server 2013 (com patches corretos)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-196">Falso</span><span class="sxs-lookup"><span data-stu-id="8cdfe-196">False</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-197">IU do Lync</span><span class="sxs-lookup"><span data-stu-id="8cdfe-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-198">O usuário é solicitado a alternar para a interface do usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="8cdfe-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cdfe-199">Lync Server 2010 ou Lync Server 2013 (sem patches)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-200">Padrão</span><span class="sxs-lookup"><span data-stu-id="8cdfe-200">Default</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-201">Modo do Lync (não é possível mudar para o Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="8cdfe-202">IU do Lync (não é possível mudar para o Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8cdfe-203">As versões de patch necessárias para gerenciar a configuração do cliente Skype for Business são:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="8cdfe-204">Lync Server 2010-atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="8cdfe-205">Para obter informações, consulte [atualizações para o Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="8cdfe-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="8cdfe-206">Lync Server 2013-atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="8cdfe-207">Para obter informações, consulte [atualizações para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="8cdfe-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="8cdfe-208">Criar um objeto de diretiva de grupo para modificar o registro em um computador ingressado no domínio</span><span class="sxs-lookup"><span data-stu-id="8cdfe-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="8cdfe-209">A atualização do registro para exibir a experiência do cliente do Lync na primeira vez que um usuário inicia o cliente Skype for Business deve ser feita apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="8cdfe-210">Se você usar um objeto de política de grupo (GPO) para atualizar o registro, será necessário definir o objeto para criar um novo valor em vez de atualizar os dados de valor.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="8cdfe-211">Quando o GPO for aplicado, se o novo valor não existir, o GPO o criará e definirá os dados do valor como 0.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="8cdfe-212">O procedimento a seguir descreve como modificar o registro para que a experiência de cliente do Lync seja exibida na primeira vez que um usuário iniciar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="8cdfe-213">Você também pode usar este procedimento para atualizar o registro para desabilitar o tutorial de tela de boas-vindas, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="8cdfe-214">**Para criar o GPO**</span><span class="sxs-lookup"><span data-stu-id="8cdfe-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="8cdfe-215">Inicie o **console de gerenciamento de política de grupo**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="8cdfe-216">Para obter informações sobre como usar o console de gerenciamento de política de grupo, consulte [console de gerenciamento de política de grupo](https://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="8cdfe-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="8cdfe-217">Clique com o botão direito do mouse no nó **objetos de política de grupo** e selecione **novo** no menu.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="8cdfe-218">Na caixa de diálogo **novo GPO** , digite um nome para o GPO, por exemplo, **MakeLyncDefaultUI**, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="8cdfe-219">Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="8cdfe-220">No **Editor de gerenciamento de política de grupo**, expanda Configuração do **usuário**, **preferências**, expanda **configurações do Windows**e selecione o nó **registro** .</span><span class="sxs-lookup"><span data-stu-id="8cdfe-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="8cdfe-221">Clique com o botão direito do mouse no nó **do registro** e selecione **novo** \> **item do registro**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="8cdfe-222">Na caixa de diálogo **novas propriedades do registro** , atualize o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8cdfe-223">Campo</span><span class="sxs-lookup"><span data-stu-id="8cdfe-223">Field</span></span></th>
    <th><span data-ttu-id="8cdfe-224">Valor a ser selecionado ou inserido</span><span class="sxs-lookup"><span data-stu-id="8cdfe-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8cdfe-225"><strong>Ação</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="8cdfe-226"><strong>Create</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8cdfe-227"><strong>Hive</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="8cdfe-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="8cdfe-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8cdfe-229"><strong>Caminho da chave</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="8cdfe-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="8cdfe-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8cdfe-231"><strong>Value name</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="8cdfe-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="8cdfe-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8cdfe-233"><strong>Value type</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="8cdfe-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="8cdfe-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8cdfe-235"><strong>Dados de valor</strong></span><span class="sxs-lookup"><span data-stu-id="8cdfe-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="8cdfe-236">00000000</span><span class="sxs-lookup"><span data-stu-id="8cdfe-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="8cdfe-237">Clique em **OK** para salvar suas alterações e, em seguida, feche o GPO.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="8cdfe-238">Em seguida, você precisará vincular o GPO que você criou ao grupo de usuários ao qual você deseja atribuir a política, como uma OU.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="8cdfe-239">**Para usar o GPO para atribuir a política**</span><span class="sxs-lookup"><span data-stu-id="8cdfe-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="8cdfe-240">No console de gerenciamento de política de grupo, clique com o botão direito do mouse na UO à qual você deseja atribuir a política e, em seguida, selecione **vincular a um GPO existente**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="8cdfe-241">Na caixa de diálogo **selecionar GPO** , selecione o GPO que você criou e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="8cdfe-242">No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8cdfe-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="8cdfe-243">**gpupdate/target: User**</span><span class="sxs-lookup"><span data-stu-id="8cdfe-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="8cdfe-244">A mensagem "Atualizando a política..." é exibido enquanto o GPO é aplicado.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="8cdfe-245">Quando ela é concluída, a mensagem "a atualização da política de usuário foi concluída com êxito" é exibida.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="8cdfe-246">No prompt de comando, digite o seguinte comando: </span><span class="sxs-lookup"><span data-stu-id="8cdfe-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="8cdfe-247">**Gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="8cdfe-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="8cdfe-248">Você deve ver "objetos de política de grupo atribuídos" com o nome do GPO que você criou exibido abaixo.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="8cdfe-249">Você também pode verificar se o GPO atualizou com êxito o registro no computador de um usuário examinando o registro.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="8cdfe-250">Abra o editor do registro e navegue até a chave do \*\* \[\_\\\\Office\\Lync\] atual\_software do usuário\\do hKey\*\* .</span><span class="sxs-lookup"><span data-stu-id="8cdfe-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="8cdfe-251">Se o GPO atualizou com êxito o registro, você verá um valor chamado EnableSkypeUI com um valor de 0.</span><span class="sxs-lookup"><span data-stu-id="8cdfe-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

