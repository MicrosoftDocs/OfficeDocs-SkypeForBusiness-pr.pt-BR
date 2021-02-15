---
title: Estrutura de segurança do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server. Entender como esses elementos funcionam em conjunto é essencial para tomar decisões informadas sobre como proteger sua implantação específica do Skype for Business Server.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832091"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="781f7-104">Estrutura de segurança do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="781f7-105">Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="781f7-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="781f7-106">Entender como esses elementos funcionam em conjunto é essencial para tomar decisões informadas sobre como proteger sua implantação específica do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="781f7-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="781f7-107">Essas elementos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="781f7-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="781f7-108">O AD DS (Serviços de Domínio Active Directory) fornece um repositório back-end confiável para contas de usuário e recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="781f7-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="781f7-109">Role-Based Controle de Acesso (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="781f7-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="781f7-110">A PKI (Infraestrutura de Chave Pública) usa certificados emitidos por autoridades de certificação confiáveis (CAs) para autenticar servidores e garantir a integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="781f7-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="781f7-p103">Os protocolos TLS, HTTP sobre SSL (HTTPS) e MTLS (TLS mútuo) permitem a autenticação de ponto de extremidade e a criptografia de mensagens instantâneas. Os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativo são criptografados usando SRTP (Secure Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="781f7-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="781f7-113">Protocolos padrão do setor para autenticação do usuário, quando possível.</span><span class="sxs-lookup"><span data-stu-id="781f7-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="781f7-114">O Windows PowerShell fornece recursos de segurança habilitados por padrão, de modo que os usuários não possam executar scripts com facilidade ou sem saber.</span><span class="sxs-lookup"><span data-stu-id="781f7-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="781f7-115">Esses elementos de segurança fundamentais trabalham juntos para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="781f7-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="781f7-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="781f7-116">In this section</span></span>

<span data-ttu-id="781f7-117">Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="781f7-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="781f7-118">Serviços de Domínio do Active Directory para Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="781f7-119">Controle de acesso baseado em função (RBAC) para Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="781f7-120">Infraestrutura de chave pública para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="781f7-121">TLS e MTLS para Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="781f7-122">Criptografia para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="781f7-123">Autenticação de usuário e cliente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="781f7-124">Ferramentas de gerenciamento do Windows PowerShell e do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="781f7-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

