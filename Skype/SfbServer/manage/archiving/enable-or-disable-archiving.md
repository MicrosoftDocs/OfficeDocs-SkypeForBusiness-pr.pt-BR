---
title: Habilitar ou desabilitar o arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: 8c970dba9a76abdb0c9417a5da5c7aa642fa059c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818913"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="fac51-103">Habilitar ou desabilitar o arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fac51-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="fac51-104">**Resumo:** Saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fac51-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="fac51-105">Habilitar ou desabilitar o arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="fac51-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="fac51-106">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fac51-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="fac51-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fac51-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="fac51-108">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="fac51-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="fac51-109">Selecione a configuração global, local ou de pool apropriada na lista de configurações de arquivamento, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="fac51-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="fac51-110">Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="fac51-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="fac51-111">Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.</span><span class="sxs-lookup"><span data-stu-id="fac51-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="fac51-112">Para desabilitar o arquivamento da configuração, clique em **Desabilitar arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="fac51-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="fac51-113">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fac51-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="fac51-114">Habilitar ou desabilitar arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fac51-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="fac51-115">Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="fac51-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="fac51-116">Por exemplo: o comando a seguir modifica todas as configurações de arquivamento, de forma que somente as sessões de IM sejam arquivadas.</span><span class="sxs-lookup"><span data-stu-id="fac51-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="fac51-117">O comando acessa o cmdlet **Get-CsArchivingConfiguration** sem nenhum parâmetro para devolver todas as configurações de arquivamento usadas atualmente na organização.</span><span class="sxs-lookup"><span data-stu-id="fac51-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="fac51-118">Essa coleção é então enviada para o cmdlet **Where-Object**, que seleciona somente as configurações nas quais a propriedade EnableArchiving é igual a (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="fac51-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="fac51-119">A coleção filtrada é então encaminhada para o cmdlet **Set-CsArchivingConfiguration**, que pega cada um dos itens da coleção e altera o valor de EnableArchiving para "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="fac51-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
