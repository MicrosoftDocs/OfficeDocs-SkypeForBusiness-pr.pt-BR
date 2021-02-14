---
title: Criar uma configuração de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumo: saiba como criar uma configuração de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817651"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="46ea8-103">Criar uma configuração de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="46ea8-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="46ea8-104">**Resumo:** Saiba como criar uma configuração de arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="46ea8-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="46ea8-105">Configurar opções de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="46ea8-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="46ea8-106">Para configurar opções de arquivamento para um site ou pool específico:</span><span class="sxs-lookup"><span data-stu-id="46ea8-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="46ea8-107">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="46ea8-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="46ea8-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="46ea8-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="46ea8-109">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="46ea8-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="46ea8-110">Na página **Configuração de arquivamento**, clique em **Novo** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="46ea8-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="46ea8-111">Para criar uma configuração de arquivamento de site, clique em Configuração do **Site** e, em Selecionar um **site,** selecione o site a ser configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="46ea8-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="46ea8-112">Para criar uma configuração de arquivamento de pool, clique em Configuração de **Pool** e, em Selecionar um **pool,** selecione o pool a ser configurado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="46ea8-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="46ea8-113">Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="46ea8-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="46ea8-114">Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="46ea8-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="46ea8-115">Para habilitar o arquivamento para sessões de IM e conferências da Web, clique em **Arquivar sessões de IM e conferência da Web**.</span><span class="sxs-lookup"><span data-stu-id="46ea8-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="46ea8-116">Para desabilitar o arquivamento para essa configuração, clique **em Desabilitar arquivamento.**</span><span class="sxs-lookup"><span data-stu-id="46ea8-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="46ea8-117">Também em **Nova configuração de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="46ea8-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="46ea8-118">Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="46ea8-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="46ea8-119">Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção de integração do **Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="46ea8-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="46ea8-120">Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="46ea8-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="46ea8-121">Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.</span><span class="sxs-lookup"><span data-stu-id="46ea8-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="46ea8-122">Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.</span><span class="sxs-lookup"><span data-stu-id="46ea8-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="46ea8-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="46ea8-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="46ea8-124">Configurar opções de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46ea8-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="46ea8-125">Você também pode configurar opções de arquivamento para um site ou pool específico usando o cmdlet **New-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="46ea8-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="46ea8-126">O comando a seguir cria um novo conjunto de definições de configuração de arquivamento para o local Redmond:</span><span class="sxs-lookup"><span data-stu-id="46ea8-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="46ea8-127">Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="46ea8-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="46ea8-128">Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado.</span><span class="sxs-lookup"><span data-stu-id="46ea8-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="46ea8-129">O exemplo a seguir cria um conjunto de definições de configuração de arquivamento que, por padrão, permitem apenas o arquivamento de sessões de mensagens instantâneas:</span><span class="sxs-lookup"><span data-stu-id="46ea8-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="46ea8-p102">Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, este comando define a nova configuração para arquivar sessões de mensagem instantânea e o bloqueio de mensagem instantânea do serviço de arquivamento não está disponível:</span><span class="sxs-lookup"><span data-stu-id="46ea8-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="46ea8-132">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="46ea8-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
