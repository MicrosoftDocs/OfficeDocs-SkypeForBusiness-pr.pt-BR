---
title: Habilitar ou desabilitar o arquivamento no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: Saiba como habilitar ou desabilitar o arquivamento no Skype para Business Server.'
ms.openlocfilehash: a0d32a3bacb604c326db13034bf5315c7f3d4d99
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965888"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="53784-103">Habilitar ou desabilitar o arquivamento no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="53784-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="53784-104">**Resumo:** Aprenda a habilitar ou desabilitar o arquivamento no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="53784-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="53784-105">Habilitar ou desabilitar o arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="53784-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="53784-106">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="53784-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="53784-107">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="53784-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="53784-108">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="53784-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="53784-109">Selecione a configuração global, local ou de pool apropriada na lista de configurações de arquivamento, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="53784-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="53784-110">Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="53784-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="53784-111">Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.</span><span class="sxs-lookup"><span data-stu-id="53784-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="53784-112">Para desabilitar o arquivamento da configuração, clique em **Desabilitar arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="53784-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="53784-113">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="53784-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="53784-114">Habilitar ou desabilitar arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53784-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="53784-115">Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="53784-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="53784-116">Por exemplo: o comando a seguir modifica todas as configurações de arquivamento, de forma que somente as sessões de IM sejam arquivadas.</span><span class="sxs-lookup"><span data-stu-id="53784-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="53784-117">O comando chama o cmdlet **Get-CsArchivingConfiguration** sem quaisquer parâmetros para retornar todas as definições de configuração de arquivamento em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="53784-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="53784-118">Esta coleção será então canalizada para o cmdlet **Where-Object** , que seleciona somente aquelas configurações cuja propriedade EnableArchiving for igual a (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="53784-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="53784-119">A coleção filtrada é então canalizada para o cmdlet **Set-CsArchivingConfiguration** , que tratará cada item na coleção e altera o valor de EnableArchiving para "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="53784-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```