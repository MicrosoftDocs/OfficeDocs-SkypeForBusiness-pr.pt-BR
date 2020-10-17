---
title: 'Lync Server 2013: estrutura de segurança para Lync Server'
description: 'Lync Server 2013: estrutura de segurança para Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d30c26929ddedbf653abd1fc353b6873ad8f36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551427"
---
# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="754c3-103">Estrutura de segurança para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-103">Security framework for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="754c3-104">_**Última modificação do tópico:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="754c3-104">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="754c3-105">Esta seção fornece uma visão geral dos elementos fundamentais que formam a estrutura de segurança do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="754c3-105">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="754c3-106">Entender como esses elementos funcionam juntos é essencial para tomar decisões informadas sobre como proteger sua implantação específica do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="754c3-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="754c3-107">Essas elementos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="754c3-107">These elements are as follows:</span></span>

  - <span data-ttu-id="754c3-108">O AD DS (Serviços de Domínio Active Directory) fornece um repositório back-end confiável para contas de usuário e recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="754c3-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="754c3-109">O controle de acesso de Role-Based (RBAC) permite delegar tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="754c3-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="754c3-110">A infraestrutura de chave pública (PKI) usa certificados emitidos por autoridades de certificação (CAs) confiáveis para autenticar servidores e garantir a integridade dos dados.</span><span class="sxs-lookup"><span data-stu-id="754c3-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="754c3-p102">Os protocolos TLS, HTTP sobre SSL (HTTPS) e MTLS (TLS mútuo) permitem a autenticação de ponto de extremidade e a criptografia de mensagens instantâneas. Os fluxos de compartilhamento ponto a ponto de áudio, vídeo e aplicativo são criptografados usando SRTP (Secure Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="754c3-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="754c3-113">Protocolos padrão do setor para autenticação do usuário, quando possível.</span><span class="sxs-lookup"><span data-stu-id="754c3-113">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="754c3-114">O Windows PowerShell fornece recursos de segurança habilitados por padrão, de modo que os usuários não possam executar scripts com facilidade ou sem saber.</span><span class="sxs-lookup"><span data-stu-id="754c3-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="754c3-115">Esses elementos de segurança fundamentais funcionam em conjunto para definir usuários, servidores, conexões e operações confiáveis para ajudar a garantir uma base segura para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="754c3-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="754c3-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="754c3-116">In This Section</span></span>

<span data-ttu-id="754c3-117">Os tópicos desta seção descrevem como cada um desses elementos fundamentais funciona para melhorar a segurança da infraestrutura do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="754c3-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="754c3-118">Serviços de domínio do Active Directory para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-118">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="754c3-119">Controle de acesso baseado em função (RBAC) para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-119">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="754c3-120">Infraestrutura de chave pública do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-120">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="754c3-121">TLS e MTLS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-121">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="754c3-122">Criptografia para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-122">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="754c3-123">Autenticação de usuário e cliente para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-123">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="754c3-124">Ferramentas de gerenciamento do Windows PowerShell e do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="754c3-124">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

