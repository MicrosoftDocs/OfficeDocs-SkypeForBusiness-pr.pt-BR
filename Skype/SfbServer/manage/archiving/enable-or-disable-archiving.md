---
title: Habilitar ou desabilitar o arquivamento no Skype for Business Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Resumo: Saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817591"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="225c8-103">Habilitar ou desabilitar o arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="225c8-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="225c8-104">**Resumo:** Saiba como habilitar ou desabilitar o arquivamento no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c8-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="225c8-105">Habilitar ou desabilitar o arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="225c8-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="225c8-106">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="225c8-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="225c8-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c8-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="225c8-108">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="225c8-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="225c8-109">Selecione a configuração global, de site ou de pool apropriada na lista de configurações de arquivo, clique em **Editar**, **Exibir detalhes** e execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="225c8-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="225c8-110">Para habilitar o arquivamento apenas para sessões de IM (mensagem instantânea), clique em **Arquivar sessões de IM**.</span><span class="sxs-lookup"><span data-stu-id="225c8-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="225c8-111">Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e conferências**.</span><span class="sxs-lookup"><span data-stu-id="225c8-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="225c8-112">Para desabilitar o arquivamento para a configuração, clique **em Desabilitar arquivamento.**</span><span class="sxs-lookup"><span data-stu-id="225c8-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="225c8-113">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="225c8-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="225c8-114">Habilitar ou desabilitar o arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="225c8-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="225c8-115">Você também pode habilitar ou desabilitar o arquivamento usando o cmdlet **Set-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="225c8-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="225c8-116">Por exemplo, o comando a seguir modifica todas as definições de configuração de arquivamento para que somente as sessões de IM sejam arquivadas.</span><span class="sxs-lookup"><span data-stu-id="225c8-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="225c8-117">O comando chama o cmdlet **Get-CsArchivingConfiguration** sem nenhum parâmetro para retornar todas as definições de configuração de arquivamento em uso na organização.</span><span class="sxs-lookup"><span data-stu-id="225c8-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="225c8-118">Esta coleção será então canalada para o cmdlet **Where-Object,** que selecionará apenas as definições nas quais a propriedade EnableArchiving for igual a (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="225c8-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="225c8-119">A coleção filtrada é então canalizada para o cmdlet **Set-CsArchivingConfiguration,** que pega cada item na coleção e altera o valor de EnableArchiving para "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="225c8-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
