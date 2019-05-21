---
title: Estrutura de segurança do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server. Entender como esses elementos funcionam juntos é essencial para tomar decisões conscientes sobre como proteger sua implantação específica do Skype for Business Server.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296872"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="ad08a-104">Estrutura de segurança do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="ad08a-105">Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad08a-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="ad08a-106">Entender como esses elementos funcionam juntos é essencial para tomar decisões conscientes sobre como proteger sua implantação específica do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad08a-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="ad08a-107">Esses elementos são:</span><span class="sxs-lookup"><span data-stu-id="ad08a-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="ad08a-108">O AD DS (serviços de domínio Active Directory) fornece um único repositório de back-end confiável para contas de usuário e recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="ad08a-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="ad08a-109">O controle de acesso baseado em função (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="ad08a-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="ad08a-110">A infraestrutura de chave pública (PKI) utiliza certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade de dados.</span><span class="sxs-lookup"><span data-stu-id="ad08a-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="ad08a-p103">A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados utilizando protocolo de transporte em tempo real seguro (SRTP).</span><span class="sxs-lookup"><span data-stu-id="ad08a-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="ad08a-113">Protocolos padrão do setor para autenticação do usuário, onde possível.</span><span class="sxs-lookup"><span data-stu-id="ad08a-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="ad08a-114">O Windows PowerShell fornece recursos de segurança habilitados por padrão para que os usuários não possam executar scripts de forma fácil ou desconhecida.</span><span class="sxs-lookup"><span data-stu-id="ad08a-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="ad08a-115">Esses elementos de segurança fundamentais trabalham juntos para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad08a-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ad08a-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ad08a-116">In this section</span></span>

<span data-ttu-id="ad08a-117">Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ad08a-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="ad08a-118">Serviços de domínio do Active Directory para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="ad08a-119">Controle de acesso baseado em função (RBAC) para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="ad08a-120">Infraestrutura de chave pública para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="ad08a-121">TLS e MTLS para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="ad08a-122">Criptografia para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="ad08a-123">Autenticação de usuário e de cliente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="ad08a-124">Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ad08a-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

