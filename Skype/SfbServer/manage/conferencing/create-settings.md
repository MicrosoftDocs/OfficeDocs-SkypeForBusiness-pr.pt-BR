---
title: Criar definições de configuração de reunião no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Resumo: Saiba como criar configurações de reunião no Skype para Business Server 2015.'
ms.openlocfilehash: 2d3bde2c856c85e0795f2e1d43fbb5cf705c7024
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="2d1f9-103">Criar definições de configuração de reunião no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d1f9-103">Create meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2d1f9-104">**Resumo:** Saiba como criar configurações de reunião no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2d1f9-105">Você pode criar configurações de reunião usando o Skype para painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2d1f9-106">Criar configurações de reunião usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="2d1f9-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2d1f9-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2d1f9-108">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2d1f9-109">Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="2d1f9-110">Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="2d1f9-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="2d1f9-p101">Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="2d1f9-p102">Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="2d1f9-p103">Para direcionar os participantes que ligam de um PSTN através do lobby, desmarque a caixa de seleção  **Chamadores PSTN ignoram o lobby**. Por padrão, os participantes discando pelo PSTN irão diretamente para a reunião.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="2d1f9-119">Para configurar quem pode ser um apresentador na reunião, em **Designar como apresentador**, siga um dos procedimentos abaixo:</span><span class="sxs-lookup"><span data-stu-id="2d1f9-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="2d1f9-120">Para não permitir que qualquer pessoa além do organizador seja o apresentador, clique em **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="2d1f9-p104">Para permitir que apenas participantes membros da sua organização sejam apresentadores, clique em **Empresa**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="2d1f9-123">Para permitir que qualquer participante seja o apresentador, clique em **Todos**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="2d1f9-p105">Para que o organizador selecione um tipo de conferência ao programar uma reunião, desmarque a caixa de seleção  **Tipo de conferência atribuída por padrão**. Por padrão, o tipo de conferência é atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="2d1f9-p106">Para evitar que usuários anônimos (não autenticados) sejam aceitos automaticamente, desmarque a caixa de seleção **Aceitar usuários anônimos por padrão**. Por padrão, os usuários anônimos são aceitos automaticamente nas reuniões.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="2d1f9-128">Para personalizar o convite da reunião enviado para os participantes, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="2d1f9-129">Observe que o comprimento máximo das URLs e o texto do rodapé padrão é de 1KB.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="2d1f9-130">Exceto para a **URL de ajuda**, se você não especificar um valor para as personalizações, elas não serão incluídas na reunião.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="2d1f9-131">Se você não incluir uma URL de Ajuda personalizado, a URL de ajuda padrão do Skype para negócios será exibida no convite da.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="2d1f9-p108">Para personalizar o logotipo exibido no convite da reunião, na **URL do Logotipo**, insira o local do logotipo. O logotipo deve ser uma imagem GIF ou JPG com um tamanho de 188 por 30 pixels.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="2d1f9-134">Para personalizar o texto de ajuda exibido no convite da reunião, na **URL de ajuda**, insira o local do texto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="2d1f9-135">Para personalizar o texto legal exibido no convite da reunião, na **URL do texto legal**, insira o texto legal.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="2d1f9-136">Para personalizar o texto do rodapé exibido no convite da reunião, em **Texto do rodapé personalizado**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="2d1f9-137">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2d1f9-138">Criar configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="2d1f9-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2d1f9-139">Para criar as novas definições de configurações de reunião, use o cmdlet **New-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="2d1f9-140">O comando a seguir cria um novo conjunto de definições de configuração de reunião para o local Redmond:</span><span class="sxs-lookup"><span data-stu-id="2d1f9-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="2d1f9-141">Como não há parâmetros (além do parâmetro obrigatório Identity) onde especificado no comando anterior, as novas definições de configuração de reunião usarão os valores padrões para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="2d1f9-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="2d1f9-p109">Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de reuniões de configuração da reunião que, por padrão, permite todos em uma reunião serem apresentadores a usarem um comando como este:</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="2d1f9-p110">Os valores de várias propriedades podem ser modificados, incluindo vários parâmetros. Por exemplo, este comando permite que todos em uma reunião serem apresentadores e também força os usuários PSTN a aguardar enquanto são formalmente admitidos na reunião:</span><span class="sxs-lookup"><span data-stu-id="2d1f9-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="2d1f9-146">Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2d1f9-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

