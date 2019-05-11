---
title: Configurar a integração com o armazenamento do Exchange para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype para Business Server.'
ms.openlocfilehash: 4b9d689ef5315c58b2fb6d78c01366ce2377a00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893543"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="e8113-103">Configurar a integração com o armazenamento do Exchange para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e8113-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="e8113-104">**Resumo:** Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8113-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="e8113-105">Se você usar a integração do Microsoft Exchange para todos os usuários em sua implantação, você não precisará configurar Skype para políticas de arquivamento Business Server para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="e8113-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="e8113-106">Em vez disso, você pode configurar políticas de retenção de In-loco do Exchange para suportar o arquivamento para usuários hospedados no Exchange, com suas caixas de correio colocadas em retenção In-loco.</span><span class="sxs-lookup"><span data-stu-id="e8113-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e8113-107">Antes de configurar a integração com Exchange storage, leia [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="e8113-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="e8113-108">Para obter detalhes sobre as políticas de retenção de In-loco do Exchange, consulte a documentação de produto do Exchange.</span><span class="sxs-lookup"><span data-stu-id="e8113-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="e8113-109">Configurar a integração com o armazenamento do Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="e8113-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="e8113-110">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e8113-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e8113-111">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e8113-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e8113-112">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e8113-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e8113-113">Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e8113-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="e8113-114">Para habilitar a integração com o armazenamento do Exchange, marque a caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="e8113-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e8113-115">Para desabilitar a integração com o armazenamento do Exchange, desmarque a caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="e8113-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="e8113-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e8113-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="e8113-117">Quando o Skype para Business Server e Microsoft Exchange são implantados em florestas diferentes</span><span class="sxs-lookup"><span data-stu-id="e8113-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="e8113-118">Se você usar a integração do Microsoft Exchange e o Microsoft Exchange Server não estiver implantado na mesma floresta do Skype para Business Server, você deve garantir que os seguintes atributos do Active Directory do Exchange são sincronizados com a floresta onde Skype para Servidor de negócios é implantado:</span><span class="sxs-lookup"><span data-stu-id="e8113-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="e8113-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e8113-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="e8113-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e8113-120">proxyAddresses</span></span>
    
<span data-ttu-id="e8113-p102">Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.</span><span class="sxs-lookup"><span data-stu-id="e8113-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

