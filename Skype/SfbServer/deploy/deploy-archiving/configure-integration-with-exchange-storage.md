---
title: Configurar a integração com o armazenamento do Exchange para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.'
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234328"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="cafca-103">Configurar a integração com o armazenamento do Exchange para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cafca-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="cafca-104">**Resumo:** Leia este tópico para saber como configurar a integração com o armazenamento do Exchange no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cafca-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="cafca-105">Se você usa a integração do Microsoft Exchange para todos os usuários em sua implantação, não precisa configurar as políticas de arquivamento do Skype for Business Server para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cafca-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="cafca-106">Em vez disso, configure as políticas de bloqueio do Exchange in loco para dar suporte ao arquivamento para usuários hospedados no Exchange, com as caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="cafca-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cafca-107">Antes de configurar a integração com o armazenamento do Exchange, leia o [plano de arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="cafca-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="cafca-108">Para obter detalhes sobre as políticas de bloqueio in-loco do Exchange, consulte a documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="cafca-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="cafca-109">Configurar a integração com o armazenamento do Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="cafca-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="cafca-110">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="cafca-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cafca-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cafca-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cafca-112">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="cafca-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="cafca-113">Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cafca-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="cafca-114">Para habilitar a integração com o armazenamento do Exchange, marque a caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="cafca-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="cafca-115">Para desabilitar a integração com o armazenamento do Exchange, desmarque a caixa de seleção **integração do Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="cafca-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="cafca-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cafca-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="cafca-117">Quando o Skype for Business Server e o Microsoft Exchange são implantados em florestas diferentes</span><span class="sxs-lookup"><span data-stu-id="cafca-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="cafca-118">Se você usa a integração do Microsoft Exchange e o Microsoft Exchange Server não está implantado na mesma floresta do Skype for Business Server, você deve verificar se os seguintes atributos do Exchange Active Directory estão sincronizados com a floresta em que o Skype for O Business Server é implantado:</span><span class="sxs-lookup"><span data-stu-id="cafca-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="cafca-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="cafca-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="cafca-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="cafca-120">proxyAddresses</span></span>
    
<span data-ttu-id="cafca-p102">Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.</span><span class="sxs-lookup"><span data-stu-id="cafca-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

