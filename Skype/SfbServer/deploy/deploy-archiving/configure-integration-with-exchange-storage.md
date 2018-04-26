---
title: Configurar integração com o armazenamento do Exchange no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumo: leia este tópico para aprender como configurar a integração com o armazenamento do Exchange no .'
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a><span data-ttu-id="ffd35-103">Configurar integração com o armazenamento do Exchange no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ffd35-103">Configure integration with Exchange storage for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ffd35-104">Resumo: leia este tópico para aprender como configurar a integração com o armazenamento do Exchange no .</span><span class="sxs-lookup"><span data-stu-id="ffd35-104">Summary: Read this topic to learn  how to configure integration with Exchange storage in .</span></span>
  
<span data-ttu-id="ffd35-105">Se você usar a integração com o  para todos os usuários da implantação, não será necessário configurar as políticas de arquivamento do  para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="ffd35-105">If you use  integration for all users in your deployment, you don’t need to configure  archiving policies for your users.</span></span> <span data-ttu-id="ffd35-106">Em vez disso, configure as políticas de retenção no local do  a fim de oferecer suporte ao arquivamento para usuários hospedados no , com suas caixas de correio em retenção no local.</span><span class="sxs-lookup"><span data-stu-id="ffd35-106">Instead, you configure   In-Place Hold policies to support archiving for users homed on , with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="ffd35-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ffd35-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="ffd35-108">Para obter detalhes sobre políticas de Bloqueio In-loco do Exchange, consulte a documentação do produto .</span><span class="sxs-lookup"><span data-stu-id="ffd35-108">For details about  Exchange In-Place Hold policies, see the  product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="ffd35-109">Configurar integração com o armazenamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="ffd35-109">Configure integration with Exchange storage</span></span>

1. <span data-ttu-id="ffd35-110">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ffd35-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ffd35-111">Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ffd35-111">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ffd35-112">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="ffd35-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="ffd35-113">Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ffd35-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
  - <span data-ttu-id="ffd35-114">Para habilitar a integração com o armazenamento do , marque a caixa de seleção .</span><span class="sxs-lookup"><span data-stu-id="ffd35-114">To enable integration with  storage, select the  check box.</span></span>
    
  - <span data-ttu-id="ffd35-115">Para desabilitar a integração com o armazenamento do , desmarque a caixa de seleção .</span><span class="sxs-lookup"><span data-stu-id="ffd35-115">To disable integration with  storage, clear the  check box.</span></span>
    
5. <span data-ttu-id="ffd35-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffd35-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="ffd35-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span><span class="sxs-lookup"><span data-stu-id="ffd35-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="ffd35-118">Se você usar a integração com o  e o  não estiver implantado na mesma floresta que o , você deverá verificar se os seguintes atributos do Active Directory do  estão sincronizados com a floresta onde o  está implantado:</span><span class="sxs-lookup"><span data-stu-id="ffd35-118">If you use  integration and  is not deployed in the same forest as , you must make sure that the following  Active Directory attributes are synchronized to the forest where  is deployed:</span></span>
  
- <span data-ttu-id="ffd35-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ffd35-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="ffd35-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ffd35-120">proxyAddresses</span></span>
    
<span data-ttu-id="ffd35-p102">Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.</span><span class="sxs-lookup"><span data-stu-id="ffd35-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

