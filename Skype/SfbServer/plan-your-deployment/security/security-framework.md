---
title: Estrutura de segurança do Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype para Business Server. Noções básicas sobre como esses elementos funcionam em conjunto é essencial para tomar decisões fundamentadas sobre como proteger sua Skype específica para implantação de servidor de negócios.
ms.openlocfilehash: 7c678e1f005178b569f8e4136d40fd911483a3d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879879"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="74bf0-104">Estrutura de segurança do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="74bf0-105">Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="74bf0-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="74bf0-106">Noções básicas sobre como esses elementos funcionam em conjunto é essencial para tomar decisões fundamentadas sobre como proteger sua Skype específica para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="74bf0-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="74bf0-107">Esses elementos são:</span><span class="sxs-lookup"><span data-stu-id="74bf0-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="74bf0-108">Serviços de domínio Active Directory (AD DS) fornece um repositório back-end confiável para contas de usuário e recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="74bf0-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="74bf0-109">O controle de acesso baseado em função (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="74bf0-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="74bf0-110">A infraestrutura de chave pública (PKI) utiliza certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade de dados.</span><span class="sxs-lookup"><span data-stu-id="74bf0-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="74bf0-p103">A segurança da camada de transporte (TLS), HTTPS sobre SSL (HTTPS) e TLS mútuo (MTLS) possibilitam a autenticação de ponto de extremidade e criptografia IM. Os fluxos de áudio e vídeo ponto a ponto e de compartilhamento de aplicativos são criptografados utilizando protocolo de transporte em tempo real seguro (SRTP).</span><span class="sxs-lookup"><span data-stu-id="74bf0-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="74bf0-113">Protocolos padrão do setor para autenticação do usuário, onde possível.</span><span class="sxs-lookup"><span data-stu-id="74bf0-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="74bf0-114">Windows PowerShell fornece recursos de segurança que estão habilitados por padrão, de modo que os usuários não podem facilmente ou inconscientemente executar scripts.</span><span class="sxs-lookup"><span data-stu-id="74bf0-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="74bf0-115">Esses elementos de segurança fundamentais funcionam juntos para definir usuários confiáveis, servidores, conexões e operações para ajudar a garantir uma base segura para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="74bf0-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="74bf0-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="74bf0-116">In this section</span></span>

<span data-ttu-id="74bf0-117">Os tópicos desta seção descrevem como cada um desses elementos fundamentais aprimoram a segurança da sua Skype infra-estrutura de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="74bf0-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="74bf0-118">Serviços de domínio do Active Directory para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="74bf0-119">Controle de acesso baseado em função (RBAC) para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="74bf0-120">Infraestrutura de chave pública para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="74bf0-121">TLS e MTLS para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="74bf0-122">Criptografia do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="74bf0-123">Autenticação de cliente e usuário para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74bf0-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="74bf0-124">Windows PowerShell e Skype para as ferramentas de gerenciamento de servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="74bf0-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

