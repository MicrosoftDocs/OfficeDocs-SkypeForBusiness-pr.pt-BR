---
title: Configurar a integração com o armazenamento do Exchange para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825061"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="f7cce-103">Configurar a integração com o armazenamento do Exchange para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7cce-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="f7cce-104">**Resumo:** Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7cce-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="f7cce-105">Se você usar a integração com o Microsoft Exchange para todos os usuários em sua implantação, não precisará configurar as políticas de arquivamento do Skype for Business Server para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f7cce-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="f7cce-106">Em vez disso, você configura as In-Place de Espera do Exchange para dar suporte ao arquivamento para usuários que estão no Exchange, com suas caixas de correio colocadas em In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="f7cce-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f7cce-107">Antes de configurar a integração com o armazenamento do Exchange, leia [Planejar o arquivamento no Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="f7cce-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="f7cce-108">Para obter detalhes sobre as In-Place De espera do Exchange, consulte a documentação do produto do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f7cce-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="f7cce-109">Configurar a integração com o armazenamento do Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="f7cce-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="f7cce-110">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f7cce-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f7cce-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7cce-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f7cce-112">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="f7cce-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f7cce-113">Clique no nome da configuração do pool, local ou global adequada na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f7cce-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="f7cce-114">Para habilitar a integração com o armazenamento do Exchange, marque a caixa de seleção de integração do **Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="f7cce-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="f7cce-115">Para desabilitar a integração com o armazenamento do Exchange, des limpe a caixa de seleção de integração do **Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="f7cce-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="f7cce-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f7cce-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="f7cce-117">Quando o Skype for Business Server e o Microsoft Exchange são implantados em florestas diferentes</span><span class="sxs-lookup"><span data-stu-id="f7cce-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="f7cce-118">Se você usar a integração com o Microsoft Exchange e o Microsoft Exchange Server não for implantado na mesma floresta que o Skype for Business Server, deverá garantir que os seguintes atributos do Exchange Active Directory estejam sincronizados com a floresta onde o Skype for Business Server está implantado:</span><span class="sxs-lookup"><span data-stu-id="f7cce-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="f7cce-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="f7cce-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="f7cce-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f7cce-120">proxyAddresses</span></span>
    
<span data-ttu-id="f7cce-p102">Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.</span><span class="sxs-lookup"><span data-stu-id="f7cce-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

