---
title: Habilitando o controle de admissão de chamada
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
description: " Depois de configurar a rede cac (controle de admissão de chamada), você deve habilitar o CAC para impor as limitações de largura de banda."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816501"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="0dda0-103">Habilitar o controle de admissão de chamada no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0dda0-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="0dda0-104">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível.</span><span class="sxs-lookup"><span data-stu-id="0dda0-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="0dda0-105">Após configurar a rede CAC, habilite o CAC para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="0dda0-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="0dda0-106">Você pode usar o Painel de Controle do Skype for Business Server para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="0dda0-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="0dda0-107">Para habilitar o CAC no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0dda0-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0dda0-108">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0dda0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0dda0-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0dda0-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0dda0-110">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Global.**</span><span class="sxs-lookup"><span data-stu-id="0dda0-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="0dda0-111">Na página **Global**, clique na configuração **Global**.</span><span class="sxs-lookup"><span data-stu-id="0dda0-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="0dda0-112">Apenas uma rede pode ser configurada para qualquer implantação do Skype for Business Server, portanto, nunca haverá mais de uma configuração de rede na lista.</span><span class="sxs-lookup"><span data-stu-id="0dda0-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="0dda0-113">Você não pode renomear a configuração Global.</span><span class="sxs-lookup"><span data-stu-id="0dda0-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="0dda0-114">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="0dda0-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0dda0-115">Na página **Editar Configuração Global**, marque a caixa de seleção **Habilitar controle de admissão de chamadas** e então clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0dda0-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="0dda0-p103">Quando você clica em **Confirmar**, você executa um teste da configuração. A caixa de diálogo **Editar Configurações Globais** é fechada, retornando você à página **Global**. Você receberá uma viso sobre qualquer erro ou inconsistência descoberta em sua configuração de rede que a impeça de funcionar corretamente (por exemplo, se cada região não estiver conectada às outras regiões através de uma rota intrarregional).</span><span class="sxs-lookup"><span data-stu-id="0dda0-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="0dda0-p104">Caso faça alterações em sua configuração de rede, você pode executar a verificação de validação novamente abrindo a configuração Global e clicando em **Confirmar**. Você não precisa desativar o CAC primeiro: deixe a caixa de seleção marcada e clique em **Confirmar**. Você pode fazer isso a qualquer hora sem fazer nenhuma alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="0dda0-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dda0-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="0dda0-122">See Also</span></span>

[<span data-ttu-id="0dda0-123">Planejar o controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="0dda0-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="0dda0-124">Implantar o serviço de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="0dda0-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="0dda0-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0dda0-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="0dda0-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0dda0-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="0dda0-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="0dda0-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
