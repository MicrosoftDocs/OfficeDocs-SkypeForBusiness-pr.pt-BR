---
title: Habilitando o controle de admissão de chamada
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Depois de configurar a rede de (CAC) do controle de admissão de chamada, você deve habilitar o CAC para impor as limitações de largura de banda."
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228404"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="8bcb9-103">Habilitar o controle de admissão de chamada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8bcb9-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="8bcb9-104">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="8bcb9-105">Depois de configurar a rede CAC, você deve habilitar o CAC para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="8bcb9-106">Você pode usar o Skype para painel de controle do Business Server para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="8bcb9-107">Para habilitar o CAC do Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="8bcb9-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="8bcb9-108">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8bcb9-109">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8bcb9-110">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Global**.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="8bcb9-111">Na página **Global** , clique na configuração **Global** .</span><span class="sxs-lookup"><span data-stu-id="8bcb9-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="8bcb9-112">Apenas uma rede pode ser configurada para qualquer Skype para implantação de servidor de negócios, portanto nunca haverá mais de uma configuração de rede na lista.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="8bcb9-113">Não é possível renomear na configuração Global.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="8bcb9-114">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8bcb9-115">Na página **Editar configuração Global** , marque a caixa de seleção **Habilitar controle de admissão de chamada** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="8bcb9-116">Quando você clica **em Confirmar**, você executa um teste da configuração.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="8bcb9-117">Fecha a caixa de diálogo **Editar configurações globais** , retornando à página **Global** .</span><span class="sxs-lookup"><span data-stu-id="8bcb9-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="8bcb9-118">Você receberá um aviso se existem erros ou inconsistências são descobertas na sua configuração de rede que impede que ele funcionando corretamente (por exemplo, se cada região não estiver conectada a outra região por meio de uma rota entre regiões).</span><span class="sxs-lookup"><span data-stu-id="8bcb9-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="8bcb9-119">Se você fizer alterações à sua configuração de rede, você pode executar a verificação de validação abrindo na configuração Global e clicando em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="8bcb9-120">Você não precisa desativar o CAC: deixe a caixa de seleção marcada e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="8bcb9-121">Você pode fazer isso a qualquer momento sem fazer quaisquer alterações de configuração.</span><span class="sxs-lookup"><span data-stu-id="8bcb9-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bcb9-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="8bcb9-122">See Also</span></span>

[<span data-ttu-id="8bcb9-123">Planejamento do controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="8bcb9-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="8bcb9-124">Implantar o serviço de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="8bcb9-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="8bcb9-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8bcb9-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="8bcb9-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8bcb9-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="8bcb9-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8bcb9-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
